---
layout: post
title: "Un peu d'histoire"
date: 2010-06-30 02:28:00 +0100
comments: false
categories: 
- "gulltopp"
- "heimdall"
- "nostalgie"
- "postfix"
- "web"
---
Voilà, ce soir, je viens de migrer totalement la gestion des mails de tous mes domaines au service mail de gandi et je m'apprête à tuer définitivement le processus qui m'a rendu ce service presque fidèlement pendant plus de 8 ans.

C'est l'occasion d'un petit cours d'histoire de ce serveur, ou plutôt les différents serveurs qui ont fièrement héberger vernois.net et nombreux autres domaines depuis 2002.


Tout commence en 2002 avec l'achat du premier domaine avec mon frangin [^1], e-bibilo.net chez gandi.net[^2]mais qui renaîtra de ses cendres un jour, soyez en sur$$. Trois jours plus tard, je me dis que les noms de domaine, c'est pas cher, et que quitte à en avoir 1, je peux bien en avoir 2, et puis ça fait classe :)

Mais avoir des domaines, c'est bien encore faut il en faire quelques choses, et surtout avoir un endroit pour les héberger. Il ne faudra pas beaucoup plus de temps pour que ma tour, un athlon 900 qui répondait au nom de Thor, se voit rajouter une deuxième carte réseau, et prenne place sur un meuble dans la cuisine de mon appart à Lyon pour faire office de gateway et serveur web 24/24 [^3], le tout raccordé au net par la célèbre manta verte de wanadoo.

Les tous premiers jours, cela tournait sous windows, le temps pour moi de porter sous linux un script qui assurait la communication avec dyndns qui permettait au domaine de toujours pointer vers ma machine malgré son ip dynamique[^4]. Ça n'a heureusement pas durer longtemps et très vite, je suis repassé sur un vrai système[^5], et après un peu de bataille, en plus de gérer le web, la machine s'est mise à servir les mail de vernois.net.

La canicule de 2003 sera fatale à thor. La machine atteint des températures folles[^6], et nécessitait un ventilateur de salon braqué sur son flan ouvert pour accepter de tourner plus de 15 minutes. Opération montage de machine à moindre frais et en express avec un pillage sur le corps encore chaud de thor. C'est la naissance d'Heimdall, le gardien du pont, dans sa première version.
Heimdall resistera à la seconde vague de canicule d'aout 2003, mais pas le circuit électrique de mon quartier, ce qui me vaut une interruption de mes vacances chez mes parents pour installer rapidement un onduleur[^7] afin de pas couper trop longtemps le service de mail[^8]. Évidemment, j'en profite pour mettre ce qu'il faut pour surveiller l'état de l'onduleur à distance :)

Tout ça tiendra un an. Heimdall v1, qui m'avait couté à peine 100euros[^9] (carte mere + proc + ventilo + boitier + ram) n'était pas taillé pour tourner 24/7 et commençait à être bruyant.
Heimdall 2ème génération est arrivé. Un mini itx monté dans une petite caisse en bois de 20cmx20cm[^10] Le silence et la fiabilité. Le bonheur.

Début 2005, plusieurs petits incidents et une interruption d'accès au web pendant 4 jours sans aucune explication ni communication malgré mes demandes d'info, et c'est la scission définitive avec wanadoo. Bonjour Free, c'est 10 euros moins cher, ça va 4 fois plus vite et j'ai une ip fixe. Bon, je suis en bout de chaîne, j'avais de fréquente perte de désynchro, mais rien de vraiment gênant. Les mails et le web tournaient bien.

Fin 2005, début 2006, déménagement sur Clermont Ferrand. Le temps de faire les migrations de ligne, je n'ai pas internet pendant 2-3 semaines. On est bien au-delà des délais autorisés pour les mails. Et perdre des mails est une idée qui ne me plait pas du tout. Heureusement, un camarade lyonnais[^11] hébergera mon serveur chez lui le temps que tout soit prêt chez moi. Ce fut un peu mouvementé, mais globalement ça a marché :) Et en février, heimdall a pu intégrer un meuble dans mon salon clermontois.

2006, c'est aussi l'année où je commence ce blog. Essentiellement pour permettre à mes parents de savoir que je suis toujours en vie, j'ai tendance à ne pas être très fort pour donner des news :)[^12].

Presque 2 ans de calme et de bon fonctionnement, sans crises majeures, pas que je m'en souvienne en tout cas. Bien sûr, je passe sur les péripéties de disques durs, qui ont émaillé toutes des ces années. Les disques grands publics ne sont pas non plus fait pour tourner 24/7 :) Mais de bons scripts de sauvegarde et de surveillance font que je ne crois pas que nous ayons eu à déplorer de perte de données. Les disques durs, j'ai toujours vu ça comme du consommable[^13], j'en ai même souvent un en stock, au cas où.

2008, c'est la rebelote du déménagement, direction Toulouse cette fois. C'est la période où gandi sort son offre d'hébergement virtuel en bêta. Hop, c'est l'idéal pour moi. Je migre tous les services d'heimdall sur une petite vm hébergée par gandi. Son petit nom : gulltopp. Après plusieurs journées à mettre au point une configuration, et le basculement se fait. C'est désormais gulltopp qui s'occupera de tout. Heimdall ne part pas à la retraite pour autant. Aujourd'hui, il est toujours dans mon salon, et me sert de firewall, de serveur secondaire pour les mails, de stockage et de backup de gulltopp[^14].
Et voilà, tous les services sont devenus autonomes, ils sont loin de la maison et font leur vie pendant que je fais la mienne. Je continue tout de même de les surveiller du coin de l'oeil, m'assurer que tout va bien, que les bases de données sont intègres, que les mails sont toujours reçus par leurs destinataires.

Le we dernier, j'ai découvert les limites de ma mémoire et des machines virtuelles. Après une mise à jour un peu violente du système[^15], gulltopp m'a gratifié d'un joyeux kernel panic, puis d'un élégant general error while mounting file system au reboot... Pas de problème, un rapide accès à la console de secours, et je vais reprendre les choses en main... Sauf qu'il y avait bien trop longtemps que je n'avais pas eu à reprendre les rênes de gulltopp, et plus moyen de me souvenir du mot de passe root qui m'aurait permis de tout arranger... voilà pour la mémoire. Sauf que si j'avais eu une machine physique en face de moi, je n'aurai eu qu'à en extraire le disque dur, le fixer sur une autre machine pour sauvagement y accéder et mettre un mot de passe dont je n'aurai plus de mal à me souvenir. Mais, sur une machine virtuelle, les disques le sont tout autant... voilà pour les machines virtuelles.

Les machines virtuelles restent à égalité sur un point avec les machines physique. Quand vraiment il n'y a plus moyen de s'en sortir, l'extrême recours du je réinstalle tout from scratch est toujours possible. Et voilà comment perdre un dimanche après midi à réinstaller et configurer gulltopp. Et la nuit à refaire fonctionner postix et ses amis. Et le reste du temps a me féliciter de ma politique de backup :p

Là, je me suis dit que j'en avais marre de passer beaucoup de temps à configurer et à m'inquiéter sur ce serveur mail. Le petite goutte qui fait déborder le vase. Le garder à la maison devient trop contraignant, je le confie à un institut spécialisé.
C'est aussi bien pour lui que pour moi. Et pourtant, tout à l'heure, quand les dns me confirmeront que mes mails seront aux bons soins de mon vieil ami gandi, que je lancerai sur gulltopp le dernier et fatal /etc/init.d/postfix stop je sais que j'aurai un petit pincement. C'est la fin d'une époque, de 8 ans de presque bons et presque loyaux services.

La nostalgie du geek peut être... ;)

Note aux utilisateurs du service mail de gulltopp : si vous deviez être impacté par ce changement, je vous ai déjà mis au courant. Pour ceux à qui j'ai rien dit, c'est que l'opération est transparente pour vous, il n'y a rien à faire.


[^1]: en fait, c'est le deuxième, j'avais déjà cottesdemailles.com depuis 2 ans, mais sa gestion en était totalement déléguée à l'hébergeur
[^2]: qui avait à peine 2 ans à l'époque :) pour un projet légèrement mort
[^3]: pendant que mon portable, un P3 1GHz, devenait mon poste principal
[^4]: pour l'anecdote, j'ai payé ce service 20$, à vie. Maintenant, le même, avec des restrictions que je n'ai, c'est 29,99$ par an :)
[^5]: un linux bien sur. mandrake, debian, slackware, ubuntu, red hat, fedora, mandriva, ... en 8 ans, je crois qu'ils y sont tous passé :)
[^6]: la sonde annonçait des relever à 100 dégrés
[^7]: une merlin gerin, qui marche toujours même si son autonomie devient très faible
[^8]: juste avant le we du 15 août et mon départ pour la fête médiévale de Bannegon, vive le tgv
[^9]: de mémoire
[^10]: gentillement faite par mon papa, merci.
[^11]: un grand merci à Raph'
[^12]: ça n'a pas beaucoup changé depuis :p
[^13]: surement un reste de l'époque d'adhersis :)
[^14]: synchronisé toutes les nuits
[^15]: à tous : essayer d'upgrader directement de 9.04 à 10.04 est une très mauvaise idée :)
