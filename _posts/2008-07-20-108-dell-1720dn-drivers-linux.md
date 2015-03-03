---
layout: post
title: "Dell 1720dn -- drivers linux"
date: 2008-07-20 19:12:00 +0100
comments: false
categories: 
- "geekeries"
- "howto"
---
Les bons drivers pour exploiter et configurer au mieux la Dell 1720dn sous linux (ubuntu).


#Introduction
Dell fournit un gestionnaire d'impression complet, mais perso, je préfère utiliser mon vieux CUPS.
La 1720dn est compatible avec les dernières générations de postscript et PCL, mais avec des drivers génériques, les résultats, bien que bons, sont décevants au vu de ce dont est capable la bête.

#Les fichiers
Heureusement, les fichiers qui vont bien pour configurer CUPS sont sur le CD d'install, mais perdus dans la partie windows.
Les deux fichiers qui nous intéressent sont `drivers/print/win_2kxp/dkabj540.gdl` et `drivers/print/win_2kxp/french/dkabj540.pp_`.
Le premier gère les options (rectoverso, bac à feuille etc.), le second le drivers compressé au format mscompress.<br />

##décompression
Pour décompresser le ppd, il vous faudra le programme mscompress.
Sous ubuntu et autre debian-like un:

{% highlight bash %}
sudo apt-get install mscompress
{% endhighlight %}

l'installera si cela est nécessaire. J'imagine que les autres distribution ont des paquets similaires.

Copiez `drivers/print/win_2kxp/french/dkabj540.pp_` dans un répertoire (`/tmp` par exemple) puis allez dans ce répertoire.

{% highlight bash %}
msexpand dkabj540.pp_
mv dkabj540.pp dkabj540.ppd
{% endhighlight %}

Et vous avez un fichier .ppd fonctionnel.

##Copier
Enfin, il ne reste plus qu'à copier le .ppd résultant et le .gdl dans un coin de votre disque ou vous pourrez les retrouvez.
`/usr/share/ppd/custom` peut être une bonne idée (il vous faudra les droits root pour cela).
Selon votre distrib, il faudra surement aussi mettre les bons droits d'accès aux fichiers (pour les users/groupes lp, lpadmin par ex).

#Et voilà
Et voilà, vous n'avez plus qu'à installer votre imprimante avec votre outils habituel. Il faudra éventuellement lui préciser l'emplacement où se situe les fichiers si il ne les découvre pas tout seul.


