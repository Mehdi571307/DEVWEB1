
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

