# Comandos no Git
>No terminal (ou Git Bash, no Windows) navegue até a pasta recém criada (utilize o comando cd para navegar entre pastas);

Abra o **Git Bash** no seu pc e escreva o caminho do documento `cd Documents/.../.../`

## Criando repositorio: 
`git init`

## Adicione os aqquivos do projeto
>adicionando arquivos para serem commitados com **git add**;

adicionar todos `git add .`

ou adicionar um específico `git add` nome do arquivo

## Salvar alterações (**commit**) arquivos adicionados
`git commit -m "coloque a mensagem de alteração"`
> **commit** é a forma de salvar um estado ou versão do nosso código; não devemos realizar commit, ou seja, salvar um estado, da nossa aplicação que não esteja funcionando.
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
## Criando servidor para Repósitorio Remoto 

1° no pronpt comando(git bush) crie uma pasta
 
`cd ..`

2° nomei a pasta pelo comando:

`mkadir nome_da_pasta`

3° Localize a pasta

`cd nome_da_pasta/`

4° criando

`git init --bare`

> **git init --bare** Indica ser um repositorio que apenas contém as alterações, Objetiva apenas armazenar as alterações

5° Voltar pra pasta onde ta o projeto

`cd ../pasta_projeto/`
> Exemplo neste curso: `cd../git-e-github/`


