
Les formulaires constituent le principal moyen pour vos visiteurs d'entrer des informations sur votre site. Dans le chapitre précédent, nous avions d'ailleurs abordé un premier formulaire de contact assez basique pour envoyer une URL avec des paramètres.

Dans ce chapitre, vous allez apprendre à faire des formulaires plus sécurisés.

Ce chapitre est particulièrement important ; nous réutiliserons ce que nous avons appris ici dans toute la suite du cours. Soyez attentif !

![[2025-02-17_16h43_56.png]]

### Rappelez-vous : la base du formulaire

![[2025-02-17_16h44_22.png]]

On l'utilise de la manière suivante :

![[2025-02-17_16h44_42.png]]

![[2025-02-17_16h44_54.png]]

Il est impératif que vous compreniez à quoi ils servent.

#### Privilégiez la méthode `post` pour envoyer les données du formulaire

Il faut savoir qu'il existe plusieurs moyens d'envoyer les données du formulaire (plusieurs « méthodes »).

Vous pouvez en employer deux :

1. `get` : les données transiteront par l'URL, comme on l'a appris précédemment. On pourra les récupérer grâce au tableau (array) `$_GET`  . Cette méthode est assez peu utilisée car on ne peut pas envoyer beaucoup d'informations dans l'URL (je vous disais dans le chapitre précédent qu'il était préférable de ne pas dépasser 256 caractères).
    
2. `post` : les données ne transiteront pas par l'URL, l'utilisateur ne les verra donc pas passer dans la barre d'adresse. Cette méthode permet d'envoyer autant de données que l'on veut, ce qui fait qu'on la privilégie le plus souvent. Néanmoins, les données ne sont pas plus sécurisées qu'avec la méthode `GET`  , et il faudra toujours vérifier si tous les paramètres sont bien présents et valides, comme on l'a fait dans le chapitre précédent. **On ne doit pas plus faire confiance aux formulaires qu'aux URL**.

![[2025-02-17_16h49_54.png]]

#### Choisissez la page appelée par le formulaire en définissant la cible

![[2025-02-17_16h50_28.png]]

Selon la méthode utilisée, ce ne sera pas la même variable spéciale qui aura accès aux données :

- Si la méthode est  `GET`  (comme dans le chapitre précédent), alors c'est la supervariable  `$_GET` qui aura les données ;
    
- Si la méthode est  `POST`  (bonne pratique), alors c'est la supervariable  `$_POST`  qui recevra les données.
    

Retenez donc bien que vous travaillez normalement sur deux pages différentes :

1. La page qui contient le formulaire ( `form.php`  dans notre exemple) ;
    
2. Et celle qui reçoit les données du formulaire pour les traiter ( `submit_form.php`  ).
    

#### Ajoutez un ou plusieurs champs input avec un attribut name

La variable  `$_GET`  sera complétée avec la valeur de l'attribut  `name`  en tant que clé, et aura pour valeur ce qui aura été soumis par l'utilisateur :

![[2025-02-17_16h53_28.png]]

![[2025-02-17_16h53_49.png]]

#### Faites attention avec les champs cachés

Les champs cachés constituent un type de champ à part.


![[2025-02-17_18h50_17.png]]

![[2025-02-17_18h50_30.png]]

Je m'explique : supposons que vous ayez besoin de « retenir » que le pseudo du visiteur est « Mateo21 ». Vous allez taper ce code :

![[2025-02-17_18h50_54.png]]

À l'écran, sur la page web on ne verra rien. Mais dans la page cible, une variable `$_POST['pseudo']` sera créée, et elle aura la valeur « Mateo21 » !

C'est apparemment inutile, mais vous verrez que vous en aurez parfois besoin.

![[2025-02-17_18h51_22.png]]

### Ne faites jamais confiance aux données reçues : la faille XSS

Vous vous souvenez des mises en garde que j'avais faites dans le chapitre précédent ? Elles ne concernaient pas que les paramètres qui transitent par l'URL : tout cela vaut aussi pour les formulaires !

![[2025-02-17_18h51_57.png]]

J'y viens…

#### La faille XSS : attention au code HTML que vous recevez !

![[2025-02-17_18h52_16.png]]

![[2025-02-17_18h52_27.png]]

Reprenons la page de récapitulatif qui affiche l'e-mail et le message qu'on a soumis dans le chapitre précédent :

![[2025-02-17_18h53_54.png]]

Si le visiteur décide d'écrire du code HTML dans la zone de message, cela fonctionnera très bien !

Par exemple, imaginons qu'il écrive dans le champ « Votre message » le code :`<strong>Badaboum</strong>`

Le code source HTML qui sera généré par PHP sera le suivant :

![[2025-02-17_18h56_28.png]]

![[2025-02-17_18h56_44.png]]

Outre le fait qu'il peut insérer n'importe quel code HTML (et rendre votre page invalide), ce qui n'est pas le plus grave, il peut aussi ouvrir des balises de type `<script>` pour faire exécuter du code JavaScript au visiteur qui visualisera la page !

![[2025-02-17_19h30_04.png]]

Tous les visiteurs qui arriveront sur cette page verront une boîte de dialogue JavaScript s'afficher. Plutôt gênant. Voyez la figure suivante.

![[2025-02-17_19h30_36.png]]

#### Sécurisez votre code en bloquant l'exécution de code JavaScript

Pour ignorer le code HTML, il suffit d'utiliser la fonction  `htmlspecialchars`  .

![[2025-02-17_19h31_16.png]]

Elle va transformer les chevrons des balises HTML  `<`  et  `>`  en `&lt;`  et `&gt;`  respectivement.

Cela provoquera l'affichage de la balise plutôt que son exécution.

![[2025-02-17_19h50_32.png]]

Le code HTML qui en résultera sera propre et protégé, car les balises HTML insérées par le visiteur auront été échappées :

![[2025-02-17_19h50_55.png]]

![[2025-02-17_19h51_36.png]]

![[2025-02-17_19h52_00.png]]

Voici donc une nouvelle version du code de réception du formulaire (avec `method="POST"`  ) sécurisée, qui prévoit tous les cas pour éviter d'être pris au dépourvu par un utilisateur mal intentionné :

![[2025-02-17_19h55_55.png]]

### **Exercez-vous**

Il est temps de refaire les modifications par vous-même et d'utiliser  `POST`  à la place de  `GET` .

![[2025-02-17_19h56_27.png]]

### En résumé

- Les formulaires sont le moyen le plus pratique pour le visiteur de transmettre des informations à votre site. PHP est capable de récupérer les données saisies par vos visiteurs et de les traiter.
    
- Les données envoyées via un formulaire se retrouvent dans un tableau (array)  `$_POST`  .
    
- De la même manière que pour les URL, il ne faut pas donner sa confiance absolue aux données que vous envoie l'utilisateur. Traitez les données reçues avec vigilance.
    
- Que ce soit pour des données issues de l'URL ( `$_GET`  ) ou d'un formulaire ( `$_POST`  ), il faut s'assurer qu'aucun texte qui vous est envoyé ne contient du HTML si celui-ci est destiné à être affiché sur une page. Sinon, vous ouvrez une faille appelée XSS qui peut être néfaste pour la sécurité de votre site.
    
- Pour éviter la faille XSS, il suffit d'appliquer la fonction `htmlspecialchars`  ou  `strip_tags` sur tous les textes envoyés par vos visiteurs que vous afficherez.
    

_Dans le prochain chapitre, nous allons voir comment permettre aux utilisateurs de votre site de partager et d'envoyer des fichiers. On y va !_