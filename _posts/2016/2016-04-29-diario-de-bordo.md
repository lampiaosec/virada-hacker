---
layout: post
title: "Diário de Bordo :: 29 de Abril"
date: 2016-04-30 19:00:00
categories: 
    - diario_de_bordo
    - estudos_gerais
tags:
    - c
    - programação
comments: true
code: true
photos:
---

* content
{:toc}

![Logo do Virada Hacker]({{ site.baseurl }}/static/img/virada.png)

# Falae

Fala, pessoal, tudo certo?! Vamos corridos aqui para um diário de bordo simples e rápido sobre o que rolou na [#ViradaHacker][virada] de 29 de abril.

Vejamos, o que é sempre presente é aquela velha conversa sobre várias coisas como métodos de estudos e tudo mais. Isso (se não nos escapou) sempre retratamos aqui nos diários de bordo, então, tranquilo, certo?

Ah, nessa [#ViradaHacker][virada] também surgiu a presença de um novo cabra lá. Na verdade, foi para conhecer o [RaulHC] e demos as boas vindas. Afinal, o convite está aberto para todos que desejarem conhecer/colaborar/fazer parte do [Raul Hacker Club][raulhc].

Sem mais delongas, vamos ser breves.

# Programação

Na semana passada (pode ver no [Diário de Bordo do dia 22 de Abril][diario]) falamos muito sobre programação. Envolveu estudos sobre a questão de arquitura de plugins a ser utilizada no [Virgulino versão Ruby][virgulinoruby]. Agora precisamos estudar e discutir sobre isso com a versão em C. Mas antes de mais nada, demos uma olhada em todo o código atual para entender melhor, revisar e ver como melhorar sua estrutura.

Bem, como não foi pensado muito sobre, não há como falarmos, mas olha, como o assunto não é tão simples, quem puder ajudar, sinta-se convidado! Pode entrar em contato com a gente pelo [facebook], por comentários aqui ou veja mais formas no [site do LampiãoSec][lampiao].

## C

Conforme íamos revisando sobre o código o membro do LampiãoSec [@userx][userx] ia passando algumas "curiosidades" sobre coisas do C. Falar aqui do máximo que lembro nesse momento:

### For no C11

Ele mostrou umas features relativamente novas no C, por exemplo, a questão do `for`. Antes, teríamos de fazer algo assim:

~~~ c
int i;
for (i = 0; i < 5; i++)
	printf ("%d\n", i);
~~~

Certo? Pois é, mas agora, podemos fazer a declaração da variável já dentro do `for`, veja:

~~~ c
for (int i = 0; i < 5; i++)
	printf("%d\n", i);
~~~

Bacana, não é?

### Struct Initialization

Outra coisa foi a questão da inicialização de uma `struct`. Vamos entender melhor: ao criar uma `struct` podemos já inicializá-la com valores, e isso é bacana, por exemplo, para retorno de funções. Veja um exemplo simples:

~~~ c
typedef struct _pessoa {
	int idade;
	char nome[100];
} pessoa;

pessoa cangaceiro = {35, "Virgulino"};

printf("%s\n", cangaceiro.nome);
~~~

Bem simples, tranquilo? Então, digamos que por algum motivo há uma função que queremos o retorno dela um tipo `pessoa`. Pois bem, dá para fazer dessa mesma forma:

~~~ c
pessoa 
exemplo (void) {
	return (pessoa){35, "Virgulino"};
}
~~~

Legal, eim? Pois bem, basta adaptar as necessidades que tiver e pronto. :)

# Flw

Bem, falei que ia ser rápido hoje, afinal, difícil transcrever tudo que rola, mas um resumo é tranquilo. :)

Mas olha, fala com a gente para trocarmos figurinhas.

Até a próxima!

[virada]: https://lampiaosec.github.io/virada-hacker/
[raulhc]: http://raulhc.cc
[diario]: {{ site.baseurl }}/2016/04/23/diario-de-bordo/
[virgulinoruby]: https://github.com/virgulino-ruby/
[facebook]: https://facebook.com/lampiaosec
[contatos]: https://lampiaosec.github.io/#contact
[userx]: https://userxgnu.github.io
