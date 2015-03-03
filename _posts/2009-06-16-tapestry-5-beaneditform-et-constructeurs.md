---
layout: post
title: "Tapestry 5, beaneditform et constructeurs"
date: 2009-06-16 21:07:00 +0100
comments: false
categories: 
- "java"
- "tapestry 5"
---
En ce moment, au bureau, je bosse sur une appli web Java. Dans la foultitude des framework disponible, on a choisi d'utilisé Tapestry. Mon Java est un peu rouillé, et je débute (comme tout le monde chez nous) sur ce framework. En créant mon premier beanediform, je suis tombé sur un comportement surprenant au premier abord pour lequel je n'ai pas trouvé beaucoup d'info. Comme ça peut être utile, autant à d'autre qu'à moi même en pense bête, je raconte ça ici.


Imaginons donc une classe Login de base :

{% highlight java %}
 public class Login {
     @Validate(required)
     private String  username ;
 
     @Validate(required)
     private String  password ;
 
     public String getUsername() {
         return username;
     }
 
     public String getPassword() {
         return password;
     }
 
     public void setUsername(String username) {
          this.username = username;
     }
 
     public void getPassword(String password) {
         this.password = password;
     }
 }
{% endhighlight %}

Jusque là, tout va bien. Imaginons maintenant une page qui ferait un formulaire pour saisir les informations de cette classe. Le .tml associé contiendrait  `<t:beaneditform object=login/>`. Et jusque là, ça va encore. En compilant, et testant la page, on devrait obtenir le résultat escompté.

Imaginons maintenant, que pour les besoins de l'application, par ailleurs, j'ai besoin d'un constructeur pour la classe Login. Pas de soucis, on lui rajoute :

{% highlight java %}
public Login (String Username, String Password) {
    this.username = username;
    this.password = password;
}
{% endhighlight %}
Rien de plus simple. Sauf que... Sauf que quand vous allez réutiliser la page de formulaire, vous risquez d'avoir des trucs bizarres : les champs de votre formulaire sont peuplés avec des informations qui sortent d'on ne sait où, il se pourrait même que vous tombiez sur des erreurs types service not found. Pas très classe...

La solution (version courte) : il suffit de rajouter un constructeur sans arguments, et l'injecter en tant que service.

{% highlight java %}
@Inject
public Login(){
}
{% endhighlight %}

La solution (version longue)[^1] : C'est la même :)

Mais je m'explique un peu. Le problème vient que Tapestry est intelligent et essaie de faire des choses intelligentes[^2]. En bref, si on ne définit pas de constructeur, Tapestry utilisera le constructeur vide sans argument que le compilateur aura eu la bonté de faire pour nous pour instancier un objet Login.

Si on rajoute un constructeur avec des arguments, Tapestry va essayer de s'en servir[^3], et comme il n'a, à ce moment, pas toutes les infos pour le faire, il va se passer des choses bizarres[^4].
En définissant le constructeur vide et en utilisant l'annotation __@inject__, on va déclarer ce constructeur comme service à Tapestry. En gros, on va lui dire que c'est ce constructeur qu'il devra utiliser et pas l'autre. Ainsi pas de soucis.


[^1]: mais dans les grandes lignes
[^2]: Et on sait bien qu'avec un code simple, être intelligent n'est pas forcément une bonne idée :)
[^3]: si j'ai bien compris, son comportement par défaut et d'utiliser le constructeur qui utilise le plus de champs
[^4]: en C, on aurait probablement eu le droit à un magnifique Segmentation Fault :)
