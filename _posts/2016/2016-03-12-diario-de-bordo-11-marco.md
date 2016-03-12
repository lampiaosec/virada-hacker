---
layout: post
title: "Diário de Bordo :: 11 de Março"
date: 2016-03-12 15:00:00
categories: 
    - diario de bordo
    - talks
    - estudos gerais
tags:
    - programação
    - c
    - criptografia
    - cyber war
comments: true
code: true
photos:
    - 2016/03/11/01.jpg
    - 2016/03/11/02.jpg
    - 2016/03/11/03.jpg
    - 2016/03/11/04.jpg
    - 2016/03/11/05.jpg
    - 2016/03/11/06.jpg
    - 2016/03/11/07.jpg
    - 2016/03/11/08.jpg
    - 2016/03/11/09.jpg
    - 2016/03/11/10.jpg
    - 2016/03/11/11.jpg
---

* content
{:toc}

![Logo do Virada Hacker]({{ site.baseurl }}/static/img/virada.png)

# Geral

Essa [#Virada] foi muito show! Fluida, altos papos e tudo que temos direito. 

> Tiveram caras novas por lá também! Tomara que eles não tenham se assustado tanto com o ritual de iniciação secreto e voltem nas próximas.

Como avisado em [nossa página][lampiaofacebook] no facebook, programamos duas talks nessa edição:

* Cyber War - Franklin Lira
* Criptografia - nekoone

E foram demais! Vamos lá!

## Talk :: Cyber War

Após trocarmos algumas figurinhas para conhecer o pessoal novo que chegou junto, fomos para a palestra sobre Cyber War, feita pelo Franklin Lira.

> Franklin é um cara super gente fina, tem uma carreira sólida em uma multinacional brasileira e está pendendo para o ramo da segurança da informação. Conta com algumas certificações de peso no mercado, como Scrum Master e CEH.

Na apresentação foram abordados vários assuntos interessantíssimos referentes ao assunto, como:

* Casos reais (ex. Stuxnet) de ataques
* Nações com exércitos cibernéticos montados
* O poder e utiliadade de esquadrão como esse
* Perigos eminentes
* Artifícios utilizados
* E muitos outros ...

> Assim que o Franklin subir os slides nós colocamos aqui para vocês poderem ver. Mais uma vez, assim que publicarmos essa alteração vamos postar na página. Então, curte e segue a gente no [facebook][lampiaofacebook] para ficar antenado.

Ficaram como recomendação para quem quer saber mais sobre o tema os livros:

* Guerra Cibernética: a próxima ameaça à segurança e o que fazer a respeito, Richard A. Clarke & Robert K. Knake
* Countdown to Zero Day: Stuxnet and the Launch of the World's First Digital Weapon, Kim Zetter

O primeiro fala do cenário de uma forma geral, já o segundo é bem focado em dissecar a história por trás do Stuxnet (veja no [Wikipédia][stuxnet]). 

No fim de tudo, ainda foi dado um overview de como fica o Brasil frente a esse cenário. Uma vez que temos tantas riquezas que interessam muitas nações e pouca segurança.

## Talk :: Criptografia

É um assunto muito debatido, certo? Após Edward Snowden então, esse assunto virou capa de revista! Pois é, os Cypherpunks não eram pessoas neuróticas, acaba que tinham razão.

A ideia era passar o conceito de criptografia e algumas informações/curiosidades a mais sobre o tema para então chegar ao assunto **RSA**.

Foi falado a importância do uso da criptografia no mundo de hoje e melhores formas/cifras/programas para se utilizar. Ficam algumas dicas:

Se for usar cifra simétrica:

* Uma chave por mensagem (assim diminue o risco da violação de toda a conversa)
* Busque por chaves seguras (sabe aquela de utilizar letras, números e caracteres especiais? Leve a sério!)

Se for usar cifra assimétrica:

* Opte por uma chave com um tamanho bacana (o mínimo recomendado é 2048 bits)
* CUIDADO COM SUA CHAVE PRIVADA!
* Ajude no processo de entropia na geração de seu par de chaves

> Uma recomendação que fica, independente do tipo de cifra é buscar utilizar softwares homologados, como o grande GnuPG. No [site do LampiãoSec][site] você consegue ver um link para um bom artigo sobre o GnuPG.

A apresentação já está online e você pode acessar por esse link: [https://lampiaosec.github.io/talks/Cripto/index.html](http://lampiaosec.github.io/talks/Cripto/index.html)

## Programação

Em uma conversa surgiu a indagação:

> "Como faria se o programa espera um `char` da entrada padrão e o usuário digita um `int`? Como fazer o tratamento dessa exceção uma vez que C não tem features pra isso?"

Então foi feito um processo investigativo acerca do `scanf()`, pois muita gente o utiliza sem testar seu retorno. Foi interessante, mas não era o que a galera estava realmente procurando.

Surgiu a ideia de tentar converter o que quer que o usuário tenha passado para `int`. Para isso, foi utilizada a função `atoi()`.

> `atoi()` retorna `0` se não conseguir converter. Mais informações em `man 3 atoi`.

A lógica para isso:

> Se a função retorna zero significa que o caractere passado na entrada padrão não é "*convertível*" pra `int`, sendo assim, significa que ele só poder ser um caractere especial ou letras.

Pois bem, um breve teste de mesa seria:

1. Usuário passa `1` ao programa
2. Programa consegue converter `"1"` (`char`) para `1` (`int`)
3. Sucesso!

Ou:

1. Usuário passa `a` ao programa
2. Programa não consegue converter `"a"` (`char`) para nenhum `int`
3. Erro! Mas sucesso, pois esse é o objetivo! :)

Abaixo tem um código para você testar:

~~~ C
#include <stdio.h>
#include <stdlib.h>


int check_char(char c) {
	return atoi (&c);
}

int 
main (void) {
	char c;
	scanf ("%c", &c);
	(check_char (c) == 0 ? printf ("OK!\n") : printf ("Please, type a char\n"));

	return 0;
}
~~~

# No mais ...

... agradecemos a todos que compareceram nessa [#Virada]! Nosso sinceros agradecimentos! Vocês são fod@s!!

E deixamos mais uma vez o convite a todos! É algo aberto, livre, basta chegar, conversar, ensinar, aprender, e todas essas coisas que vocês podem presumir.

Abaixo ficam algumas* fotos** do evento:

> *: **Algumas**, claro. Quem quiser ver tudo, cola com a gente! :P
>
> **: Viu? Falamos que tinhamos que melhorar isso, e olha o tanto de fotos agora! :)

[#virada]: https://lampiaosec.github.io/virada-hacker/
[lampiaofacebook]: https://facebook.com/lampiaosec
[stuxnet]: https://pt.wikipedia.org/wiki/Stuxnet
[site]: https://lampiaosec.github.io
