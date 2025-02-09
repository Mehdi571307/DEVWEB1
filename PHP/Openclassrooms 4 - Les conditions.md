
Dans notre projet fil rouge de création de site de recettes, on voudra afficher des informations en fonction du contexte. Par exemple :

- autoriser l'auteur d'une recette à la modifier, mais pas les autres utilisateurs ;
    
- afficher seulement la liste des recettes qui auront été vérifiées par un administrateur ;
    
- etc.
    

Les conditions, c'est ce qui va réellement vous permettre de créer une application dynamique. À la fin de ce chapitre, vous aurez les bases nécessaires pour autoriser l'affichage d'une recette ou l'accès d'un utilisateur à une page selon les conditions de votre application.

### Appropriez vous la structure de base :  `if… else`

![[2025-02-07_11h55_59.png]]

Celle que je vais vous apprendre à utiliser maintenant est la principale à connaître. Nous en verrons d'autres un peu plus loin.

Pour apprendre à utiliser `if… else`  , nous allons :

1. D'abord voir **les symboles qu'il faut connaître** : vous allez devoir retenir quelques symboles qui permettent de faire des comparaisons. Soyez attentif, car ils vous seront utiles pour les conditions.
    
2. Ensuite voir comment fonctionne une condition avec `if… else`  . Inutile de vous dire qu'il est indispensable de bien comprendre cela.
    
3. Après, on compliquera un peu nos conditions avec **les conditions multiples**. Vous allez voir en effet qu'on peut utiliser plusieurs conditions à la fois.
    
4. Et enfin, **l'astuce bonus** : parce qu'il y a toujours un bonus pour récompenser ceux qui ont bien suivi jusqu'au bout !

#### Retenez les symboles à connaître

Voici les symboles que nous serons amenés à utiliser. Essayez de bien les retenir, ils vous seront utiles :

|Symbole|Signification|
|---|---|
|===|Est égal à|
|>|Est supérieur à|
|<|Est inférieur à|
|>=|Est supérieur ou égal à|
|<=|Est inférieur ou égal à|
|!==|Est différent de|

![[2025-02-07_11h57_45.png]]


#### Utilisez la structure  `if… else`

Voici ce qu'on doit écrire, dans l'ordre, pour utiliser cette condition.

- Pour introduire une condition, on utilise le mot `if` qui signifie « si », en anglais.
    
- On ajoute à la suite entre parenthèses la condition en elle-même (vous allez voir que vous pouvez inventer une infinité de conditions).
    
- Enfin, on ouvre des accolades à l'intérieur desquelles on placera les instructions à exécuter si la condition est remplie.
    

Puisqu'un exemple vaut toujours mieux qu'un long discours :

![[2025-02-07_11h59_00.png]]

Ici, on demande à PHP :

> Si la variable `$isEnabled` est vraie, affiche « Vous êtes autorisé(e) à accéder au site ✅ ».

Vous remarquerez que dans la quasi-totalité des cas, c'est sur une variable qu'on fait la condition.

Ce qui compte ici, c'est qu'il y a deux possibilités :

1. Soit la condition est remplie et alors on affiche quelque chose.
    
2. Sinon, on saute les instructions entre accolades, on ne fait rien.
    

Bon, on peut quand même améliorer notre exemple :


![[2025-02-07_12h02_37.png]]

Tout d'abord, j'ai mis plusieurs instructions entre accolades. Ensuite, vous avez remarqué que j'ai ajouté le mot `else`  (« sinon »). 

Essayez ce bout de code en modifiant la valeur de `$isEnabled` (sur la première ligne).

Vous allez voir que le message qui s'affiche change en fonction de la valeur que vous indiquez !

Bien entendu, vous mettez les instructions que vous voulez entre accolades.

Ici, par exemple, j'ai donné une valeur différente à la variable `$isAllowedToEnter` après avoir affiché un message (une valeur qui pourrait nous servir par la suite) :

![[2025-02-07_13h22_16.png]]

La principale nouveauté ici, c'est le mot-clé `elseif`  qui signifie « sinon si ».

Dans l'ordre, PHP rencontre les conditions suivantes :

1. Si `$isAllowedToEnter` est égale à « Oui », tu exécutes ces instructions…
    
2. Sinon, si `$isAllowedToEnter` est égale à « Non », tu exécutes ces autres instructions…
    
3. Sinon, tu redemandes l'âge pour savoir si on a ou non l'autorisation d'entrer.

Pour vérifier si la variable est vide, vous pouvez taper : `if ($variable === NULL)`

#### Étudiez le cas des booléens

Si on regarde bien le dernier code source (avec `$isAllowedToEnter` ), il serait plus adapté d'utiliser des booléens.

Les booléens sont ces variables qui valent :

- soit `true`  (vrai) ;
    
- soit `false`  (faux).
    

Voici comment on teste une variable booléenne :

![[2025-02-07_13h27_51.png]]

L'un des avantages des booléens, c'est qu'ils sont particulièrement adaptés aux conditions.

Parce qu'en fait vous n'êtes pas obligé d'ajouter le`=== true`. 

PHP comprend qu'il faut qu'il vérifie si `$isAllowedToEnter` vaut `true`.

![[2025-02-08_10h24_50.png]]

En effet, si vous « lisez » la première ligne, ça donne :

> « SI on a l'autorisation d'entrer… ».

C'est donc un raccourci à connaître quand on travaille sur des booléens.

Il y a un symbole qui permet de vérifier si la variable vaut `false` : le point d'exclamation (`!`).

On écrit :

![[2025-02-08_10h25_56.png]]

![[2025-02-08_10h27_16.png]]

#### Posez des conditions multiples

Ce qu'on va essayer de faire, c'est de poser plusieurs conditions à la fois. Pour cela, on aura besoin de nouveaux mots-clés. Voici les principaux à connaître :

|Mot-clé|Signification|Symbole équivalent|
|---|---|---|
|AND|Et|&&|
|OR|Ou|\||

![[2025-02-08_10h28_58.png]]

La première colonne contient le mot-clé en anglais, la troisième son équivalent en symbole. Voici un premier exemple :

![[2025-02-08_10h32_49.png]]

C'est tout simple, en fait, et ça se comprend très bien : si l'utilisateur est actif et qu'il est l'auteur, il peut accéder à la recette validée. Sinon, il verra s'afficher un message de refus.

Bon allez, un dernier exemple avec`||`  pour que vous l'ayez vu au moins une fois, et on arrête là.

![[2025-02-08_10h33_19.png]]

Nous rajoutons une condition supplémentaire : soit la condition précédente s'applique, soit l'utilisateur concerné est un administrateur.

#### Utilisez cette astuce bonus

Avec les conditions, il y a une astuce à connaître.  
Sachez que les deux codes ci-dessous donnent exactement le même résultat :

![[2025-02-08_10h41_35.png]]

![[2025-02-08_10h41_50.png]]

Comme vous le voyez, dans le second cas on n'a pas utilisé de  `echo`  .

La syntaxe pour utiliser la condition diffère un peu :

- Il n'y a pas d'accolade.
    
- On ajoute  `:`  après la parenthèse fermante de l'instruction  `if`  .
    
- Et il faut ajouter une instruction  `endif;`  .


Nous aurons d'ailleurs bientôt l'occasion de pratiquer un peu, et vous verrez que les conditions sont souvent indispensables.

### Utilisez la condition `switch` pour optimiser votre code

En théorie, les structures à base de `if… elseif… else` que je viens de vous montrer suffisent pour traiter n'importe quelle condition.

Mais alors, pourquoi se compliquer la vie avec une autre structure ?

Pour vous montrer l'intérêt de `switch` ! Vous allez bientôt comprendre…

Regardez cet exemple à base de `if`  et de `elseif`  :

![[2025-02-08_10h44_20.png]]

Comme vous le voyez : c'est lourd, long, et répétitif.

Dans ce cas, on peut utiliser une autre structure plus souple : c'est `switch` !

Voici le même exemple avec `switch`  (le résultat est le même, mais le code est plus adapté) :

![[2025-02-08_10h45_53.png]]


Bon alors, qu'est-ce qui est différent ?

- Il y a beaucoup moins d'accolades : elles marquent seulement le début et la fin du  `switch`  .
    
- On indique au début du switch sur quelle variable on travaille, ici `$grade`. On dit à PHP :
    

> Je vais analyser la valeur de  `$grade`  .

- On utilise des `case` pour analyser chaque cas : `case 0` ,`case 10` , etc. Cela signifie :
    

> Dans le cas où la valeur est 0… Dans le cas où la valeur est 10…

L'avantage d'utiliser switch, est qu'on a plus besoin de mettre de triple égal !

Attention ! Cela ne fonctionne pas avec les autres symboles < > <= >= !==

Le `switch` ne peut tester que l'égalité.

Le mot-clé `default` à la fin est un peu l'équivalent du  `else`  .

C'est le message qui s'affiche par défaut, quelle que soit la valeur de la variable.


Il y a cependant une chose importante à savoir :

Supposons dans notre exemple que la note soit de 10.

PHP va lire :

> `case 0` ? Non. Je saute. 
> 
> `case 5` ? Non plus. Je saute. 
> 
> `case 7` ? Non plus. Je saute. 
> 
> `case 10` ? Oui, j'exécute les instructions.


![[2025-02-08_10h59_49.png]]

Pour empêcher cela, utilisez l'instruction `break`

![[2025-02-08_11h00_16.png]]

En pratique, on utilise très souvent un `break` car sinon, PHP lit des instructions qui suivent et qui ne conviennent pas.

Essayez d'enlever les `break` dans le code précédent, vous allez comprendre pourquoi ils sont indispensables !


![[2025-02-08_11h01_23.png]]


C'est surtout un problème de présentation et de clarté :

1. Pour une condition simple et courte, on utilise le  `if`  .
    
2. Et quand on a une série de conditions à analyser, on préfère utiliser `switch` pour rendre le code plus clair.
    

### Découvrez les ternaires : des conditions condensées

Il existe une autre forme de condition, beaucoup moins fréquente, mais que je vous présente quand même car vous pourriez un jour ou l'autre tomber dessus. Il s'agit de ce qu'on appelle les **ternaires**.

![[2025-02-08_11h02_27.png]]

Prenons cet exemple à base de `if… else`  qui met un booléen `$majeur`  à vrai ou faux selon l'âge du visiteur :

![[2025-02-08_11h04_19.png]]

On peut faire la même chose en une seule ligne grâce à une structure ternaire :

![[2025-02-08_11h05_43.png]]

Ici, tout notre test précédent a été fait sur une seule ligne !

La condition testée est `$userAge >= 18`  .

Si c'est vrai, alors la valeur indiquée après le point d'interrogation (ici `true`) sera affectée à la variable  `$isAdult`  .

Sinon, c'est la valeur qui suit le symbole `:` (ici `false` ) qui sera affectée à  `$isAdult`  .

C'est un peu tordu, mais ça marche.

![[2025-02-08_11h08_03.png]]

### En résumé

- Les conditions permettent à PHP de prendre des décisions en fonction de la valeur des variables.
    
- La forme de condition la plus courante est `if`  ...  `elseif`  ... `else`  qui signifie « si »… « sinon si »… « sinon ».
    
- On peut combiner des conditions avec les instructions`&&`  (« et ») et`||`  (« ou »).
    
- Si une condition comporte de nombreux `elseif` , il peut être plus pratique d'utiliser la condition `switch`.
    
- Les ternaires sont des conditions condensées qui font un test sur une variable, et en fonction des résultats de ce test, elles donnent une valeur à une autre variable. Elles sont cependant plus rarement utilisées.