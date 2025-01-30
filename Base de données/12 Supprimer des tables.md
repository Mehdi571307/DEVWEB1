
![[2025-01-28_11h55_01.png]]
![[2025-01-28_11h55_23.png]]

Dans cet exemple, la table Locations a été supprimée.

Pour indiquer le nom de la table à supprimer,  on indique le nom de la table à supprimer après l'instruction **==DROP TABLE


![[2025-01-28_11h57_29.png]]
![[2025-01-28_11h57_49.png]]

Dans cet exemple, la requête a échoué, parce qu'une contrainte de clé étrangère bloque la requête. Si on supprime la table CLIENTS, alors il y aura des codeclient inconnus dans la table Locations.

Pour supprimer la table Clients, il faut soit commencer par supprimer la table Locations, soit supprimer ma contrainte de clé étrangère.

## Synthèse : Suppression table

Pour supprimer une table on utilise l'instruction **==DROP TABLE==** nomtable.  
Il faut tenir compte des contraintes de clé étrangère.

