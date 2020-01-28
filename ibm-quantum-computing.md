---
description: Mardi 28 janvier 2020
---

# IBM Quantum Computing

## State of the art \(harware and software\)

Quantum computing = basé sur la physique quantique, années 90 pour les ordinateur

1970 naissance de la théorie de l'information quantique

1996 critères de construction d'un ordi quantique \(IBM\)

2007 premier Qubit pour IBM

2016 disponibilité dans le cloud \(IBM\) --&gt; ibm q network



But d'ici quelques années est de montrer l'utilité de l'info quantique dans le cas de CERTAINS problème qui seront résoluts plus rapidement avec des algos quantiques. D'ici là on sait que ce ne sera pas répandu, on veut pouvoir identifier les applications/problèmes qui sont concernés.



La base est le QUBIT 

Contrairement au bit classique - 0 ou 1, seulement deux états possible

le qbit est l'unité de base et peut être dans un état compris entre 0 et 1 --&gt; "infinité" d'états possibles AVANTAGE principal

--&gt; qbit : superpostion and entanglement=supposons deux bits classiques si je mesure celui de droite je ne peux pas déduire la valeur de celui de gauche. Au contraire avec les qbit, je peux déduire l'état d'un bit selon ses voisins? les états sont reliés d'une certaine façon

we will apply to te qbit some quantum gates



On envoit des signaux aux qbits pour manipuler la superpostion et l'entaglement.  le système est refroidit à 0.02°Kelvin , c'est une nécessité pour que le système agisse comme un ordinateur quantique.



le but d'imb est de dévlopper du vrai hardware. celui-ci est mis à disposition depuis le cloud.

L'utilisateur developpe ses algorithme et les envoie pour une "compulation" en signaux qui seront utilisés pour manipuler les qbits.

U ordi quantique ne fonctionne pas seul!! il est toujours accompagné d'un ordi classique qui permet la traduction des algos en signaux, qui permet d'avoir des algos plus performants en quantique



Quantum Volume = capacité de mesurer le gain en performance obtenu lorsqu'on augmente le nombre de qbits,

IBM s'attend à doubler l'usage chaque année, pas le nombre de qbits. **Ce n'est pas le nombre de qbits qui détermine les performances mais l'usage qu'on en fait.**

**LE quantum volum**e est définit par différents critères techniques sur lesquels ils faut jouer pour gagner en performances \(-&gt; plus compliqué que en ordi classique\)

Un **aspect critique est la topologie**=interconnexions des qbits



Point de vue software - comment le programmer

depuis leur interface cloud, QISKIT SOFTWAARE STACK programme dIBM pour programmer, proposer es building blocks disponibles gratuitemtn

* AQUA -&gt; building block, algos et applications \(chemistry, finance, ai, optimization\) ensemble de algo quantiques prêts à l'emploi.
* AER
* IGNIS
* TERRA

on construit un "quantum circuit" en appliquant des portes aux qbits 

Actuellement de nombreuses banques travaillent sur l'informatique quantique

## Applications domains and use case

un ordi quantique a pour but de répondre à certains problèmes, ex:

* les problèmes pour lesquelles la **complexité est exponentielle**

avec n qbits on peut obtenir 2\*\*n etats possibles



## IBM Q network

le but est de construire un réseau de partenaires \(etudiants, institutions, ...\)

accéléré la recherche en info quantique

développer des applications commerciales



