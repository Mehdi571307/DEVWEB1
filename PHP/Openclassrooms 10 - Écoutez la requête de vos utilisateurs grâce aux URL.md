
Grâce aux URL et à PHP, nous allons rendre le formulaire de contact dynamique en retournant une page de prise en compte de la demande à chaque personne qui soumettra le formulaire.

![[2025-02-17_14h50_58.png]]

Un petit peu.

![[2025-02-17_14h51_24.png]]

Toutes les adresses que vous voyez en haut de votre navigateur, comme : `https://www.openclassrooms.com` sont des URL.

Lorsque vous faites une recherche sur Google pour trouver le site d'OpenClassrooms en tapant le mot "OpenClassrooms", la barre d'adresse contient une URL un peu longue qui ressemble à ceci :

`http://www.google.fr/search?rlz=1C1GFR343&q=openclassrooms`

![[2025-02-17_14h52_12.png]]

Les informations après le point d'interrogation `?` sont en réalité des données que l'on fait transiter d'une page à une autre. Nous allons découvrir dans ce chapitre comment cela fonctionne.

### Envoyez des paramètres dans l'URL

Les URL permettent de transmettre des informations. Comment est-ce que ça fonctionne, exactement ? J'y viens !

#### Formez une URL pour envoyer des paramètres

Imaginons :

- votre site s'appelle  `monsite.com`  ;
    
- et possède une page PHP de contact :    `contact.php`  .
    

Pour accéder à la page de contact, vous devez aller à l'URL suivante :

`http://www.monsite.com/contact.php`

Jusque-là, rien de bien nouveau. Ce que je vous propose d'apprendre à faire, c'est d'**envoyer** des informations à la page  `contact.php`  .

Ces informations vont figurer à la fin de l'URL, comme ceci :

`http://www.monsite.com/contact.php?nom=Dupont&prenom=Jean`

![[2025-02-17_14h53_29.png]]

Voici comment on peut découper cette URL :

![[2025-02-17_14h53_48.png]]

Le point d'interrogation sépare le nom de la page PHP des paramètres.

Les paramètres s'enchaînent selon la forme `nom=valeur` et sont séparés les uns des autres par le symbole   `&`  .

![[2025-02-17_14h54_32.png]]

En théorie, oui.

Il suffit de les séparer par des `&` comme je l'ai fait. On peut donc voir une URL de la forme : 

`page.php?param1=valeur1&param2=valeur2&param3=valeur3&param4=valeur4…`

![[2025-02-17_14h54_53.png]]

#### Créez un lien avec des paramètres

Maintenant que nous savons cela, nous pouvons créer des liens en HTML, qui transmettent des paramètres d'une page vers une autre.

Imaginons que vous ayez deux fichiers sur votre site :

- `index.php`  (l'accueil) ;
    
- `bonjour.php` .
    

Nous voulons faire un lien de `index.php`  à `bonjour.php`  pour transmettre des informations dans l'URL :

![[2025-02-17_14h55_50.png]]

Pour cela, ouvrez `index.php`  (puisque c'est lui qui contiendra le lien) et insérez-y par exemple le code suivant :

![[2025-02-17_14h59_37.png]]

![[2025-02-17_14h59_49.png]]

Ce lien appelle la page `bonjour.php` et lui envoie deux paramètres :

- `nom` : Dupont ;
    
- `prenom` : Jean.
    

#### Créez un formulaire avec la méthode HTTP GET


![[2025-02-17_15h01_02.png]]

La deuxième solution pour faire passer des informations dans l'URL, c'est de proposer à l'utilisateur de soumettre un formulaire avec la méthode HTTP GET.

Nous pouvons faire cela avec une balise `form` qui a pour attribut `method` la valeur **GET**.

![[2025-02-17_15h01_34.png]]

Les données soumises à l'aide du formulaire se retrouveront dans l'URL, comme pour un lien.

![[2025-02-17_15h01_55.png]]

C'est ce que nous allons voir maintenant !

### Récupérez les paramètres en PHP

Nous savons maintenant comment faire pour envoyer des paramètres vers une autre page.

Intéressons-nous maintenant à la page qui réceptionne les paramètres.

Pour notre besoin, nous avons un formulaire de contact – `contact.php`  – que nous allons soumettre sur une autre page, et qui affichera un message de bonne réception :`submit_contact.php`

Pour rappel, voici le formulaire de contact (simplifié) que nous avions dans le chapitre précédent :

![[2025-02-17_15h04_31.png]]

![[2025-02-17_15h04_47.png]]

Le formulaire va alors être converti en lien vers :`submit_contact.php?email=utilisateur%40exemple.com&message=Bonjour` 

Et ces informations pourront être récupérées par PHP dans le fichier `submit_contact.php` .

![[2025-02-17_15h43_19.png]]

|Nom|Valeur|
|---|---|
|`$_GET['email']`|[utilisateur@exemple.com](mailto:utilisateur@exemple.com)|
|`$_GET['message']`|Bonjour|

On peut donc :

- récupérer ces informations ;
    
- les traiter ;
    
- les afficher ;
    
- bref, faire ce que l'on veut avec.
    

Pour l'exemple, créez un nouveau fichier PHP `submit_contact.php` et placez-y le code suivant :

![[2025-02-17_16h01_21.png]]

Vous obtiendrez le résultat suivant :

![[2025-02-17_16h02_24.png]]

### Ne faites jamais confiance aux données reçues !

![[2025-02-17_16h02_44.png]]

Oui je suis alarmiste, et oui je veux que vous ayez – un peu – peur !

Mais rassurez-vous : je vais vous expliquer tout ce qu'il faut savoir pour que ça se passe bien et que vous ne risquiez rien.

#### Tous les visiteurs peuvent trafiquer les URL

Si vous faites les tests des codes précédents chez vous, vous devriez tomber sur une URL de la forme :

`http://localhost/submit_contact.php?email=utilisateur%40exemple.com&message=Bonjour`

Mais si vous êtes un peu bricoleur, vous pouvez vous amuser à changer les paramètres directement dans la barre d'adresse, comme ici :

![[2025-02-17_16h04_41.png]]

Mais si vous êtes un peu bricoleur, vous pouvez vous amuser à changer les paramètres directement dans la barre d'adresse, comme ici :

![[2025-02-17_16h05_45.png]]

Essayez par exemple de modifier l'adresse pour :

![[2025-02-17_16h06_09.png]]

Comme vous le voyez, ça marche ! N'importe qui peut facilement modifier les URL et y mettre ce qu'il veut : il suffit simplement de changer l'URL dans la barre d'adresse de votre navigateur.

![[2025-02-17_16h06_50.png]]

![[2025-02-17_16h07_19.png]]

#### Testez la présence d'un paramètre

Allons plus loin. Qu'est-ce qui empêche le visiteur de supprimer tous les paramètres de l'URL ? Par exemple, il peut très bien tenter d'accéder à :

`http://localhost/submit_contact.php`

Que va afficher la page `submit_contact.php`  ?

Faites le test ! Elle va afficher quelque chose comme :

![[2025-02-17_16h13_22.png]]

![[2025-02-17_16h13_35.png]]

On a essayé d'afficher la valeur de `$_GET['email']`  et celle de  `$_GET['message']`  .

Mais comme on vient de les supprimer de l'URL, ces variables n'ont pas été créées, et donc elles n'existent pas ! PHP nous avertit qu'on essaie d'utiliser des variables qui n'existent pas, d'où les « `Undefined index` ».

Pour résoudre ce problème, on peut faire appel à une fonction un peu spéciale :  `isset()`  .

![[2025-02-17_16h14_45.png]]

Nous allons nous en servir pour afficher un message spécifique, dans le cas où le nom ou le prénom serait absent.

![[2025-02-17_16h15_20.png]]

![[2025-02-17_16h15_32.png]]

Il teste si les variables `$getData['email']`  et `$getData['message']`  existent.

1. Si elles existent, on affiche la confirmation de prise en compte du message.
    
2. S'il nous manque une des variables (ou les deux), on affiche un message d'erreur : "Il faut un e-mail et un message pour soumettre le formulaire", et on arrête l'exécution de la page.
    

Essayez maintenant d'accéder à la page `submit_contact.php` sans les paramètres.

Vous allez voir qu'on gère bien le cas où le visiteur aurait retiré les paramètres de l'URL :

![[2025-02-17_16h15_51.png]]

![[2025-02-17_16h25_35.png]]

Oui, oui, **trois fois oui** : il faut que vous pensiez à gérer le cas où des paramètres que vous attendiez viendraient à manquer.

Vous vous souvenez de ce que je vous ai dit ? Il ne faut jamais faire confiance à l'utilisateur.

![[2025-02-17_16h26_11.png]]

Dans notre exemple, si on ne gérait pas le cas, ça ne faisait rien de bien grave (ça affichait juste des messages d'erreur). Mais lorsque votre site web deviendra plus complexe, cela pourrait avoir des conséquences plus ennuyeuses.

#### Contrôlez la valeur des paramètres

Une fois les valeurs soumises et correctement récupérées, il faut vérifier qu'elles correspondent à ce qui est attendu !

Imaginez par exemple que l'utilisateur se soit trompé et que l'e-mail envoyé ne soit pas valide : vous ne pourrez donc pas le recontacter pour répondre à son besoin !

Il va donc falloir :

- contrôler si l'e-mail passé est bien valide, à l'aide de la fonction [filter_var](https://www.php.net/manual/fr/filter.examples.validation.php) ;
    
- et vérifier que le message n'est pas vide, à l'aide de la fonction [empty](https://www.php.net/manual/fr/function.empty.php).
    

Voici donc le code final sécurisé, qui prévoit tous les cas pour éviter d'être pris au dépourvu par un utilisateur mal intentionné :

![[2025-02-17_16h27_31.png]]

Cela fait beaucoup de conditions pour quelque chose qui était à la base assez simple, mais c'était nécessaire. Vous devrez toujours faire très attention et prévoir tous les cas les plus tordus, comme nous venons de le faire :

- vérifier que tous les paramètres que vous attendiez sont bien là ;
    
- vérifier qu'ils contiennent des valeurs correctes, comprises dans des intervalles raisonnables.
    

Si vous gardez cela en tête, vous n'aurez pas de problèmes !

![[2025-02-17_16h31_38.png]]

### **Exercez-vous**

C'est à vous maintenant de valider les données du formulaire de contact (e-mail et message) dans notre projet fil rouge !

![[2025-02-17_16h32_13.png]]

### En résumé

- Une URL représente l'adresse d'une page web, commençant généralement par `http://`   .
    
- Lorsqu'on fait un lien vers une page, il est possible d'ajouter des paramètres sous la forme `bonjour.php?nom=Dupont&prenom=Jean` qui seront transmis à la page.
    
- La page de réception recevra ces paramètres dans un tableau (array) nommé  `$_GET`  .
    
- Cette technique est très pratique pour transmettre des valeurs à une page, mais il faut prendre garde au fait que le visiteur peut les modifier très facilement.
    
- La fonction `isset()` permet de vérifier si une variable est définie ou non.
    
- D'autres fonctions comme `filter_var()` ,  `trim()`  ou `empty()` peuvent être utilisées pour la validation des champs.
    

_Dans le prochain chapitre, nous allons voir comment administrer des formulaires de manière sécurisée. C'est parti !_