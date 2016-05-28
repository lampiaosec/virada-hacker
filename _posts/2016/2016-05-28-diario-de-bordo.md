---
layout: post
title: "Diário de Bordo :: 27 de Maio"
date: 2016-05-27 18:00:00
categories: 
    - diario_de_bordo
    - estudos_gerais
    - ctf
tags:
    - docker
    - programação
    - ruby
comments: true
code: true
photos:
---

* content
{:toc}

![Logo do Virada Hacker]({{ site.baseurl }}/static/img/virada.png)

# Opa

Bom, essa [#ViradaHacker][virada] foi bem bacana, bem envolvente. A chuva por aqui ajudou o clima ficar mais agradável e beeem mais confortável para a gente :D

Seremos, sucintos, ok? Então, vamos ver o que rolou?! Simbora!

# Programação

Como é de praxe, um pouco de programação. Parece até que é regra, né?! Mas aqui tem isso não. Bom, o alvo inédito dessa noite foi o [Virgulino versão ruby][virgulino-ruby], haha.

## Ruby

Foi reportado para a gente, no meio da semana, um bug no Virgulino. Para seguir o padrão de um projeto minimamente organizado, abrimos uma [issue] para documentar isso. Logo depois, veio o [pr] para resolver, que você pode olhar com mais detalhes do que mudou clicando no link ai.

# Docker

Outra coisa que rolou foi que o [@gjuniioor], para facilitar o estudo de todos com segurança web, fez uma imagem Docker do DVWA, que você pode pegar os Dockerfiles no [repositório no Github][dvwa].

Para rodar essa imagem, você precisa, claro, ter o Docker instalado, e então poderá criar as imagens e depois os container:

~~~
$ docker build -t dvwa:tag .
$ docker run -d -p 80:80 -p 3306:3306 dvwa:tag
~~~

Veja bem, a palavra `tag` você vai mudar pela versão do Dockerfile que for utilizar, para ficar mais organizado. Basta entrar no diretório da versão que deseja e então rodar o comando `build` do Docker (perceba o `.` mostrando a origem do Dockerfile ;) ).

# CTF

Mas o que fez a noite mesmo foi CTF. Vocês devem saber o que é, mas caso não, basicamente, é um jogo de perguntas e respostas, que para encontrar a bendita da resposta, você geralmente passa por alguns procedimentos técnicos da área de computação, como cripto, web, exploração, estegnografia e coisas afim. Para saber mais, você pode dar uma olhada no [CTF-Br], que é uma referência disso no Brasil. ;)

# Até

mais ver! :)

## Roadsec

Ah, mas não se esquece do [Roadsec] não eim?! Vai acontecer em Salvador no dia 11 de junho, e você vai conseguir uma entrada com um cupom de desconto bacana seguindo a [página do LampiãoSec no facebook][fb], fica atento!

[virada]: {{ site.url }}{{ site.baseurl }}
[virgulino-ruby]: https://github.com/lampiaosec/virgulino-ruby
[issue]: https://github.com/lampiaosec/virgulino-ruby/issues/7
[pr]: https://github.com/lampiaosec/virgulino-ruby/pull/6
[dvwa]: https://github.com/gjuniioor/docker-dvwa
[ctf-br]: https://ctf-br.org/
[roadsec]: http://roadsec.com.br/salvador2016
[fb]: https://facebook.com/lampiaosec
