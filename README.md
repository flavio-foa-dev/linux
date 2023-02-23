# a - linux conhecendo e utilizando o terminal
Há uma opção de usar o Git Bash,
uma linha de comando para rodar a linguagem Git
que oferece ainda um terminal Linux para o computador.

### Comando terminal
 - pwd
 - ls = retorna o conteúdo do diretório atual
 - touch = criar um arquivo exemplo  touch teste.md
 - echo "bem vindo" >  teste.txt
 - echo "bem vindo dois" >  teste.txt
 - cat = recebe o nome do arquivo como argumento e imprime seu conteúdo  exemplo cat teste.txt
 - clear = para limpar a tela do terminal. O atalho Ctrl + L tem a mesma função.
 - ls -l =  Para listar de forma detalha usamos o parâmetro -l
 - ls -la =  Para listar os arquivos e diretórios incluindo arquivos ocultos
 - man = manual dos comandos exemplo -  man ls -
 - help = date --help
 - whoami  = nome do usuario no Linux
 - cd
 - cd ..
 - mkdir
 - / raiz do nosso hd linux
 - rmdir = apagar diretorio
 - rm apagar arquivo
 - rm -r remove recursivamente
 - cat teste?.txt = ler todos arquivos com mais um caractere
 - cat teste*.txt = ler todos arquivos com qualquer caractere
 - cat *.txt = ler todos arquivos com qualquer nome
 - head alvo = ler as 10 inicio arquivo
 - head -n (linhas)  alvo = ler as n linhas do inicio arquivo
 - tail alvo = ler as 10 ultimas linhas
 - tail -n (linhas)  alvo = ler as n linhas do fim do arquivo
 -
 - cp copia
 - cp bemvindo.txt (alvo)   mensagem.txt(destino) cp passando o nome do arquivo que desejamos copiar, e o nome do novo arquivo após cópia.
 - mv move
 - cp -r copia recorsiv
 - zip nome.zip alvo
 - zip -r nome.zip alvo
 - unzip -l mostra o que tem dentro do zip
 - posso passar a flag   q (quiet)   para nao apresentar log
 - zip bemvindo.zip *.txt
 - tar -c(create) -z(zip) alvo  > nome.tar.gz (gzip)  padrao do tar ja e recursivo e quiet
 - tar x(extract) -z < (saida) alvo
 - tar -cz -f(referencia nome do arquivo)  teste3.tar.gz alvo
 - tar -xzf teste3.tar.gz
 - tar -v (verbose quiet) -xzf teste3.tar.gz
 - o comando tar não compacta, apenas empacota os arquivos
 - date "+%d/%m/%y"   formata data saida
 - date "+%d de %B de %Y"  saida

 - vi (editor de codigo no terminal) alvo
 - i: inclui (na posição atual)
 - a: adiciona (na posição posterior)
 - Shift+A: adiciona (fim da linha)
 - x: remove caracteres (n* x remove *n caracteres)
 - dd: remove uma linha (n* dd remove *n linhas)
 - Shift + g = última linha do texto
 - 5 e depois Shift + g = quisermos ir para a linha 5
 - $ final da linha atual
 - procura de palavras
 - digitamos "/"  + o texto que procuramos
 - tecla n, ele irá para a próxima ocorrência e com Shift + n
 - yy copia a linha
 - p cola

 ```
  tar -czf work.tar.gz workspace/
  O parâmetro -c indica ao comando tar que desejamos criar um novo arquivo.
  O comando tar apenas empacota vários arquivos em um único arquivo, sem realizar compactação, e por isso passamos o parâmetro -z para indicar que queremos, além de criar um único arquivo, realizar um processo de compactação utilizando o formato .gz. Quando compactamos podemos reduzir o tamanho.
  O parâmetro -f indica que compactaremos para um arquivo.

  tar -xzf work.tar.gz
  Para descompactar o arquivo .tar.gz, substituímos o -c que usamos antes por -x, para indicar que iremos extrair os arquivos.
  O f indica que lemos de um arquivo. E o z, que o arquivo está compactado.
  O parâmetro z na verdade é ignorado na extração, no man fala que só funciona no creation mode.
  poderíamos fazer: tar -xf work.tar.gz.
```

```
Um outro formato de compactação junto com o tar é .bzip2.
Esse formato é mais eficiente na compactação, conseguindo criar arquivos menores. Porém o tempo que o .bzip2 leva para criar o arquivo compactado é maior do que o tempo do gzip.
Para criar um arquivo .tar compactado com o bzip2,
substituímos o -z (de gzip) por um -j. O formato que utilizamos é o .tar.bz2.
 exemplo: tar -cjf work.tar.bz2 workspace/
```
<hr>
exemplo ls -l
```
drwxr-xr-x 4 vagrant vagrant 4096 Jan 13 19:00 .
drwxr-xr-x 4 root    root    4096 Jan  6 12:19 ..
-rw------- 1 vagrant vagrant  184 Jan  6 13:29 .bash_history
-rw-r--r-- 1 vagrant vagrant  220 Apr  9  2014 .bash_logout
-rw-r--r-- 1 vagrant vagrant 3637 Apr  9  2014 .bashrc
drwx------ 2 vagrant vagrant 4096 Jan  6 12:19 .cache
-rw-rw-r-- 1 vagrant vagrant    0 Jan  6 13:06 .cloud-locale-test.skip
-rw-r--r-- 1 vagrant vagrant  675 Apr  9  2014 .profile
drwx------ 2 vagrant vagrant 4096 Jan  6 12:19 .ssh
-rw-rw-r-- 1 vagrant vagrant   37 Jan 13 19:00 bemvindo.txt
```

1.  iniciando com de de diretorio
2.  regras do arquivo
3.  grupo
4.  usuario
5.  tamanho
6.  data
7.  nome
<hr>

# b - linux programas, processos e pacotes
- Controle dos processos rodando na máquina
- Variáveis de ambiente e o PATH
- Gerenciando pacotes com o APT
- Sistema de permissões
- SSH e SCP para comunicação remota

- ps = mostra os processos que estão em execução no bash atual
- ps -e = mostra todos os processos pc
- pf -ef = mostra processos detalhes
- grep = filtra as linhas
- kill pid = mata programa, dando chance
- kill -9 pid = mata programa sem da chance
- kill -stop pid
- kill -cont pid
- killall = permite matar todos os processos de um mesmo programa, com um mesmo nome, sem precisar digitar seus ID's
- cat google.txt | grep "Larry Page and Sergey Brin" = busca palavras em arquivos
- top = mostra consumo dos processos
- top -u name = mostrar apenas os processos de um determinado usuário
- top -p pid = podemos acompanhaer um processo
- d = alterar esse tempo basta pressionar d enquanto estiver rodando o top, inserir o valor desejado e pressionar a tecla Enter

### Jobs, bg, fg, pstree, &
- <programa> = abrimos o programa
- CTRL + Z = nós paramos temporariamente o processo.
- jobs = mostra os processos que estão sendo executados dentro do bash;
- fg e bg = jogam os processos para foreground e background, respectivamente;
- <programa> & = abre o <programa> diretamente em background;
- pstree = mostra todos os processos em um gráfico de árvore.

### sh e chmod
- gedit <nome> = cria um script
- sh <nome> = executa script sem a permissao x
- ./(local)<nome> = executa script com a permissao x
- chmod +<perm> <arquivo >= adiciona a permissao
- chmod -<perm> <arquivo> = remove a permissao
- chmod +rwx
- chmod u-rwx = tiro as permissoes do usuario
- chmod g-rwx. = tiro as permissoes do grupo
- chmod o-rwx. = tiro as permissoes dos outros users


d = marca que e um diretorio
1. r (leitura)
2. w (escrita)
3. x (execucao)
4. dono
5. grupo
6. outros usuarios

### locate e updatedb
- sudo updatedb
- sudo locate firefox
- sudo locate *.txt
- which = mostra local do executal do programa
- which firefox = /snap/bin/firefox

### trocar usuario
- passwd = muda senha usuario
- sudo passwd = adiciona senha ao root
- whoami = mostra username
- su <nome usuario> = muda para usuario logar com outro usuário
- adduser <nome novo ususario> = adiciona um novo usuario
- sudo adduser nico = add new user

### PATH
- env = mostra todas as variaveis de ambiente
- env | grep PATH
- PATH = variavem de ambiente que podemos addicionar path do script
- PATH=$PATH/home/flavio/src = bashrc
- gedit .bashrc &
Esse arquivo é carregado toda vez que abrimos uma aba nova no Terminal.
Ele já possui vários comandos.
adicionar a seguinte linha e salvar:

PATH=$PATH:/home/local/src

A variável PATH, guarda informações de onde estão nossos arquivos executáveis para que possamos executar um comando sem a necessidade de digitar o caminho absoluto

- wc = para contar o número de palavras
- -w = para indicar que desejamos contar apenas o número de palavras que existem no arquivo.  *.txt ou contagem em todos os arquivos .txt do nosso diretório atual.
- -c = o número de caracteres
- -l = para linhas.
- exemplo = ps -e | wc - l

### PS1 Alterando a configuração do prompt
- ps1 = Uma outra variável de ambiente

### instalacao de programa APT
- apt = sistema de gerenciamento de pacotes central de programas do ubuntu
- sudo apt-get update = busca uma lista das versões atualizadas dos programas
- apt-cache search <programa> procura os programas disponíveis para instalação
- sudo apt-get install <programa> instala os pacotes
- sudo apt-get remove <programa> remove os pacotes
- show, mostra informacoes sobre um determinado pacote exemplo apt-cache show mysql-server-5.6

Podemos instalar programas que não estão disponibilizados na central de programas do Ubuntu, ou seja, sem o uso do apt
Para isso nós baixamos um pacote desse programa em um site e depois o instalamos. O formato desse pacote é dpkg, que é um arquivo com a extensão .deb.
exemplpo
- sudo dpkg -i(install) <programa>.deb
- sudo dpkg -r(remove) <programa>

No caso do Google Chrome, iremos receber alguns erros, pois o pacote depende de outros pacotes e o dpkg não resolveu isso pra gente. Para baixar as dependências e fazer com que o Google Chrome funcione corretamente, pedimos para o apt-get tentar resolver esse problema:
-  sudo apt-get -f install
-  A opção -f no comando apt-get tem a função de tentar corrigir possíveis pacotes quebrados que podem ser resultados de uma instalação mal sucedida causada por exemplo por uma queda de energia, instalação interrompida ou ainda pela instalação de um programa instável que possa ter gerado problemas entre dependências de pacotes.

Resumindo: O parâmetro -f tenta fazer um fix (conserta) em pacotes quebrados.

1. Via apt: quando o programa já está disponibilizado na central do Sistema Operacional Linux.
2. Via dpkg: quando baixamos pelo navegador da internet um pacote .deb do programa.

### scripts init e services
- sudo service <programa> stop = para um servico
- sudo service <programa> start = inicia um servico
- Os scripts dentro do diretório /etc/init.d são os programas que são executados no startup da máquina.
- ls /etc/init.d/ = veja quais serviços o seu computador possui.
- sudo service <programa> status = verifica o status de um servico

### instalacao a parti do codigo fonte
bildar um projeto

1. ./configure
2. make
3. sudo make install

### acesso remoto
- ssh = logar em uma outra maquina
- exemplo ssh fulano@ip
- ssh -x  = o que for feito na maquina la , mostra na minha maquina
- scp -r(recursiva) <nome arquivo> alvo@ip = copia arquivo para a maquina alvo:diretorio(~/)
