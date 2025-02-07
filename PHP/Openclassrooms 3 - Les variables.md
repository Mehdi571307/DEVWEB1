
Pour pouvoir développer notre projet de partage, nous allons avoir besoin de structurer votre application autour d'objets qui la composent. C'est ce qu'on appelle des objets "métiers".

Pour un site de partage de recettes de cuisine, c'est simple :

- Des utilisateurs se connectent : ils ont un nom, un e-mail, un mot de passe, un âge...
    
- Ils consultent ou créent des recettes : elles ont un titre, un corps (la recette), un statut d'activation...
    
- Et ainsi de suite pour chacun des objets qui constituent votre projet.
### Comprenez ce qu'est une variable

Rien qu'avec leur nom, vous devez vous dire que c'est quelque chose qui change tout le temps.

En effet, le propre d'une variable c'est de pouvoir **varier**.

![[2025-02-07_11h20_32.png]]

C'est à vous de créer des variables. Vous en créez quand vous en avez besoin pour retenir des informations.

#### Donnez toujours un nom et une valeur aux variables

Une variable est toujours constituée de deux éléments :

- **son nom** : pour pouvoir la reconnaître, vous devez donner un nom à votre variable. Par exemple `age`  ;
    
- **sa valeur** : c'est l'information qu'elle contient, et qui peut changer. Par exemple :  `17`  .
    

Ici, je vous ai donné l'exemple d'une variable appelée `age`  qui a pour valeur  `17`  .

On peut modifier quand on veut la valeur de cette variable, faire des opérations dessus, etc. Et quand on en a besoin, on l'appelle (par son nom), et elle nous dit gentiment la valeur qu'elle contient.

Maintenant que vous comprenez ça, allons plus loin : il existe différents types de variables.

#### Découvrez les différents types de variables

![[2025-02-07_11h21_58.png]]


- **Les chaînes de caractères (`string`)** : c'est le nom informatique qu'on donne au texte. 
    
- **Les nombres entiers (`int`)** : ce sont les nombres du type 1, 2, 3, 4, etc. On compte aussi parmi eux les entiers relatifs : -1, -2, -3…
    
- **Les nombres décimaux (`float` )** : ce sont les nombres à virgule, comme 14,738. Attention, les nombres doivent être écrits avec un point au lieu de la virgule (c'est la notation anglaise).
    
- **Les booléens (`bool` )** : c'est un type très important qui permet de stocker soit vrai soit faux. 
    
- **Rien (`NULL` )** : aussi bizarre que cela puisse paraître, on a parfois besoin de dire qu'une variable ne contient rien. Ce n'est pas vraiment un type de données, mais plutôt **l'absence** de type.
    

Cela devrait vous donner une idée de tout ce que PHP est capable de stocker en mémoire. Ces types suffiront pour la création de notre site !


### Affectez une valeur à une variable

Regardez ce code d'exemple :

![[2025-02-07_11h23_17.png]]

Avec ce code PHP, on vient en fait de créer une variable :

- son nom est `userAge`  ;
    
- sa valeur est `17`  .

![[2025-02-07_11h23_58.png]]

Analysons dans le détail le code qu'on vient de voir.

- D'abord, on écrit le symbole "dollar" (`$`) : il précède toujours le nom d'une variable. C'est comme un signe de reconnaissance, si vous préférez : ça permet de dire à PHP "J'utilise une variable". 
    
- Ensuite, il y a le signe "égal" (`=` ) : celui-là, c'est logique, c'est pour dire que  `$userAge`  est égal à…
    
- À la suite, il y a la valeur de la variable, ici 17.
    
- Enfin, il y a l'incontournable point-virgule ( `;`) qui permet de terminer l'instruction.

![[2025-02-07_11h25_03.png]]

Supposons maintenant que l'on écrive ceci :

![[2025-02-07_11h25_38.png]]


### Utilisez les types de données

Vous vous souvenez des types de données dont je vous ai parlé il y a quelques minutes ? Les`string` , `int` , `float` ...

Voici un exemple de variable pour chacun de ces types.

#### Le type `string`  (chaîne de caractères)

Pour cela, vous devez entourer votre texte de :

- guillemets doubles  `""`  ;
    
- ou de guillemets simples `''`  (attention, ce sont des apostrophes).
    

Par exemple, pour conserver en mémoire les noms et mails de nos utilisateurs :

![[2025-02-07_11h27_05.png]]

![[2025-02-07_11h27_50.png]]

Voici un exemple pour bien comprendre :

![[2025-02-07_11h28_15.png]]

En effet, si vous oubliez de mettre un antislash, PHP va croire que c'est la fin de la chaîne et il ne comprendra pas le texte qui suivra (et vous aurez en fait un message `Parse error`).

Vous pouvez en revanche insérer sans problème des guillemets simples au milieu de guillemets doubles, et inversement :

![[2025-02-07_11h29_02.png]]

La différence est subtile, faites attention. Il y a d'ailleurs une différence plus importante entre les deux types de guillemets, dont nous parlerons plus loin.

#### Le type `int`  (nombre entier)

Il suffit tout simplement d'écrire le nombre que vous voulez stocker, sans guillemets :

![[2025-02-07_11h29_39.png]]

#### Le type `float`  (nombre décimal)

Vous devez écrire votre nombre avec un point au lieu d'une virgule. C'est la notation anglaise.

![[2025-02-07_11h30_06.png]]

#### Le type `bool`  (booléen)

Pour dire si une variable vaut vrai ou faux, vous devez écrire le mot `true`  ou `false`  sans guillemets autour (ce n'est pas une chaîne de caractères !) :

![[2025-02-07_11h30_33.png]]

#### Une variable vide avec `NULL`

Si vous voulez créer une variable qui ne contient rien, vous devez lui passer le mot-clé `NULL`  (vous pouvez aussi l'écrire en minuscules :  `null`  ).

![[2025-02-07_11h31_42.png]]

Cela sert simplement à indiquer que la variable ne contient rien, tout du moins pour le moment.

Bon, nous avons appris à créer des variables et à stocker des informations à l'intérieur. Mais pour le moment, aucun de nos codes sources n'affiche quoi que ce soit.

Voyons donc comment faire.

### Affichez le contenu d'une variable

Vous vous souvenez que l'on peut afficher du texte avec `echo`  ?

On peut aussi s'en servir pour afficher la valeur d'une variable !

![[2025-02-07_11h32_31.png]]

Comme vous le voyez, il suffit d'écrire le nom de la variable que vous voulez afficher.
Quand il s'agit d'une variable, on ne met pas de guillemets autour.

### Concaténez une variable

Non, ce n'est pas une insulte. Cela signifie **assemblage**. ;-)

![[2025-02-07_11h34_31.png]]

Les petits malins auront l'idée d'écrire trois instructions `echo`  :

![[2025-02-07_11h35_00.png]]


Vous pouvez tester et vérifier dans votre navigateur que ça fonctionne.

Mais il y a plus malin : on peut tout faire sur une ligne.

Pour cela, il y a deux méthodes :

1. Avec des guillemets simples.
    
2. Ou avec guillemets doubles.
    

Et c'est là qu'on va voir, qu'entre les deux, il y a une différence !

#### **Effectuez l'interpolation avec des guillemets doubles**

L'interpolation en PHP vous permet d'inclure directement des variables dans une chaîne de caractères sans avoir à les concaténer séparément, ce qui rend votre code plus lisible et concis.

Concrètement, essayez ce code :

![[2025-02-07_11h38_16.png]]

Ça affiche :  Bonjour Mathieu Nebra et bienvenue sur le site !

![[2025-02-07_11h39_04.png]]

En effet, lorsque vous utilisez des guillemets doubles, les variables qui se trouvent à l'intérieur sont analysées et remplacées par leur vraie valeur.

Pratique, non?

#### **Concaténez avec des guillemets simples**

Si vous écrivez le code précédent entre guillemets simples, vous allez avoir une drôle de surprise :

![[2025-02-07_11h40_30.png]]

Ça affiche :   `Bonjour {$fullname} et bienvenue sur le site !`

On ne peut concaténer du texte avec des guillemets simples, il faut écrire la variable en dehors des guillemets et séparer les éléments les uns des autres à l'aide d'un point. Regardez :

![[2025-02-07_11h42_49.png]]

Cette fois, ça affiche bien comme on voulait.

Dans quels cas devrais-je utiliser l'interpolation ou la concaténation ?

En règle générale, on utilise l'interpolation lorsqu'on a besoin d'incorporer des variables directement dans une chaîne de caractères de manière propre et concise. C'est idéal pour rendre le code plus lisible.

En revanche, s'il y a des expressions complexes, des conditions ou des opérations à effectuer pendant la concaténation, alors la concaténation traditionnelle avec des guillemets simples reste une option solide. L'essentiel est de choisir l'approche qui rend le code le plus clair et le plus maintenable en fonction du contexte du projet.

### Faites des calculs simples

On va maintenant faire travailler votre ordinateur, et vous allez voir qu'il encaisse les calculs sans broncher. Eh oui, PHP sait aussi faire des calculs !  
Oh je vous rassure : on ne va pas faire des calculs tordus, juste des additions, des soustractions, des multiplications et des divisions. C'est du niveau de tout le monde, non ? 😬😄

Ici, comme vous vous en doutez, on ne va travailler que sur des variables qui contiennent des nombres.

#### Les opérations de base : addition, soustraction…

Les signes à connaître pour faire les quatre opérations de base (vous les trouverez sur votre pavé numérique, à droite du clavier, en principe) sont représentés par le tableau suivant. En complément vous avez l'opération modulo, c'est-à-dire le reste d'une division euclidienne.

|Symbole|Signification|
|---|---|
|+|Addition|
|-|Soustraction|
|*|Multiplication|
|/|Division|
|%|Modulo|

Après, pour vous en servir, ça coule de source. Voici quelques exemples :

![[2025-02-07_11h45_56.png]]

Vérifiez mes calculs : comme vous pouvez le voir il n'y a rien de bien compliqué dans tout ça.

Seulement, il ne faut pas avoir peur de « jongler » avec les variables.  
Voici des calculs avec plusieurs variables :

![[2025-02-07_11h48_27.png]]

C'est de la pure logique, je ne peux rien vous dire de plus.  
Si vous avez compris ces bouts de code, vous avez tout compris.


#### Le modulo

Il est possible de faire un autre type d'opération un peu moins connu : le **modulo**. Cela représente le reste de la division entière.

Par exemple, 6 / 3 = 2 et il n'y a pas de reste. En revanche, 7 / 3 = 2 (car le nombre 3 « rentre » 2 fois dans le nombre 7) et il reste 1. Vous avez fait ce type de calculs à l'école primaire, souvenez-vous !

Le modulo permet justement de récupérer ce reste :

![[2025-02-07_11h50_14.png]]


Je passe sous silence les opérations plus complexes telles que :

- la racine carrée ;
    
- l'exponentielle ;
    
- la factorielle ;
    
- etc.
    

Toutes ces opérations peuvent être réalisées en PHP mais il faudra passer par ce qu'on appelle des fonctions, une notion que l'on découvrira plus tard. Les opérations basiques que l'on vient de voir sont amplement suffisantes pour la programmation PHP de tous les jours.

### En résumé

- Une variable est une petite information qui reste stockée en mémoire le temps de la génération de la page PHP. Elle a un nom et une valeur.
    
- Il existe plusieurs types de variables qui permettent de stocker différents types d'informations : du texte ( `string`  ), des nombres entiers ( `int`  ), des nombres décimaux (`float`), des booléens pour stocker vrai ou faux ( `bool`  ), etc.
    
- En PHP, un nom de variable commence par le symbole dollar : `$age`  , par exemple.
    
- La valeur d'une variable peut être affichée avec l'instruction `echo`  .
    
- Il est possible de faire des calculs mathématiques entre plusieurs variables : addition, soustraction, multiplication…