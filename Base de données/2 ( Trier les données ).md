
## Cours à partir de cette base de données :

![[2025-01-23_10h01_10.png]] 
![[2025-01-23_10h02_13.png]]
![[2025-01-23_10h02_49.png]]

Les données affichées proviennent de la table Livres 

On peut voir ici que les livres ne sont pas classés dans le même ordre que dans la base de données.
Ils sont triés dans l'ordre croissant des prix ( du plus petit au plus grand ) avec **==ORDER BY==**


![[2025-01-23_10h37_45.png]]
![[2025-01-23_10h38_05.png]]

Dans cet exemple, les livres sont classés dans l'ordre décroissant des prix.

L'instruction qui permet de classer dans l'ordre décroissant est **==ORDER BY==** nom_du_champs **==DESC==**. Ici **==ORDER BY==** prix **==DESC==** 



![[2025-01-23_10h41_46.png]] 
![[2025-01-23_10h42_03.png]] 

Ici la table a été triée dans l'ordre alphabétique du nom de famille du client avec l'instruction **==ORDER BY==**


![[2025-01-23_10h43_31.png]]
![[2025-01-23_10h46_44.png]]


Toutes les colonnes de la table Clients sont affichées grâce à cette requête, avec l'instruction **==SELECT==** suivie de l'étoile ==( * )==
Mais ici la table de cet exemple à été triée dans l'ordre décroissant des noms de famille, grâce a l'instruction **==ORDRE BY==** nomcli **==DESC==**.


![[2025-01-23_10h52_14.png]]
![[2025-01-23_10h52_34.png]]
![[2025-01-23_10h52_49.png]]

Dans cet exemple, il y a dans chaque requête deux champs dans les instructions **==ORDER BY==**
 - prix **==DESC==** et isbn dans la première
 - prix **==DESC==** et titre dans la deuxième
Si on compare les résultats donnée pour chaque requête, on constate que seule l'ordre des livres a 7€ à changer.
 - Dans la première requête, ils sont triés dans l'ordre alphabétique des ISBN.  ( prix DESC, isbn )
 - Dans la seconde dans l'ordre alphabétique des titres. ( prix DESC, titre )
  
Le second champ sert à trier les lignes dont la valeur du premier champ utilisé dans le **==ORDER BY==** est identique. Dans notre exemple le second champ est utilisé uniquement pour trier les livres qui ont un prix identique.

On peut en mettre autant qu'on veut. Le troisième champ s'appliquera uniquement au ligne dont la valeur des 2 premiers champs est identique. Par exemple on classe souvent les étudiants qui ont le même nom et le même prénom par date de naissance. 


## Synthèse : Trier des données

Pour classer dans l'ordre croissant des colonnes on utilise l'instruction **==ORDER BY==** Champ.  
Pour classer dans l'ordre décroissant on utilise l'instruction **==ORDER BY==** Champ **==DESC==**.  
L'ordre alphabétique correspond à l'ordre croissant.  
Il est possible d'indiquer plusieurs champs dans une instruction **==ORDER BY==**.  
Le second champ s'applique uniquement aux lignes qui ont des valeurs identiques pour le premier champ.  
  
L'instruction ==**ORDER BY**== est toujours la dernière instruction.


