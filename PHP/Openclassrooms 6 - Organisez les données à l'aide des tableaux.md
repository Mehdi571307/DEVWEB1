
![[2025-02-09_12h18_40.png]]

On peut faire énormément de choses avec les tableaux, et leur utilisation n'est pas toujours très facile. Cependant, ils vont très rapidement nous devenir indispensables et vous devez bien comprendre leur fonctionnement pour la suite du cours, qui s'annonce concrète et passionnante.

Mais restez concentré sur votre projet : nous allons profiter de ce chapitre pour réaliser l'affichage de la liste des recettes.

Un tableau est une variable. Mais une variable un peu spéciale.

Reprenons : jusqu'ici vous avez travaillé avec des variables simples : elles ont un nom et une valeur. Par exemple :

![[2025-02-09_12h19_46.png]]

Ce qui peut se matérialiser sous la forme :

|Nom|Valeur|
|---|---|
|`$recipeTitle`|Cassoulet|

Ici, nous allons voir qu'il est possible d'enregistrer de nombreuses informations dans une seule variable grâce aux tableaux. On en distingue deux types :

1. Les tableaux numérotés.
    
2. Et les tableaux associatifs.
    

### Familiarisez vous avec les tableaux numérotés

Ces tableaux sont très simples à imaginer. Regardez par exemple celui-ci, contenu de la variable`$recipes` :

|Clé|Valeur|
|---|---|
|0|Cassoulet|
|1|Couscous|
|2|Escalope milanaise|
|3|Salade César|
|4|Bo bun|
|…|…|

![[2025-02-09_12h23_18.png]]

![[2025-02-09_12h23_34.png]]

#### Construisez un tableau numéroté

Pour créer un tableau numéroté en PHP, on liste ses valeurs entre crochets`[]`  .

Cet exemple vous montre comment créer l'array `$recipes` :

![[2025-02-09_12h24_24.png]]

L'ordre a beaucoup d'importance :

1. Le premier élément (« Cassoulet») aura le n° 0.
    
2. Ensuite Couscous le n° 1.
    
3. Etc.
    

Vous pouvez aussi créer manuellement le tableau, case par case :

![[2025-02-09_12h24_45.png]]

Si vous ne voulez pas avoir à écrire vous-même le numéro de la case que vous créez, vous pouvez laisser PHP le sélectionner automatiquement en laissant les crochets vides :

![[2025-02-09_12h29_03.png]]

#### Affichez un tableau numéroté

Pour afficher un élément, il faut donner sa position entre crochets après  `$recipes`    .

Cela revient à dire à PHP :

> « Affiche-moi le contenu de la case n° 1 de `$recipes` »

Pour faire cela en PHP, il faut écrire le nom de la variable, suivi du numéro entre crochets.

Pour afficher « Couscous », on doit donc écrire :

![[2025-02-09_12h31_00.png]]

C'est tout bête : du moment que vous n'oubliez pas que Couscous est en seconde position et donc qu'il a le numéro 1 (étant donné qu'on commence à compter à partir de 0).

![[2025-02-09_12h31_26.png]]

### Familiarisez vous avec les tableaux associatifs

![[2025-02-09_12h32_13.png]]

Notre objectif ici est d'utiliser un tableau pour décrire une recette, comme nous l'avions fait dans le chapitre précédent.

![[2025-02-09_12h32_31.png]]

C'est là que les tableaux associatifs deviennent utiles.

#### Construisez un tableau associatif

Pour mieux décrire notre recette sous forme de tableau, nous pouvons stocker une recette sous la forme d'un tableau associatif, dans lequel chaque clé est une propriété de la recette :

![[2025-02-09_12h36_09.png]]

![[2025-02-09_12h36_23.png]]

Vous remarquez qu'on écrit une flèche ( `=>`  ) pour dire « associé à ».

Par exemple, on dit que la propriété « title » du tableau`$recipe` a pour valeur « Cassoulet ».

Nous avons créé un tableau qui ressemble à la structure suivante :

|Clé|Valeur|
|---|---|
|title|Cassoulet|
|recipe|Étape 1 : des flageolets, Étape 2 : ...|
|author|john.doe@exemple.com|
|enabled|true|

Il est aussi possible de créer le tableau case par case, comme ceci :

![[2025-02-09_12h37_52.png]]

#### Affichez un tableau associatif

![[2025-02-09_12h38_17.png]]

Par exemple, pour extraire le titre de la recette, on devra taper :

![[2025-02-09_12h41_16.png]]

Ce code affiche : « Cassoulet ».

![[2025-02-09_12h41_40.png]]

Comme vous l'avez vu dans mes exemples, ils ne servent pas à stocker la même chose…

![[2025-02-09_12h42_03.png]]

![[2025-02-09_12h42_35.png]]

Oui, tout à fait !

Mais il fallait introduire rapidement les tableaux car qui dit "liste d'éléments", dit "boucle" !

D'ailleurs, nous allons profiter de ce chapitre pour aborder un nouveau type de boucle, comme ça, la boucle est... bouclée !

### Parcourez un tableau

Lorsqu'un tableau a été créé, on a souvent besoin de le parcourir pour savoir ce qu'il contient. Nous allons voir trois moyens d'explorer un tableau :

1. La boucle  `for`  .
    
2. La boucle  `foreach`  .
    
3. La fonction `print_r` (utilisée principalement pour le déboggage).
    

#### Avec la boucle `for`

Il est très simple de parcourir un tableau numéroté avec une boucle  `for`  .

Nous l'avions abordé rapidement dans le chapitre précédent avec un tableau de tableaux.

Pour rappel :

![[2025-02-09_12h44_27.png]]

![[2025-02-09_12h47_19.png]]

Exemple :

Si `$lines` vaut 1, cela signifie qu'on cherche ce que contient `$recipes[1][0]` , c'est-à-dire : Couscous.

Bravo, vous avez compris !

#### Avec la boucle `foreach`

La boucle `for`  a beau fonctionner, on peut utiliser un autre type de boucle – plus adapté aux tableaux – qu'on n'a pas encore vu jusqu'ici :  `foreach`  .

`foreach` passe en revue chaque ligne du tableau. Lors de chaque passage, elle met la valeur de cette ligne dans une variable temporaire (par exemple `$element`  ).

Je parle chinois ? Regardez plutôt :

![[2025-02-09_12h49_19.png]]

C'est le même code que tout à l'heure, mais cette fois basé sur une boucle  `foreach`  .

À chaque tour de boucle, la valeur de l'élément suivant est mise dans la variable  `$recipe`  .

On peut donc utiliser `$recipe` uniquement à l'intérieur de la boucle, pour afficher l'élément en cours.

L'avantage de `foreach` , c'est qu'il permet aussi de parcourir les tableaux associatifs.

![[2025-02-09_12h52_06.png]]

`foreach` va mettre tour à tour dans la variable `$value`  :

- le titre de la recette ;
    
- les étapes de la recette ;
    
- l'auteur ;
    
- et la réponse à "enabled"...
    

… contenus dans le tableau `$recipe` 

On met donc entre parenthèses :

1. D'abord le nom du tableau, ici `$recipe`  .
    
2. Ensuite le mot-clé `as`  (qui signifie « en tant que »).
    
3. Enfin, le nom d'une variable que vous choisissez, et qui va contenir tour à tour chacune des valeurs du tableau, ici `$value`  .

![[2025-02-09_12h55_00.png]]

L'intérêt devient encore plus flagrant quand nous utilisons un tableau de tableaux :

![[2025-02-09_12h55_24.png]]

Qui produit le résultat suivant :

![[2025-02-09_12h55_50.png]]

![[2025-02-09_13h02_24.png]]

Toutefois, avec cet exemple, on ne récupère que la valeur. **Or, on peut aussi récupérer la clé de l'élément.** On doit dans ce cas écrire `foreach`  , comme ceci :

![[2025-02-09_13h03_28.png]]

À chaque tour de boucle, on disposera non pas d'une, mais de deux variables :

1. `$property` qui contiendra la clé de l'élément en cours d'analyse (« title », « author », etc.).
    
2. `$propertyValue` qui contiendra la valeur de l'élément en cours (« Cassoulet », « laurene.castor@exemple.com », etc.).
    

Testons le fonctionnement avec un exemple :

![[2025-02-09_13h07_50.png]]

Qui aura le résultat suivant :

![[2025-02-09_13h08_10.png]]

Avec cette façon de procéder, vous avez maintenant dans la boucle la clé ET la valeur.

Et croyez-moi, `foreach` est une boucle vraiment pratique : on s'en sert régulièrement !

#### Affichez rapidement un tableau avec `print_r`

Parfois, en codant votre site en PHP, vous aurez sur les bras un tableau et vous voudrez savoir ce qu'il contient, juste pour votre information.

Vous pourriez utiliser une boucle `for`  ou mieux, une boucle  `foreach`  .

![[2025-02-09_13h08_31.png]]

Cette commande a toutefois un défaut : elle ne renvoie pas de code HTML comme `<br />` pour les retours à la ligne. Pour bien les voir, il faut donc utiliser la balise HTML `<pre>`  qui nous permet d'avoir un affichage plus correct.

![[2025-02-09_13h09_38.png]]

![[2025-02-09_13h09_56.png]]

![[2025-02-09_13h12_35.png]]

Bien entendu, vous n'afficherez jamais des choses comme ça à vos visiteurs. On peut en revanche s'en servir pour le déboggage, pendant la création du site, afin de voir rapidement ce que contient le tableau.

### Recherchez dans un tableau

Nous allons maintenant faire des recherches dans des tableaux. Cela sera très utile quand vous voudrez savoir si votre tableau contient ou non certaines informations.

Nous allons voir trois types de recherches, basées sur des fonctions PHP :

1. `array_key_exists` pour vérifier si une **clé** existe dans le tableau.
    
2. `in_array` pour vérifier si une **valeur** existe dans le tableau.
    
3. `array_search` pour récupérer la clé d'une valeur dans le tableau.
    

#### Vérifiez si une clé existe dans un tableau avec `array_key_exists`

Voici notre problème : on a un array, mais on ne sait pas si la clé qu'on cherche s'y trouve.  
Pour vérifier ça, on va utiliser la fonction `array_key_exists` qui va parcourir le tableau pour nous, et nous dire s'il contient cette clé.

On doit lui donner :

4. Le nom de la clé à rechercher.
    
5. Puis le nom du tableau dans lequel on fait la recherche :
 ![[2025-02-09_13h13_49.png]]

![[2025-02-09_13h14_14.png]]

Ça nous permet de faire un test facilement avec un `if` :

![[2025-02-09_13h14_41.png]]

![[2025-02-09_13h14_54.png]]

On ne trouvera que « title », et pas « commentaires ». C'est logique : seule la première condition sera donc exécutée.

#### Vérifiez si une valeur existe dans un tableau avec `in_array`

Le principe est le même que `array_key_exists` mais cette fois on recherche dans les **valeurs**.

![[2025-02-09_13h15_13.png]]

Pour changer un peu de notre tableau `$recipes`  , je vais créer un tableau qui contient le nom des utilisateurs du site :

![[2025-02-09_13h20_11.png]]

![[2025-02-09_13h20_23.png]]

On ne voit que le message pour Mathieu, car Arlette ne fait pas partie des utilisateurs enregistrés.

#### Récupérez la clé d'une valeur dans un tableau avec `array_search`

`array_search` fonctionne comme `in_array` : il travaille sur les valeurs d'un tableau.

![[2025-02-09_13h20_44.png]]

On reprend le tableau numéroté :

![[2025-02-09_13h21_02.png]]

![[2025-02-09_13h21_19.png]]

Cela explique donc pourquoi on nous répond que Mathieu se trouve en position 0 :

![[2025-02-09_13h21_36.png]]

Voilà les fonctions qu'il fallait connaître pour faire une recherche dans un tableau. Il y en a d'autres, mais vous connaissez maintenant les principales.

### **Exercez vous** 

Avec tout ce que nous avons appris dans ce chapitre, nous pouvons améliorer le code d'affichage des recettes de notre projet fil rouge.

1. Utilisez le tableau fourni  `$recipes`  qui contient plusieurs recettes. Chaque recette possède des clés telles que  `title`  ,  `recipe`  ,  `author`  et  `is_enabled`  : 
    
 ![[2025-02-09_13h22_04.png]]

2. Pour chaque recette, vérifiez si la clé  `is_enabled`  existe dans la recette et si sa valeur est égale à vrai (  `true`  ).
    
3. Si la recette est activée (  `is_enabled`  à vrai), affichez le titre, la recette et l'auteur de la recette dans des balises HTML appropriées.
    
4. Testez votre page web : vérifiez que l’affichage est identique à l’image en dessous :


![[2025-02-09_13h22_26.png]]

![[2025-02-16_16h26_39.png]]
### En résumé

- Les tableaux (ou _arrays_) sont des variables représentées sous forme de tableau. Elles peuvent stocker de grandes quantités d'informations.
    
- Chaque ligne d'un tableau possède une clé (qui permet de l'identifier) et une valeur.
    
- Il existe deux types de tableaux :
    
    - les tableaux **numérotés** : chaque ligne est identifiée par une clé numérotée. La numérotation commence à partir de 0 ;
        
    - les tableaux **associatifs** : chaque ligne est identifiée par une courte chaîne de texte.
        
- Pour parcourir un tableau, on peut utiliser la boucle `for`  que l'on connaît déjà, mais aussi la boucle `foreach`  qui est dédiée aux tableaux.
    
- Il existe de nombreuses fonctions permettant de travailler sur des tableaux, notamment pour effectuer des recherches.
    

_Dans le prochain chapitre, nous allons aborder les fonctions PHP, et vous verrez, vous ne pourrez bientôt plus vous en passer !_