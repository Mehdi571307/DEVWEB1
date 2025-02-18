
Imaginez qu'une personne essaie de vous contacter car elle est victime d'un bug d'utilisation sur votre site : elle souhaiterait peut-être vous partager une capture d'écran, ce qui faciliterait beaucoup votre travail de déboggage.

Pour cela, vous allez devoir proposer la soumission de fichiers dans votre formulaire de contact !

Vous aviez découvert les superglobales  `$_GET`  et  `$_POST`  dans les chapitres précédents, c'est maintenant au tour de la supervariable  `$_FILES`  de faire son entrée dans votre projet !

### Donnez la possibilité d'envoyer des fichiers

Vous saviez qu'on pouvait aussi envoyer des fichiers grâce aux formulaires ?

Là encore, ça se passe en deux temps.

1. Le visiteur arrive sur votre formulaire et le remplit (en indiquant le fichier à envoyer). Une simple page HTML suffit pour créer le formulaire.
    
2. PHP réceptionne les données du formulaire et, s'il y a des fichiers dedans, il les « enregistre » dans un des dossiers du serveur.

![[2025-02-18_19h24_04.png]]

Vous allez devoir adapter votre formulaire de contact pour autoriser l'envoi et la soumission.

#### Paramétrez le formulaire d'envoi de fichier

Dès l'instant où votre formulaire propose aux visiteurs d'envoyer un fichier, il faut ajouter l'attribut `enctype="multipart/form-data"` à la balise  `<form>`  .

![[2025-02-18_19h25_07.png]]

Grâce à `enctype` , le navigateur du visiteur sait qu'il s'apprête à envoyer des fichiers.

Maintenant que c'est fait, nous pouvons ajouter à l'intérieur du formulaire une balise permettant d'envoyer un fichier.

C'est une balise très simple de type   `<input type="file" />`  .

Il faut donner un nom à ce champ de formulaire (grâce à l'attribut `name` ) pour que PHP puisse reconnaître le champ par la suite.

![[2025-02-18_19h26_53.png]]


Voilà, c'est suffisant.

#### Traitez l'envoi en PHP

C'est maintenant que ça devient important. Il faut que l'on ajoute du code dans la page `submit_contact.php` pour traiter l'envoi du fichier.

![[2025-02-18_19h28_21.png]]

![[2025-02-18_19h28_35.png]]

Vous pouvez par exemple vérifier si le fichier a la bonne extension (si vous demandez une image et qu'on vous envoie un « .txt », vous devrez refuser le fichier).

Si le fichier est bon, vous l'accepterez grâce à la fonction [move_uploaded_file](https://www.php.net/manual/fr/function.move-uploaded-file) et ce, d'une manière définitive.

![[2025-02-18_19h29_57.png]]

Pour chaque fichier envoyé, une variable `$_FILES['nom_du_champ']` est créée.

Dans notre cas, la variable s'appellera `$_FILES['screenshot']` 

Cette variable est un tableau qui contient plusieurs informations sur le fichier :

|Variable|Signification|
|---|---|
|`$_FILES['screenshot']['name']`|Contient le nom du fichier envoyé par le visiteur.|
|`$_FILES['screenshot']['type']`|Indique le type du fichier envoyé. Si c'est une image gif par exemple, le type sera `image/gif`|
|`$_FILES['screenshot']['size']`|Indique la taille du fichier envoyé.<br><br>**Attention** : cette taille est en octets. Il faut environ 1 000 octets pour faire 1 Ko, et 1 000 000 d'octets pour faire 1 Mo.  <br>La taille de l'envoi est limitée par PHP. Par défaut, impossible d'uploader des fichiers de plus de 8 Mo.|
|`$_FILES['screenshot']['tmp_name']`|Juste après l'envoi, le fichier est placé dans un répertoire temporaire sur le serveur en attendant que votre script PHP décide si oui ou non il accepte de le stocker pour de bon. Cette variable contient l'emplacement temporaire du fichier (c'est PHP qui gère ça).|
|`$_FILES['screenshot']['error']`|Contient un code d'erreur permettant de savoir si l'envoi s'est bien effectué ou s'il y a eu un problème et si oui, lequel. La variable vaut 0 s'il n'y a pas eu d'erreur.|
![[2025-02-18_19h31_29.png]]

Je vous propose de faire les vérifications suivantes pour décider si l'on accepte le fichier ou non.

1. Vérifier tout d'abord si le visiteur a bien envoyé un fichier, en testant la variable `$_FILES['screenshot']` avec `isset()` et s'il n'y a pas eu d'erreur d'envoi, grâce à `$_FILES['screenshot']['error']` .
    
2. Vérifier si la taille du fichier ne dépasse pas 1 Mo par exemple (environ 1 000 000 d'octets), grâce à `$_FILES['screenshot']['size']`  .
    
3. Vérifier si l'extension du fichier est autorisée (il faut interdire à tout prix que les gens puissent envoyer des fichiers PHP, sinon ils pourraient exécuter des scripts sur votre serveur). Dans notre cas, nous autoriserons seulement les images (fichiers .png, .jpg, .jpeg et .gif).  
    Nous analyserons pour cela la variable `$_FILES['screenshot']['name']` .
    

Nous allons donc faire une série de tests dans notre page `submit_contact.php` .

##### 1/ Testez si le fichier a bien été envoyé

On commence par vérifier qu'un fichier a été envoyé.

Pour cela, on va tester si la variable `$_FILES['screenshot']`  existe avec  `isset()`  .

On vérifie dans le même temps s'il n'y a pas d'erreur d'envoi.

![[2025-02-18_19h36_31.png]]

##### 2/ Vérifiez la taille du fichier

On veut interdire que le fichier dépasse 1 Mo, soit environ 1 000 000 d'octets (j'arrondis pour simplifier). On doit donc tester `$_FILES['screenshot']['size']` :

![[2025-02-18_19h37_13.png]]

##### 3/ Vérifiez l'extension du fichier

On peut récupérer l'extension du fichier dans une variable grâce à ce code :

![[2025-02-18_19h37_33.png]]

La fonction `pathinfo` renvoie un tableau (array) contenant entre autres l'extension du fichier dans  `$fileInfo['extension']`  .

On stocke ça dans une variable  `$extension`  .

Une fois l'extension récupérée, on peut la comparer à un tableau d'extensions autorisées, et vérifier si l'extension récupérée fait bien partie des extensions autorisées à l'aide de la fonction `in_array()` .

Ouf ! On obtient ce code :

![[2025-02-18_19h37_55.png]]

##### 4/ Vérifiez si le dossier pour stocker les images existe

Je propose de placer le fichier dans un sous-dossier « uploads ». Pour vérifier si notre dossier uploads existe, nous allons utiliser la fonction  `is_dir()`  . Il nous suffit de lui fournir le chemin du dossier que nous souhaitons tester. La fonction renvoie true si le dossier existe et false dans le cas contraire.

![[2025-02-18_19h38_30.png]]

##### 5/ Validez l'upload du fichier

Si tout est bon, on accepte le fichier en appelant   `move_uploaded_file()`  .

Cette fonction prend deux paramètres :

1. Le nom temporaire du fichier (on l'a avec  `$_FILES['screenshot']['tmp_name']`  ).
    
2. Le chemin qui est le nom sous lequel sera stocké le fichier de façon définitive. On peut utiliser le nom d'origine du fichier  `$_FILES['screenshot']['name']`  ou générer un nom au hasard.
    

On gardera le même nom de fichier que celui d'origine.

Comme  `$_FILES['screenshot']['name']`  contient le chemin entier vers le fichier d'origine (  `C:\dossier\fichier.png`  , par exemple), il nous faudra extraire le nom du fichier.

On peut utiliser pour cela la fonction  `basename`  qui renverra juste « fichier.png ».

![[2025-02-18_19h39_02.png]]

![[2025-02-18_19h39_15.png]]

Ce script est un début, mais en pratique il vous faudra sûrement encore l'améliorer.

Par exemple, si le nom du fichier contient des espaces ou des accents, ça posera un problème une fois envoyé sur le Web. D'autre part, si quelqu'un envoie un fichier qui a le même nom que celui d'une autre personne, l'ancien sera écrasé !

La solution consiste en général à « choisir » nous-mêmes le nom du fichier stocké sur le serveur, plutôt que de nous servir du nom d'origine. Vous pouvez faire un compteur qui s'incrémente : 1.png, 2.png, 3.jpg, etc.

![[2025-02-18_19h39_38.png]]

### **Exercez-vous**

Il nous reste à apporter une modification supplémentaire pour que notre affichage prenne en compte le chargement du fichier.

Étant donné que le champ d'image n'est pas obligatoire dans notre formulaire, nous afficherons le message suivant "L'envoi a bien été effectué !" uniquement si une image a été téléchargée.

Vous pouvez retrouver le code modifié dans le [dossier P3C3 du GitHub.](https://github.com/OpenClassrooms-Student-Center/siteweb-PHP-MySQL/tree/main/P3/P3C3)

### En résumé

- Les formulaires permettent d'envoyer des fichiers. On retrouve les informations sur les fichiers envoyés dans un array `$_FILES` . Leur traitement est cependant plus complexe.
    
- Il faudra toujours contrôler les fichiers reçus : leur existence et leur taille qui est soumise à limitation par la configuration de PHP.
    
- Il faudra vérifier leur extension (à l'aide de la fonction [pathinfo](https://www.php.net/manual/fr/function.pathinfo)) et **surtout refuser tout fichier PHP** qui pourrait par la suite s'exécuter sur votre serveur.
    
- À l'aide de la fonction [move_uploaded_file](https://www.php.net/manual/fr/function.move-uploaded-file), vous pouvez conserver le fichier téléversé sur votre serveur, mais vérifiez bien que vous avez les droits d'écrire des fichiers d'abord.
    

_Dans le prochain chapitre, nous allons voir comment implémenter un système de connexion pour vos utilisateurs._