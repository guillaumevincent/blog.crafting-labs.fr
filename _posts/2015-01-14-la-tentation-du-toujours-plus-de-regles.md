---
layout: post
title: "La tentation du toujours plus de règles"
date: 2015-01-14 16:43:00 +0100
comments: false
categories: 
---
Un jour, un chef de projet un peu perdu me contacte :

> -- Je comprends pas, tous les indicateurs de mon projet sont au vert. Le code est couvert à plus de 90% par des tests unitaires, le sonar dit qu'on est bon. Et pourtant, l'appli est une catastrophe.

> -- Comment ça ?

> -- Non seulement elle fait mal le métier, mais en plus, elle plante régulièrement. On m'avait dit qu'avec des tests unitaires, ce genre de choses n'arrivaient plus.

> -- Montrez moi le code, je vais voir ça.


Et j'ai vu. Oui, il y avait bien des tests, un sacré paquet même. Plein de tests, mais aucun `Assert`[^1]. Donc plein de code de tests, mais qui ne vérifie rien.
Et comme une grosse partie des `Exception` étaient silencieusement rattrapées, au final, tout cela n'avait quasiment aucune utilité...

Quand j'ai raconté ça à mon chef de projet, sa réaction ne s'est pas fait attendre

> -- ah, ouais, c'est nul. Bon, ben je vais demander qu'on rajoute une règle pour vérifier qu'il y a bien des `Assert`. Et puis une pour les `Exception` et les `@SuppressWarning` aussi.[^2].

Et c'est la réaction qu'ont eu la plupart des chefs de projet et développeurs à qui j'ai raconté cette histoire : si une règle se trouve inefficace, on rajoute de nouvelles règles pour contrôler encore plus.

Sauf que ce n'est pas une solution. Pourquoi ? tout simplement parce que les développeurs de l'histoire d'origine ne savaient juste pas à quoi servaient tout ça. On leur a demandé d'avoir un certain taux de couverture, ils l'ont fait. 
Personne n'avait pris le temps de leur expliquer ni de leur apprendre ce qu'était un test, comment le rendre utile, intéressant. Comment ça pouvait les aider dans leur quotidien.
Rajoutez leurs des règles, des contraintes, il est fort à parier qu'ils trouveront un moyen de les satisfaire sans pour autant faire le taf derrière. De saboter[^3] le code, sans que cela puisse se voir de ceux qui surveillent et créer les règles.

Par contre, pour le développeur qui sait faire des tests, écrire du code de qualité, ces règles le contraignent inutilement. Cela rendra son travail plus compliqué au quotidien car il devra satisfaire tout un paquet de règles qui n'ont de sens que pour ceux qui les enfreignent.

### Ok, si les règles ça ne marche pas, c'est quoi la solution ?

La solution est simple. Il suffit juste de leur apprendre. Expliquer à quoi ça sert, comment on fait
La plupart des gens qui font des applications toutes moisies ne le font pas volontairement. C'est juste que personne n'a jamais pris le temps de leur montrer qu'on pouvait faire autrement. Qu'il était possible de faire les choses bien, en travaillant ensemble, en réfléchissant ''pour'' le système et non ''contre''.

C'est sur, expliquer, éduquer, enseigner, c'est plus long, plus compliqué et ça demande plus de courage que de rajouter de nouvelles règles pour contraindre. Mais au final, c'est bien plus efficace et les effets durent sur le long terme.


__Remarque__ : toute tentative de rapprochement de cette histoire avec l'idée de rajouter de nouvelles lois liberticides suite à l'échec des précédentes au lieu d'aller à la source du problème par l'éducation et la pédagogie est fortement encouragée.


[^1]: le truc dans lequel on va effectivement vérifier que le résultat est bien celui qu'on attendait
[^2]: parce que c'est ce qui étaient utilisés pour masquer les problèmes relevés par `checkstyle` et `pmd`
[^3]: probablement involontairement
