
On considère qu'il existe deux types de sites web :

1. Les sites **statiques**.
    
2. Et les sites **dynamiques**.


#### **Découvrez le principe d'un site statique** 

Un site statique est réalisé uniquement à l'aide des langages HTML et CSS.

Il fonctionne très bien, mais son contenu ne peut pas être mis à jour automatiquement : il faut que le webmaster modifie le code source pour y ajouter des nouveautés.

Ce n'est pas très pratique quand on doit mettre à jour son site plusieurs fois dans la même journée…

Un site statique est adapté pour un site « vitrine » (pour présenter par exemple son entreprise), mais sans aller plus loin.


#### **Découvrez le principe d'un site dynamique**

Plus complexe, un site dynamique utilise d'autres langages en plus de HTML et CSS, tels que PHP et MySQL.

Le contenu de ce type de site est dit « dynamique » parce qu'il peut changer sans l'intervention du webmaster !

Maintenant que vous comprenez la différence entre un site statique et un site dynamique, nous pouvons passer à la suite !


### Comprenez le fonctionnement d'un site web

Lorsque vous voulez visiter un site web, vous tapez son adresse dans votre navigateur web. Mais ne vous êtes-vous jamais demandé comment faisait la page web pour arriver jusqu'à vous ?

Il faut savoir qu'Internet est un réseau composé d'ordinateurs. Ceux-ci peuvent être classés en deux catégories :

1. Les **clients** : ce sont les ordinateurs des internautes comme vous. Votre ordinateur fait donc partie de la catégorie des clients. Chaque client représente un visiteur d'un site web.
    
2. Les **serveurs** : ce sont des ordinateurs puissants qui stockent et délivrent des sites web aux internautes, c'est-à-dire aux clients. La plupart des internautes n'ont jamais vu un serveur de leur vie. Pourtant, les serveurs sont indispensables au bon fonctionnement du Web.


#### Consultez un site statique

Lorsque vous vous rendez sur site statique, c'est très simple. Cela se passe en deux temps :

1. Le client demande au serveur à voir une page web.
    
2. Le serveur lui répond en lui envoyant la page réclamée.


![[2025-02-07_09h06_31.png]]


La communication est donc plutôt basique :

- « Bonjour, je suis le client, je voudrais voir cette page web. »
    
- « Tiens, voilà la page que tu m'as demandée. »
    

Sur un site statique, il ne se passe rien d'autre. Le serveur stocke des pages web et les envoie aux clients qui les demandent, sans les modifier.


#### Consultez un site dynamique

Lorsque vous consultez un site dynamique, il y a une étape intermédiaire : la page est **générée**.


Eh bien, il y a une étape supplémentaire, et elle se situe entre les deux étapes de base :

1. Le client demande au serveur à voir une page web.
    
2. Le serveur prépare la page spécialement pour le client (il la génère).
    
3. Le serveur lui envoie la page qu'il vient de générer.

![[2025-02-07_09h07_42.png]]


La page web est générée à chaque fois qu'un client la réclame. C'est précisément ce qui rend les sites dynamiques "vivants" : le contenu d'une même page peut changer d'un instant à l'autre.

### Exploitez les langages du Web

Lorsqu'on crée un site web, on est amené à manipuler non pas un mais plusieurs langages. En tant que webmaster, il faut impérativement les connaître.

#### Utilisez HTML et CSS pour un site statique

De nombreux langages ont été créés pour produire des sites web. Deux d'entre eux constituent une base incontournable pour tous les webmasters.

##### **HTML**

C'est le langage à la base des sites web. Simple à apprendre, il fonctionne à partir de balises. Voici un exemple de code HTML :

![[2025-02-07_09h10_28.png]]

##### **CSS** 

C'est le langage de mise en forme des sites web. Alors que le HTML permet d'écrire le contenu de vos pages web et de le structurer, le langage CSS s'occupe de la mise en forme et de la mise en page. C'est en CSS que l'on choisit notamment la couleur, la taille des menus et bien d'autres choses encore.

Voici un code CSS :

![[2025-02-07_09h10_54.png]]

#### Ajoutez PHP et MySQL pour un site dynamique

Quel que soit le site web que l'on souhaite créer, HTML et CSS sont donc indispensables. Cependant, ils ne suffisent pas pour réaliser des sites dynamiques. Il faut les compléter avec d'autres langages.

C'est justement tout l'objet de ce cours : vous allez apprendre à manipuler PHP et MySQL pour réaliser un site web dynamique.

##### **PHP**

C'est un langage que seuls les serveurs comprennent, et qui permet de rendre votre site dynamique. C'est PHP qui « génère » la page web comme on l'a vu sur un des schémas précédents.

Ce sera le premier langage que nous découvrirons dans ce cours.

Voici un code PHP :

![[2025-02-07_09h11_26.png]]

##### **MySQL**

C'est grâce à MySQL que vous pourrez enregistrer :

- la liste des membres de votre site web ;
    
- les messages postés sur le forum ;
    
- etc.


Le langage qui permet de communiquer avec la base de données s'appelle le SQL.

Voici un code en langage SQL :

![[2025-02-07_09h12_11.png]]

Oublions pour le moment MySQL et concentrons nous sur PHP.

Les clients sont incapables de comprendre le code PHP : ils ne connaissent que le HTML et le CSS. Seul le serveur est capable de lire du PHP. Le rôle de PHP est justement de générer du code HTML, code qui est ensuite envoyé au client de la même manière qu'un site statique, comme le montre la figure suivante :

![[2025-02-07_09h13_23.png]]


PHP est un langage de programmation utilisé sur de nombreux serveurs pour prendre des décisions. C'est PHP qui décide du code HTML qui sera généré et envoyé au client à chaque fois.

Pour bien comprendre l'intérêt de tout cela, prenons un exemple.

> On peut écrire en PHP :
> 
> « Si le visiteur est membre de mon site et qu'il s'appelle Jonathan, affiche **Bienvenue Jonathan** sur la page web. En revanche, si ce n'est pas un membre de mon site, affiche **Bienvenue** à la place, et propose au visiteur de s’inscrire. »

C'est un exemple très basique de site dynamique : selon que vous êtes un membre enregistré ou non, vous ne verrez pas les mêmes choses, et n'aurez peut-être pas accès au même contenu.


### En résumé

- Il existe deux types de sites web :
    
    1. Les sites **statiques** : réalisés en HTML et CSS, leur contenu ne peut être mis à jour que par le webmaster.
        
    2. Les sites **dynamiques** : réalisés avec d'autres outils comme PHP et MySQL en plus de HTML et CSS, ils permettent aux visiteurs de participer à la vie du site, de poster des messages… bref, de rendre le site vivant !
        
- Les visiteurs du site sont appelés les "clients". Ils demandent au serveur qui héberge le site de leur transmettre les pages web.
    
- PHP est un langage exécuté par le serveur. Il permet de personnaliser la page en fonction du visiteur, de traiter ses messages, d'effectuer des calculs, etc. Il génère une page HTML.
    
- MySQL est un système de gestion de bases de données. Il se charge du stockage des informations (liste des messages, des membres…).





