# a - linux
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


