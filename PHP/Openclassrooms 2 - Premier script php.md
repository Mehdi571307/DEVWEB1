
Le code source d'une page HTML est constitué de **balises** (aussi appelées **tags**, en anglais). Par exemple, `<ul>`  est une balise.

Le code PHP viendra s'insérer au milieu du code HTML. On va progressivement placer dans nos pages web des morceaux de code PHP à l'intérieur du HTML. Ces bouts de code PHP seront les parties dynamiques de la page, c'est-à-dire les parties qui peuvent changer toutes seules.

Le code suivant illustre cela :

![[2025-02-07_09h51_07.png]]

Comme vous pouvez le voir, on retrouve le code HTML que l'on connaît bien… et on insère en plus des données dynamiques au milieu. Ici, par exemple, c'est le pseudonyme : il change en fonction du visiteur.

#### Reconnaissez la forme d'une balise PHP

Si je vous parle de cela, ce n'est pas par hasard. Pour utiliser du PHP, on va devoir introduire une nouvelle balise… et celle-ci est un peu spéciale.

1. Elle commence par  `<?php` 
    
2. Et se termine par`?>`   
    

C'est à l'intérieur que l'on mettra du code PHP (ce que je vais vous apprendre tout au long de ce cours).

Voici une balise PHP vide :

![[2025-02-07_09h51_45.png]]

À l'intérieur, on écrira donc du code source PHP :

![[2025-02-07_09h52_10.png]]

On peut sans problème écrire la balise PHP sur plusieurs lignes.

En fait, c'est même indispensable car la plupart du temps, le code PHP fera plusieurs lignes.

Cela donnera quelque chose comme :

![[2025-02-07_09h52_32.png]]

![[2025-02-07_09h53_11.png]]

#### Insérez une balise PHP au milieu du code HTML

La balise PHP que nous venons de découvrir s'insère au milieu du code HTML, comme je vous l'ai dit plus tôt. Pour reprendre l'exemple que l'on a vu au chapitre précédent :

![[2025-02-07_09h53_51.png]]

On peut placer une balise PHP n'importe où dans le code. Pas seulement dans le corps de la page, d'ailleurs : vous pouvez placer une balise PHP dans l'en-tête de la page (regardez la ligne 4 de l'exemple ci-dessous).

![[2025-02-07_09h59_19.png]]

Il faut se rappeler que PHP génère du code HTML. Nous allons mieux comprendre le fonctionnement en apprenant à afficher du texte en PHP.

### Affichez du texte

Grande nouvelle : c'est maintenant que vous allez apprendre votre première instruction en PHP.

Ne vous attendez pas à quelque chose d'extraordinaire, votre PC ne va pas se mettre à danser la samba tout seul. 😄

Vous allez cependant un peu mieux comprendre comment le PHP fonctionne, c'est-à-dire comment il génère du code HTML. Il est indispensable de bien comprendre cela ; soyez donc attentif !

#### Utilisez l'instruction `echo`

Le PHP est un langage de programmation, ce qui n'était pas le cas du HTML. Dans ce cours, nous partons de zéro et donc je vais supposer que vous n'avez jamais fait de programmation auparavant.

![[2025-02-07_10h01_06.png]]

Ici, la première instruction que nous allons découvrir permet d'insérer du texte dans la page web. Il s'agit de l'instruction echo, la plus simple et la plus basique de toutes les instructions que vous devez connaître.

Voici un exemple d'utilisation de cette instruction :

![[2025-02-07_10h47_28.png]]


Comme vous le voyez, à l'intérieur de la balise PHP on écrit l'instruction `echo`  suivie du texte à afficher entre guillemets. Les guillemets permettent de délimiter le début et la fin du texte, ce qui aide l'ordinateur à se repérer.

L'instruction se termine par un point-virgule comme je vous l'avais annoncé, ce qui signifie "**Fin de l'instruction**".

C'est beaucoup plus rare, mais l'instruction `echo` peut être entourée de parenthèses ouvrantes et fermantes : nous reviendrons là-dessus dans le chapitre sur les fonctions.

Il faut savoir qu'on a aussi le droit de demander d'afficher des balises. Par exemple, le code suivant fonctionne :

![[2025-02-07_10h49_22.png]]

Le mot « texte » sera affiché en gras grâce à la présence des balises `<strong>`  et `</strong>`  .

Si vous mettez un guillemet, ça veut dire pour l'ordinateur que le texte à afficher s'arrête là. Vous risquez au mieux de faire planter votre beau code et d'avoir une terrible « Parse error ».

La solution consiste à faire précéder le guillemet d'un antislash  `\`  :

![[2025-02-07_10h50_25.png]]

Vous savez que le code PHP s'insère au milieu du code HTML. Alors allons y, prenons une page basique en HTML et plaçons y du code PHP (ligne 12).

![[2025-02-07_10h51_02.png]]


Testez ce code et admirez : la date et l'heure s'affichent automatiquement sur la page web !

![[2025-02-07_11h00_43.png]]


### Commentez votre code

Avant de terminer ce chapitre, je tiens à vous parler de quelque chose qui à mes yeux a une très grande importance quand on développe des programmes : les commentaires.

Ce texte est ignoré, c'est-à-dire qu'il disparaît complètement lors de la génération de la page. Il n'y a que vous qui voyez ce texte.

Cela permet de vous y retrouver dans votre code PHP, parce que si vous n'y touchez pas pendant des semaines et que vous y revenez, vous risquez d'être un peu perdu.

Vous pouvez écrire tout et n'importe quoi, le tout est de s'en servir à bon escient.

Il existe deux types de commentaire :

1. Les commentaires **monolignes**.
    
2. Les commentaires **multilignes**.
    

Tout dépend de la longueur de votre commentaire. Je vais vous présenter les deux.

#### Faites des commentaires monolignes

Pour indiquer que vous écrivez un commentaire sur une seule ligne, vous devez taper deux slashs : « `//`  ». Tapez ensuite votre commentaire.  
Un exemple ?

![[Pasted image 20250207110223.png]]

Je vous ai mis deux commentaires à des endroits différents :

- le premier est à la fin d'une ligne ;
    
- le second est sur toute une ligne.
    

À vous de voir où vous placez vos commentaires : si vous commentez une ligne précise, mieux vaut mettre le commentaire à la fin de cette ligne.

#### Faites des commentaires multilignes

Ce sont les plus pratiques si vous pensez écrire un commentaire sur plusieurs lignes, mais on peut aussi s'en servir pour écrire des commentaires d'une seule ligne. Il faut commencer par écrire `/*`  puis refermer par `*/`  :

![[2025-02-07_11h03_25.png]]


Ici, les commentaires n'ont pas grande utilité, mais vous verrez de quelle façon je les utilise dans les prochains chapitres pour vous décrire le code PHP.

### En résumé

- Les pages web contenant du PHP ont l'extension `.php` 
    
- Une page PHP est une simple page HTML qui contient des instructions en langage PHP.
    
- Les instructions PHP sont placées dans une balise ouvrante et fermante : `<?php ?>`  
    
- Pour afficher du texte en PHP, on utilise l'instruction `echo`  
    
- Il est possible d'ajouter des commentaires en PHP pour décrire le fonctionnement du code. On utilise pour cela les symboles `//` ou `/* */`







