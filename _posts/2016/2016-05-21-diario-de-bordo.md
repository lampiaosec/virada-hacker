---
layout: post
title: "Diário de Bordo :: 20 de Maio"
date: 2016-05-20 18:00:00
categories: 
    - diario_de_bordo
    - estudos_gerais
tags:
    - dns
    - programação
    - rede
    - ruby
comments: true
code: false
photos:
---

* content
{:toc}

![Logo do Virada Hacker]({{ site.baseurl }}/static/img/virada.png)

# Oi

Oi, tudo bem? Vamos ser rápidos? Breves? Bora! Acontece rsrs' Olha, nessa [#ViradaHacker][virada] rolou alguns estudos marotos sobre coisas marotas. Vou pular essa introdução para irmos logo ao que é interessante mesmo, né?!

# Programação

Olha, parece até que é regra sempre falarmos de programação na [#ViradaHacker][virada], né?! Mas fazer o quê?! É um tema bacana, é algo que empolga o pessoal e todos curtem, então, convivemos felizes com isso (espero que todos, vai que...).

## Ruby

Dessa vez rolou o seguinte: nós fizemos o [Virgulino] como resultado de um estudo nosso sobre criptografia e com ele acabamos aprendendo também várias e várias coisas sobre os problemas que implicam em se manter um projeto, como exemplo, a questão de manter documentação, fazer um código bem estruturado para facilitar futuras manutenções, fazer um código com boa performance e que seja bem legível para alguém novo no projeto e várias dessas coisas.

Inclusive, uma das nossas vontades, era justamente fazer o [Virgulino] ser bem feito de modo que possa ser utilizado como uma API para qualquer outro programa. Como nosso alvo para PoCs, fizemos isso na versão do [virgulino-ruby]. Como forma de mostrar que o projeto está bem responsável para essa questão, o [@userx] fez, em ruby, uma GUI, simples (lembre-se: **PoC**), sem precisar alterar nada no core do projeto.

A parte dessa GUI feita você pode ver [nesse Pull Request][pr]. Portanto, faça seus testes, e qualquer coisa, entra em contato com a gente! Estamos ai para tentarmos aprender e encinar sempre o máximo possível.

# Redes

Tivemos mais coisas na noite, como por exemplo, estudos a respeito da segurança do DNS.

## Segurança em DNS

Pois bem, vocês devem lembrar que [@gjuniioor] já fez uma palestra sobre o DNS (que você pode ver sobre [clicando aqui][talk-feita]). Agora ele vai palestrar lá no [RoadSec de Aracaju][roadsec], dia 04 de junho (portanto, ESTÃO TODOS CONVIDADOS, CABRAS DA PESTE!), justamente sobre segurança em DNS. Então, como uma forma de teste e tudo mais, ele fez uma prévia dessa palestra aqui no [#ViradaHacker][virada].

> Calma, não se preocupem! Os slides vão ficar disponíveis online! Basta ficar ligado na [página no facebook][fb] e também pode assinar os feeds RSS ou Atom no [site do LampiãoSec][site], eles vão aparecer lá.

# Aviso Importante!

Ah! Em parceria com o [RoadSec], vai rolar alguns cupons de desconto para o evento em Salvador, dia 11 de junho! Então, fiquem atentos e keep hacking! :D

# Até

a próxima!

[virada]: {{ site.url }}{{ site.baseurl }}
[virgulino]: https://github.com/lampiaosec/virgulino
[virgulino-ruby]: https://github.com/lampiaosec/virgulino-ruby
[pr]: https://github.com/lampiaosec/virgulino-ruby/pull/4
[@userx]: https://github.com/userxgnu
[@gjuniioor]: https://github.com/gjuniioor
[talk-feita]: {{ site.url }}{{ site.baseurl }}/2016/02/28/pos-ultima-de-fevereiro/#talk-de-dns
[roadsec]: https://roadsec.com.br/aracaju2016
[fb]: https://facebook.com/lampiaosec
[site]: https://lampiaosec.github.io
