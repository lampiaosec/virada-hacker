---
layout: post
title: "Diário de Bordo :: 06 de Maio"
date: 2016-05-07 02:00:00
categories: 
    - diario_de_bordo
    - estudos_gerais
tags:
    - c
    - criptografia
    - programação
comments: true
code: true
photos:
---

* content
{:toc}

![Logo do Virada Hacker]({{ site.baseurl }}/static/img/virada.png)

# Opa

Falaê, galerinha! Bem, essa [#ViradaHacker][virada] foi muito mais diversão que muitas das anteriores relatadas aqui. Tivemos a presença de algumas ladies do [Raul Hacker Club][raul] para abrilhantar mais a noite e risadas não faltaram. 

Mas vamos lá que isso não seria uma "Virada Hacker" se não tivesse ao menos um estudosinho que seja :P

# Criptografia

Estamos num momento de estudar um pouco mais de criptografia para podermos implementar o [Virgulino] (e [Virgulino-ruby]). Vamos ver o que rolou.

## RSA

Nós demos uma rápida olhada sobre como é o funcionamento do algoritmo RSA. Pensamos em algumas formas de fazê-lo funcionar e coisas assim. Mas prezamos pela ideia de afiar o machado 70% do tempo para gastar 15% derrubando a árvore e 15% tomando café e assistindo seriados.

Ainda temos de estudar mais sobre ele, para entender melhor e fazer um bom proveito. E olha, antes de mais nada, já fica aqui o convite, claro, para se você quiser, venha ajudar a gente! Só mandar um **Pull Request**! :D

# Programação
{:id="programacao"}

O [@gjuniioor][gjuniioor] está estudando uma linguagem com menos abstração, a digníssima C, então, em todo processo de estudos rola aquela dúvida sacana. Então ele aproveita o [@userx][userx] para saná-las na [#ViradaHacker][virada]. Vamos ver qual foi a da vez:

## C

Siga o pensamento: usando ponteiro, posso percorrer toda uma string até chegar em seu final (`\0`), certo? Porém como poderia fazer isso com um vetor de inteiros, por exemplo?

Esse seria uma das questões que o C++ se interessou em tentar resolver. Como eles fizeram? Usando o conceito de Fat Pointer. Não vale falarmos muito disso aqui pois é fácil de se encontrar informações sobre. Para isso, tu pode dar uma olhada [aqui][fp].

Como as discussões foram mais coisas teóricas, para entendimento do funcionamento de certos conceitos, talvez não valha nos alongarmos tanto aqui. Mas se precisar de mais esclarecimentos, pode entrar em contato conosco! ;)

# Flw

Bem, pessoal! Fomos curtos mais uma vez, afinal, isso aqui é um resumo, uma listagem dos tópicos mais discutidos da noite, não uma transcrição do que foi dito, só pra lembrar caso precise. ;)

[virada]: {{ site.url }}{{ site.baseurl }}
[raul]: http://raulhc.cc
[virgulino]: https://github.com/lampiaosec/virgulino
[virgulino-ruby]: https://github.com/lampiaosec/virgulino-ruby
[gjuniioor]: https://github.com/gjuniioor
[userx]: https://github.com/userxgnu
[fp]: https://en.wikipedia.org/wiki/Function_pointer
