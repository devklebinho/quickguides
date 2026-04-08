
# 📚Guia Básico do Git

Este é um guia simples para aqueles que querem lembrar dos principais comandos git e acessá-los de forma rápida e objetiva.

O Git é um sistema de controle de versão distribuído amplamente utilizado no desenvolvimento de software. Seus principais usos incluem:

1. **Controle de Versão:** Mantém um histórico completo de todas as alterações feitas em um projeto.
2. **Colaboração:** Permite que várias pessoas trabalhem simultaneamente no mesmo projeto.
3. **Rastreamento de Alterações:** Oferece a capacidade de ver quem fez quais alterações e quando.
4. **Branching e Merging:** Facilita a criação de branches para trabalhar em novas funcionalidades e mesclar as alterações de volta à versão principal.
5. **Backup e Restauração:** Simplifica o processo de backup e restauração de projetos.


## Tabelas de comandos

Abaixo encontra-se algumas tabelas de comandos básicos para o dia a dia.

#### Configurações Iniciais

| Comando                       | Descrição                                             | 
| :---------------------------- | :---------------------------------------------------- | 
| `git config --global user.name "[seu nome]"` | Configura o nome de usuário globalmente |
| `git config --global user.email "[seu email]"` | Configura o email do usuário globalmente |
| `git config --list` | Exibe todas as configurações do Git (pressione "q" para voltar) |

#### Comandos básicos

| Comando      | Descrição                           | 
| :----------- | :---------------------------------- | 
| `git init`   | Inicializa um repositório           | 
| `git add`    | Adiciona arquivos ao staging area   | 
| `git commit` | Salva as alterações no repositório  | 
| `git status` | Exibe o estado atual do repositório | 
| `git remote add [nome] [url]`                        | Adiciona um novo repositório remoto ao seu projeto       |
| `git log`    | Exibe o histórico de commits        |


#### Colaboração

| Comando               | Descrição                                          | 
| :-------------------- | :------------------------------------------------- | 
| `git clone`           | Clona um repositório remoto para o repositório local | 
| `git pull`            | Puxa alterações do repositório remoto e mescla com o repositório local  | 
| `git fetch`           | Busca alterações do repositório remoto, mas não as mescla automaticamente  | 
| `git push`            | Envia commits locais para um repositório remoto  | 
| `git pull-request`    | Solicita a integração de mudanças no repositório remoto através de uma pull request |

#### Ramificação (branch)

| Comando                           | Descrição                                                 | 
| :-------------------------------- | :-------------------------------------------------------- | 
| `git branch`                      | Lista todas as branches no repositório                    | 
| `git branch [nome]`               | Cria uma nova branch com o nome especificado              | 
| `git checkout [branch]`           | Muda para a branch especificada                           | 
| `git checkout -b [nome]`          | Cria uma nova branch com o nome especificado e muda para ela |
| `git branch -d [nome]`            | Apaga a branch especificada                               |
| `git branch -D [nome]`            | Força a remoção da branch especificada, mesmo que haja commits não mesclados  |
| `git push origin --delete [nome]` | Apaga a instância remota da branch |
| `git merge [branch]`              | Mescla uma branch com a branch atual                      | 
| `git remote`                      | Lista os repositórios remotos configurados                | 

#### Mesclagem (merge)

| Comando           | Descrição                                        | 
| :---------------- | :----------------------------------------------- | 
| `git merge`      | Mescla uma branch com a branch atual            | 
| `git rebase`     | Reaplica as alterações de uma branch sobre outra| 
| `git mergetool`  | Abre uma ferramenta para resolver conflitos     | 


#### Criação e Exclusão de Arquivos

| Comando                                       | Descrição                                                 | 
| :-------------------------------------------- | :-------------------------------------------------------- | 
| `touch [nome_arquivo]`                        | Cria um novo arquivo vazio com o nome especificado        |
| `echo [conteúdo] > [nome_arquivo]`            | Cria um novo arquivo com o conteúdo especificado          |
| `rm [nome_arquivo]`                           | Remove (apaga) um arquivo                                 |
| `rm -rf [diretório]`                          | Remove (apaga) um diretório e seu conteúdo recursivamente |


#### Desfazendo Alterações no Git

| Comando                                              | Descrição                                                                               | 
| :--------------------------------------------------- | :-------------------------------------------------------------------------------------- | 
| `git commit --amend -m "[nova mensagem]"`           | Altera a mensagem do último commit                                                       |
| `git restore --staged [arquivo]`                    | Remove arquivos do staging area, mas mantém as alterações nos arquivos no diretório de trabalho |
| `git restore [arquivo]`                             | Desfaz as alterações em um arquivo específico, revertendo para a versão do último commit |
| `git reset --soft [hash code]`                           | Desfaz o último commit, mantendo as alterações no diretório de trabalho e no staging area |
| `git reset --mixed [hash code]`                          | Desfaz o último commit, mantendo as alterações no diretório de trabalho, mas removendo do staging area |
| `git reset --hard [hash code]`                           | Desfaz o último commit, descartando completamente as alterações                           |


# Arquivos especiais

## .gitkeep

O arquivo `.gitkeep` é comumente usado em diretórios vazios em repositórios Git para garantir que o Git mantenha o diretório vazio ao ser clonado ou puxado por outros usuários. O Git normalmente não rastreia diretórios vazios, então adicionar um arquivo `.gitkeep` dentro de um diretório vazio força o Git a manter o diretório no controle de versão. Por exemplo:

```bash
# Criar um diretório vazio
mkdir meu_diretorio

# Entrar no diretório
cd meu_diretorio

# Criar o arquivo .gitkeep
touch .gitkeep

# Adicionar e commitar o arquivo .gitkeep
git add .gitkeep
git commit -m "Adiciona arquivo .gitkeep para manter o diretório vazio"

# O diretório vazio agora será rastreado pelo Git
```



## .gitignore

O arquivo `.gitignore` é utilizado para especificar quais arquivos e diretórios devem ser ignorados pelo Git. Isso é útil para evitar que arquivos temporários, arquivos de compilação ou qualquer outro tipo de arquivo desnecessário seja incluído no controle de versão. O `.gitignore` pode conter padrões de arquivos ou diretórios que o Git deve ignorar. Por exemplo:

```plaintext
# Arquivos de compilação
*.o
*.out

# Arquivos temporários
*.tmp

# Diretórios específicos
temp/
logs/
```

Para usar o `.gitignore`, crie um arquivo chamado `.gitignore` na raiz do seu repositório e liste os padrões de arquivos ou diretórios que você deseja ignorar. Depois, adicione e confirme o arquivo `.gitignore` no seu repositório Git. O Git então automaticamente ignorará os arquivos e diretórios especificados, não os rastreando no controle de versão.

## Autores

- [@devklebinho](https://www.github.com/devklebinho)


## Referência

- [Documentação oficial](https://git-scm.com/doc)

[Voltar](README.md)