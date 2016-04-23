---
layout: post
title: "Diário de Bordo :: 22 de Abril"
date: 2016-04-23 09:00:00
categories: 
    - diario_de_bordo
    - estudos_gerais
tags:
    - gnu_linux
    - ruby
    - webdev
comments: true
code: false
photos:
---

* content
{:toc}

![Logo do Virada Hacker]({{ site.baseurl }}/static/img/virada.png)

# Opa!

Fala, galera, firmeza?!

Bom, como de prache, essa [#ViradaHacker][virada] foi bem produtiva. Nessa tivemos bastante conversa sobre engenharia de software, e tudo isso direcionado para um caso, o [Virgulino].

E claro, sempre tem aquelas conversas sobre carreira, comunidade e tudo mais que é de lei. Dúvidas importantes foram esclarecidas, mas vamos falar disso mais abaixo.

# Engenharia de software

Desenvolver um projeto de software vai muito além do que apenas escrever um código que rode. Você tem de pensar em performance, manutenibilidade, padrões para resolução de bugs e várias outras boas práticas, como documentação e uma boa estrutura para o projeto.

O [Virgulino] está sendo nosso *boi de piranha* (rs') para estudar e praticar tudo isso. E a discussão da vez coube ao assunto **Arquitetura de plugins**.

Além dessa questão sobre a arquitetura dos plugins ainda foi muito conversado sobre novas features e vista a questão de issues que estavam ultrapassadas já (acontece ;] ).

## Arquitetura de plugins

Foi estudada a questão de como funciona implementar um programa para que funcione rodando com plugins. Isso vai facilitar **DEMAIS** para quem quiser contribuir! Por quê? Explico: Simples, a pessoa que quer contribuir com uma parte do software não vai precisar entender todo seu core para poder fazer isso, basta estudar a documentação sobre a criação de plugins e fazer o seu que se adeque ao que o programa precisa.

Casos importantes disso podemos pensar no NMAP com seu NSE, que é bem mais simples e viável de se fazer. Ou ainda extensões para navegadores e módulos para o kernel. A ideia da motivação da coisa toda ainda serve.

### Mas e como funciona?

Bem, a ideia é você fazer uma interface central para o programa. Essa interface deve ser capaz de entender toda a hierarquia de diretórios dos plugins para carregar o código corretamente. Para diminuir a chance de erros dos programadores, é bom se trabalhar com a questão de classes abstratas, em que os herdeiros dessa classe irão precisar implementar determinados métodos. Métodos esses que serão o corpo do plugin, que sem ele, não funcionaria.

### Talk is cheap, show me the code!

Tranquilo! Fizemos alguns PoCs em ruby para se entender na prática. Como já tem sido estudado há um pouco tempo e conversado mais encorpadamente na [#ViradaHacker][virada], veja esse [Pull Request #71][pr] dessa semana.

E essa é justamente a ideia que estamos a implementar no [Virgulino]. O que acham? Bora submeter PR lá? hehe

## Novo layout

Atrelado à essa questão de renovação de nosso software veio a questão do nosso site. Passamos um bom tempo afiando o machado, pensando em um layout que nos agradasse mas que fosse mais amigável. Depois que foi decidido fizemos uma hackatona (na falta de um nome melhor) em que cada um ia fazendo uma parte. Isso, claro, em paralelo com o desenvolvimento do [Virgulino]. Foi lindo! Só não tem foto pois todos estavam ocupados codando algo. haha :P

Diz ai o que achou da mudança:

Antes:

![Site do LampiãoSec antes da modificação]({{ site.baseurl }}/static/img/2016/04/22/antes.png)

Depois:

![Site do LampiãoSec depois da modificação]({{ site.baseurl }}/static/img/2016/04/22/depois.png)

O [Pull Request #19](https://github.com/lampiaosec/lampiaosec.github.io/pull/19) foi o que fez toda a modificação. Então, se por alguma causa, motivo, razão ou circunstância, você quer pegar os antigo e mexer um pouco, fica a vontade! :)

# Comunidade

Como foi dito, dúvidas importantes sobre como começar a contribuir para a comunidade foram sanadas. Ou melhor dizendo, esclarecidas (afinal, ninguém tem a verdade concreta sobre nada :P ).

Podemos indicar alguns textos na internet sobre por onde começar, mas claro que falar sobre isso pessoalmente é muito mais **empolgante**!!

* [Comunidade funciona](http://phpba.com.br/comunidade-funciona/)
* [Contribuindo para projetos abertos](https://gjuniioor.github.io/blog/contribuindo-projetos-open-source/)

# Até
{:id="ate"}

No mais, até mais ver, pessoas!

Qualquer dúvida sobre algo, só comentar aqui ou entrar em contato com a gente pelo [facebook] ou [e-mail][contatos].

Flws!

[virada]: https://lampiaosec.github.io/virada-hacker/
[virgulino]: https://github.com/virgulino/
[facebook]: https://facebook.com/lampiaosec
[contatos]: https://lampiaosec.github.io/#contact
[pr]: https://github.com/lampiaosec/virgulino/pull/71
