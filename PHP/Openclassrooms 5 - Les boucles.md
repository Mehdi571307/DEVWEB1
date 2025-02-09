
Dans notre site de partage de recettes de cuisine, vous aurez sûrement envie de donner la possibilité à vos utilisateurs de commenter les recettes.

Pour cela, nous allons utiliser des tableaux.

Les tableaux sont des structures capables de conserver en mémoire plusieurs éléments. Et c'est ensuite grâce aux boucles que nous allons pouvoir :

1. Parcourir les différentes recettes.
    
2. Les afficher à l'aide du langage HTML.

![[2025-02-08_11h12_12.png]]

À la fin de ce chapitre, non seulement vous saurez parcourir une liste d'éléments, mais vous aurez également commencé à construire pour de bon votre application.

### Utilisez un tableau pour lister des éléments

Reprenons notre projet là où nous l'avions laissé au chapitre précédent.

Nous avons :

- des utilisateurs ;
    
- des recettes ;
    
- et peut-être des commentaires.
    

Avec les connaissances que vous avez pour le moment, voici comment vous pourriez définir deux utilisateurs :

![[2025-02-08_11h14_16.png]]

![[2025-02-08_11h14_34.png]]

Par exemple, voici un premier tableau :

![[2025-02-08_11h14_57.png]]

Notez pour le moment que :

- un tableau se déclare entre crochets : `[ ]` ;
    
- il possède des indices : 0, 1, 2, … ;
    
- on peut accéder à un élément du tableau à partir de ces clés.

Les indices d'un tableau commencent à 0, et pas à 1.

Mais la puissance des tableaux ne s'arrête pas là !

Vous pouvez construire des tableaux de tableaux :

![[2025-02-08_11h15_45.png]]

### Utilisez une boucle simple :  `while`

![[2025-02-08_11h17_02.png]]

On peut, si vous voulez, présenter le principe avec le schéma suivant :

![[2025-02-08_11h17_40.png]]

Voilà ce qui se passe dans une boucle :

1. Comme d'habitude, les instructions sont d'abord exécutées dans l'ordre, de haut en bas.
    
2. À la fin des instructions, on retourne à la première.
    
3. On recommence à lire les instructions dans l'ordre.
    
4. Et on retourne à la première, etc.

![[2025-02-08_11h18_26.png]]

Voici comment faire avec une boucle simple :  `while`  .

![[2025-02-08_11h19_02.png]]

`while`  peut se traduire par « tant que ».

Ici, on demande à PHP :

> TANT QUE `$isValid` est vrai, exécuter ces instructions.

Les instructions qui sont répétées en boucle se trouvent entre les accolades `{`  et  `}`  .

Mais bon, là je ne vous apprends rien, vous commencez à avoir l'habitude de voir des accolades partout. 🤓

Et voilà, il n'y a guère plus de choses à savoir. Cependant, je vais quand même vous montrer un ou deux exemples d'utilisation de boucles, pour que vous voyiez à quoi ça peut servir.

Pour notre premier exemple, on va supposer que vous avez été puni et que vous devez recopier 100 fois :

> « Je ne dois pas regarder les mouches voler quand j'apprends le PHP ».

Avant, il fallait prendre son mal en patience et ça prenait des heures… Avec PHP, on va faire ça en un clin d'œil !

Regardez ce code :

![[2025-02-08_11h20_35.png]]

Ce qui affiche... un grand nombre de lignes :

![[2025-02-08_11h22_26.png]]

La boucle pose la condition :

> TANT QUE `$lines` est inférieur ou égal à 100.

Dans cette boucle, il y a deux instructions :

1. `echo` permet d'afficher du texte en PHP. À noter qu'il y a une balise HTML `<br />`  à la fin : cela permet d'aller à la ligne (vu que vous connaissez le HTML, ça n'a rien de surprenant : chaque phrase sera écrite sur une seule ligne).
    
2. `$lines++;` est une façon plus courte d'ajouter 1 à la variable. On appelle cela **l'incrémentation** (ce nom barbare signifie tout simplement que l'on a ajouté 1 à la variable).
    

Chaque fois qu'on fait une boucle, la valeur de la variable augmente : 1, 2, 3, 4… 99, 100…

Dès que la variable atteint 101, on arrête la boucle.

Et voilà, on a écrit 100 lignes en un clin d'œil.

Si la punition avait été plus grosse, pas de problème ! Il aurait suffi de changer la condition, par exemple : mettre **« TANT QUE c'est inférieur ou égal à 500 »** pour l'écrire 500 fois.

![[2025-02-08_11h23_37.png]]

Nous venons donc de voir comment afficher une phrase plusieurs centaines de fois sans effort.

![[2025-02-08_11h24_23.png]]

Pas vraiment, mais nous apprenons ici des techniques de base que l'on va pouvoir réutiliser plus tard dans ce cours. Imaginez à la fin que ce système de boucle va vous permettre de demander à PHP d'afficher d'une seule traite tous les messages de votre forum. Bien sûr, il vous faudra d'autres connaissances pour y parvenir, mais sans les boucles vous n'auriez rien pu faire !

Je vous demande pour le moment de pratiquer et de comprendre comment ça marche.

On peut écrire de la même manière une centaine de lignes, mais chacune peut être différente : on n'est pas obligé d'écrire la même chose à chaque fois.

Cet exemple devrait vous montrer que la valeur de la variable augmente à chaque passage dans la boucle :

![[2025-02-08_11h27_05.png]]

Voilà, c'est tout bête, et cet exemple ressemble beaucoup au précédent.

La particularité, là, c'est qu'on affiche à chaque fois la valeur de  `$lines`  .

Cela vous permet de voir que sa valeur augmente petit à petit.

![[2025-02-08_11h28_09.png]]

![[2025-02-08_11h28_31.png]]

On va l'aborder en détail dans le chapitre suivant ; en attendant, voici le code fonctionnel :

![[2025-02-08_11h28_58.png]]


![[2025-02-08_11h37_25.png]]

### Découvrez une boucle plus complexe :  `for`

Mais non, n'ayez pas peur, voyons.  
Il ne vous arrivera rien de mal : ici le mot « complexe » ne veut pas dire « compliqué ».

![[2025-02-09_10h14_29.png]]

Cependant, sachez que `for`  et `while`  donnent le même résultat et servent à la même chose : répéter des instructions en boucle.

L'une peut paraître plus adaptée que l'autre dans certains cas ; cela dépend aussi des goûts.


Ça ressemble beaucoup au `while` mais c'est la première ligne qui est un peu particulière.

Pour voir la différence avec le `while` , reprenons l'exemple précédent, cette fois avec un `for` :

![[2025-02-09_10h15_48.png]]


Que de choses dans une même ligne !

Bon, vous vous en doutez : je vais vous analyser la ligne du `for` uniquement (le reste n'a pas changé).

Après le mot `for`  , il y a des parenthèses qui contiennent trois éléments, séparés par des points-virgules `;`  :

1. Le premier sert à l'**initialisation**. C'est la valeur que l'on donne au départ à la variable (ici, elle vaut 0).
    
2. Le second, c'est la **condition**. Comme pour le `while` : tant que la condition est remplie, la boucle est réexécutée. Dès que la condition ne l'est plus, on en sort.
    
3. Enfin, le troisième c'est l'**incrémentation**. Cela permet d'ajouter 1 à la variable à chaque tour de boucle.
    

Les deux derniers codes donnent donc exactement le même résultat :

- le `for` fait la même chose que le  `while`  ;
    
- … mais il rassemble sur une seule ligne tout ce qu'il faut savoir sur le fonctionnement de la boucle.

![[2025-02-09_10h19_40.png]]

`while`  est plus simple et plus flexible : on peut faire tous les types de boucles avec, mais on peut oublier de faire certaines étapes, comme l'incrémentation de la variable.

`for`  est bien adapté quand on doit compter le nombre de fois que l'on répète les instructions, et il permet de ne pas oublier de faire l'incrémentation pour augmenter la valeur de la variable !

Si vous hésitez entre les deux, il suffit simplement de vous poser la question suivante : « **Est-ce que je sais d'avance combien de fois je veux que mes instructions soient répétées ?** ».

Si la réponse est oui, alors la boucle `for`  est tout indiquée.

Sinon, alors il vaut mieux utiliser la boucle `while` .

### Affichez des recettes

Reprenons ce que nous avions dit sur les recettes.

Une recette, c'est :

- un titre ;
    
- un auteur ;
    
- un statut activé ;
    
- et des instructions (la recette à suivre).
    

Le code de votre application à ce stade pourrait être le suivant (avec des recettes d'exemple, bien sûr) :

![[2025-02-09_10h26_38.png]]

Pour le rendu suivant :

![[2025-02-09_10h27_00.png]]

![[2025-02-09_10h39_31.png]]

Tout à fait, comme vous pouvez le voir, c'est assez pratique !


![[2025-02-09_10h39_53.png]]

Oui, mais nous verrons cela dans le prochain chapitre !

### **Exercez-vous**

Félicitations pour avoir atteint la fin de notre chapitre sur les boucles en PHP ! C'est maintenant le moment tant attendu de mettre en pratique ce que vous avez appris au travers de notre projet fil rouge.

Vous allez créer une page web qui affiche différentes recettes en utilisant les boucles en PHP pour générer le contenu HTML.

1. Créez le fichier index.php.
    
2. Définissez un tableau en PHP contenant quatre recettes. Chaque recette devrait avoir un titre et l'auteur de la recette.
    
3. Utilisez une boucle pour parcourir le tableau de recettes.
    
4. Pour chaque recette, affichez le titre et l'auteur dans des balises HTML appropriées.
    
5. Testez votre page web : vérifiez que les quatre recettes s’affichent avec le titre et l’auteur.

![[2025-02-09_11h37_10.png]]

### En résumé

- Les boucles demandent à PHP de répéter des instructions plusieurs fois.
    
- Les deux principaux types de boucles sont :
    
    - `while` : à utiliser de préférence lorsqu'on ne sait pas par avance combien de fois la boucle doit être répétée ;
        
    - `for`  : à utiliser lorsqu'on veut répéter des instructions un nombre précis de fois.
        
- L'incrémentation est une technique qui consiste à ajouter 1 à la valeur d'une variable. La décrémentation retire au contraire 1 à cette variable. On trouve souvent des incrémentations au sein de boucles `for`  .