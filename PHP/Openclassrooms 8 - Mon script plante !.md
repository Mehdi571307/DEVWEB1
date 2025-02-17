
# Au secours ! Mon script plante !

Alors comme ça, votre script ne marche pas ? Et PHP vous affiche des erreurs incompréhensibles ?

Pas de souci à vous faire, c'est tout à fait normal, on ne réussit jamais un script du premier coup… en tout cas, moi, jamais !

Des milliers de messages d'erreur différents peuvent survenir.

OK, jusque-là rien de très rassurant. Et je n'ai pas vraiment la possibilité de vous en dresser une liste complète… mais je peux vous présenter les erreurs les plus courantes, ce qui devrait résoudre la grande majorité de vos problèmes. 😅

Allons-y !

### Préparez-vous à faire ces erreurs courantes

Je pense qu'il est facile de parler d'erreurs « courantes », car vous verrez que certaines erreurs reviennent plus souvent que d'autres.

Nous allons passer en revue les erreurs suivantes :

1. "Parse error".
    
2. "Undefined function".
    
3. "Wrong parameter count".
    

#### "Parse error" = si vous formulez mal une instruction

Si on devait dire qu'il existe UNE erreur de base, ça serait très certainement celle-là. Impossible de programmer en PHP sans y avoir droit un jour.

Le message d'erreur que vous obtenez ressemble à celui-ci :

![[2025-02-17_13h02_47.png]]

Ce message vous indique une erreur dans error `.php` à la ligne 7.

![[2025-02-17_13h03_16.png]]

![[2025-02-17_13h03_29.png]]

![[2025-02-17_13h03_45.png]]


![[2025-02-17_13h04_00.png]]

Une "parse error" est en fait une instruction PHP mal formée. Il peut y avoir plusieurs causes :

![[2025-02-17_13h04_19.png]]

Comme toutes les instructions doivent se terminer par un point-virgule, si vous oubliez d'en mettre un, ça provoquera une parse error. Par exemple :

![[2025-02-17_13h04_41.png]]

… génèrera une parse error. Si vous mettez le point-virgule à la fin, tout rentrera dans l'ordre !

![[2025-02-17_13h05_09.png]]

![[2025-02-17_13h05_20.png]]

Par exemple :

![[2025-02-17_13h05_42.png]]

Il suffit de fermer correctement les guillemets et vous n'aurez plus de problème :

![[2025-02-17_13h06_06.png]]

![[2025-02-17_13h06_25.png]]

![[2025-02-17_13h06_39.png]]

Une fois l'erreur corrigée, ça donne :

![[2025-02-17_13h06_57.png]]

![[2025-02-17_13h07_12.png]]

Cela peut être le cas pour une structure en `if`  , par exemple.

Vérifiez que vous avez correctement fermé toutes vos accolades.

![[2025-02-17_13h07_30.png]]


![[2025-02-17_13h07_44.png]]

#### "Undefined function" = si vous utilisez une fonction non reconnue

Une autre erreur assez classique, c'est la fonction inconnue.

Vous obtenez ce message d'erreur :

![[2025-02-17_13h10_42.png]]

Là, il faut comprendre que vous avez utilisé une fonction qui n'existe pas.

Deux possibilités :

1. Soit **la fonction n'existe vraiment pas**. Vous avez probablement fait une faute de frappe, vérifiez si une fonction à l'orthographe similaire existe.
    
2. Soit la fonction existe vraiment, mais PHP ne la reconnaît pas. C'est parce que cette fonction se trouve dans **une extension de PHP que vous n'avez pas activée**. Par exemple, si vous essayez d'utiliser la fonction `imagepng` alors que vous n'avez pas activé la bibliothèque nécessaire pour les images en PHP, on vous dira que la fonction n'existe pas. Activez la bibliothèque qui utilise la fonction, et tout sera réglé.

![[2025-02-17_13h11_44.png]]

#### "Wrong parameter count" = si vous entrez un nombre incorrect de paramètres pour une fonction

Si vous utilisez mal une fonction, vous aurez cette erreur :

![[2025-02-17_13h12_59.png]]

Cela signifie que :

- vous avez oublié des paramètres pour la fonction ;
    
- ou même que vous en avez trop mis.

![[2025-02-17_13h12_10.png]]

Par exemple, la fonction `fopen` requiert au minimum deux paramètres :

1. Le premier pour le nom du fichier à ouvrir.
    
2. Et le second pour le mode d'ouverture (en lecture seule, écriture, etc.).
    

Si vous ne mettez que le nom du fichier à ouvrir, comme ceci :

![[2025-02-17_13h13_51.png]]

… vous aurez l'erreur « Wrong parameter count ». Pensez donc à rajouter le paramètre qui manque, par exemple comme ceci :

![[2025-02-17_13h14_11.png]]

### Découvrez ces erreurs plus rares

Les erreurs PHP sont très variées. N'espérez donc pas que je vous fasse ici la liste des 3 946 erreurs de PHP, j'en serais incapable (je ne les ai pas encore toutes eues, mais ça ne saurait tarder, à l'allure à laquelle je vais).

Je vais vous montrer quelques erreurs un peu plus rares que « parse error », mais que vous rencontrerez probablement un jour. Si déjà je peux vous aider pour ces erreurs-là, ce sera bien.

Nous allons voir les erreurs :

1. "Headers already sent by…".
    
2. "L'image contient des erreurs".
    
3. "Maximum execution time exceeded".
    

#### "Headers already sent by…" = si vous écrivez du code au mauvais endroit

Voilà une erreur classique quand on travaille avec les sessions ou avec les cookies :

![[2025-02-17_13h15_30.png]]

![[2025-02-17_13h15_43.png]]

![[2025-02-17_13h15_53.png]]

Elles permettent de dire :

> "Ce que tu vas recevoir est une page HTML".
> 
> ou
> 
> "Ce que tu vas recevoir est une image PNG", ou encore "Inscris un cookie".

![[2025-02-17_13h16_41.png]]

En PHP, la fonction qui permet d'envoyer des informations de "headers" s'appelle  `header()` 

. Il y a d'autres fonctions qui envoient des "headers" toutes seules. C'est le cas de :

-  `session_start()` 
    
-  `setcookie()

![[2025-02-17_13h17_41.png]]

Un exemple de code qui génère l'erreur :

![[2025-02-17_13h18_00.png]]

Ici, j'ai eu le malheur de mettre un peu de code HTML avant le `session_start()` et c'est ce qui a provoqué l'erreur.

Mettez le `session_start()` en tout premier, et vous n'aurez plus de problème :

![[2025-02-17_13h18_55.png]]

#### "L'image contient des erreurs" = si vous avez fait une erreur d'utilisation de la librairie GD

![[2025-02-17_13h19_23.png]]

Si vous avez fait une erreur dans votre code (par exemple une banale « parse error »), cette erreur sera **inscrite dans l'image**. Du coup, l'image ne sera pas valide et le navigateur ne pourra pas l'afficher.

![[2025-02-17_13h19_56.png]]

Deux possibilités :

- vous pouvez supprimer la ligne suivante dans votre code :

![[2025-02-17_13h20_29.png]]

L'erreur apparaîtra à la place du message « L'image contient des erreurs » ;

- vous pouvez aussi afficher le code source de l'image (comme si vous alliez regarder la source HTML de la page, sauf que là, il s'agit d'une image).
    

Dans les deux cas, vous verrez le message d'erreur apparaître. À partir de là, il ne vous restera plus qu'à corriger le bug !

#### "Maximum execution time exceeded" = si vous avez fait une boucle infinie

Ça, c'est le genre d'erreur qui arrive le plus souvent à cause d'une boucle infinie !

![[2025-02-17_13h21_49.png]]

Imaginez que vous fassiez une boucle `while` mais que celle-ci ne s'arrête jamais : votre script PHP va tourner en boucle sans jamais s'arrêter.

![[2025-02-17_13h22_08.png]]

Voici un exemple de boucle `while` qui ne s'arrêtera jamais :

![[2025-02-17_13h22_54.png]]

Comme vous pouvez le voir, un tel code PHP ne s'arrêtera jamais parce que `$counter` vaut toujours 5…

![[2025-02-17_13h23_47.png]]

Rassurez-vous : la limite est fixée à 30 secondes, mais vous n'y serez jamais confronté. En général, un serveur met moins de 50 millisecondes à charger une page PHP. On est très loin des 30 secondes !

### Déboguez votre premier script

Rien ne vaut la pratique pour mettre en application ce que vous venez d'apprendre ! Je vous propose donc de copier le code ci-dessous et de le corriger :



![[2025-02-17_13h27_16.png]]

![[2025-02-17_13h36_10.png]]

Alors, avez-vous fait des erreurs en corrigeant des erreurs ? 🤣

La première erreur affichée par PHP est la suivante :

![[2025-02-17_13h36_38.png]]

Il y a donc une erreur à la ligne 7, ou autour... vous aurez peut être remarqué qu'il manque une virgule en ligne 6 juste après l'assignation de la propriété `email` :

![[2025-02-17_13h36_59.png]]

La deuxième erreur est plus discrète puisque le site a l'air de s'afficher correctement sous vos yeux, mais il y a pourtant un message d'erreur sous le titre principal :

![[2025-02-17_13h38_03.png]]

L'index ou la clé pour le tableau `$recipe` ne semblent pas définis (bug qui ne serait jamais arrivé si on avait utilisé la fonction `array_key_exists`, d'ailleurs ! 🤓

Il va nous falloir vérifier le tableau des recettes et compléter ou corriger :

![[2025-02-17_13h39_19.png]]

Il y avait une toute petite coquille : `is_enabled` avait été remplacé par  `is_enablad`  .

La troisième erreur et dernière erreur est beaucoup plus bavarde :

![[2025-02-17_13h39_47.png]]

Cette fois, l'erreur provient du retour de la fonction `displayAuthor` qui doit retourner une chaîne de caractères (le nom de l'utilisateur) et retourne... rien (None).

![[2025-02-17_13h41_15.png]]

![[2025-02-17_13h41_31.png]]

Si l'on considère le code de la fonction, on peut noter que si l'e-mail est trouvé, alors le nom et l'âge de l'utilisateur sont retournés.

![[2025-02-17_13h43_57.png]]

Eh bien, il ne se passe rien car le cas n'a pas été prévu. Le plus simple est de retourner une chaîne de caractère même si l’email n’a pas été trouvé (“Auteur inconnu”) :

![[2025-02-17_13h44_44.png]]

![[2025-02-17_13h45_02.png]]

### En résumé

- Vous rencontrerez des bugs dans vos projets, c'est inéluctable.
    
- Ne paniquez pas, lisez et essayez de comprendre le message d'erreur.
    
- Vous pouvez aussi copier le message d'erreur et le rechercher sur Internet : il y a de fortes chances que d'autres personnes aient déjà rencontré ce problème. 
    

_Nous approchons de la fin de cette partie du cours, mais avant, un dernier point important : nous allons voir comment faire pour organiser les pages de votre site en blocs fonctionnels._



