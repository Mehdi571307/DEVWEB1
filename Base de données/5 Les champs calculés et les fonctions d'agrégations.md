

![[2025-01-24_11h52_24.png]]


![[2025-01-24_11h52_04.png]]
![[2025-01-24_11h52_40.png]]

Ici on affiche grâce a cette requête les 3 colonnes codecli, Durée de la location et Prix de la location

On note que la colonne "Prix de la location n'apparait pas dans la base données".
C'est un champ calculé.

En faisant duree * 3, on arrive a calculer ce champ.

L'instruction qui permet de faire cela est **==SELECT==** duree3 **==AS==** "Prix de la location". 

Comme la colonne duree3 n'existe pas, il est obligatoire de la nommer grâce à l'instruction **==AS==**. On peut utiliser les opérateurs mathématiques simples pour créer un champ calculé : + - / * 


![[2025-01-24_11h58_38.png]]
![[2025-01-24_11h58_54.png]]

Ici, l'instruction qui a permis d'afficher la durée de location la plus longue est **==SELECT MAX==** (Duree) **==AS==** "Duree de la location la plus longue".

**==MAX==** (champ) est une fonction d'agrégat. Une fonction d'agrégat permet de faire des calculs sur un champ. Il existe plusieurs fonctions d'agrégat : **==MIN==**, **==MAX==**, **==COUNT==**, **==SUM==**, **==AVG==** 

Il faut nommer les colonnes qui affichent une fonction d'agregat, parce qu'elle n'existe pas dans la base de données.



![[2025-01-24_13h08_09.png]]
![[2025-01-24_13h08_47.png]]

Dans cet exemple, chaque colonne a une fonction bien a elle : 

**==MIN==** affiche le minimum
**==MAX==** affiche le maximum
**==AVG==** affiche la moyenne
**==COUNT==** compte le nombre d'éléments
**==SUM==** additionne tous les éléments sélectionnés.


![[2025-01-24_13h12_04.png]]
![[2025-01-24_13h12_19.png]]

Dans cet exemple, la fonction qui permet d'effectuer un arrondi est **==ROUND==**(champ, entier).

Si on avait voulu afficher la durée moyenne de location arrondi à 1 chiffre après la virgule, on aurait écrit **==ROUND==**(**==AVG==**(duree),1) Si vous saisissez un entier négatif vous arrondirez les chiffre à gauche de la virgule : -1 arrondi à la dizaine, -2 à la centaine etc.

## Synthèse : Synthèse sur les fonctions et les agrégats

Les champs calculés s'obtiennent en utilisant les **==opérateurs mathématiques + * - /==** sur des champs.  
La fonction qui permet de trouver la plus petite valeur d'un champ est **==MIN(champ) AS "Nom de la colonne"==**.  
La fonction qui permet de trouver la plus grande valeur d'un champ est **==MAX(champ) AS "Nom de la colonne"==**.  
La fonction qui permet de calculer la moyenne d'un champ numérique est **==AVG(champ) AS "Nom de la colonne"==**.  
La fonction qui permet de compter le nombre de ligne d'un champ est **==COUNT(champ) AS "Nom de la colonne"==**.  
La fonction qui permet d'additionner les valeurs d'un champ est **==SUM(champ) AS "Nom de la colonne"==**.  
La fonction qui permet d'arrondir la valeur d'un champ est
**==ROUND(champ, nombre de chiffre après la virgule) AS "Nom de la colonne"==**.
code




