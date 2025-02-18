
Croyez-le ou non, vous avez déjà le niveau pour protéger le contenu d'une page par mot de passe ! C'est ce que je vais vous apprendre à faire dans ce chapitre.

Voici la liste des connaissances que vous allez devoir mobiliser pour cela :

- afficher du texte avec `echo` ;
    
- utiliser les variables  ;
    
- transmettre des variables via une zone de texte d'un formulaire ;
    
- utiliser des conditions simples ( `if` , `else`  ) ;
    
- utiliser les inclusions de fichiers avec `include` ou `include_once` .
    

Si l'un de ces points est un peu flou pour vous (vous avez peut-être oublié), n'hésitez pas à relire le chapitre correspondant.

Le but est de parvenir à assembler toutes vos connaissances pour répondre à un problème précis.

### Protégez le contenu d'une page par un mot de passe

Vous voulez que les contributeurs et contributrices de recettes puissent se connecter sur votre site et être reconnus.

Pour faire simple, il y aura un formulaire de connexion avec e-mail et mot de passe et une fois la personne connectée, nous afficherons un message du type :

> "Bonjour [utilisateur@exemple.com](mailto:utilisateur@exemple.com) et bienvenue sur le site !"

Et nous rajoutons une contrainte : la liste des recettes ne sera affichée que si l'utilisateur est connecté !

Les utilisateurs seront déjà disponibles sous forme d'un tableau associatif PHP. Ils ont :

1. Une clé 'password' avec un mot de passe.
    
2. Et une clé 'email' avec leur e-mail.
    

#### Travaillez d'abord au brouillon

Pour coder correctement, je recommande toujours de travailler d'abord au brouillon (vous savez, avec un stylo et une feuille de papier !). Ça peut bien souvent paraître une perte de temps, mais c'est tout à fait le contraire.

![[2025-02-18_20h30_29.png]]

![[2025-02-18_20h30_41.png]]

1. Au problème que vous vous posez (qu'est-ce que je veux arriver à faire ?).
    
2. Au schéma du code, c'est-à-dire que vous allez commencer à le découper en plusieurs morceaux, eux-mêmes découpés en petits morceaux (c'est plus facile à avaler).
    
3. Aux fonctions et aux connaissances en PHP dont vous allez avoir besoin (pour être sûr que vous les utilisez convenablement).
    

Et pour montrer l'exemple, nous allons suivre cette liste.

##### 1. Posez le problème

On doit soumettre un e-mail et un mot de passe dans un formulaire de connexion.

Si le formulaire est valide, nous affichons un message de succès, et sinon un message d'erreur. La liste de recettes n'est affichée qu'à un utilisateur qui s'est connecté avec succès.

##### 2. Schématisez le code

Pour que l'utilisateur puisse entrer le mot de passe, le plus simple est de créer un formulaire. Celui-ci sera directement intégré dans la page d'accueil du site telle que nous la connaissons déjà.

Trois situations peuvent survenir :

1. Vous n'êtes **pas connecté** : auquel cas, le formulaire de contact s'affiche, et la liste des recettes ne s'affiche pas.
    
2. Vous avez soumis le formulaire avec le **bon mot de passe** pour l'utilisateur : le message de succès s'affiche, le formulaire de connexion ne s'affiche pas et les recettes s'affichent.
    
3. Vous avez soumis le formulaire avec le **mauvais mot de passe** pour l'utilisateur : le message d'erreur s'affiche, le formulaire de connexion s'affiche et les recettes ne s'affichent pas.
    

Vous devez donc créer une nouvelle page et adapter la page d'accueil :

- **login.php** : contient un simple formulaire comme vous savez les faire ;
    
- **index.php** : qui doit maintenant inclure un formulaire de connexion et une condition sur l'affichage des recettes.
    

##### 3. Mobilisez les connaissances requises

Nous avons détaillé les connaissances requises au début de ce chapitre. Vous allez voir que ce n'est qu'une simple application pratique de ce que vous connaissez déjà, mais cela sera une bonne occasion de vous entraîner.

Bon ! On a préparé le terrain ensemble ; maintenant, vous savez tout ce qu'il faut pour réaliser le script !

Vous êtes normalement capable de trouver le code à écrire par vous-même, et c'est ce que je vous invite à faire. Ça ne marchera peut-être pas du premier coup, mais ne vous en faites pas : c'est le métier qui rentre !

![[2025-02-18_20h37_42.png]]

Pas de panique ! Voyons tout cela ensemble.

Comme vous le savez, il y a deux pages à créer :

1. La page login.php.
    
2. La page index.php.
    

#### Codez la page login.php

Commençons par la plus simple, `login.php` :

![[2025-02-18_21h32_55.png]]

J'ai choisi un champ de type `password` puisqu'il s'agit d'un mot de passe. À part ça, rien de bien particulier.

#### Codez la page index.php

Maintenant, intéressons-nous à la page `index.php` qui va inclure le formulaire et limiter l'accès aux recettes :

![[2025-02-18_21h38_28.png]]

Pour le résultat suivant :

![[2025-02-18_21h38_58.png]]

![[2025-02-18_21h58_59.png]]

Oui, honnêtement il l'est. Du moins, tant que vos utilisateurs ne choisissent pas de mots de passe trop simples à deviner !

![[2025-02-18_21h59_21.png]]

### Allez plus loin

Pour l'instant ce système de connexion n'est pas "persistant". C'est-à-dire que si vous rechargez la page d'accueil ou que vous revenez sur votre site plus tard, l'information de la connexion n'aura pas été conservée.

![[2025-02-18_21h59_48.png]]

Eh bien, ce sera l'objet des prochains chapitres !

### **Exercez-vous**

Il ne vous reste plus qu'à modifier le projet pour implémenter le système de connexion. C'est parti !

Vous pouvez retrouver le code modifié dans le [dossier P3C4 du GitHub.](https://github.com/OpenClassrooms-Student-Center/siteweb-PHP-MySQL/tree/main/P3/P3C4)

### En résumé

- Il est recommandé de passer des informations en POST lorsqu'on conçoit un formulaire de connexion.
    
- Soit l'utilisateur est identifiable, c'est-à-dire que l'on retrouve une correspondance avec les identifiants fournis ; auquel cas, on autorise l'affichage du contenu.
    
- Soit l'utilisateur n'est pas identifiable : alors, on affichera un message d'erreur !
    

_Dans le prochain chapitre, nous allons voir comment conserver les données grâce aux sessions et aux cookies. À tout de suite !_