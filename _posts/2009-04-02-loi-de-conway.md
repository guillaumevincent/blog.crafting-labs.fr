---
layout: post
title: "loi de Conway"
date: 2009-04-02 21:56:00 +0100
comments: false
categories: 
- "agilité"
- "communication"
- "conway"
- "petite phrase"
---
[Conway\'s law](http://www.melconway.com/law/index.html) :

> Any organization that designs a system (defined broadly) will produce a design whose structure is a copy of the organization's communication structure.


Lors de sa présentation à l'[inauguration du SUG France](/index.php?post/2009/03/20/19-mars-2009-Inauguration-du-Scrum-User-Group-France), Jeff Sutherland s'est également attardé sur l'importance de l'architecture logiciel et a rappelé cette loi (largement diffusée par le célèbre [Mythical Man-Month ](http://www.amazon.fr/gp/product/0201835959?ie=UTF8&tag=monbloamoique-21&linkCode=as2&camp=1642&creative=19458&creativeASIN=0201835959)[^1] de Frederic Brooks).

Une traduction littérale serait : 

> Une organisation qui conçoit un système concevra un système dont la structure est une copie de la structure de communication de l'organisation>>.

Un peu moins pompeusement, on pourrait dire :

> La structure d'un système est à l'image de la structure de communication de l'organisation qui l'a conçu.

Évidemment, on parle ici de logiciel. Et c'est une loi dont j'ai pu apprécier la véracité à plusieurs reprises.
Alors, on peut la prendre telle quelle et juste se contenter de l'observer. Ou on peut essayer de la comprendre et en tirer des mises en garde.

La prendre à l'envers, peut-être une idée : si la structure du code reflète la structure de communication de l'organisation, alors un code avec une structure en vrac peut révéler de vrais problèmes au sein de l'organisation.
Lorsqu'on rencontre un système bancal, on a instinctivement envie de blâmer les développeurs et leur compétence à développer. Après tout, c'est bien eux qui sont responsables de ce --merdier--système. Ce que rappelle la loi de Conway, c'est que ce n'est pas forcément un problème de compétence ou de qualité. C'est probablement un problème plus profond qui montre que la communication ne passe pas ou mal, entre les développeurs mais aussi[^2] entre tous les intervenants (dev, manager, client, chef de projet, donneur d'ordre, etc.) C'est un tout, et une responsabilité collective qui ne se résout pas juste en apportant de nouvelles compétences. Cela demandera une réflexion posée sur la nature même de la structure.


Alors la prochaine fois que vous croiserez un développement bancal, regardez aussi l'environnement dans lequel il a été développé. Et tirez en les bonnes conclusions :)


[^1]: que vous avez le droit de m'offrir pour que je le lise complètement :)
[^2]: et surtout ?
