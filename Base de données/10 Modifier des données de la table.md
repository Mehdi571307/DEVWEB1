
![[2025-01-27_16h27_27.png]]
![[2025-01-27_16h27_46.png]]
![[2025-01-27_16h28_05.png]]


Dans cet exemple, l'effet de la requête est que la valeur du champ VilleCli est Haguenau pour tous les clients.

L'instruction qui permet de choisir la table dans laquelle on va modifier des lignes est **==UPDATE==** Nom de la table.

L'instruction qui permet d'indiquer le champ à modifier est **==SET==** Nomduchamp="Valeur".


![[2025-01-27_16h31_52.png]]
![[2025-01-27_16h32_09.png]]

Ici, on constate que par rapport à la requête de l'exemple 1, on constate une ligne **==WHERE==** Codecli=1 qui a été rajoutée.

L'effet de cette ligne sur la requête est une restriction. La requête ne s'applique qu'aux lignes qui ont un Codecli égal à 1.



![[2025-01-27_16h35_10.png]]
![[2025-01-27_16h35_29.png]]

Ici, comparé a l'exemple n°2, on constate que le champ cpcli a été rajouté dans l'instruction **==SET==**

L'effet de cet ajout est que la requête permet de modifier deux valeurs de champ d'un seul coup.


## Synthèse : Update

Pour modifier les valeurs des champs on utilise l'instruction **==UPDATE==** pour indiquer la table dans laquelle on veut effectuer des modifications.  
On indique le nom des champs avec l'instruction **==SET==**.  
Il est possible de modifier la valeur de plusieurs champs en séparant les couples champs="valeur" par des virgules.
