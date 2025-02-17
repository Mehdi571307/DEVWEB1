
Jusque-là, nous avions travaillé sur la page d'accueil de notre site, qui contient la liste des articles.

Mais notre projet va contenir plusieurs pages :

- Une page "recettes".
    
- Une page d'édition et de création de recette.
    
- Une page avec un formulaire de contact.
    

Et pour pouvoir accéder à ces pages, il faudra nécessairement quelques liens HTML regroupés dans un menu principal.

Vous est-il déjà arrivé de vouloir modifier le menu de votre site et de devoir pour cela corriger le code HTML de chacune de vos pages web ?

Le menu d'une page web apparaît en effet sur chacune des pages, et vous avez très certainement dû le recopier sur chacune d'elles. Ça marche, mais ce n'est pas très pratique…

![[2025-02-17_13h48_24.png]]

Au fil de ce chapitre, vous allez découvrir un des multiples avantages que vous donne le PHP lors de la création de votre site. C'est d'ailleurs ce qui m'a fait instantanément aimer ce langage lorsque je l'ai découvert, alors que je venais comme vous seulement d'apprendre le HTML et le CSS. 😉

### Visualisez le découpage d'une page web

La plupart des sites web sont généralement découpés selon le schéma suivant.

![[2025-02-17_13h49_28.png]]

![[2025-02-17_13h49_57.png]]

Regardez le code d'exemple ci-dessous qui représente une page web avec un en-tête, un menu et un pied de page. Appelons cette page :  `index.php`  .

![[2025-02-17_13h50_26.png]]

![[2025-02-17_13h51_51.png]]

### Pensez votre contenu web en blocs fonctionnels

![[2025-02-17_13h52_13.png]]

Le principe de fonctionnement des **inclusions** en PHP est plutôt simple à comprendre. Vous avez un site web composé de, disons, vingt pages. Sur chaque page, il y a un menu, toujours le même. Pourquoi ne pas écrire ce menu (et seulement lui) une seule fois dans une page `header.php`  ?

![[2025-02-17_13h53_13.png]]

Maintenant, imaginez que vous ayez besoin de fonctions ou de variables sur toutes les pages du site.

Créons un nouveau fichier PHP : nous allons insérer uniquement le code HTML correspondant à votre menu, comme ceci :

![[2025-02-17_13h56_43.png]]

Faites de même pour la page `pied_de_page.php` et toute autre page utile, en fonction des besoins de votre site.

![[2025-02-17_13h57_49.png]]

![[2025-02-17_13h58_02.png]]

En théorie, vous pourriez très bien enregistrer votre page avec l'extension `.html`  :  `header.html`  .

![[2025-02-17_13h58_40.png]]

Maintenant que vos « morceaux de pages » sont prêts :

1. Reprenez les pages de votre site, par exemple la page d'accueil nommée `index.php`  .
    
2. Remplacez le menu par le code PHP suivant :

![[2025-02-17_14h01_06.png]]

Cette instruction ordonne à l'ordinateur :

> « Insère ici le contenu de la page `header.php` ».

![[2025-02-17_14h01_27.png]]

Si nous reprenons le code que nous avons vu tout à l'heure et que nous remplaçons chaque code répétitif par un `require_once(__DIR__ . '/header.php');` (lignes 10, 12 et 27), cela donne le code source suivant :

![[2025-02-17_14h03_18.png]]

![[2025-02-17_14h04_33.png]]

Nous avons vu que la page PHP était **générée** ; donc la question que vous devez vous poser est : que reçoit le visiteur ? Eh bien, il reçoit exactement le même code qu'avant !

La page finale que reçoit le visiteur est identique à celle que je vous ai montrée au début du chapitre… mais vous, vous avez énormément gagné en flexibilité, puisque votre code n'est plus recopié 150 fois inutilement.

Le nombre de  `require_once`  par page n'est pas limité ; par conséquent, vous pouvez découper votre code en autant de sous-parties que vous le souhaitez !

### Réorganisez votre site de recettes

Bon, appliquons ce que nous venons d'apprendre à notre projet, maintenant !

Nous avons besoin de fonctions et de variables pour afficher la liste de nos articles, et puisque nous aurons peut être besoin de les réutiliser (surtout les fonctions), nous allons également extraire ces concepts dans leurs propres fichiers.

Nous aurons donc deux fichiers, `variables.php` et `functions.php`  , qui contiendront respectivement les variables et les fonctions de notre projet :

![[2025-02-17_14h10_59.png]]

![[2025-02-17_14h11_24.png]]

#### Codez l'en-tête du site

Ensuite, nous aurons évidemment un en-tête de site avec un menu et un titre :

![[2025-02-17_14h11_50.png]]

Le menu est basique pour l'instant, mais il vous permet de passer de la page d'accueil à la page de contact, par exemple.

![[2025-02-17_14h13_14.png]]

Oui, la partie visuelle est assurée par le framework CSS Bootstrap 5 : il n'est pas nécessaire de le connaître pour suivre ce cours. Gardez juste en tête que chacune des classes ajoutées va permettre de concevoir la page correctement. Mais si cela vous ennuie, supprimez toutes les classes et le projet restera fonctionnel, c'est promis !

#### Codez le pied de page du site

Cette partie du site reste "ferrée" en bas de page, et contient quelques liens et surtout les conditions d'utilisation du site (les fameux "copyrights") :

![[2025-02-17_14h14_24.png]]

#### Codez le corps de la page d'accueil du site

Maintenant, nous pouvons reprendre ce que nous avions construit ensemble dans les chapitres précédents. Nous allons avoir besoin d'inclure nos variables et nos fonctions :

![[2025-02-17_14h15_07.png]]

Pressé(e) de voir le résultat ?

![[2025-02-17_14h24_31.png]]


#### Codez le corps de la page de contact du site

En bonus, nous pourrions ajouter un simple formulaire HTML.

Nous verrons dans les prochains chapitres comment les traiter avec PHP de manière à avoir une navigation fonctionnelle.

Rien d'extraordinaire, voici la page de contact à ce stade du projet :

![[2025-02-17_14h37_13.png]]

### **Exercez-vous**

Testez le code de notre projet fil rouge !

- Vérifiez si la page d’accueil s’affiche avec les deux recettes.
    
- En cliquant sur le lien 'Contact' dans le menu, vous devriez voir le formulaire s'afficher.

![[2025-02-17_14h37_43.png]]

### En résumé

- Une page PHP peut inclure une autre page (ou un morceau de page) grâce à l'instruction  `require_once`  .
    
- L'instruction `require_once` sera remplacée par le contenu de la page demandée.
    
- Cette technique, très simple à mettre en place, permet par exemple de placer les menus de son site dans un fichier `header.php` que l'on inclura dans toutes les pages. Cela permet de centraliser le code des menus, alors qu'on était auparavant obligés de le copier dans chaque page sur nos sites statiques en HTML et CSS.