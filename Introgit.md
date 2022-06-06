# Aula 2
## _Introdução ao Git/GitHub

[Git-Livro](https://git-scm.com/book/en/v2)

**Git / GitHub**
O Git é um software de versionamento de código (controla versões)  que ajuda a criar e a monitorar diferentes versões do nosso código, dentro de nossa máquina.  
Interagimos com o Git através de linhas de comando - CLI = Uma interface de linha de comandos, em inglês command-line interface, é um meio de interagir com um programa de computador, onde o utilizador emite comandos para o programa sob a forma de sucessivas linhas de texto.


**Como Git funciona por  baixo dos panos:**
SHA1 = É um algoritmo de encriptação, é um conjunto de funções  hash criptográficas, ele gera um conjunto de caracteres identificadores de 40 dígitos. Isso traz mais rapidez e segurança  aos arquivos.
Uma forma que o Git tem para identificar que determinado arquivo sofreu ou não modificações.
Comando para encriptar os arquivos: openssl sha1 nome do arquivo.
Objetos internos do Git
Blobs: Um blob (objeto binário grande) específico do Git que contém metadados e é o tipo de objeto usado para armazenar o conteúdo de cada arquivo em um repositório. O hash SHA-1 do arquivo é calculado e armazenado no objeto do blob. 
Tree: Armazenam blobs, a blob é o bloco básico da composição enquanto a Tree armazena e aponta para tipos de blobs diferentes. A tree também contém metadados e tem seu próprio SHA1. É responsável por montar a estrutura de onde estão localizados os arquivos, podem apontar blobs e até para outras árvores. 
Commit: É o mais importante, ele aponta para uma árvore, ele junta todas as informações e alterações do arquivo dando significado para as alterações. Também possui SHA1 . 
Esses objetos estão relacionados entre si. Qualquer coisa alterada no arquivo, também é alterada toda essa estrutura até o Commit. 

**Chaves SSH E Tokens**
 Quando vamos colocar nosso código no Github é necessário uma autenticação 
Chave SSH: É uma forma de estabelecer uma conexão segura, encriptada entre duas máquinas, vamos se conectar ao servidor do Github e configurar a nossa máquina local como uma máquina confiável através de duas chaves: uma pública e uma privada. Pegamos a chave pública e colocamos ela lá e a partir desse momento o Github reconhece a assinatura da nossa máquina sempre que precisarmos.
Token de acesso pessoal:



## Comandos do Git:


- git init: Para iniciar o repositório do Git. cria-se um repositório dentro da pasta. 
- git add: Para mover arquivos e começar o versionamento.
- git commit -m: Para criar o primeiro commit
- git status: Diz sem qual status o arquivo está.
- git remote -v: mostra as lista de repositórios que temos cadastrados.
- mv: move arquivos no git - $ mv receitas.txt ./receitas/
- git clone link no github
- git remote add origin link do arquivo :Para empurrar nosso arquivo de um repositório local para um servidor remoto. 
- git push origin master: empurra o repositório local para o remoto.

Configuração inicial antes de criar nosso primeiro arquivo é necessário configurá-lo através de um email e um username. Para que o commit apresente o autor. 

 - git config - -global user.email ‘’email “ 
 - git config - -global user.name ‘’nomedeusuário “ 

**Tracked e Untracked**
Tracked: arquivos que a gente tem ciência deles. 
Untracked: arquivos que a gente não tem ciência deles. Ex: arquivos que estão sendo criados - git init e quando damos o comando git add * Esses arquivos que estão Untracked, ou seja, que acabaram de ser criados com o Git init é movido direto para o Staged está aguardando alguma coisa ou uma nova modificação.
Unmodified: Arquivos não modificados, e que após serem modificados vão direto para próxima etapa. O terminal Git reconhece a modificação através da comparação do SHA1, onde ele consegue reconhecer que aquele arquivo sofre uma modificação. Após a modificação do arquivo damos o comando git add * para ele seguir para próxima etapa de modificados. 
Modified: Modificados, quando damos o comando git add * Ele vai direto para próxima etapa Staged. 
Staged: Onde ficam os arquivos que estão se preparando para fazer parte de um commit. O commit retorna todos os arquivos para Unmodified, para que o arquivo possa receber novas modificações (versões) um processo de ciclos. 
Quando usamos o git commit - m, pegamos todos arquivos que estavam em stage e transferimmos para o repositório local. 
Como funciona o ambiente de desenvolvimento (máquina local)
Os arquivos passam pelas de etapas de Untracked até Modified, estão transitando em WORKING DIRECTORY E A STAGING AREA. 

Tudo que está comitado, tem que estar em um repositório local. Para depois irem para nosso repositório remoto o Github.

**Como acontecem os conflitos no Github**
Quando já temos nosso código no Github e baixamos ele para nossa máquina e uma outra pessoa clona para fazer uma contribuição, durante a edição pode ocorrer de ambos fazerem a edição na mesma linha, um dos dois vai mandar o arquivo para o Github primeiro deixando o outro desatualizado, quando isso ocorre gera um conflito de Merje. Para resolver isso, é necessário baixar o arquivo novamente e trabalhar nele e depois empurrá-lo novamente. 













