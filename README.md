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
> Veja a posição dos ultimos comites exe:  `git log -n 2`
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

## Enviar dados aos servidor remoto (Sincronizando Dados)

> Pra onde? De onde?

Mandando dados:

`git push nome-repósitorio branch-ramo`

obs: nome-repositorio é o repositorio remoto que receberá as informações
> NOTA: branch-ramo é a linha de trabalho ex: **master**. 

AGora Como trazer os dados do repósitório 
remoto (repositorio central) ?

comando `git pull nome-repositorio branch-ramo`

> NOTA: VOCÊ PODE RENOMEAR UM REPÓSITORIO: `git romote rename nome-antigo nome-atualizado` 
## Utilizando um repósitorio na Web (Github)
> Copie o http do repositório

Codigo:

`git remote add origin https://github.com/sua-url.git`

> Nota: `origin` é nome do repósitorio adicionado mas você pode mudar

2 - Envie os dados do repositório:

`git push origin(nome-repositorio) master`

## Divisões nos ramos de desenvolvimento (Branches)

> São linhas de desenvolvimento. Ex : `master`

consultando os Branchs atuais :
`git branch`

adicionando um branch, ex : titulo :
`git branch titulo`

Como ir a um determinado ramo de desenvolvimento, neste exemplo **titulo**:

`git checkout titulo`
> DICA: Use o site para ter noção da arquitetura no github https://git-school.github.io/visualizing-git/

>ATalho para criar o branch e ir direto para ele: `git checkout -b nome-branch`

## Para saber mais: Ramificações

Branches ("ramos") são utilizados para desenvolver funcionalidades isoladas umas das outras. A branch master é a branch "padrão" quando você cria um repositório.

É interessante separar o desenvolvimento de funcionalidades em branches diferentes, para que as mudanças no código para uma não influencie no funcionamento de outra.

## Unificando todas as alterações para o repósitorio principal

no branch master digite o comando `git merge nome-repositorio`

outra forma: `git rebase nome-repositorio`

## EVITANDO CONFLITOS

> ANTES DE ENVIAR QUALQUER ALTERAÇÃO VERIFIQUE SE TEM ALGUMA ALTERAÇÃO NO REPOSITORIO REMOTO

verificar fazer primeiro `git pull repositorio-remoto`

depois enviar suas alterações `git push repositorio-remoto`

## NINIFICANDO TRABALHO PARA REPOSITORIO PRINCIPAL

 > EXEMPLO : Execute o comando `git merge titulo` para trazer o trabalho feito na branch titulo para a branch master

 > VOce pode usar também `git rebase nome-repositorio`

 Execute o comando `git log --graph` para ver as linhas de desenvolvimento (branches);


 ## DESFAZENDO
Antes do git add:

> Pode usar `git restore nome-arquivo`

Ou
 1) Na pasta que representa o seu projeto, faça uma alteração qualquer no arquivo index.html;

2) Execute o git status e veja que há uma alteração para adicionar;

3) Execute o comando `git checkout -- index.html`. Confira se sua alteração foi desfeita;

>1.  Após o `git add`: 

 Execute o comando `git reset HEAD index.html` para trazer o arquivo index.html de volta para a HEAD do projeto (remover do stage, que é o que será enviado para o commit);

 >2. Após git add index.html e o comando git commit -m ""

 1) Execute o comando git log e copie o hash deste commit recém criado;

2) Rode o comando `git revert hash-numero`, substituindo {hash-numero} pelo hash que você copiou anteriormente;

3) Confira que suas alterações foram desfeitas;

## Guardando para continuar depois

1) Faça mudanças

2) Execute o comando `git stash` para salvar estas alterações na stash;

>Execute o comando `git stash pop`  para trazer a última alteração da stash;

> OUtro jeito:  Ver lista `git stash list` depois `git stash apply numero-stash` depois remova o que guardou `git stash drop`

## Viajando no historico

1. Execute o comando `git log --oneline` para ver os commits de forma resumida. Copie o hash do commit de merge com a branch lista;

2.  Execute o comando `git checkout hash-numero` substituindo {hash} pelo hash que você copiou;

3. Veja que diversas alterações não estão mais presentes;

4. Execute `git checkout master` para voltar à linha principal de desenvolvimento.

## Exibição das mudanças com o Diff

comando: `git diff`. É possível visualizarmos as mudanças realizadas em determinado código. Podemos ver as diferenças entre commits, branches, etc.

1. Ver mudanças Entre commits: `git diff hash-do-commit..hash-do-último-commit-realizado`

## Release (versões)

> Execute o comando `git tag -a nome-desejado` para criar uma tag no seu código;

exemplo: `git push origin v0.1.0`

>Enviando tag(versão): `git push local v0.1.0`
>Enviando para o github(Consulte o nome `git remote -v`)
depois envie `git push origin v0.1.0`