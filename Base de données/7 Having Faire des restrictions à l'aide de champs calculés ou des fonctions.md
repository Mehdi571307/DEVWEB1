 L![[2025-01-27_14h05_48.png]]
![[2025-01-27_14h05_32.png]]
![[2025-01-27_14h06_02.png]]

Ici la colonne affichée est villecli de la table Clients.

Toutes les villes ne sont pas affichées, il manque Freyming.

**==HAVING==** permet de faire une restriction à l'aide d'un agrégat. Cela signifie qu'on utilise le **==COUNT==** pour sélectionner les lignes de la table à afficher.
Il est impossible de comprendre le tableau résultat sans avoir la requête sous les yeux. Il est donc conseillé d'afficher à l'aide d'un select le champ sur lequel on effectue la restriction.


![[2025-01-27_14h11_44.png]]
![[2025-01-27_14h12_00.png]]


Ici cette requête permet d'afficher les durées moyennes de location supérieures à 2 jours pour chaque client.

L'instruction qui affiche les moyennes est  **==SELECT==** le champ **==AVG==**(duree).

L'instruction qui permet d'afficher les moyennes pour chaque client est **==GROUP BY==** codecli.

L'instruction qui permet d'afficher uniquement les durées moyennes de location supérieures à 2 jours est **==HAVING==** **==AVG==**(duree)>2.

## Synthèse : Having

Une restriction permet de sélectionner les lignes que l'on souhaite afficher.  
Une restriction peut se faire avec un **==WHERE==** ou un **==HAVING==**.  
L'instruction HAVING s'utilise quand on veut un agrégat comme critère de restriction.  
Un agrégat s'obtient grâce aux fonctions **==SUM==**, **==COUNT==**, **==AVG==**, **==MIN==**, **==MAX==**.

