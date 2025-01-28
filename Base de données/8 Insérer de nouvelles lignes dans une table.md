
![[2025-01-27_15h03_31.png]]
![[2025-01-27_15h03_56.png]]
![[2025-01-27_15h04_18.png]]


Avant cette requête, il y avait 11 clients dans la table Clients.
Après cette requête, il y a 12 clients dans la table Clients.

L'instruction qui a permis de choisir la table Clients et **==INSERT INTO==** Clients.

Dans la requête, l'instruction qui a permis d'indiquer la valeur des champs des lignes insérées est 
**==VALUES==**('12', 'Scott', 'BIS', '3, rue des Capucins', '67500', 'Haguenau')



![[2025-01-27_15h40_09.png]]
![[2025-01-27_15h40_29.png]]


Ici, une ligne a été rajoutée a la table Locations.

Dans l'exemple n°2, 3 champs ont été rajoutés après le nom de la table (codecli, codefilm et datedebut).

Les valeurs qui ont été ajoutées à la table Locations est   
CodeCli --> 7 CodeFilm --> 11 DateDebut --> 2013/05/31 --> Durée -->0

On ne retrouve pas toutes les valeurs ajoutées à la table dans l'instruction VALUES.
La durée 0 n’apparaît pas dans la requête. MySql a complété la table avec la valeur par défaut de la table. 
Vous apprendrez à configurer la valeur par défaut lors de la création de la table.

Si on souhaite insérer une ligne sans indiquer toutes les valeurs de cette ligne, il faut indiquer dans le **==INSERT INTO==** les champs auxquels ont souhaite donner une valeur puis indiquer cette valeur dans l'instruction **==VALUES==**



![[2025-01-27_15h48_43.png]]
![[2025-01-27_15h49_07.png]]

Dans cet exemple, 2 lignes ont été rajoutées à la table de location.

Pour insérer plusieurs lignes, dans l'instruction **==VALUES==**, il faut indiquer les valeurs de chaque ligne entre des parenthèses et séparer chaque ligne par des virgules.


## Synthèse : INSERT INTO

Lorsqu'on insère une ligne dans une table, on utilise l'instruction **==INSERT INTO==** pour indiquer dans quelle table on insère la ligne.  
Pour indiquer les valeurs à insérer on utilise l'instruction **==VALUES==**.

