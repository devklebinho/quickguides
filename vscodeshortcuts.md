# Customizando Atalhos no VS Code

Guia prático para alterar e personalizar atalhos de teclado no VS Code.

## 📁 Localização do Arquivo

No Linux, o arquivo de keybindings fica em:
```
~/.config/Code/User/keybindings.json
```

## 🎯 Como Abrir o Arquivo

### Opção 1: Pelo VS Code
1. Pressione `Ctrl + Shift + P` para abrir a paleta de comandos
2. Digite: `Preferences: Open Keyboard Shortcuts (JSON)`
3. Pressione Enter

### Opção 2: Abrir Manualmente
1. Navegue até a pasta `~/.config/Code/User/`
2. Abra o arquivo `keybindings.json` em um editor de texto

## ✏️ Estrutura do Arquivo

Um atalho personalizado segue este formato:

```json
{
    "key": "ctrl+'",
    "command": "workbench.action.terminal.toggleTerminal"
}
```

### Elementos Principais

| Elemento | Descrição | Exemplo |
|----------|-----------|---------|
| `key` | Combinação de teclas | `ctrl+'`, `shift+ctrl+k`, `alt+t` |
| `command` | Comando a executar | `workbench.action.terminal.toggleTerminal` |
| `when` | Condição (opcional) | `editorFocus`, `terminalFocus` |

## 🔧 Modificadores de Teclado

- `ctrl` - Control
- `shift` - Shift
- `alt` - Alt
- `cmd` - Command (macOS)

## 📝 Exemplos de Atalhos Úteis

```json
[
    {
        "key": "ctrl+'",
        "command": "workbench.action.terminal.toggleTerminal"
    },
    {
        "key": "ctrl+shift+n",
        "command": "workbench.action.files.newUntitledFile"
    },
    {
        "key": "ctrl+shift+d",
        "command": "workbench.action.debug.start"
    },
    {
        "key": "alt+z",
        "command": "editor.action.toggleWordWrap"
    }
]
```

## 🔍 Encontrar Comandos Disponíveis

1. Pressione `Ctrl + Shift + P`
2. Digite `Preferences: Open Keyboard Shortcuts`
3. Procure pelo comando que deseja personalizar
4. Clique no ícone de lápis para editar o atalho

## 💡 Dicas Úteis

- **Evite conflitos**: Um atalho não pode fazer duas coisas ao mesmo tempo
- **Use `when`**: Restrinja atalhos a contextos específicos (ex: apenas quando o editor está em foco)
- **Recarregue**: Após salvar, o VS Code aplica as alterações automaticamente
- **Verifique a sintaxe**: Certifique-se de que o JSON está válido (sem vírgulas faltantes)

## ⚠️ Solucionando Problemas

### Atalho não funciona
- Verifique se o comando existe
- Procure por conflitos com outros atalhos
- Verifique a sintaxe JSON

### Erro: "command not found"
- O comando pode estar desatualizado
- Consulte a paleta de comandos para encontrar o comando correto

---

[Voltar](README.md)