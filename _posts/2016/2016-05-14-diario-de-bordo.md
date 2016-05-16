---
layout: post
title: "Diário de Bordo :: 13 de Maio"
date: 2016-05-14 18:00:00
categories: 
    - diario_de_bordo
    - estudos_gerais
tags:
    - c
    - programação
    - rede
comments: true
code: true
photos:
---

* content
{:toc}

![Logo do Virada Hacker]({{ site.baseurl }}/static/img/virada.png)

# Hi!

Bem, então vamos começar nosso resumo rapidinho aqui. Antes de mais nada, importante agradecer a presença de gente nova no [#ViradaHacker][virada]. É sempre bom ver novas pessoas se interessando por esse projeto bacana. Uma pena que quem apareceu não vai poder ficar por muito tempo, mas o período que o conhecemos e que tivemos (e vamos ter) contato com ele, com certeza, será de grande valia para ambos os lados. :)

# Programação

Nessa [#ViradaHacker][virada] planejamos ter uma oficina sobre um framework front end, já que uma boa parte do pessoal está começando a estudar web. Porém, contudo, entretanto, todavia, o responsável por conduzir a noite não apareceu, e sem um aviso prévio, tivemos de improvisar. Vamos ver :P

## C

Bem, no meio da semana, o [@userx] passou um simples desafio em C para quem estava começando estudar a questão de ponteiros trabalhasse mais sua mente com essa coisa toda. O desafio era o seguinte:

### Desafio

> Desafio: Implementar esse código para que ele exiba a matriz, elemento por elemento, sem usar o modo normal de indexação (eg: m[1][2]).

~~~ c
#include <stdio.h>

int
main (void) {
	int m[3][4] = {
		{1,2,3,4},
		{5,6,7,8},
		{9,10,11,12}
	};

	// desafio

	return 0;
}
~~~

A ideia para resolução aqui era utilizar aritmética de ponteiros. Claro, há várias soluções, vamos ver algumas das que foram mostradas:

> **Nota**: As soluções apresentadas abaixo consideram a utilização do gcc na versão 6.1.1

#### Solução 01

~~~ c
#include <stdio.h>

#define lin 3
#define col 4

int
main (void) {
	int m[lin][col] = {
		{1,2,3,4},
		{5,6,7,8},
		{9,10,11,12}
	};

	int *p = (int *)m;

	for (int i = 0; i < lin; i++) {
		for (int j = 0; j < col; j++)
			printf("%d ", *(p + (i * col) + j));
		printf ("\n");
	}

	return 0;
}
~~~

#### Solução 02

~~~ c
#include <stdio.h>

#define lin 3
#define col 4

int
main (void) {
	int m[lin][col] = {
		{1,2,3,4},
		{5,6,7,8},
		{9,10,11,12}
	};

	int *p = (int *)m;

	for (int i = 0; i < (lin * col); i++) {
		printf(((i+1) % col == 0) ? "%d\n" : "%d ", *(p+i));
	}

	return 0;
}
~~~

#### Solução 03

~~~ c
#include <stdio.h>

#define lin 3
#define col 4

int
main (void) {
    int m[lin][col] = {
      {  1, 2, 3, 4 },
      {  5, 6, 7, 8 },
      { 9, 10, 11, 12 },
    };

	for (int i = 0; i < (lin * col); i++)
		printf((i % col ? "%d " : "\n%d "), *(int *)m+i);

	return 0;
}
~~~

#### Solução 04

~~~ c
#include <stdio.h>

#define lin 3
#define col 4

int
main (void) {

    int m[lin][col] = {
      {  1, 2, 3, 4 },
      {  5, 6, 7, 8 },
      { 9, 10, 11, 12 },
    };

    for (int i = 0; i < lin; i++ ) {
        for (int j = 0; j < col; j++) {
            printf ("%d ", *((int *)(*(m+i))+j));
        }
        printf ("\n");
    }

	return 0;
}
~~~


> **Nota:** Sabemos que há possibilidades de melhorar o algoritmo ai, mas colocamos as respostas cruas pois pode ajudar quem está começando a estudar C ;)

Desafios desse tipo é legal para fazer a galera tentar aplicar os conceitos teóricos que aprendeu em seus estudos, portanto, recomendamos muito a prática.

# Redes

Depois de passada toda essa questão dos desafios e de algumas discussões sobre **Arch Linux vs Slackware vs Debian**, **CoffeeScript vs JavaScript**, **Node "vs" Rails** (perceba as aspas no *vs* do Node e Rails, rs'), fomos pensar em mais coisas para fazer. Após alguns devaneios, olhando umas máquinas, doações que o [RaulHC] recebeu, começamos fuçar nelas a ver o que estava funcionando. Conclusão dessa parte: HDs com badblocks foram soluções melhores, RAM com metade da capacidade foram melhores que outras, e no fim, colocamos uma distro atual para rodar em um note de 2000 :)

Mas o que isso tem a ver com redes? Simples, nesse momento, pensamos em subir uma VPN lá no [RaulHC]. Estudamos a parte de DMZ, DNS Dinâmico, Encaminhamento de portas ... Deixamos tudo isso funcionando, só faltou um servidor para ficar local com a VPN, fixo. Isso há de conseguirmos, mas a pior parte, que é realmente saber como montar a coisa toda funciona e configurar ao menos o básico, isso já foi.

Não vamos fazer um tutorial disso tudo, afinal, tem muita coisa na internet e provavelmente, nada diferenciado do que poderíamos trazer.

# Abraço!

Então, no mais, um forte abraço a todos e vamos que vamos!

[virada]: {{ site.url }}{{ site.baseurl }}
[raulhc]: http://raulhc.cc
[@userx]: https://github.com/userxgnu
