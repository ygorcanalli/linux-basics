# linux-basics
Curso rápido de introdução ao Linux

Curso Ministrado no Colégio Pedro II - Campus Duque de Caxias, considerando um ambiente Ubuntu 22.04 via WSL2.

![Tux](https://upload.wikimedia.org/wikipedia/commons/thumb/3/35/Tux.svg/220px-Tux.svg.png)

## Quem usa Linux?

- Todo mundo com um Smartphone Android usa Linux :)
- Desenvolvedores de Software em geral
- A internet roda em Linux
- Google, Twitter, Facebook, Amazon, IBM, NASA, e até a Microsoft (kkk)
- [Curiosidades](https://webtribunal.net/blog/linux-statistics/#gref)
    - todos os 500 supercomputadores mais poderosos do mundo rodam Linux
    - 96% dos principais servidores do mundo rodam Linux
    - 90% de toda infraestrutura de nuvem roda sobre o Linux

## Breve Histórico

 - O que é um Sistema Operacional?
    - Primeiros computadores não possuiam Sistema Operacional (consulte um breve resumo História da Computação [Parte 1](ICC%20Aula%201.pdf) e [Parte 2](ICC%20Aula%202.pdf))
    - Utilizar outro programa significava desligar o computador e substituir fisicamente as instruções
    - Gerencia recursos: processador, memória, disco, periféricos, etc
 - [Unix](https://pt.wikipedia.org/wiki/Unix)
    - Revolucionário Sistema Operacional Portátil, Multitarefa e Multiusuário
    - Criado por [Ken Thompson](https://pt.wikipedia.org/wiki/Ken_Thompson) e [Dennis Ritchie](https://pt.wikipedia.org/wiki/Dennis_Ritchie) (e outros) na [Bell Labs](https://pt.wikipedia.org/wiki/Bell_Labs) a partir de 1969
    - Reescrito em 1973 em [C](https://pt.wikipedia.org/wiki/C_(linguagem_de_programa%C3%A7%C3%A3o))
    - Amplamente utilizado nas décadas de 70 e 80
    - Define um [padrão](https://pt.wikipedia.org/wiki/POSIX) de Sistemas Operacionais
 - [Minix](https://pt.wikipedia.org/wiki/Minix)
    - Clone educacional do Unix
    - Desenvolvido pelo [prof. Andrew Tanembaum](https://pt.wikipedia.org/wiki/Andrew_Stuart_Tanenbaum) para lecionar a [disciplina](https://www.amazon.com.br/Sistemas-operacionais-modernos-Andrew-Tanenbaum/dp/8543005671) de Sistemas Operacionais
    - Código distribuído Livremente para a turma
 - [Linux](https://pt.wikipedia.org/wiki/Linux)
    - [Treta histórica](https://pt.wikipedia.org/wiki/Debate_entre_Tanenbaum_e_Torvalds) entre Tanembaum e seu aluno [Linus Torvalds](https://pt.wikipedia.org/wiki/Linus_Torvalds)
    - Linus decide criar um "Minix melhor que o Minix"
    - Seria um "UNIX do Linus", lançado oficialmente em 1991 
    - Código publicado na para contribuições na [Usenet](https://pt.wikipedia.org/wiki/Usenet), comunidade de nerds de antigamente
    - Mascote [Tux](https://pt.wikipedia.org/wiki/Tux)
 - Free Software e GNU
    - Filosofia do [Software Livre](https://pt.wikipedia.org/wiki/Software_livre)
        - A liberdade de executar o programa, para qualquer propósito;
        - A liberdade de estudar o programa, e adaptá-lo para as suas necessidades.
        - A liberdade de redistribuir cópias do programa de modo que você possa ajudar ao seu próximo;
        - A liberdade de modificar (aperfeiçoar) o programa e distribuir estas modificações, de modo que toda a comunidade se beneficie.
    - [Free Software Foundation](https://pt.wikipedia.org/wiki/Free_Software_Foundation)
    - [GNU](https://pt.wikipedia.org/wiki/Projeto_GNU) Not Unix
 - [OS X](https://pt.wikipedia.org/wiki/MacOS)
    - Sistema Operacional da [Apple]() baseado em Unix
 - [Android](https://pt.wikipedia.org/wiki/Android)
    - Principal sistema operacional móvel, baseado em Linux
 - [Distros](https://pt.wikipedia.org/wiki/Distribui%C3%A7%C3%A3o_Linux)
    - Código livre permite variações
    - Não existe um Linux, existem [vários](https://distrowatch.com/)!
        - Debian
        - Ubuntu
        - Fedora
        - Mint
        - MX Linux
        - Manjaro
        - Kali
        - RedHat
        - Pop!_OS
        - Elementary
        - Mais um bilhão ...

## Manipulação básica de arquivos

 - diretórios e caminhos
    - `/caminho/para/meu/arquivo.txt`
    - Não confunda barra `/` com contra-barra `\`
 - `cd` - navegar em diretórios
    - entrando na pasta `/`, raiz (root) do sistema
    ```bash
    cd /
    ```
    - entrando na pasta `bin`
    ```bash
    cd bin
    ```
    - voltando para a pasta 'acima'
    ```bash
    cd ..
    ```
    - indo para a pasta `~`, a home do seu usuário
    ```bash
    cd ~
    ```
    
 - `ls` - listar um diretório
    - Lista todos os arquivos em uma pasta
    ```bash
    ls
    ```
    - Variação exibindo detalhes
    ```bash
    ls -l
    ```
    - Variação apresentando os ponteiros `.` e `..`
    ```bash
    ls -a
    ```

 - `mkdir` - criar diretórios
    - entrar na `home` e criar uma pasta com meu nome
    ```bash
    cd ~
    mkdir ygor
    ```
 - `cp` - copiar arquivos
    - entre na pasta downloads do windows, liste os arquivos e faça copia de um deles
    ```bash
    cd /mnt/c/Users/<NomeDoUsuarioDoSeuWindows>/Downloads
    ls
    cp <meuArquivo.txt> <copiaDoMeuAquivo.txt>
    ```
 - `mv` - movimentar arquivos
    - ainda na pasta Downloads do windows mova um arquivo para a home
    ```bash
    ls
    mv <meuArquivo.txt> ~/
    cd ~
    ls
    ```
    - ainda na home, renomeie o arquivo
    ```bash
    ls
    mv <meuArquivo.txt> <novoNomeDoArquivo.txt>
    ls
    ```
 - `rm` - remover arquivos
    - remova o arquivo anteriormente movido
    ```bash
    ls
    rm <novoNomeDoArquivo.txt>
    ls
    ```
 - `*` - wildcard todos
    - use o asterisco para indicar 'todos'
    - `*` - todos os arquivos de um diretório
    - `*.pdf` - todos os arquivos pdf
    - `*.docx` - todos os arquivos docx
    - `A*` - todos os arquivos iniciados com A
    - `A*.pdf` - todos os arquivos pdf iniciados com A
    - copie todos os arquivos pdf de Downloads para sua home
    ```bash
    cd /mnt/c/Users/<NomeDoUsuarioDoSeuWindows>/Downloads
    cp *.pdf ~/
    cd ~
    ls
    ```
 
## Utilitários

 - `man` - manual de uso dos comandos
    - consulte o manual do comando `ls`, use setas para navegar e digite `q` para sair
    ```bash
    man ls
    ```
    - consulte o manual do comando `rm`
    ```bash
    man rm
    ```
 - `touch` - criar um arquivo vazio
    - crie um arquivo vazio `conteudo.txt`
    ```bash
    touch conteudo.txt
    ls
    ```
 - `vim` - editor de texto
    - edite o arquivo criado
    ```bash
    vim conteudo.txt
    ```
    - digite `a` para entrar no modo edição
    - escreva alguma coisa
    - tecle `esc` para sair do modo edição
    - digite `:w` para salvar
    - digite `:q` para sair
    - para um tutorial completo do `vim` use o comando
    ```bash
    vimtutor
    ```
 - `cat` - imprime o conteúdo de um arquivo de texto no terminal
    - imprima na tela o conteúdo do arquivo editado no `vim`
    ```bash
    cat conteudo.txt
    ```
 - `less` - pagina um conteúdo
    - útil para arquivos grandes, setas para navegar, `q` para sair
    ```bash
    less conteudo.txt
    ```
 - `echo` - imprime conteúdo na tela
    - similar ao `print`
    - imprima olá mundo
    ```bash
    echo "olá mundo!"
    ```
    - imprima a variável de ambiente `$HOME`
    ```bash
    echo $HOME
    ```
    - imprima conteúdo misturado
    ```bash
    echo "sou $USER e meus arquivos ficam em $HOME"
    ```
 - `wget` - download de arquivos
    - baixe e pagine o arquivo deste tutorial
    ```bash
    wget https://raw.githubusercontent.com/ygorcanalli/linux-basics/main/README.md
    ls
    less README.md
    ```

## Permissões de acesso

 - Usuários e grupos
    - Cada usuário é uma conta
    - Cada grupo junta usuários e concede permissões
    - Cada usuário pode estar em diversos grupos
 - consulte as permissões dos arquivos em um diretório
    ```bash
    ls -l
    ```
    - `r` -> read = leitura
    - `w` -> write = escrita
    - `x` -> eXecute = execução
    - 1° usuário, 2° grupo, 3° outros usuários
    - `-rwxr-x-r--`
        - usuário pode ler, escrever e executar
        - grupo pode ler e executar
        - outros usuários podem apenas ler
 - `chown` - mudança de propritário (change own)
    - altere o dono de um arquivo
    ```bash
    chown <user> <file>
    ```
 - `chmod` - altera as permissões de um arquivo
    - permissões em formato octal
        - execução (x) = 1
        - escrita (w) = 2
        - leitura (r) = 4
        - some os valores para combinar permissões
        - 6 = l+w
        - 7 = l+w+x
        - 4 = r
    - conjunto de três dígitos octais
        - 1° usuário, 2° grupo, 3° outros usuários
        - 644 = usuário l+w, grupo e outros apenas r
        - 777 = todos possuem l+w+x
        - 751 = usuário l+w+x, grupo r+x, outros apenas x
    - retire premissão de escrita do `conteudo.txt` e tente editar
        ```bash
        chmod 444 conteudo.txt
        vim conteudo.txt
        ```
    - conceda permissão completa a todos os arquivos na home
        ```bash
        chown 777 *
        ```
- sudo - super do, realize uma tarefa com super privilégios
    - exige que seu usuário seja administrdor (sudoer)
    ```bash
    sudo <comando>
    ```

## Gerenciamento de pacotes

- O que são pacotes
    - pedaços de software reutilizáveis em diversos programas
    - cada pacote possui dependência de outros que usa para funcionar
    - instalar um programa significa instalar um pacote
    - instalar o pacote de um programa sifnifica instalar todas as dependências
- `apt` - gerenciador de pacotes do Ubuntu
    - instale o pacote w3m
    ```bash
    sudo apt install w3m
    ```
    - w3m é um navegador web em texto, experimente!
    ```bash
    w3m google.com
    ```
    - tab avança, shift+tab recua, enter para preencher ou navegar em links


## Como continuo?

 - Dualboot
    - Faça um backup seguro
    - Baixe a imagem da distro
        - Sugestão: Ubuntu na última versão LTS (atualmente 22.04)
    - Crie um pendriver bootavel (BalenaEtchr, UNetBootin, Rufus, etc)
        - Fuja de baixaki, superdownloads, softonic, uptown, etc!
    - Habilite o boot USB na BIOS
    - Reinicie o PC
    - Siga os passos para instalar
 - Uso como sistema principal
    - Tente usar para programar
    - Tente usar no dia-a-dia
    - Os problemas enfrentados no dia-a-dia serão o treinamento
 - Boa sorte!
 

## Referências

 - [Guia Foca Linux](https://www.guiafoca.org/)
 - [Linux - Curso em Vídeo](https://www.cursoemvideo.com/curso/linux/)
