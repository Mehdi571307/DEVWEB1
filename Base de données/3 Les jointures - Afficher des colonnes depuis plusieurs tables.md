code
![[2025-01-23_11h18_52.png]] 

![[2025-01-23_11h19_12.png]]
![[2025-01-23_11h19_27.png]]


Dans cet exemple,  le rôle du champ codecli est d'être la **==*clé étrangère*==** de la table Locations.

Dans la table Clients, son rôle sera d'être la ***==clé primaire==***.

L'instruction **==INNER JOIN==** sert à indiquer le nom d'une seconde table.
Les instructions **==INNER JOIN==** et **==ON==** permettent d'afficher des champs de la table Locations.

Avec l'instruction **==FROM==** c'est la table Clients qui est affichée.

Seul les noms des clients dont le code est présent dans les deux tables de la jointure sont affichés.
Ces colonnes proviennent des tables Clients et Locations.
Les colonnes affichées sont nomcli, codefilm et duree.

Le but de l'instruction **==ON==** et de faire la liaison entre la ***==clé primaire==*** de la table indiquée par l'instruction **==FROM==** et la clé étrangère correspondante dans la table indiquée par l'instruction **==INNER JOIN==**.

![[2025-01-23_11h32_40.png]]
![[2025-01-23_11h32_57.png]] 

Dans cet exemple, le rôle du champ codefilm dans la table Locations est d'être la ***==clé étrangère==*** 
Dans la table Films, il sera la ==***clé primaire***==.

L'instruction **==INNER JOIN==** permet d'indiquer le nom d'une deuxième table. Seuls les éléments présents dans les 2 tables sont affichés.
Les instructions **==INNER JOIN==** et **==ON==** permettent d'afficher la table Locations.

Avec l'instruction **==FROM==**, on affiche la table Films.

Seul les noms des films dont le code est présent dans les 2 tables de la jointure sont affichés. Ici des tables Films et Locations. On affiche également les colonnes nomfilm et duree.

Le but de **==ON==** est de faire la liaison entre la ***==clé primaire==*** de la table indiquée par l'instruction **==FROM==** et la clé étrangère correspondante dans la table indiquée par l'instruction **==INNER JOIN==**.



![[2025-01-23_11h44_29.png]]
![[2025-01-23_11h44_57.png]]

Le message d'erreur suivant indique que le champ codefilm est ambigu. En français ambigu signifie "dont le sens est incertain".

Dans l'instruction **==SELECT==** le champ codefilm peut provenir de la table Films ou de la table Locations . Comme le champ peut provenir de deux tables, le serveur SQL dit qu'il est ambigu.

Pour lever l'ambiguïté sur le champ codefilm dans l'instruction **==ON==**, le nom de la table de provenance du champ codefilm est précisé sous la forme table.champs.

Ce qui donne : **==SELECT==** Films.codefilm, nomfilm, duree ou lieu de **==SELECT==** codefilm, nomfilm, duree



![[2025-01-23_11h53_06.png]]
![[2025-01-23_11h53_50.png]]

Si on compare cette requête avec la précédente, on remarque que l'instruction **==INNER JOIN==** a été remplacée par **==LETF OUTER JOIN==**.
**==LEFT OUTER JOIN==** fait quand même apparaitre les noms des films dont le code n'est pas dans la table Locations dans le résultat.

![[2025-01-23_19h52_00.png]]
![[2025-01-23_19h52_21.png]]

Si on compare cette requête avec la précédente, on constate que les tables de l'instruction **==FROM==** et **==LEFT OUTER JOIN==** ont été inversées.

Lorsque l'instruction **==LEFT==** est ajoutée, le serveur SQL affiche les éléments qui sont présents dans les deux tables de la jointure *MAIS AUSSI* les éléments qui sont présents uniquement dans la table indiquée par le **==FROM==**.


![[2025-01-23_20h00_00.png]]
![[2025-01-23_20h00_16.png]]

Dans cet exemple, les colonnes affichées proviennent des tables Clients, Films et Locations.

Pour afficher les 3 tables, il faut utiliser deux fois les instructions **==JOIN==** et **==ON==**

Pour afficher les colonnes de deux tables, il faut 1 jointure. Pour afficher les colonnes de 3 tables, il en faudrait 2.

Pour afficher les colonnes de 5 tables, il faudrait faire 4 jointures. En généralisant, on peut dire que pour afficher les colonnes de x tables, il faut faire x-1 jointures.

## Synthèse : Les jointures

Si l'on veut afficher des colonnes qui proviennent de plusieurs tables, il faut utiliser les instruction **==JOIN==** et ==**ON**==.  
Grâce à l'instruction **==JOIN==**, on indique le nom d'une table supplémentaire.  
L'instruction **==ON==** fait le lien entre la *clé primaire* d'une table et la *clé étrangère*correspondante d'une autre table.  
Avec **==INNER JOIN==** seuls les éléments présents dans les deux tables de la jointure sont affichés.  
Si l'on rajoute l'instruction **==LEFT OUTER==** avant **==JOIN==**, les éléments présents dans les deux tables sont affichés ainsi que ceux qui sont présent uniquement dans la table précisée par l'instruction ==**FROM**==.
