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

> Com este comando nós criamos um repositório que não terá a working tree, ou seja, não conterá uma cópia dos nossos arquivos. Como o repositório servirá apenas como servidor, para que outros membros da equipe sincronizem seus trabalhos, poupamos espaço de armazenamento desta forma.

5° Voltar pra pasta onde ta o projeto

`cd ../pasta_projeto/`
> Exemplo neste curso: `cd../git-e-github/`

6° Reconhecer o Repósitorio Remoto

`git remote`

> essa função lista todos os repósitorios remotos que o meu ropositorio local conhece

7° Adicionando repósitorio remoto

`git remote add nome-repositorio caminho/para/o/repositorio`
> O caminho pode ser qualquer coisa de outro computador, url...

revendo endereço: `git remote -v`

## Clonar Repósitorio Remoto de alguém
> Quero trazer pela primeira vez os dados de um Repósitorio Remoto para meu repósitorio local

Em uma determinada em pasta em um certo local crie uma pasta:

Exemplo:

`mkadir ana`

Entre na pasta:

`cd ana`

> AGora Imagina que essa pasta é no computador da Ana e ela quer trabalhar ela precisa clonar um determinado repósitorio pra sua pasta:

`git clone endereço-do-repositório nome-da-pasta-que-voce-criar`

> Conclusão: Troussemos os dados de um repositorio remoto para a pasta Ana

## Sincronizando Dados (Enviar dados aos servidor remoto)

> Pra onde? De onde?

Mandando dados:

`git push nome-repósitorio branch-ramo`

obs: nome-repositorio é o repositorio remoto que receberá as informações
> NOTA: branch-ramo é a linha de trabalho ex: **master**. 

AGora Como trazer os dados do repósitório 
remoto (repositorio central) ?

comando `git pull nome-repositorio branch-ramo`

> NOTA: VOCÊ PODE RENOMEAR UM REPÓSITORIO: `git romote rename nome-antigo nome-atualizado` 


