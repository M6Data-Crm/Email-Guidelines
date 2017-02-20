# Data-CRM 6play Email Guidelines

## Objectifs :

* Garantir un bon niveau de déliverabilité,
* Offrir le meilleur rendu possible, quelle que soit la plateforme de destination : webmail, FAI, desktop, mobile...
* Respecter la charte graphique 6play,
* D'une manière générale, participer à la meilleure expérience d'utilisation possible.

## Development Guidelines : back to 1999

L'intégration HTML spécifique aux emails, est très éloignée de l'intégration html5 pratiquée aujourd'hui en développement front end et très proche de ce qui se pratiquait au siècle dernier quand on ignorait les feuilles de style externes et le concept DRY (Don't Repeat Yourself).

### L'encodage HTML

#### Des `<table>`, pas des `<div>`

La structure doit être apportée par des balises `<table>` et non pas des `<div>` qui risquent d' être mal interprétées par les FAI, clients email ou webmails, voire pas du tout.

Autant que possible, il fait veiller à régler les cellspacing et cellpadding à 0.

#### Attention aux `<td>` et `<tr>`

L'idéal est d'indiquer les largeurs à chaque `<td>`.

Du côté des balises `<tr>`, il est déconseillé de les empiler et il est recommandé d'utiliser à la place des balises `<table>` indépendantes.

Enfin, aucun élément de style ne doit être inclus dans les balises `<tr>`.

#### Elément de style dans `<body>`

Ils seront systématiquement ignorés par la grande majorité des webmails. Lorsqu'il s'agit d'indiquer une couleur d'arrière-plan, il est possible de contourner le problème en utilisant cet attribut dans l'élément `<table>`, même s'il ne s'agit juste que d'une table-container.

#### Attributs "Float"

Ils poseront indubitablement toutes sortes de problèmes. Ils ne s'affichent que très rarement correctement.

#### `<p>` ou `<span>`

La balise `<span style="block;">` devra être utilisée aussi souvent que possible. La balise de paragraphe `<p>` donne des résultats d'affichage irréguliers, notamment en matière d'interlignage.

#### Raccourcis CSS

Ils ne sont pas interprétés, il faut donc éviter les syntaxes du type : "font: 10px/16px #000 Arial". Les attributs de style doivent être renseignés de façon individuelle (font-size, color, font-family...).

#### Titres

On préférera le vieil élément `<span>` aux balises de titre `<h1>`, `<h2>`, `<h3>`... 

#### Centrage, Alignements...

L'usage de l'attribut "align=" dans une table est à privilégier. L'usage de la balise `<center>` est à éviter.

Par ailleurs, chaque élément `<td>` contenant du texte devra idéalement contenir cet attribut dûment renseigné.

#### Images affichées en tant qu'éléments "block"

Les images sont supposées être des éléments "block" par défaut, mais malgré cela, certains clients email demande une spécification (display:block;).

#### Attribut "alt"

C'est toujours mieux de le renseigner, il améliore l'expérience utilisateur des destinataires ayant le blocage des images activé sur leur client email. C'est également un moyen d'optimiser le ration image/code du message.

#### Mise en forme du texte

Les éléments textuels doivent être stylisés un par un, séparément. C'est le seul moyen d'éviter l'écueil de l'horrible typo par défaut de certains clients email.

### Autres bonnes pratiques d'intégration

#### Pas d'image d'arrière-plan

A éviter, absolument. Cette pratique dégrade le ratio image/code d'une part et offre un rendu très inégal suivant les boitres de réception.

#### Lien miroir vers une version hébergée, lien de désabonnement

C'est l'évidence même, mais c'est mieux quand c'est écrit.

#### Validation

Bien entendu, l'opération de validation du code devra se faire en XHTML Transitional et non pas en html5.

## Styleguide : sobriété obligatoire

Le design appliqué aux emails doit obéir à certaines bonnes pratiques afin de garantir un bon niveau de déliverabilité. Il doit aussi s'adapter aux contraintes de développement évoquées plus haut.

### Dimensions

La largeur idéale se situe entre 600 et 800 pixels. Toutefois, il semble que les largeurs arrondies à un chiffre rond soient à privilégier.

La hauteur est sans importance, le scrolling étant généralement admis. Toutefois, l'incidence sur le poids du fichier n'est pas à négliger.

### Layout

#### Grilles et colonnes

Sont préférés par les boites de réception les designs à base de grids, avec une préférence pour les construction en 1 colonne quand c'est possible. Les éléments comportant des positionnements et des floats sont à proscrire (cf. voir plus haut).

#### Éléments visuels

Ils doivent rester le plus simple possible et ne doivent absolument pas se chevaucher.

### Contenu

#### Hiérarchie

L'importance doit être décroissante de bas en haut, à la manière des articles de blog.

#### Style

Un style concis et percutant est requis. Les premiers mots sont à soigner particulièrement puisqu'ils sont amenés à être repris en extrait.

### Images

#### A anticiper

Il faut anticiper le fait que les images sont souvent bloquées par certains clients email, et que les images de grande taille (background par exemple) ne se chargeront tout simplement pas du tout.

#### Poids

Afin de garantir le poids le plus faible pour ces fichiers, le meilleur compromis qualité/poids doit être recherché. Une dégradation systématique doit être opérée.

A titre d'exemple, un .jpg de 500px x 500px devrait peser aux alentours de 100ko.

#### Nombre

Un bon ratio image/code devant être respecté, il faut être très attentif au fait de ne pas surcharger l'email en images. Les messages constitués d'une image unique sont à proscrire totalement.

### Typographie

#### Polices

Les polices web basiques cross platform sont à privilégier : Arial, Verdana, Georgia, and Times New Roman. C'est triste, mais c'est comme ça.

#### Taille

Les tailles doivent être exprimées en pixel (nombre entier), et ne doivent pas être inférieures à 10px pour les textes constituant le corps du message.

### Flash, JavaScript

Flash et JavaScript sont à éviter. Pour les animations, seul l'usage du  format .gif sera sans conséquence sur la déliverabilité.

### Responsiveness

L'expérience de lecture sur mobile doit absolument être prise en considération : temps de chargement réduit, taille des boutons/liens cliquables...

## Charte graphique 6play

## Axes de réflexion

### Tests

* Envisager le recours à un service de test tel que [Litmus](https://litmus.com/).
 
## Pour aller plus loin
Si vous souhaitez en savoir davantage :

* [Les recommandations MailChimp](https://templates.mailchimp.com/getting-started/html-email-basics/)
* [Les recommandations d'Unruthless](https://gist.github.com/unruthless/11383824)
 