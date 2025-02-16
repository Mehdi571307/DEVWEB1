
# Exploitez toute la puissance des fonctions PHP

![[2025-02-16_16h31_15.png]]

Nous profiterons de ces nouvelles connaissances pour améliorer et simplifier le code de l'affichage des recettes en recoupant la liste des utilisateurs et des recettes pour afficher, non pas leur e-mail, mais directement leur nom à côté de la recette.

![[2025-02-16_16h33_40.png]]

![[2025-02-16_16h33_51.png]]

Imaginez que les fonctions sont des robots. Vous ne savez pas ce qui se passe à l'intérieur de ce robot, mais vous pouvez appuyer sur un bouton pour lui demander de faire quelque chose de précis. Avec les fonctions, c'est le même principe !

![[2025-02-16_16h34_36.png]]

### Comprenez le principe d'une fonction

Voici le genre de dialogue qu'on peut avoir avec une fonction :

> "Toi, la fonction `allowRecipe`  , dis-moi si j'ai le droit d'afficher cette recette".

La fonction effectue les calculs demandés puis répond :

> "Oui, tu peux".

En clair :

1. On donne en **entrée** à la fonction un **paramètre** sur lequel elle va faire des calculs (ici, une recette sous forme d'un tableau).
    
2. Et la fonction nous retourne en **sortie** le résultat :  `true`  .

![[2025-02-16_16h35_26.png]]

![[2025-02-16_16h35_39.png]]

Bon, ici c'était assez simple : il suffisait de vérifier la valeur de la clé  `is_enabled`  .

Mais vous serez souvent amené à faire des opérations de plus en plus complexes, et les fonctions vous permettront de ne pas avoir à vous soucier des détails des calculs.

Les fonctions deviennent pratiques quand on a besoin de l'information plusieurs fois, et qu'il y a plusieurs conditions à respecter.

Imaginons par exemple que les conditions pour l'affichage d'une recette évoluent :

1. La clé `is_enabled` est `true`  .
    
2. L'utilisateur doit être connecté.
    
3. L'utilisateur doit avoir un rôle administrateur.
    
4. L'utilisateur doit être majeur.
    
5. Etc.
    

Nous n'allons pas recopier et implémenter toutes ces instructions à chaque fois, nous utiliserons une fonction dont le rôle sera de retourner `true` ou `false`  .

![[2025-02-16_16h45_17.png]]

Oui, mais les fonctions sont capables de s'adapter en fonction des informations que vous leur envoyez. Par exemple dans notre cas, il suffit de transmettre l'array  `$recipe`  à notre fonction pour qu'elle nous retourne le résultat. Ces informations que l'on donne en **entrée** à la fonction sont appelées _**paramètres**_ (un mot à connaître !).

Concrètement, les fonctions peuvent permettre de récupérer des informations comme la date et l'heure actuelles, de chiffrer des données, d'envoyer des e-mails, de faire des recherches dans du texte, et bien d'autres choses encore !

Nous avons jusqu'ici imaginé un cas d'utilisation très simple que nous avions résolu précédemment avec une boucle et une condition, ce qui n'est pas très intéressant.  
Revenons aux choses sérieuses et concrètes, et explorons les fonctions pour pouvoir par la suite afficher le nom de l'auteur plutôt que l'e-mail lors de l'affichage d'une recette.

### Appelez une fonction

En PHP, comment appelle-t-on une fonction ? Par son nom, pardi !

Exemple :

![[2025-02-16_16h46_34.png]]

![[2025-02-16_16h46_55.png]]

Comme vous le voyez, j'ai simplement écrit le nom de la fonction, suivi de parenthèses vides, puis de l'inévitable point-virgule. En faisant cela, j'appelle la fonction `allowRecipe` mais je ne lui envoie aucune information, aucun **paramètre**.

![[2025-02-16_16h47_43.png]]

Si on veut lui envoyer un paramètre (un nombre, une chaîne de caractères, un booléen...), il faut l'écrire entre les parenthèses :

![[2025-02-16_16h48_22.png]]

Ainsi, `allowRecipe` saura qu'elle doit travailler avec le tableau PHP passé en paramètre.

Souvent, les fonctions acceptent plusieurs paramètres. Vous devez dans ce cas les séparer par des virgules :

![[2025-02-16_16h49_13.png]]

Cette fonction recevra quatre paramètres :

- 17 ;
    
- le texte « Vert » ;
    
- le booléen Vrai ;
    
- et le nombre 41,7.
    

### Récupérez la valeur de retour de la fonction

Maintenant que nous savons appeler une fonction et même lui envoyer plusieurs paramètres, il faut récupérer ce qu'elle nous retourne, si toutefois elle retourne quelque chose.

![[2025-02-16_16h49_50.png]]

Si la fonction ne retourne aucune valeur, il n'y a rien de plus à faire que dans les codes précédents. La fonction est appelée, elle fait son travail. On ne lui demande rien de plus.

En revanche, si la fonction retourne une valeur (comme ça devrait être le cas pour `allowRecipe`  ), on la récupère dans une variable, comme ceci :

![[2025-02-16_16h51_14.png]]

Sur une ligne comme celle-ci, il se passe en fait les deux choses suivantes (dans l'ordre, et de droite à gauche) :

1. La fonction `allowRecipe` est appelée avec un tableau en paramètre.
    
2. Le résultat renvoyé par la fonction (lorsqu'elle a terminé) est stocké dans la variable  `$isAllowed`  .
    

La variable `$isAllowed` aura donc pour valeur `true` après l'exécution de cette ligne de code !

![[2025-02-16_16h57_15.png]]
### Utilisez les fonctions prêtes à l'emploi de PHP

![[2025-02-16_16h57_36.png]]

Ces fonctions sont très pratiques. En fait, c'est en partie là que réside la force de PHP : ses fonctions sont vraiment excellentes car elles couvrent la quasi-totalité de nos besoins. En fait, pratiquement à chaque fois que je m'apprêtais à écrire une fonction, j'ai pu remarquer que celle-ci existait déjà.

Voici un petit aperçu de ce que peuvent vous permettre de faire des fonctions PHP :

- `str_replace` pour [rechercher et remplacer](https://www.php.net/manual/fr/function.str-replace.php) des mots dans une variable ;
    
- `move_uploaded_file` pour [envoyer un fichier sur un serveur](https://www.php.net/manual/fr/function.move-uploaded-file) ;
    
- `imagecreate` pour [créer des images miniatures](https://www.php.net/manual/fr/function.imagecreate) (aussi appelées "thumbnails") ;
    
- `mail` pour [envoyer un mail](https://www.php.net/manual/fr/function.mail) avec PHP (très pratique pour faire une newsletter) ;
    
- de [nombreuses options](https://www.php.net/manual/fr/book.image) pour modifier des images, y écrire du texte, tracer des lignes, des rectangles, etc. ;
    
- `crypt` pour [chiffrer des mots de passe](https://www.php.net/manual/fr/function.crypt) ;
    
- `date`  pour [renvoyer l'heure, la date](https://www.php.net/manual/fr/function.date), etc.
    

Dans la plupart des cas, il faudra indiquer des paramètres à la fonction, pour qu'elle sache sur quoi travailler.

Nous allons ici découvrir rapidement quelques fonctions pour vous habituer à les utiliser.

![[2025-02-16_16h59_20.png]]

Nous allons voir :

- trois fonctions qui effectuent des modifications sur des chaînes de caractères ;
    
- et une qui permet de récupérer la date.
    

Ce sont seulement des exemples destinés à vous habituer à utiliser des fonctions.

### Manipulez du texte avec les fonctions

De nombreuses fonctions permettent de manipuler le texte. En voici trois qui peuvent être utiles :

1. `strlen` pour calculer la longueur d'une chaîne de caractères ;
    
2. `str_replace` pour rechercher et remplacer une chaîne de caractères ;
    
3. `sprintf` pour formater une chaîne de caractères.
    

#### Calculez la longueur d'une chaîne de caractères avec `strlen`

![[2025-02-16_17h01_14.png]]

Exemple :

![[2025-02-16_17h05_36.png]]

![[2025-02-16_17h06_19.png]]

Dans le même ordre d'idée, la fonction [`count`](https://www.php.net/manual/fr/function.count.php)  permet aussi de compter le nombre d'éléments dans un tableau ; car en PHP une chaîne de caractères, c'est… un tableau de caractères !

#### Recherchez et remplacez une chaîne de caractères avec `str_replace`

![[2025-02-16_17h07_02.png]]

Exemple :

![[2025-02-16_17h07_21.png]]

![[2025-02-16_17h07_34.png]]

On a besoin d'indiquer trois paramètres :

1. La chaîne qu'on recherche – ici, les « c » (on aurait pu rechercher un mot aussi).
    
2. La chaîne qu'on veut mettre à la place – ici, on met des « C » à la place des « c ».
    
3. La chaîne dans laquelle on doit faire la recherche.
    

Ce qui nous donne « le Cassoulet, C'est très bon ».

#### Formatez une chaîne de caractères avec `sprintf`

La fonction `sprintf` permet de formater une chaîne de caractères.

Elle est très pratique lorsque nous avons besoin de passer plusieurs variables et elle peut remplacer la concaténation pour des raisons de lisibilité du code.

![[2025-02-16_17h10_11.png]]

![[2025-02-16_17h10_32.png]]

![[2025-02-16_17h10_59.png]]

#### Récupérez la date

Nous allons découvrir la fonction qui renvoie l'heure et la date. Il s'agit de `date`  (un nom facile à retenir, avouez !).

Cette fonction peut donner beaucoup d'informations. Voici les principaux paramètres à connaître :

| Paramètre | Description |
| --------- | ----------- |
| H         | Heure       |
| i         | Minute      |
| d         | Jour        |
| m         | Mois        |
| Y         | Année       |

![[2025-02-16_17h22_49 1.png]]

Si vous voulez afficher l'année, il faut donc envoyer le paramètre `Y` à la fonction :

![[2025-02-16_17h23_22.png]]

On peut bien entendu faire mieux ; voici la date complète et l'heure :

![[2025-02-16_17h23_45.png]]

Et voilà le travail ! On a pu afficher la date et l'heure en un clin d'œil.

Normalement, quand vous avez testé le code précédent, vous avez dû avoir la date et l'heure exactes (n'hésitez donc pas à essayer d'exécuter ce code source chez vous).

![[2025-02-16_17h34_01.png]]

Absolument ! Pour simplifier le code, nous pouvons utiliser les formats de la fonction  `date` , comme ceci :

![[2025-02-16_17h34_27.png]]

Ces lignes de code effectuent le même travail que les lignes précédentes, mais de manière plus concise.  `date('d/m/Y')`  formate la date sous la forme jour/mois/année, et  `date('H \h i')`  formate l'heure sous le format heure h minute (exemple 12 h 25). Voici la version finale :

![[2025-02-16_17h44_56.png]]

### Créez vos propres fonctions

![[2025-02-16_17h45_22.png]]

![[2025-02-16_17h45_40.png]]

En général, si vous effectuez des opérations un peu complexes que vous pensez avoir besoin de refaire régulièrement, il est conseillé de créer une fonction.

Nous allons découvrir la création de fonctions à travers trois exemples :

1. Vérifier si la recette est valide.
    
2. Récupérer des recettes à afficher.
    
3. Récupérer le nom d'un utilisateur en fonction de l'e-mail associé à la création d'une recette.
    

#### Exemple 1 : vérifiez la validité d'une recette

Un premier exemple simple, c'est d'établir une fonction qui retourne :

- `true`  si la recette est valide ;
    
- `faux`  si la recette ne l'est pas.
    

Pour cela, nous avions utilisé une condition `if` pour vérifier la propriété `is_enabled` de la recette. C'est l'occasion de réutiliser des connaissances vues dans le chapitre des tableaux et des conditions :

![[2025-02-16_17h47_43.png]]

![[2025-02-16_17h47_59.png]]

Non, c'est tout l'objectif de ce chapitre du cours !

Voici la fonction correspondante :

![[2025-02-16_17h48_19.png]]

Pour créer une fonction,

1. Vous devez taper `function`  (en français, ça veut dire « fonction »).
    
2. Ensuite, donnez-lui un nom. Par exemple, celle-ci s'appelle  `isValidRecipe`  .
    

Ce qui est plus particulier après, c'est ce qu'on met entre parenthèses : il y a une variable. C'est le **paramètre** dont a besoin la fonction pour travailler, ici il s'agit de notre tableau.

Nous pouvons – et c'est une bonne pratique – définir le type de la variable attendue : ici, nous souhaitons un tableau donc nous préfixons la variable `$recipe` par le mot-clé   `array`  .

![[2025-02-16_17h48_44.png]]

![[2025-02-16_17h48_56.png]]

Notre fonction peut aussi – et c'est une deuxième bonne pratique – donner un type de retour, c'est-à-dire le type de valeur que la fonction doit retourner.

Ici, nous récupérons soit `true` , soit  `false` donc le type est **bool**.

Ensuite, vous repérez des accolades. Elles permettent de marquer les limites de la fonction. Cette dernière commence dès qu'il y a une `{`  et se termine lorsqu'il y a une `}` . Entre les deux, il y a son contenu.

Voilà, la fonction est créée, vous n'avez plus besoin d'y toucher. Après, pour faire appel à elle, il suffit d'indiquer son nom, et de préciser ses paramètres entre parenthèses.

![[2025-02-16_18h00_23.png]]

Exemple :

![[2025-02-16_18h00_56.png]]

![[2025-02-16_18h04_39.png]]

#### Exemple 2 : récupérez les recettes "valides"

Rappelez-vous, nous avions convenu que nous devions afficher la liste des recettes valides.

Nous venons de créer la fonction qui permet de vérifier qu'une recette est valide, il nous manque maintenant à boucler sur la liste des recettes : voilà une première occasion de réutiliser la fonction créée précédemment !

![[2025-02-16_18h13_33.png]]

Ici, la fonction contient le code nécessaire à la récupération des recettes valides.

Comme précédemment, on boucle et on ne conserve que les recettes valides identifiées grâce à la fonction  `isValidRecipe`  .

![[2025-02-16_18h14_07.png]]

#### Exemple 3 : affichez le nom de l'auteur

Allez, on passe à la vitesse supérieure. Nous allons créer une fonction pour améliorer l'affichage, ce qui nous donne à nouveau l'occasion de manipuler des tableaux.

Cette fois, la problématique est de relier l'e-mail associé à un compte utilisateur à l'e-mail utilisé pour la contribution d'une recette.

Si on découpe le problème en étapes, vous avez déjà toutes les connaissances nécessaires :

1. Prendre l'e-mail.
    
2. Boucler sur les utilisateurs de la plateforme.
    
3. Si les e-mails correspondent, prendre le nom et l'âge.
    
4. Sinon, continuer à parcourir la liste des utilisateurs.
    

Une solution tout à fait valide serait donc celle-ci (avec une boucle dans une boucle) :

![[2025-02-16_18h14_38.png]]

Avec pour résultat ceci :

![[2025-02-16_18h24_23.png]]

### Exploitez toute la puissance de la documentation PHP !

Le langage PHP fournit énormément de fonctions pour vous aider à développer vos sites web, vous devez donc toutes les apprendre.

Bien sûr que non !

L'équipe de développeurs qui a créé et fait évoluer PHP a publié un site web dans lequel toutes les fonctions du langage PHP sont expliquées et détaillées avec des exemples !

### **Exercez-vous**

Ajoutons les fonctions dans notre projet fil rouge.

1. Utilisez le tableau fourni  `$users`  qui contient plusieurs utilisateurs. Chaque utilisateur possède des clés telles que  `full_name`  , `email`  et `age`.

![[2025-02-16_18h30_10.png]]

1. Ajoutez les fonctions  `isValidRecipe` ,  `getRecipes`  et`displayAuthor`.
    
2. Retirez le test pour savoir si une recette est activée.
    
3. Modifiez la boucle pour utiliser la fonction  `getRecipes` à la place du tableau des recettes.
    
4. Utilisez la fonction  `displayAuthor`  pour afficher l'auteur.
    
5. Testez votre page web : assurez-vous que votre page affiche les recettes avec l'auteur et son âge.

### En résumé

- Les fonctions sont des blocs de code qui exécutent des instructions selon certains paramètres.
    
- Les fonctions ont généralement une entrée et une sortie, et peuvent avoir un type (string, int, bool, array...).
    
- PHP propose des centaines de fonctions prêtes à l'emploi pour tout type de tâches : envoyer un e-mail, récupérer l'heure, chiffrer des mots de passe, etc.
    
- Si PHP ne propose pas la fonction dont on a besoin, il est possible de la créer avec le mot-clé `function` : on définira alors le **type** des paramètres et du retour de la fonction.

![[2025-02-16_18h30_50.png]]

_C'est justement ce que l'on va voir dans le prochain chapitre. Allez, suivez-moi !_

