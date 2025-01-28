
![[2025-01-27_13h22_51.png]]
![[2025-01-27_13h23_06.png]]
![[2025-01-27_13h23_33.png]]


Dans cet exemple, la requête permet d'afficher le nom des clients de la table Clients et le nombre de code client dans la table location pour chaque client.

L'instruction qui a permis de compter le nombre de location est   
==COUNT==(LOCATIONS.CodeCLi). 

En comptant le nombre de codecli dans la table LOCATIONS, on peut connaitre le nombre de location. En effet lors de chaque location, une ligne qui contient le code du film, le code du client et la date de location est ajoutée à la table LOCATIONS.

L'instruction qui a permis d'utiliser la fonction COUNT pour chaque client et **==GROUP BY==** LOCATION.CodeCli.


![[2025-01-27_13h29_15.png]]
![[2025-01-27_13h29_30.png]]


Ici les colonnes affichées grâce à cette requête sont le nom des films et pour chaque film la durées de location.

L'instruction qui a permis de calculer la durée de location est **==SUM==**(duree)

L'instruction qui a permis de regrouper ce calcul pour chaque film est **==GROUP BY==** Films.Codefilm

## Synthèse : Synthèse sur les regroupements

L'instruction **==GROUP BY==** permet d'effectuer un calcul sur un groupe d'enregistrement.  
Généralement il faut utiliser l'instruction **==GROUP BY==** quand on cherche à obtenir une information pour chaque élément.  
Il est souvent plus judicieux de faire un **==GROUP BY==** sur une clé primaire.
