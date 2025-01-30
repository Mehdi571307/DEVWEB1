

![[2025-01-28_11h17_11.png]]
![[2025-01-28_11h17_54.png]]
![[2025-01-28_11h18_39.png]]
![[2025-01-28_11h19_58.png]]

Dans cet exemple, on remarque que deux requêtes sont présentées, une requête **==CREATE TABLE==** et une requête **==INSERT INTO==**

Les requêtes ont servi a créer une table Cd et d'y insérer des données.

Dans la première requête, l'instruction qui permet de créer la table est   
**==CREATE TABLE==** suivi du nom de la table. Ici la table créée s'appelle CD.

codecd et nomcd sont les noms des champs créés ( les titres des colonnes de la table CD ).

INT et VARCHAR correspondent aux types de variables. **==INT==** correspond à INTEGER c'est à dire des nombres entiers. **==VARCHAR(40)==** veut dire des chaines de caractère d'une taille maximale de 40 caractères.

**==PRIMARY KEY==** veut dire clé primaire. Ici le champ CodeCD est la clé primaire de la table CD. La clé primaire est le champ qui permet d'identifier chaque ligne de la table. Cela implique que chaque CodeCD est unique : 2 CD ne peuvent avoir le même CodeCD.


![[2025-01-28_11h29_12.png]]
![[2025-01-28_11h29_58.png]]
![[2025-01-28_11h30_43.png]]
![[2025-01-28_11h31_04.png]]


Si on compare la requête **==CREATE==** **==TABLE==** de l'exemple 1 et celle-ci, on constate qu'il y a plusieurs changements. Pour le champ codecd, le mot clé utilisé pour indiquer qu'il s'agit d'un entier est devenu INTEGER et l'attribut **==PRIMARY KEY==** a été inséré. Pour le champ nomcd, l'attribut **==DEFAULT==** a été rajouté avec la valeur 'a saisir'.

On constate dans la première requête **==INSERT==** que la valeur définie pour le codecd est 'null'. 

Dans la base le codecd rajouté est 1 puis 2. 

On dit que le codecd s'auto incrémente. Il augmente de 1, lors de chaque **==INSERT==**. Cela évite de chercher la dernière valeur de la clé primaire avant d'insérer une nouvelle ligne.

Dans la deuxième requête **==INSERT==**, une seule valeur a été indiquée. C'est la valeur null pour le codecd.

Le codecd ajouté est le 3 grâce à l'auto incrémentation. Le nomcd est 'a saisir'. La valeur 'a saisir' correspond à la valeur par défaut précisée dans la requête **==CREATE==** à l'aide de l'attribut **==DEFAULT==**


## Synthèse : Création table

Pour créer une table on utilise l'instruction **==CREATE TABLE==** nomtable ().  
Entre les parenthèses on indique les nom des champs suivi de leur type.  
Chaque champ est séparé par des virgules.  
Il est possible de rajouter l'attribut **==DEFAULT==** qui indique la valeur d'un champ lorsqu'une requête d'insertion ne la précise pas.  
L'attribut **==AUTO_INCREMENT==** augmente la valeur d'un champ de 1 à chaque fois qu'une nouvelle est insérée.  
L'instruction **==PRIMARY KEY==**(champ) permet d'indiquer qu'un champ est une clé primaire.