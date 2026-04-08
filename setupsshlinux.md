
# 🔐 Como configurar SSH no GitHub (Linux) — Guia Rápido e Definitivo

## 1. Verifique se já tem chave SSH

```bash
ls -al ~/.ssh
````

Procure por arquivos como:

* `id_ed25519`
* `id_rsa`

Se **não tiver**, siga para o passo 2.

---

## 2. Gerar uma nova chave SSH

Use o padrão moderno (`ed25519`):

```bash
ssh-keygen -t ed25519 -C "seu_email@example.com"
```

Quando pedir:

* Caminho: só aperte **Enter**
* Senha (passphrase): opcional (recomendado usar)

Isso cria:

* 🔑 privada: `~/.ssh/id_ed25519`
* 🔑 pública: `~/.ssh/id_ed25519.pub`

---

## 3. Iniciar o agente SSH

```bash
eval "$(ssh-agent -s)"
```

Adicionar sua chave:

```bash
ssh-add ~/.ssh/id_ed25519
```

---

## 4. Copiar a chave pública

```bash
cat ~/.ssh/id_ed25519.pub
```

Copie **tudo** que aparecer (começa com `ssh-ed25519`).

---

## 5. Adicionar no GitHub

Acesse: [https://github.com/settings/keys](https://github.com/settings/keys)

Passos:

* Clique em **New SSH key**
* Title: nome do seu PC (ex: "Linux Kleber")
* Key: cole a chave copiada
* Save

---

## 6. Testar conexão

```bash
ssh -T git@github.com
```

Se aparecer:

```
Hi username! You've successfully authenticated...
```

✅ Funcionou

---

## 7. Usar SSH nos repositórios

Clone assim:

```bash
git clone git@github.com:usuario/repositorio.git
```

⚠️ Evite usar HTTPS se quer autenticação via SSH.

[Voltar](README.md)