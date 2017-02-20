# Data-CRM 6play Email Guidelines

## Development Guidelines : back to 1999

L'intégration HTML spécifique aux emails, est très éloignée de l'intégration html5 pratiquée aujourd'hui en développement front end et très proche de ce qui se pratiquait au siècle dernier quand on ignorait les feuilles de style externes et le concept DRY (Don't Repeat Yourself).

### Des `<table>`, pas des `<div>`

La structure doit être apportée par des balises `<table>` et non pas des `<div>` qui risquent d' être mal interprétées par les FAI, clients email ou webmails, voire pas du tout. Autant que possible, il fait veiller à régler les cellspacing et cellpadding à 0.

### Attention aux `<td>` et `<tr>`

indiquer les largeurs à chaque `<td>`.

## Styleguide

Le design appliqué aux emails doit obéir à certaines bonnes pratiques afin de garantir un bon niveau de déliverabilité. Il doit aussi s'adapter aux contraintes de développement évoquées plus haut.

### Dimensions

La largeur idéale se situe entre 600 et 800 pixels. La hauteur est sans importance, le scrolling étant généralement admis. Toutefois, l'incidence sur le poids du fichier n'est pas à négliger.

### Layout

Sont préférés par les boites de réception les designs à base de grids, avec une préférence pour les construction en 1 colonne quand c'est possible. Les éléments comportant des positionnements et des floats sont à proscrire.

### Images

#### A anticiper

Il faut anticiper le fait que les images sont souvent bloquées par certains clients email, et que les images de grande taille (background par exemple) ne se chargeront tout simplement pas du tout.

#### Poids

Afin de garantir le poids le plus faible pour ces fichiers, le meilleur compromis qualité/poids doit être recherché. Une dégradation systématique doit être opérée.

#### Nombre

Un bon ratio image/code devant être respecté, il faut être très attentif au fait de ne pas surcharger l'email en images. Les messages constitués d'une image unique sont à proscrire totalement.

### Typographie

Les polices web basiques cross platform sont à privilégier : Arial, Verdana, Georgia, and Times New Roman. C'est triste, mais c'est comme ça.

### Flash, JavaScript

Flash et JavaScript sont à éviter. Pour les animations, seul l'usage du  format .gif sera sans conséquence sur la déliverabilité.

### Responsiveness

L'expérience de lecture sur mobile doit absolument être prise en considération : temps de chargement réduit, taille des boutons/liens cliquables...
 

## Pour aller plus loin
Si vous souhaitez en savoir davantage :

* [Les recommandations MailChimp](https://templates.mailchimp.com/getting-started/html-email-basics/)
* 
 