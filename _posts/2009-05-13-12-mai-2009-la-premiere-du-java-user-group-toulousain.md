---
layout: post
title: "12 mai 2009 -- la première du Java User Group Toulousain"
date: 2009-05-13 00:03:00 +0100
comments: false
categories: 
- "conférence"
- "java"
- "jug"
- "toulouse"
---
Ce soir avait lieu la première session organisé par le tout jeune [Java User Group Toulousain](http://www.jugtoulouse.org).
Au programme :

* JavaME -- Sylvain Wallez (CTO Goojet)
* L'écosystème GWT -- Bruno Marchesson (consultant senior Valtech)


Au cours du [SigmaT9](/index.php?post/2009/03/27/27-mars-2009-SigmaT-9), Gaël Blondelle et Florent Garin nous annonçait la création[^1] du Java User Group Toulousain. 
Des liens évidents s'amorçant avec le SigmaT, mon envie de me remettre à Java et un programme alléchant pour moi et voilà trois bonnes raisons d'y assister.

Les présentations ont eu lieu dans l'amphi U3 de l'Université Paul Sabatier, hébergé par l'IUP ISI[^2].

## JavaME - Sylvain Wallez - CTO et cofondateur de Goojet
JavaME c'est Java Mobile Edition, j'avais joué un peu avec il y a quelques années, à l'époque où je bossais sérieusement sur [e-biblio](http://www.e-biblio.net).

Sylvain nous a fait une très bonne présentation mêlant aspect pratique et théorique sur JavaME.
Qui dit Mobile Edition, dit pour téléphone. Et qui dit téléphone, dit diversité : fabriquant (Nokia, Samsung, LG [^3], Motorola, etc.), d'OS (Symbian, Windows Mobile, ...), d'interface (clavier, tactile, trackball, ...), d'écran (couleur, taille, ...).

Même si le monde l'ignore, la plupart des téléphones modernes embarque une JVM JavaME, dont les spéc minimales ne requiert que 128ko de RAM et un petit écran monochrome.

Point de vue dev, le processus suit celui d'une appli Java classique à laquelle on rajoute :

* un fichier de description : l'url du jar, la caractéristique minimum et ce genre de chose.
* une prévérification : la vérification faite à l'exécution dans la JVM habituellement est préparé au préalable et embarqué dans le .class pour gagner de la place en RAM[^4]
* une phase d'obfuscation : pour éviter le reverse engeeniring mais aussi, et surtout ?, pour gagner de la place en renommant tout et en supprimant le code mort[^5].

JavaME fourni une API de base avec les fonctionnalités génériques de bases requises par tous les apareils.
À cela s'ajoutent des APIs optionnelles pour toutes les fonctionnalités spécifiques. Et comme souvent dans le monde Java, il y en a pour tous les gouts.
Cela reste souvent d'éléments très bas niveau, et il faut refaire à la main pas mal de choses à l'ancienne et à la main.

Normalement JavaME est censé fonctionner partout de la même façon. Dans la vraie vie, ce n'est pas le cas et pour s'adapter au maximum de plateforme, il faudra passer par des directives de précompilation[^6] ou de try catch[^7].

En gros, JavaME, c'est bien, et ça a encore de beaux jours devant lui car il permet de faire un code à peu près portable sur une grande majorité de terminaux diverses et variés.
Mais si je lis entre les lignes du discours de Sylvain, l'avenir, c'est Android[^8].

## L'écosystème GWT - Bruno Marchesson - consultant senior Valtech

GWT, c'est le Google Web Toolkit.
L'idée c'est de pouvoir coder toute son interface web en Java et s'abstraire de la compléxité de maintenance d'un code Javascript[^9].
En pratique, la compilation du code java génère du code javascript[^10].

Bruno rappelle que Toolkit n'est pas Framework. GWT vous fournit des opérations de bases pour faire tout un tas de choses, mais en aucun cas il ne vous conseille sur la façon de vous en servir, les bonnes pratiques, le cadre ou la mise en place de garde fou. Ces vides sont en partie comblés par l'efficace communauté open source dont il nous propose de faire un petit tour.

* Coté client : 
	* ce sont essentiellement des réécritures/extensions des widgets graphiques de l'interface. Ext GWT[^11] semble le plus abouti, avec Smart GWT. Le premier est un portage de Ext JS, l'autre est une encapsulation de Javascript de SmartClient. GWT Incubator sont des widgets basiques en essai qui seront, si validé, intégré dans GWT. GWT Mosaic intègre les widgets d'Incubator plus un ensemble d'autre utilisant strictement les widgets GWT[^12].
	* pour les graphiques, GChart semble être le petit frère du bien connu JFreeChart : c'est complet, ça fait tout, mais c'est pas très beau... Une solution [^13] permet de générer de magnifiques graphes flash[^14].
	* coté MVC, Smart GWT et GXT intègre plus ou moins nativement ces méchanismes. Gwittir semble, lui, l'outil le plus mature. Mais pléthore d'autres frappent à la porte : GWTruts[^15], GWT-MVC, mvc4g, PureMVC[^16].

* Coté serveur : GWT c'est uniquement la présentation, et les canaux de communications avec la partie serveur, le reste, c'est pas son business.
	* GWT-SL s'occupe de la communication avec vos applis Spring directement depuis la couche GWT.
	* Gilead[^17] ex hibernate4GWT, permet de dialoguer avec des objets hibernate [^18].
	* gwt-validation est un framework coté client et serveur qui permet aussi de sa validation.
	* gwt-php, gwt AIR, GWT flash : besoin de plus de détails ? :)  après l'intérêt de tels systèmes peut surement être discutable[^19]

Bref, la communauté autour de GWT est fleurissante, mais les nouveaux projets meurt à peu près aussi vite qu'ils n'apparaissent, il faut donc prendre soin de s'assurer de la solidité de ceux que l'on va utiliser dans son propre système.

À noter aussi, que, de façon surprenante, GWT n'est pas encore supporté sur l'offre cloud computing de Google[^20].

## le Java User Group Toulousain
À priori, la prochaine session devrait avoir lieu avant les grande vacances[^21]. A ce sujet, les organisateurs lancent un appel à speakers : si vous avez envie de parler de quelque chose qui vous passionne autour de Java, n'hésitez pas à les [contacter](http://www.jugtoulouse.org).
Ils envisagent également l'organisation de coding dojo. Comme c'est aussi une des idées qui émerge dans SigmaT, un rapprochement sur ce point devrait avoir lieu entre les deux assos :)

## L'apéro
Et comme tout bon séminaire d'un User Group, cette session se termine autour d'un apéro pour étendre les discussions avec les intervenants et l'assistance.

## Ma conclusion
Avec un peu plus de 60 personnes présentes, c'est une première plutôt bien réussie. L'ambiance est sympathique et les présentations de très bonnes qualités, techniques sans être incompréhensible par les non-expert. Vivement la prochaine :)


[^1]: avec Sami Jaber
[^2]: qui accueille également les SigmaT
[^3]: le tant montré Apple avec son iPhone est un ptit joueur comparé à ces géants
[^4]: un des éléments limitants sur ces plateformes
[^5]: morceaux de code dans lesquels il est impossible de passer
[^6]: gérées par ant
[^7]: pour deviner les fonctionnalités supportées par le terminal
[^8]: c'est décidé, mon prochain téléphone sera sous Android :)
[^9]: dont le comportement diffère d'un navigateur à l'autre
[^10]: avec autant de version que de navigateur cible :)
[^11]: aussi connu sous le nom GXT
[^12]: ainsi, on ne se retrouve pas coincé avec une lib. on peut faire marche arrière sans trop de frais
[^13]: dont j'ai oublié le nom
[^14]: mais nécéssite donc le binaire qui va bien coté client
[^15]: inspiré de Struts comme on ne s'en serait pas douté :)
[^16]: dont les concepts sont portés dans une dizaine de langages
[^17]: dont Bruno est le main committer
[^18]: comme on ne s'en serait pas douté :)
[^19]: si l'idée c'est de faire du Java pour la partie cliente, pourquoi faire du php coté serveur ? :)
[^20]: problème possible de communication avec leur système de stockage. Mais il ne serait pas impossible que Gilead propose prochainement une solution :)
[^21]: le mois prochain donc
