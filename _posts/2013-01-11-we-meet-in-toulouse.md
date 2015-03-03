---
layout: post
title: "We Meet In Toulouse"
date: 2013-01-11 16:06:00 +0100
comments: false
categories: 
- "agenda"
- "conférence"
- "it"
- "toulouse"
---
La communauté IT à Toulouse est fabuleuse, diversifiée et très active. JUG, Toulouse JS, Apéro Web, Apéro Ruby, AFUP Toulouse, Meetup UX, et j'en oublie évidemment.
C'est formidable, mais dès fois, pas facile de se repérer, de savoir où aller quand, et de caler ses dates pour les autres orgas.


# We Meet In Toulouse
Donc, on lance [We Meet In Toulouse](http://www.wemeetintoulouse.net) un calendrier qui recense les événements.

# Ajouter un événement
Pour l'instant, le processus est manuel. Si vous êtes organisateur régulier d'événements sur Toulouse, il suffit de demander gentillement à avoir accès en écriture au calendrier à [Antoine](http://twitter.com/avernois) ou [Nicolas](http://twitter.com/ndeverge). Sinon, un petit message avec les bonnes infos, et on le rajoutera (nom, lieu, lien vers descriptif et inscription).

# Les détails

## La génèse
En fait, ça fait une éternité qu'on parle de lancer un site pour recenser tout ce qui se passe. Au début de l'été, on a même commencé un truc qui allait déchirer tout. Et puis on a un peu trop procrastiner et rien n'est sorti. 
Le sujet est revenu hier matin au ''code and coffee'', et avec Nicolas on a décidé de s'y mettre sérieusement en faisant simple : un bon vieux calendrier google partagé[^1].

## La technique
Il s'agit d'un bon vieux calendrier google partagé enrobé dans une petite appli rails[^2], le tout hébergé sur [heroku](http://www.heroku.com). 

## Contribuer
Le code est dispo sur [mon github](https://github.com/avernois/wmit-lite). Si vous voulez contribuer, proposer des fonctionnalités, soumettre des idées, c'est via le repo que ça se passe :)


[^1]: on a commencé en essayant avec les communautés google+, mais bien trop restrictive
[^2]: totalement overkill puiqu'elle ne sert que des pages statiques. Mais c'est ce que je sais faire :)
