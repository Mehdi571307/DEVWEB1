
Base de donnée avec 3 tables, une clients, une films, et une locations

La table Clients comporte : 

-  Un id unique ==**clé primaire**== ( codecli )
-  Les prénom des clients ( prenomcli )
-  Le nom des clients ( nomcli )
-  La rue des clients ( ruecli )
-  Le code postale ( cpcli )
-  La ville des clients ( villecli )

Une table Films qui comporte :
 - Un id **==clé primaire==** ( codefilm )
 - Le nom des films ( nomfilm )

Une table Locations qui comporte :
-  Un id **==clé primaire==** ( codecli ) *clé étrangère* : ( codecli ) de la table Clients
-  Un id **==clé primaire==** ( codefilm) *clé étrangère* : ( codefilm ) de la table Films
-  Une date de début de location ( datedebut )
-  La durée ( duree )


![[2025-01-23_08h54_46.png]]
![[2025-01-23_09h16_34.png]]
==**SELECT**== duree = Afficher la colonne duree 

==**SELECT**== est l'instruction qui indique la colonne à afficher

La colonne provient de la table Locations

==**FROM**== est l'instruction qui indique dans quelle table il fat chercher la colonne à afficher

Les requête se termine toujours pas point virgule ==**( ; )**==  


![[2025-01-23_09h17_51.png]]
![[2025-01-23_09h18_08 1.png]]

La colonne affichée est nomcli 

La colonne provient de la table Clients

L'instruction **==FROM==** indique dans quelle table il faut chercher la colonne à afficher

**==SELECT==** est l'instruction qui permet de choisir la colonne à afficher

![[2025-01-23_09h25_13.png]]
![[2025-01-23_09h25_33.png]]

Les colonnes affichées sont ruecli et villecli 

Elles proviennent de la table Clients

Pour afficher plusieurs colonnes, on ajoute après le **==SELECT==** toutes les colonnes que l'on souhaite afficher en les séparant par des virgules. 

Les requêtes se termine toujours par un point virgule ==(  ;  )== 

![[2025-01-23_09h29_27.png]]
![[2025-01-23_09h30_00.png]]

L'instruction **==SELECT==** permet d'afficher la colonne nomfilm 

Dans la table résultat, cette colonne porte le nom de *==" Le titre du Film "==*, on a rajouté **==AS==** et le titre voulu entre guillemets après le nom de la colonne dans l'instruction **==SELECT==**.


![[2025-01-23_09h33_29.png]] 
![[2025-01-23_09h34_08.png]]

Les colonnes affichées dans la table résultat sont toutes les colonnes de la table Clients.

Pour cela pas besoin d'indiquer toutes les colonnes dans la requête, ils ont été remplacés par une étoile **==(  *  )==**


![[2025-01-23_09h37_04.png]]
![[2025-01-23_09h37_23.png]]

La colonne affcihée grâce à l'instruction **==SELECT==** est villecli 

Dans la base de donnée, la colonne villecli comporte 11 lignes, le résultat donné dans la colonne comporte 3 lignes.
Des villes apparaissent plusieurs fois dans la table Clients. Pour ne faire apparaitre les villes qu'une seule fois, on dit que les doublons ont été supprimés.

L'instruction **==DISTINCT==** qui est placée juste après l'instruction **==SELECT==** permet de supprimer les doublons. 

## Synthèse : Afficher les colonnes depuis une table.

Les requêtes finissent par des points virgules.  
L'instruction **==SELECT==** permet d'afficher une ou plusieurs colonnes d'une table.  
L'instruction **==FROM==** permet de choisir la table dans laquelle on va chercher les informations.  
Pour afficher plusieurs colonnes, il faut séparer chaque nom de colonne par une virgule.  
Pour afficher toutes les colonnes d'une table, il faut indiquer une étoile après le **==SELECT==**.  
Pour modifier le titre d'une colonne que l'on a affichée grâce à un **==SELECT==**, il faut rajouter après son nom le mot **==AS==** puis, entre guillemets, le titre que l'on souhaite afficher.


