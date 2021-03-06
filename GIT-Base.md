# Git Quickstart Guide

## Preparando o Ambiente
Antes de entrar no que é o GIT e seus usos, vamos explicar como instalá-lo nas plataformas
## Instalação 
Para esse Quickstart não utilizaremos GUI, somente linha de comando
###	Windows
Para instalar o GIT em seu Windows, acesse https://git-scm.com/downloads e baixe a versão para Windows. 
O Instalador é simples, next-next-finish.
###	Linux / Unix
####	Debian/Ubuntu
`apt-get install git`

*Para Ubuntu, esse PPA fornece a última versão estável*

`add-apt-repository ppa:git-core/ppa `
` apt update`
` apt install git`


## Configuração do Git
Após a instalação, podemos verificar se o GitBash se encontra instalado no Windows, ou abrirmos um console no Linux e digitar o seguinte comando
`git` 
 
 Como resultado de sucesso, deveremos ver algo similar a:\
![](https://github.com/xonho/GitHandsOn/raw/master/images/git-console.png)

Devemos configurar nosso user global:
`git config --global user.name "Paulo Antonio Cerávolo"`
`git config --global user.email "contato@ceravolo.com.br"`
  
Essas são as configurações padrão para todos os repositórios.

##*Dica*
Para uma configuração específica de repositório, você deverá, na pasta dele, digitar

`git config user.name "Paulo Antonio Cerávolo"`
`git config user.email "contato@ceravolo.com.br"`
 
Utilizamos essa opção quando temos credenciais específicas para um projeto. 
## *GIT e Versionamento*
Um sistema de controle de versões (ou versionamento), VCS (do inglês version control system) ou ainda SCM (do inglês source code management) na função prática da Ciência da Computação e da Engenharia de Software, é um software que tem a finalidade de gerenciar diferentes versões no desenvolvimento de um documento qualquer. Esses sistemas são comumente utilizados no desenvolvimento de software para controlar as diferentes versões — histórico e desenvolvimento — dos códigos-fontes e da documentação

O Git é um sistema open-source de controle de versão.

### *História*
O desenvolvimento do Git surgiu após vários desenvolvedores do kernel do Linux terem uma desavença com o proprietário do BitKeeper por conta de engenharia reversa de protocolos (não ocorreu, na verdade foi um telnet para a porta do servidor e envio do comando help).
A partir daí, Linus Torvalds e sua equipe começaram a desenhar um sistema para desenvolvimento não linear, distribuído, retrocompatível, escalável, com suporte para grandes projetos, timeline com criptografia, 
### *Motivação*
Imagine os seguintes cenários
- Tenho uma aplicação que desenvolvo com mais pessoas. Cada pessoa é responsável por uma funcionalidade específica do código. Como vamos trabalhar em conjunto para que todas as partes sejam integradas da forma menos traumática possível?
- Tenho uma aplicação que mantenho sozinho. Quero aumentar as funcionalidades da aplicação. Fiz uma modificação que inseriu um bug, e meu backup tem data de ontem. Perdi um dia de trabalho? Tento fazer um BugFix? Quanto tempo eu vou gastar caçando esse Bug?

Por isso é importante termos um sistema de controle de código
### *Benefícios*
- Linha do tempo
	*Temos uma linha cronológica de desenvolvimento de um aplicativo, mostrando a ordem de commits, branches, merges etc.*
- Segurança
	*Evita corrupções de arquivos, identificação de mudanças. Uso de repositórios remotos garante resiliência.*
- Trabalho em equipe
	*Os branches permitem que mais de uma pessoa possa trabalhar na mesma feature ou no mesmo projeto. 	*
- Organização
	*O ciclo de vida da aplicação é controlado.
- Rasterabilidade
	*Quando se trata de algo importante, é sempre interessante saber “Quem”, “Quando”, “Como”, “Por que” e “Onde”.*

## GitHub – Um depósito de Códigos *social*

>O GitHub é uma plataforma de desenvolvimento inspirada na maneira como você trabalha. Do código aberto aos negócios, você pode hospedar e revisar códigos, gerenciar projetos e criar software junto a 50 milhões de desenvolvedores.
Ele permite que programadores, utilitários ou qualquer usuário cadastrado na plataforma contribuam em projetos privados e/ou Open Source de qualquer lugar do mundo.
Projetos hospedados: Worpress, GNU Linux, Atom, Electron

### Criação de Conta
*Piece of cake. Entre no site do GitHub*
![](https://github.com/xonho/GitHandsOn/raw/master/images/github-init.png)


## Conceitos e Comandos
**Regra de ouro: Teve dúvida? Sua primeira linha de frente é** 
`git NOME_COMANDO --help`

### Repositório

Um repositório é o elemento mais básico do Git e GitHub. Imagine isso como uma pasta do projeto (que contém outras pastas também). Um repositório contém todos os arquivos do projeto (incluindo a documentação) e armazena o histórico de revisões de cada arquivo.

#### Init
Utilizado para iniciar nosso projeto com um sistema de controle de versão de código. Na pasta do projeto, digite
`git init`

#### Clone
Clona um projeto já existente em algum *remote*
`git clone URL`
 (***Com o GitHub, é necessário a configuração das chaves SSH***)
#### Remote
Repositório Remoto do nosso Projeto. Para configurá-lo: 
`git remote add origin URL_REPO`
`git remote remove origin`

*Na maioria casos, quando clonamos um repositório, o remote já vem configurado*

#### Workflow e Lifecycle

![Lifecycle de um arquivo](https://git-scm.com/book/en/v2/images/lifecycle.png)
> *Possíveis estados de um arquivo*

![](https://raw.githubusercontent.com/rohit120582sharma/Documentation/master/images/git.png)
> Primeiro, você edita seus arquivos no diretório de trabalho. 
> Quando você estiver pronto para salvar uma cópia do estado atual do projeto, faça mudanças com o git add.
> Depois de ficar satisfeito com o snapshot em staging, você o confirma no histórico do projeto com o git commit.
> Os comandos: git add, git status e git commit usados ​​em conjunto para salvar um snapshot do estado atual de um projeto Git.

### Status

O comando confere o status e reporta que não existe nada para fazer um commit, o que quer dizer que o repositório está com o atual estado do diretório de trabalho e não existem modificações a serem gravadas.

### Add

O comando git add inclui uma alteração do diretório de trabalho na área de preparação (Staging).
`git add arquivo`

### Commit

O commit do git é usado para criar um snapshot das alterações em etapas ao longo de uma linha do tempo de um histórico de projetos do Git.
`git commit -m "MESSAGE"`


### Branch
Uma ramificação (branch) representa uma linha de desenvolvimento independente. 
As ramificações servem como uma abstração para o processo de edit / stage / commit.

Lista os branches locais

`git branch`

Lista os branches remotos

`git branch -a`

Cria um branch mas não dá checkout
`git branch <branch>`


### Checkout
Mudar de branch. Quando o git muda de branch, todas as alterações que foram aplicadas na branch serão substituídas pelas alterações da branch que foi feito o checkout.

Faz checkout num branch existente

`git checkout <branch` 

Cria um brancheo dá checkout

`git checkout -b <branch>`


### Push

O git push é utilizado para enviar as alterações confirmadas para repositórios remotos para colaboração

### Pull

O comando git pull é, na verdade, uma combinação de dois outros comandos git fetch seguido por git merge. Na primeira etapa da operação, git pull vai executar um git fetch do escopo para o ramo local ao qual HEAD está apontado. Depois que o conteúdo for baixado, git pull vai entrar em um fluxo de trabalho de merge. Um novo commit de merge vai ser criado e HEAD vai ser atualizado para apontar para o novo commit.

### Head
O ponteiro HEAD aponta para o último grupo de alterações(snapshot) comitado.

### Merge

A fusão (merge) é a maneira de o Git reunir novamente uma história bifurcada (forked). O comando git merge permite pegar as linhas independentes de desenvolvimento criadas pelo git branch e integrá-las em um único branch.

`git merge <branch>`

## Futuro
O Básico de Git está aqui. Existem outros conceitos e comandos importantes como Rebase, Tagging, Stash, Prune, Hooks, Ammend

# Referências
https://git-scm.com/ - Git 
https://github.com/rohit120582sharma/Documentation/wiki/Git-~-Saving-changes - rohit120582sharma@GitHub






