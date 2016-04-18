---
layout: post
title: "Diário de Bordo :: 15 de Abril"
date: 2016-04-15 12:00:00
categories: 
    - diario_de_bordo
    - estudos_gerais
    - tips_and_tricks
tags:
    - rede
    - gnu_linux
    - pentest
comments: true
code: true
photos:
---

* content
{:toc}

![Logo do Virada Hacker]({{ site.baseurl }}/static/img/virada.png)

# Falaê		{#falae}

Antes de mais nada, vale informar que essa [#ViradaHacker][virada] contou com pouca gente, mas afinal, qualidade importa em que? Contanto que não seja em quantidade de memória que o browser teima em usar ou em quantidade de pacote que algum FDP insiste em enviar para meus servidores, de nada importa! :)

Então, sigamos.

# Tips and Tricks

## Desativar teclado interno de notebook

O título já é bem descritivo, mas vamos ver algumas questões que fizeram a gente precisar disso:

### Problema

Estávamos precisando de um outro computador com placa de rede à cabo para fazer alguns testes. Rodamos o [RaulHC] todo e encontramos um notebook um pouco antigo, mas que poderia servir nosso propósito. Só para se ter uma ideia, o notebook que encontramos ainda tinha USB 1.0 e entrada para linha telefônica.

Demos o boot na máquina mas ela estava sem sistema. Tentamos rodar um LiveUSB, mas como já dito, a entrada antiga não deixou. Por sorte encontramos um LiveCD com Ubuntu 12.04. E pasmem, o notebook sucateado rodou Unity quase que tranquilo. Bem, só precisávamos do terminal e do X para alguns screenshots, mas não foi algo de arrancar cabelos.

Mas, ao usar o terminal, o teclado do notebook sempre vinha com letras aleatórias.

### Solução		{#solucao}

Encontramos um teclado USB por lá. Fizemos uma limpeza, algumas mexidas aqui e outras ali, e o notebook o aceitou numa boa. Já dava para digitar, só precisava parar a zorra do teclado do notebook.

Então, fomos pesquisar por isso. Só encontrávamos soluções para configurar o Grub. Isso não funcionaria para a gente uma vez que estávamos rodando um sistema Live. Mas então tomamos conhecimento de um utilitário do X: `xinput`.

### How 2

Esse `xinput` serve para configurar os dispositivos de entrada no X. E como precisávamos utilizar a parte gráfica para alguns screenshots, servia para a gente.

Agora o passo a passo é rápido:

~~~
$ xinput list
⎣ Virtual core keyboard                   	id=3	[master keyboard (2)]
 ↳ AT Translated Set 2 keyboard            	id=11	[slave  keyboard (3)]
~~~

> Alguns dados foram tirados do output pois são desnecessários para o entendimento.

Vai mostrar uma lista dos dispositivos de entrada. Poderá ver que tem uma seção chamada `Virtual core keyboard` direcionada à parte de entrada de dados dessa maneira. E ligado a ela tem um dispotivo `AT Translated Set 2 keyboard`. Esse é o teclado interno do notebook.

O que vamos precisar saber para desativer é o `id`. E para reativar, vamos precisar do `id` e do dispotivo *master* dele. Note que a terceira coluna informa que ele é um *slave* e mostra um identificador, que é o que nos importa para reativar.

#### Desativar

Basta um comando:

~~~
$ xinput float 11
~~~

#### Reativar

Também é apenas um comando simples:

~~~
$ xinput reattach 11 3
~~~

# Gnu/Linux

Aproveitando a Hype do [#flisol][flisol], um cabra que cola no [#ViradaHacker][virada] queria formatar sua máquina, colocando agora o ArchLinux. Seguindo a ideia de mostrar como pescar e não entregar o peixe, [@gjuniioor][gjuniioor] passou dois guias que ele poderia usar feito por ele mesmo:

* [Instalação do ArchLinux com LVM e Luks](https://gjuniioor.github.io/blog/archlinux-lvm-luks/)
* [Pós Instalação do ArchLinux](https://gjuniioor.github.io/blog/pos-instalacao-archlinux/)

Também fez uma breve explicação sobre alguns pontos fortes de sua preferência ao ArchLinux sobre outras distribuições e junto a isso, falou um pouco sobre a arquitetura de diretórios do Linux e uns pontos fortes que ajudam, por exemplo, na segurança.

> Todo esse material pode ser encontrado rapidinho na internet, então reproduzir aqui poderia ser ruim. Mas qualquer coisa, comenta aqui ou na [págna do LampiãoSec][facebook] que mudamos nas próximas.

# Pentest

Encontro de profissionais (ou curiosos) de uma determinada área sempre gera muito papo interessante. É o caso de toda [#ViradaHacker][virada]. Nesse, um dos pontos importantes foi a questão de um pentest. Algumas dúvidas sobre como ele é feito, quais caminhos tomar e coisas correlatas, foram tiradas. 

[@gjuniioor][gjuniioor] explicou essas dúvidas fazendo a junção e correlação de várias metodologias de pentests. Por exemplo, juntou a ideia da necessidade de limpar os logs e de manter acesso, coisa que não é todo pentest que precisa. Também tirou a ideia de que pentest é algo linear, e mostrou que na verdade é um ciclo, sendo que várias vezes, após chegar a certo ponto, é preciso voltar à "fase inicial" para continuar. Fazendo isso, explicou algo como se fosse um pentest *completão*.

Em resumo, a lista que ele fez dos passos para a explicação foi a seguinte:

1. Coleta de informações
	* Footprint
	* Fingerprint
2. Reconhecimento
3. Análise de vulnerabilidade
4. Exploração
5. Manutenção de acesso
6. Escalação de privilégio
7. Limpeza de logs (+ uso de técnicas anti-forense desde início do ciclo)
8. Geração de relatórios

> É importante enxergar que a ideia do item 7 foi feita para mostrar a questão de um pentest com o fim de testar a equipe de resposta à incidentes, não para algum tipo de ato criminoso.

# Redes

## Prática com rede cabeada		{#pratica-com-rede-cabeada}

[@gjuniioor][gjuniioor] aproveitou seus estudos sobre redes de computadores e levou algumas atividades para serem feitas. Como exemplo, pode-se citar:

* crimpagem de cabos padrão EIA 568A;
* crimpagem de cabos padrão EIA 568B;
* crimpagem de cabos cross-over para redes 10 e 100 megabits;
* crimpagem de cabos cross-over para redes 1000 megabits;
* teste dos programas `ethtool` e `mii-tool`;

> Novamente, talvez não valha a pena descrevermos cada um desses itens aqui por conta do material pela internet. Mas caso queira algo com nossas criativas palavras, basta comentar.

## Sniff de Fibra Ótica		{#sniff-de-fibra-otica}

[@gjuniioor][gjuniioor] trouxe também uma rápida explicação sobre o funcionamento de redes com fribra ótica e mostrou relatos de uma pesquisa que ele fez sobre uma ideia que surgiu logo quando estava estudando sobre isso: **sniffing de redes com fibra ótica**.

Pela explicação dele, seria algo indetectável pelos usuários da rede, a não ser que percorrecem todo o cabeamento em busca de intrusos. Veja bem:

Quando o sniff de uma rede "normal" é feita, todo o tráfego é capturado pelo computador do atacante. Se ele for capturar algo de uma rede cabeada de par trançado, por exemplo, terá que colocar um dispositivo para que todos os dados passem por ele e depois continue seu caminho normal. Isso gera uma queda da velocidade da rede e algum usuário poderia detectar o intruso.

Diferente de se for feito em fibra ótica. Esse cabo utiliza de transmissões de feixe de luz infravermelho, algo que é invisível ao olho humano, mas pode ser visto por certos dispositivos (a câmera de um celular, por exemplo, pode ver certa faixas que nós não podemos). Então, o que seria feito? Seria colocado um dispositivo capaz de ver esse infravermelho passar e com isso todo o tráfego que é feito sem criptografia estaria agora nas mãos do atacante. Isso torna o ataque indetectável pelo fato de que a rede vai continuar funcionando perfeitamente. O atacante não vai precisar se intrometer no meio dos cabos, apenas ficar de fora pegando o sinal.

Após algumas pesquisas foi encontrado um vídeo do Kevin Mitnick mostrando esse ataque. O vídeo pode ser acessado através [desse link][video].

# Até mais		{#ate-mais}

... e obrigado pelos peixes. Ficamos por aqui, com mais esse relato de um ótimo encontro. Pessoal, esperamos vocês na próxima!

Vlw, flw!



[virada]: https://lampiaosec.github.io/virada-hacker/
[raulhc]: http://raulhc.cc
[flisol]: http://www.flisol.info/
[gjuniioor]: https://gjuniioor.github.io
[facebook]: https://facebook.com/lampiaosec
[video]: https://www.dropbox.com/s/fexmecnnb6gg6y6/KevinMitnick_EmailHack.mp4?dl=0
