---
layout: post
title: "15 juin 2010 -- JUG Toulouse"
date: 2010-06-20 21:34:00 +0100
comments: false
categories: 
- "brms"
- "java"
- "jug"
- "rest"
- "toulouse"
---
Mardi dernier avait lieu la cinquième soirée du JUG Toulouse. À vue de nez, une grosse trentaine de personnes étaient présentes pour les deux présentations du jour. Au programme, du REST et des moteurs de règles.


Gaël Blondelle a commencé la soirée par parler un peu du JUG.  Il a évoqué le souhait de renforcer le petit noyau de base et organisé plus d'évènement. L'idée de coding dojo ainsi qu'un rapprochement avec la [sigmat](http://www.sigmat.fr) est revenu à l'ordre du jour... À suivre :)

Ensuite, les choses sérieuses ont commencées.

## Service web et architecture RESTful par Nicolas Zozol.
Nicolas commence par une présentation rapide de REST pour REpresentational State Transfert. REST c'est avant tout un ensemble de pratiques pour la conception d'application web se basant sur le fonctionnement du protocole de communication du web, à savoir HTTP.
Ces bonnes pratiques sont :

* Tout est ressource, toute ressources est URI
* CRUD : Create, Read, Update, Delete, qui devient PUT, GET, POST et DELETE en HTTP.
* Stateless : sans états. En fait c'est ServerSessionLess : au revoir les sessions server
* Connectivité

Ensuite, il fait quelque rappelle sur le protocole HTTP et les URI, pour montrer à quel point REST leur doit tout :)

L'intérêt visible de REST, c'est la lisibiité des URLs. Le tout URI implique de pouvoir accéder aux objets manipulés via une URL qui décrit le chemin d'accès. Ça fait des URLs dont on comprend ce qu'elle contiennent en les lisant.

Un autre intérêt c'est son coté stateless. Déjà, parce que la base du web est basé sur ce principe et que les sessions serveurs sont (et là c'est mon avis) une perversion de la nature même du réseau. L'avantage du stateless, c'est qu'une url donne toujours l'accès à la même page, et que toutes les infos pour y accéder sont contenus dans l'uri. Idéal pour les bookmarks ou l'échange de lien.
Deuxième effet kiss cool, le stateless est bien pour le buzzword du moment qu'est le cloud computing. Pas de session serveur fait qu'on se fiche complètement de qui traite la requête du moment qu'il a accès à la source des données. Parfait pour un environnement dans les nuages.

En apparence très simple, le REST impose beaucoup au niveau de l'architecture même de l'appli, tout en facilitant pas mal de chose assez sympatique au niveau du concept objet enttre autres.
L'une des contraintes, c'est l'utilisation parcimonieuse d'ajax. En effet, le tout ajax, comme le fait GWT est incompatible avec REST puisqu'il n'y qu'une unique URL (les pages étant partiellement modifiées via des appels ajax sans rechargement complet). Cela n'empêche pas pour autant l'utilsation d'ajax, mais il faudra le faire de façon parcimonieuse pour ne pas déroger à la règle du tout est ressource, tout est URI.

Enfin, Nicolas nous parle de RESTful, un framework java pour faire du REST et uniquement.

C'était une belle présentation, Nicolas maitrise son sujet et les nombreux exemples qui ont ponctué sa présentation l'a rendu très agréable. Je pense que son message est bien passé : REST c'est lisible, c'est simple, ça respecte la nature du web, bref, REST, c'est bien, faites en.

Et sur ce point je suis totalement d'accord avec lui. Par contre, je ne comprend pas pourquoi le monde du web professionnel ne fait que de le découvrir... 
Tout est ressource, toute ressource est URI, c'était la phrase par laquelle je commençais et concluais mes cours sur http il y a presque 10ans... C'est la nature profonde du web. Enfin, ceux qui font les applis web viennent de le comprendre. C'est beau. C'est un peu tard peut être. Espérons que ce message REST continue à se propager.

## Les BRMS par Emmanuel Bonnet
Deuxième présentation sur les BRMS, Business Rules Management System, plus communément appelé moteur de règles.
La présentation d'Emmanuel était vraiment très intéressante et très concrète. Mais il est difficile d'en faire un compte rendu complet et fidèle, je me contenterai d'en résumer les idées principales.

L'objectif des BRMS c'est de permettre de prendre des décisions en fonction d'un certain nombre de facteurs et de règles définies par le métier.

Pour cela, ils remplissent trois fonctions :

* décrire les règles métiers sous la forme si alors sinon
* exécuter ces règles
* gérer ces règles

L'intérêt :

* externaliser une partie de la logique métier : on peut mettre à jour ces règles fréquemment sans déployer l'intégralité de l'application.
* expliciter les règles : de façon lisible et compréhensible par un utilisateur
* gérer les décisions métier : on peut, à tout moment, savoir exactement pourquoi telle décision a été prise

Quand les utiliser :

* il est plus long au spécialiste métier de faire comprendre les règles aux développeur que de les écrire lui même.
* les règles métier changent très fréquemment
* il y a besoin de traçabilité sur les décisions prises par le système

Emmanuel rappelle que les BRMS sont un outils très efficace mais ne sont pas une panacée universelle. Il faut éviter le syndrôme du marteau pour écraser une mouche et ne s'en servir que lorsque cela est justifié.

## Apéro
Comme toute soirée de ce type, un apéro a suivi les présentations. L'occasion de discuter, d'approfondir des points avec les orateurs ou d'en aborder de nouveau. Étonnement, je me suis vite retrouvé à parler d'agilité :) Les discussions ont continué assez longtemps et se sont finis, pour les plus acharnés, au resto[^1]


[^1]: sans moi pour cette fois, mais ce n'est que partie remise :)
