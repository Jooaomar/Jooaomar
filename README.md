# Comandos no Git

Abra o **Git Bash** no seu pc e escreva o caminho do documento `cd Documents/.../.../`

## Criando repositorio: 
`git init`

## Adicione os aqquivos do projeto
adicionar todos `git add .`

ou adicionar um específico `git add` nome do arquivo
## Salvar alterações (**commit**) arquivos adicionados
`git commit -m "coloque a mensagem de alteração"`
## Como analisar o estado do nosso repositório através do comando?
`git status`
## Informar o Autor dos dados 
`git config --local user.name "Seu nome aqui"`
`git config --local user.email "seu@email.aqui"`
## visualizar o histórico de alterações 
`git log`
## Visualizar alteração mais resumida
`git log --oneline`

## Ver alterações do **commit**
`git log -p` para sair do comando preicione "**`q`**"

## Pesquise sobre **git log** de uma olhada no link
https://devhints.io/git-log

## Ignorar arquivos. Você não quer adicionar determinado arquivo no repositório

crie na pasta direta do projeto um arquivo chamado `.gitignore` e coloque o nome dos arquivos que você não quer levar ao repositório
> Para funcionar você deve no terminal (`git bush`) adiciona-lo --> `git add .gitignore` depois `git commit -m "descrição"`
