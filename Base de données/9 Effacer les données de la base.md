
![[2025-01-27_16h02_52.png]]
![[2025-01-27_16h03_08.png]]
![[2025-01-27_16h03_28.png]]


Dans cet exemple, la requête a eu pour effet de supprimé toutes les lignes de la table Locations.

La requête qui devrait permettre d'effacer la table Clients est   
**==DELETE==** **==FROM==** Clients;


![[2025-01-27_16h05_22.png]]
![[2025-01-27_16h05_43.png]]

Dans cet exemple, la table qui devrait être supprimée est la table Clients.

Le message d'erreur qui s'affiche, signifie qu'il y a une erreur à cause de la contrainte de clé étrangère qui s'appelle FK_location_clients. 

Cette contrainte relie la table LOCATION à la table CLIENTS par la clé étrangère CodeCli. 

Il est donc impossible de supprimer une ligne de la table CLIENTS qui contient un CodeCli qui apparait dans la table LOCATION. Cela voudrait dire qu'un client inconnu à loué un film

Les lignes de la table Clients que l'on peut supprimer sont toutes les lignes qui contiennent des CodeCli qui ne sont pas dans la table LOCATION. 

Les clients 8, 9, 10, et 11 n'ont jamais loué de film, on peut donc les supprimer de la table.

Pour supprimer les autres lignes, il faut commencer par supprimer les lignes de la table Locations dans lesquelles apparaissent des codecli que l'on souhaite supprimer. Puis ensuite supprimer les lignes de la table Clients.


![[2025-01-27_16h10_27.png]]
![[2025-01-27_16h10_45.png]]


Dans cet exemple, la requête a supprimé une ligne dans la table Films.

C'est la ligne du film 11 qui a été supprimé.

La suppression de cette ligne ne pose pas de problème de contrainte de clé étrangère, parce que le film n°11 n'a jamais été loué.

Le codefilm 11 a été sélectionné grâce à une restriction avec l'instruction **==WHERE==**. Les restrictions vues dans les requêtes de sélection s'appliquent de la même façon aux requêtes de modification.

## Synthèse : Delete

Pour supprimer une ou plusieurs lignes dans une table on utilise l'instruction **==DELETE==** **==FROM==**.  
Pour sélectionner les lignes à supprimer on utilise l'instruction **==WHERE==**.


