---
layout: post
title: "Diário de Bordo :: 1° de Abril"
date: 2016-04-02 07:00:00
categories: 
    - diario_de_bordo
    - oficinas
    - estudos_gerais
    - cine_hacker
    - tips_and_tricks
tags:
    - programação
    - low_level
    - assembly
comments: true
code: true
photos:
    - 2016/04/01/01.jpg
    - 2016/04/01/02.jpg
    - 2016/04/01/03.jpg
    - 2016/04/01/04.jpg
    - 2016/04/01/05.jpg
    - 2016/04/01/06.jpg
    - 2016/04/01/07.jpg
---

* content
{:toc}

![Logo do Virada Hacker]({{ site.baseurl }}/static/img/virada.png)

# Olá!

Opa, pessoal! Tudo tranquilo?

Pois bem, depois de duas semanas de folga nós voltamos com muito gás com o [#ViradaHacker](virada) e foi show demais! (se bem que há um tempo só vem melhorando, ó)

Nessa houveram algumas atividades marotas e ocorreram tudo certo. Vamos a um breve resumo da coisa toda:

# Aviso

## Pwn2Win

Um tempo atrás anunciamos que semana passada iria rolar o jogo Pwn2Win, que é um CTF bem bacana. Estava tudo programado para jogarmos na edição do [#ViradaHacker][virada], mas infelizmente algumas coisas desandaram e alguns membros não poderam participar. 

Portanto, fica aqui nosso sincero arrependimento por isso e saudamos toda a galera que jogou e fez uma competição massa demais!! **Vocês são f0d4s!!**

# Oficina :: Low Level

## Introdução à Assembly x86_64

Essa oficina foi feita pelo [User_X][x], co-fundador do [LampiãoSec][lampiao] e nosso *low level boy*, e nela foi dada uma introdução à assembly na arquitetura 64 bits. Com isso, foi explicado também várias questões e termos do mundo low level, como o conceito de *stack*, *stack frame*, *base pointer* e alguns outros ... Com tudo isso, ficou muito claro o que realmente acontece em alguns ataques como *buffer overflow*, *stack overflow* ou alguns bugs, como o *segmentation fault*.

> Não houveram slides, o conteúdo mostrado seguiu sendo por tabelas de referência da linguagem e alguns mapas mentais para facilitar o entendimento. Será feito qualquer ajuste necessário e então subiremos os materiais aqui. Se por algum motivo demorar e tiver interesse, basta cobrar, seja comentando aqui no post ou na [página no facebook][facebook].

Mas caso queira já ter um gostinho, olha como ficou o quadro usado para algumas explicações:

<center><img alt="Quadro com explicações sobre low level" src="{{ site.baseurl }}/static/img/2016/04/01/lousa.jpg" width="50%"></center>

# Cine Hacker

Depois da oficina de low level queimar bastante neurônios da galera e nos empanzinarmos de comida bateu aquela preguiça que é de praxe e todos vocês devem conhecer. Isso é algo bastante comum e um tempo atrás, para contornar isso, pensamos na volta do **Cine Hacker**!

## O que é

Mas que diabos é **Cine Hacker**?

Começou na [#ViradaHacker][virada] que por diversão a galera colocava para exibir filmes nas paredes do prédio ao lado. E por ser algo bem diferente chamava bastante atenção do pessoal que estava por aqui na região. Então decidimos voltar com isso. Mas por alguns motivos, fizemos algo mais ameno e só pro pessoal da [#ViradaHacker][virada] mesmo.

O que foi/será feito então? Exibimos e vamos começar exibir, nesses momentos de "improdutividade", algumas obras cinematográficas que tenham relação com a nossa querida área. Como vai ter uma galera curiosa assistindo junta, a troca de figurinhas vai ser demais!

## Edição da noite

E foi o que realmente aconteceu! Nessa noite nós exibimos o filme **The Fifth Estate (O Quinto Poder)**, indicação do [User_X][x]. É um filme que conta um pouco da história do Wikileaks e do Julian Assange (mesmo que de forma controvérsia).

Conversamos várias coisas sobre os fatos que aconteceram, a forma de política de alguns países e demais coisas que acabaram por serem abordadas. Para dar o gostinho de querer assistir também, fica aqui a página no [IMDB](http://www.imdb.com/title/tt1837703/) do filme e o trailer:

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/JV7S888zYm0" frameborder="0" allowfullscreen></iframe></center>

# Tips and Tricks

E depois de acabado as atrações principais (leia-se a oficina e cine hacker) as conversas e trocas de figurinhas que rolam são sensacionais, e com elas trazemos coisas que acabamos aprendendo por ai.

## Site para estudos

Uma delas foi um site muito bacana, que um dos co-fundadores do [LampiãoSec][lampiao], o [gjuniioor], mostrou, com um conteúdo bem organizado e ótimo para o estudo em segurança, que é o:

* [pwnwiki.io](http://pwnwiki.io)

Nele há várias dicas e textos sobre várias coisas, como *pivoting*, *privilege escalation* e várias outras coisas. Vale a pena dar uma olhada e pôr nos favoritos! :P

## Ver vídeo privado do Vimeo localmente

O [gjuniioor] também relatou que recentemente ele estava com a seguinte problemática: precisava mostrar um vídeo para um amigo, mas esse vídeo estava hospedado no Vimeo e com as configurações de privacidade para serem exibidas apenas em um determinado site.

E depois ele apresentou a solução que encontrou: "então vamos dizer ao Vimeo que meu computador é o site que eles querem". Veja como pode ser feito:

### Primeiro passo

Criar um servidor web em sua máquina. Isso pode ser feito de diversas maneiras e a que ele prefiriu pela velocidade da coisa foi utilizando um módulo do python:

~~~
$ sudo python -m http.server --bind seu_ip 80
~~~

Algumas observações sobre o comando:

* O `seu_ip` você pode conseguir de várias formas, uma delas é com o comando `ip add`
* O `sudo` foi só utilizado para que rode bem na porta 80, facilitando qualquer configuração extra que precisasse fazer

### Segundo passo

Criar dentro do servidor uma página que mostre o vídeo. Para isso você pode clonar a página original ou pode simplesmente inserir o `iframe` que o Vimeo pede, que foi como ele fez:

~~~ html
<iframe style="width: 100%; height: 571px;" allowfullscreen="" src="https://player.vimeo.com/video/ID_do_video" frameborder="0"></iframe> 
~~~

> **OBS:** Lembre-se de trocar o `ID_do_video` pelo ID que o Vimeo atribui ao vídeo, ok? Ok.

### Terceiro passo

Agora você vai criar um registro DNS simples dizendo que sua máquina responde as consultas para determinado domínio. Isso pode ser feito envenenando o cache DNS, ou pode montar um servidor DNS para isso, mas o intuito aqui é facilidade e ser mais rápido na hora de fazer a coisa toda, portanto, ele optou por criar a entrada no próprio `/etc/hosts`:

~~~
$ sudo echo -e "seu_ip \t dominio_permitido \t dominio_permitido" >> /etc/hosts
~~~

Breves observações também:

* Lembre de trocar o `seu_ip` pelo IP da máquina que você criou o servidor web previamente
* O `dominio_permitido` se trata do domínio que o Vimeo aceita que o vídeo seja mostrado
* Caso na verdade seja um subdomínio, você coloca o subdomínio na primeira aparição de `dominio_permitido` e na segunda põe o domínio simples mesmo

> Quer entender melhor essa questão de DNS? Pois bem, lembra que um tempo atrás, numa [#ViradaHacker][virada] rolou uma palestra sobre isso? Ela está disponível online para assistir já! Olha aqui: http://gjuniioor.github.io/talks/dns-o-que-voce-precisa-saber/

### Enjoy

Depois de todos esses passos seguidos, só lhe resta apreciar o vídeo que antes era privado mas agora você conseguiu reproduzir de forma simples! :P

## Transferência de arquivos com Netcat

O [gjuniioor] veio cheio de coisa nessa edição, eim?! Pois bem, trouxe mais essa.

Ele reclamou que ao utilizar o netcat para transferir arquivos sempre fazia do modelo convencional:

~~~
$ cat arquivo | nc -l -p 8000 # servidor enviando arquivo
$ nc localhost 8000 > arquivo_recebido # cliente recebendo arquivo
~~~

E com isso não poderia saber quando que o arquivo já terminou de ser transferido para que pudesse finalizar a conexão. A não ser que ficasse analisando o final do arquivo recebido sempre, mas isso seria chato.

Solução: ele resolveu dar uma olhada no `--help` do `netcat` e viu que tem uma opção que poderia servir:

~~~
-c, --close                close connection on EOF from stdin
~~~

Então ele resolveu testar, só precisava adicionar uma opção a quem estava enviando o arquivo, ficando assim:

~~~
$ cat arquivo | nc -l -c -p 8000 # servidor enviando arquivo
$ nc localhost 8000 > arquivo_recebido
~~~

E com isso solucionou o problema, pois no momento em que o `cat` do arquivo terminar no `stdin` (aparecer o sinal de end of file - EOF) o servidor vai fechar a conexão. Logo, tanto cliente como servidor saberá que a transição foi feita.

Boa dica, não?!

# Finalização

Pois é, galerinha! Essa [#ViradaHacker][virada] foi repleta de coisa bacana. Aprendemos muito uns com os outros e nos esforçamos para colocar online e ajudar quem está de longe. Então se esforça um pouquinho e tenta dar uma força, pode ser de várias maneiras:

* Compartilha esse post nas redes sociais (já tem os botões ai embaixo, então só clicar e pronto, simples né?!)
* Curte e convida seus amigos para curtir a [página do LampiãoSec][facebook] e do [Raul Hacker Club][raul] no facebook
* Dá uma olhada no [site do Raul Hacker Club][siteraul] e vê se pode ajudar de alguma forma

No mais, estamos por perto e **KEEP HACKING**!!

[virada]: https://lampiaosec.github.io/virada-hacker/
[facebook]: https://facebook.com/lampiaosec
[lampiao]: https://lampiaosec.github.io
[x]: https://userxgnu.github.io/
[gjuniioor]: https://gjuniioor.github.io
[raul]: https://facebook.com/raulhackerclub
[siteraul]: http://raulhc.cc/Doc/ComoParticipar
