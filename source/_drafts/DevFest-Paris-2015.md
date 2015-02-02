title: "DevFest Paris 2015"
tags:
- Angular2
- CSS
- PolymerJS
category:
- Event
---

# Devfest Paris : 30 / 01 / 2015

J'ai eu la chance d'être retenu comme speaker au [DevFest Paris](http://devfest.gdgparis.com) sur un sujet autour du WebRTC.

![](/assets/2015-01-DevFest/logos.png)

La journée s'est déroulée de façon assez classique et voici le programme que j'ai suivi sur cette journée : 

* 9h00 : Keynote avec le [GDG Paris](http://gdgparis.com) et [Alexis Moussine-Pouchkine](http://twitter.com/alexismp)
* 10h00 : PolymerJS avec [Martin Gorner](https://plus.google.com/u/0/+MartinGorner/posts) et [Cyril Balit](http://twitter.com/cbalit)    
* 11h00 : J'ai préféré faire une pause networking
* 12h00 : Repas
* 13h30 : J'ai donné ma session sur WebRTC
* 14h30 : Angular2 avec [Thierry Chatel](http://twitter.com/ThierryChatel)
* 16h15 : Flexbox par [Raphael Goetter](http://twitter.com/goetter)

## Keynote

![](/assets/2015-01-DevFest/devfest_paris.jpg)

Pendant la keynote, le GDG Paris a commencé par nous présenter la journée puis Alexis a pris la parole pour parler des composantes à prendre en compte pour faire des applications de qualités.

Globalement, Alexis nous a expliqué en quoi Google mettait à disposition tout un ensemble d'outils aussi bien sur la partie front que sur la partie backend pour aider les développeurs. Il a donc été question de Material Design / Plateforme Cloud / Retours utilisateurs.

* Matérial design est le nouveau thème par défaut dans lolipop mais il s'adresse aussi aux applications desktop via Polymer par exemple.
* L'offre cloud s'est beaucoup diversifiée ces derniers temps surtout avec l'intégration d'outils comme docker par exemple.

Je ne mettrais qu'une citation d'Alexis qui m'a bien fait sourire : 
<blockquote>On ne désire pas les choses par ce qu'elles sont belles mais c'est par ce qu'elles sont belles qu'on les désire</blockquote>


## Les WebComponents & Polymer : une révolution ?

Cyril Balit & Martin Gorner ont fait une introduction aux concepts & composants disponibles via PolymerJS avec le style Paper. Ils nous ont ainsi expliqué certains des principes qui se cachent derrière Material Design.

### L'enjeu

Un des principaux objectifs de Polymer et de permettre de concevoir des IHMs  réutilisables et basées sur les nouveaux standards des webComponents

Polymer, c'est donc l'association de 4 standards : 
* HTML Import : 
    - Importer un fragment html depuis une page web
* Shadow Dom
    - C'est la garantie de l'isolation du composant
* Templates
    - Permet de définir une zone réutilisable dans votre code html qui sera disponible après coup via le javascript
* Custom Elements
    - La création des tags personnels ! (je tacherais de créer une balise à titre d'exemple dans un prochain article) <jef-binomed></jef-binomed>

### Compatibilité navigateurs

<iframe src="https://docs.google.com/spreadsheet/pub?key=0Anye-JMjUkZZdDdoblh6dTlwcWRLQkhKbTVzdHJtcXc&single=true&gid=2&output=html&range=A1:Q43" seamless style="border:none;width:100%;height:830px;"></iframe>

### Polymer ! 

C'est donc un polyfill pour les WebComponents qui propose aussi un certain nombre de composants utilisables dans nos interfaces.

#### Architecture 

![](/assets/2015-01-DevFest/polymer_archi.png)

### Paper & Material design

Viens ensuite Paper & Material Design. Paper est donc une implémentation de Matérial Design pour le web. Le nom n'est pas anodin car un des principes de Material Design est de dire que l'information est proposée sur du papier (le matériel !) et donc c'est le support de base de présentation du contenu.

On peut retenir qu'un des enjeux est de donner de l'information rapidement et efficacement ! Pour cela, les informations sont très colorées. Dans lolipop, on peut donner une image et il nous ressort en fonction de l'image la couleur principale correspondante. Les animations et transitions permettent de compléter l'expérience utilisateur en lui offrant une continuité graphique qui ne perd pas notre utilisateur avec un écran noir de transition !

#### Composants : 

PolymerJS vient donc avec un certain nombre de composants que l'on peut réutiliser afin d'agrémenter notre IHM. Je n'en ai noté que quelque uns mais la liste est grande et facilite grandement le travail des développeurs

* FAB : Floating Action Button : Bouton d'action principal
* Ripple ou Ink Effect : Retour visuel sur une interaction
* Hero element : Elément qui fait la transition entre 2 vues
* core-toolbar : L'actionbar 
* core-header-panel : Conteneur au-dessus qui gère la toolbar et le contenu
* core-drawer-panel : Composant responsive 
* paper-input : Composant de saisie avec toutes les informations nécessaire à la validation
* [Liste des éléments](https://www.polymer-project.org/docs/elements/paper-elements.html)

#### Nos propres composants

Pour déclarer un composant personnel, il suffit simplement de déclarer un fichier html qui contient la déclaration de la balise (le nom doit forcément contenir un "-" pour ne pas être confondu avec un autre élément du DOM), le html, le css, le javascript associé.

```html
<link rel="import"
      href="/components/polymer/polymer.html">

<polymer-element name="ready-element">
  <template>
    This element has a ready() method.
    <span id="el">Not ready...</span>
  </template>
  <script>  
    Polymer({
      owner: "Daniel",
      ready: function() {
        this.$.el.textContent = this.owner +
                                " is ready!";
      }
    });
  </script>
</polymer-element>
```

## WebRTC : Révolutionnons le partage d'informations dans le browser

Plutôt que de parler de ma session, je vous invite à aller voir les slides ou les vidéos que l'on a déjà pu filmer de cette présentation

[Présentation WebRTC](http://jef.binomed.fr/binomed_docs/Prezs/WebRTC/index.html)

## AngularJS 2.0... et avant ?

Thierry Chatel nous a fait une présentation pour nous rassurer sur l'avenir d'Angular 2 et il a ainsi revu les principales annonces qui ont pu être faites pendant NG-Europe.

Globalement, s'il y a une chose à  retenir, c'est : ne vous inquiétez pas ! Certes Angular 2 va changer beaucoup de choses mais en même temps c'est une bonne chose. Alors que le web bouge très vite et que nous sommes à l'aube de voir débarquer EMACScript 6, les webcomponents, ... dans nos navigateurs, il n'était pas envisageable pour la team Angular de ne pas en tenir compte et donc Angular 2 est clairement tourné vers l'avenir !

Prenons quelques-uns des arguments de Thierry.

### Application perdurant dans le temps

Thierry a rencontré beaucoup de personnes lui expliquant vouloir développer des applications durant 10 ans basées sur AngularJS. Thierry s'est posé la question suivante : "c'était quoi le web il y a 10 ans ?". Et en effet, si l'on regarde en arrière, on se rend compte qu'en février 2005 sortait "prototype" et que ce n'est qu'en juillet 2006 que le terme AJAX est apparu vraiment. Il n'y a donc que depuis 9 ans que l'on a commencé à réaliser des applications asynchrones ! Autant dire qu'il s'en est passé des choses depuis 10 ans. Il va surement s'en passer encore beaucoup sur les 10 prochaines années. 

Dire que l'on veut une application qui va durer 10, pourquoi pas, mais cela a surtout du sens côté serveur ! Le front évolue trop vite pour que l'on puisse chercher à faire durer des applications côté front sur 10 ans. Pour information, la version d'IE disponible il y a 10 ans était IE 6...

### Maintenance de la version 1.x

Pour le moment, l'équipe de Google n'a communiqué aucune date sur l'arrêt du support d'Angular en version 1.x. Mais Thierry faisait remarquer que l'adhésion à ce framework a été tellement forte par la communauté qu'il ne fait aucun doute que des gens reprendront le projet pour du support mineur lors de l'arrêt officiel du support de Google.

### Suppression du scope et du contrôleur, je fais comment maintenant ?

Thierry s'est penché sur les raisons qui ont amené à la suppression de ces 2 composants qui sont aujourd'hui au coeur du framework Angular. Il nous a expliqué que si l'on suit les bonnes pratiques du développement Angular, notre contrôleur ne sert qu'à initialiser le scope et que très souvent, il sert de "passe plat" entre nos services et nos directives. En effet, pour Thierry, le code métier doit figurer dans les services afin de séparer au mieux les couches et ainsi avoir un code propre et maintenable. Tout ça pour en venir au fait que même la déclaration d'un contrôleur dans notre application se fait via une directive ng-controller... Ne serait-il pas plus logique de faire en sorte que nos directives portent les informations directement et que la simple hiérarchie du DOM et un agencement propres de nos services suffise à faire communiquer le tout ? C'est exactement ce qui est proposé avec Angular2.

Il nous a donc expliqué qu'au lieu de publier dans le scope d'un contrôleur, nous allions simplement publier dans une directive. 

Afin de faciliter la migration vers Angular2, Thierry propose d'utiliser par exemple la déclaration "Controller as" et il préconnise aussi de bien séparer les couches (services,...) pour rendre notre contrôleur le moins important possible.

### Slides

Retrouvez les slides de Thierry : [Slides](http://tchatel.github.io/slides-devfestparis2015#/#/1)

## FlexBox Révolution

Raphaël Goetter nous a présenté la propriété css "flex-box". Cette dernière ou plutôt ensemble de propriétés a 4 objectifs : 

* Distribuer : Comment mes éléments vont se positionner dans le parent (verticalement / horizontalement )
* Ordonnancer : Dans quel ordre vont-ils être affichés ? 
* Alignement : Comment les éléments vont-ils être alignés ?
* Flexibilité : Quelle places vont prendre mes éléments dans le parent ?

### Spec & compatibilité

Aujourd'hui c'est disponible à partir de IE10+ et dans tous les autres navigateurs (c'est même disponible dans android 2.1). Raphaël nous disait que cela représente 95% du marché ! Mais en tout cas ce qui est sûr, c'est que concernant le mobile, vous pouvez foncer les yeux fermés et utiliser flexbox dans la partie media-quieries de vos sites mobiles !

Concernant la spec, elle a été rétrogradée il y a peu à l'état de brouillon. Ceci est dû à un manque de cohérence dans l'écriture de certaines propriétés. Mais Raphaël mise quand même sur une disponibilité officielle de la part du W3C prochainement. 

### Fonctionnalités

Voici en vrac ce que l'on peut faire avec flexbox :

* Alignement vertical : oui j'ai bien dit alignement vertical ! 
* Regroupement par catégorie grâce à la notion d'ordre
* Réorganisation graphique et très simple de nos IHMs


#### La Distribution

Par défaut, la distribution est horizontale. C'est à dire que nos éléments au lieu d'être les un en dessous des autres, seront les uns à côté des autres

``` css
 display:flex
```

Si l'on veut changer la direction passée sur vertical par exemple, il faudra setter la propriété flex-direction. De même si notre contenu dépasse, on peut demander à la propriété de faire un retour à la ligne automatique via

``` css
 flex-wrap: true
```

#### L'ordonnancement

Concrètement, on peut changer l'ordre d'affichage de nos éléments du dom grâce à la propriété

``` css
{order : 0} 
```

Cela fonctionne de façon comparable aux z-index. Plus l'ordre est grand, plus il sera loin dans le flux, plus le chiffre est bas (chiffres négatifs autorisés), plus l'élément sera au début du flux.

L'ordonnacement peut être utilisé par exemple pour faire des regroupements graphiques d'éléments ayant quelque chose en commun. Raphaël nous a montré comment au sein d'une div contenant des liens vers des fichiers (ppt, pdf, doc, ...) les regrouper visuellement grâce à flex.

``` css

[href$=".pdf"]{
    order:0;
}

[href$=".doc"]{
    order:1;
}
...
```

De cette manière, tous les pdfs se retrouveront à côté, même chose pour les docs.

#### L'alignement

L'alignement permet de définir comment nos éléments vont être alignés dans leur conteneur ! 

``` css
{justify-content:flex-end}
```

Fera par exemple alignement vers le bas si flex-orientation est en column

``` css
justify-content:center 
```

Quant à lui centrera le contenu en fonction de l'orientation primaire de la flexbox.

``` css 
align-items : strech
```

Permettra d'aligner selon l'autre axe

#### La flexibilité

Concernant la place prise par l'élément, 3 propriétés sont en jeux : 

La propriété flex est un raccourci de trois propriétés, flex-grow, flex-shrink et flex-basis, qui s’appliquent au flex-container et dont les fonctionnalités sont:

* flex-grow : capacité pour un élément à s’étirer dans l’espace restant,
* flex-shrink : capacité pour un élément à se contracter si nécessaire,
* flex-basis : taille initiale de l’élément avant que l’espace restant ne soit distribué.

Par défaut, les valeurs de ces propriétés sont : flex-grow: 0, flex-shrink: 1 et flex-basis: auto.

En clair, les flex-items n’occupent initialement que la taille minimale de leur contenu.

### Resssources

Je vous invite à aller consulter l'article disponible sur le site d'Alsa créations : [Article AlsaCréations](http://www.alsacreations.com/tuto/lire/1493-css3-flexbox-layout-module.html)

[Slides de la présentation](https://speakerdeck.com/goetter/flexbox-revolution)

# Conclusion

La journée fut riche en rencontre et en conférences de qualités, je suis donc content d'avoir pu faire partie de cette édition ! Suiviez le GDG Paris pour être tenus au courant de la publication des vidéos et slides.