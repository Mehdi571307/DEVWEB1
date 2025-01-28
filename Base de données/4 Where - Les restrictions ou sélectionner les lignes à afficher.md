WHERE
![[2025-01-24_09h44_39.png]]



![[2025-01-24_09h43_41.png]]
![[2025-01-24_09h44_01.png]]

Dans cet exemple, les colonnes affichées sont codecli et nomcli.
On peut voir que l'intégralité de ces colonnes n'ont pas été affichées, seul le client numéro 1, M. Dubois.

L'instruction qui a permis de sélectionner le client numéro 1 est **==WHERE==** codecli=1


![[2025-01-24_09h47_55.png]]
![[2025-01-24_09h48_13.png]]

Ici, toutes les colonnes de la table Films sont affichées grâce à l'instruction étoile ==( * )== 

On peut voir que seul le film dont le nom est Bernie apparait. L'instruction qui permet cela est **==WHERE==** nomfilm="Bernie".

Le nom du film est entouré de guillemets, pour indiquer qu'il ne s'agit ni d'une instruction SQL, ni d'un nom de table ou de colonne mais d'une chaîne de caractères (string en anglais).


![[2025-01-24_09h56_10.png]]
![[2025-01-24_09h56_28.png]]


Ici toutes les colonnes de la table Locations sont affichées grâce à l'instruction étoile **==( * )==** 

On peut voir aussi que seules les locations qui ont commencées avant le 17/04/2013 sont affichées.
Pour faire cela, on utilise l'instruction **==WHERE==** DateDebut **==<==** "2013/04/17"

Comme en mathématique, le signe **==<==** veut dire "inférieur à". C'est un opérateur de comparaison. Il en existe plusieurs :  

|Opérateur de comparaison|Signification|
|---|---|
|=|Egal|
|<|Inférieur à|
|>|Supérieur à|
|<=|Inférieur ou égal|
|>=|Supérieur ou égal|
|<>|Différent de|

La date est affichées a l'envers, c'est la façon d'écrire les dates des anglosaxons. Il est possible de modifier le format d'affichage à l'intérieur de la requête. Ce point sera étudié dans la partie suivante : 4 Afficher des données calculées.

Pour indiquer qu'il s'agit d'une date, il faut comme pour les chaines de caractères, il faut entourer les dates de guillemets.


![[2025-01-24_10h05_21.png]]
![[2025-01-24_10h05_39.png]]

Ici, toures les colonnes de la table Locations sont affichées.

On peut voir qu'il n'y a pas l'intégralité de ces colonnes qui sont affichées, parce qu'une restriction a été effectuée.
Les critères utilisés pour cette restriction sont le client numéro 1 ET le film numéro 4

Les instructions à utiliser pour combiner plusieurs critères sont **==WHERE==** Critère 1 **==AND==** Critère 2 **==AND==** Critère 3.


![[2025-01-24_10h45_47.png]]
![[2025-01-24_10h46_04.png]]

Si on compare cet exemple avec le précédent, on peut voir que les lignes qui correspondent au client 1 ou au film 4 sont affichées.

Contrairement à **==AND==**, l'instruction ==OR== permet d'afficher les lignes qui respectent au moins 1 des critères.

![[2025-01-24_10h50_14.png]]
![[2025-01-24_10h50_27.png]]

Ici on affiche toutes les colonnes de la table Locations avec l'instruction étoile **==( * )==** 

Les Locations affichées sont celles qui ont été effectuées par les clients 1, 2, et 3.
L'instruction qui permet d'utiliser ces critères de restriction sont **==WHERE==** CodeCli **==BETWEEN==** 1 **==AND==** 3. 

**==BETWEEN==** veut dire compris entre ... et .... En généralisant, cela donne **==WHERE==** Champ **==BETWEEN==** Borne Inférieure **==AND==** Borne Supérieure.

On aurait pu utiliser l'instruction **==OR==** mais cela aurait été plus long :  
**==WHERE==** CodeCli =1  
**==OR==** CodeCli=2  
**==OR==** CodeCli=3  
Attention l'instruction **==AND==** aurait affiché les films loués à la fois par les clients 1, 2, et 3.


![[2025-01-24_11h01_15.png]]
![[2025-01-24_11h01_35.png]]

Ici, les colonnes proviennent de la table Clients.

On peut voir que les deux premières lettres des clients qui sont affichées sont M et I.
Pour faire cette restriction,  on utilise l'instruction **==WHERE==** PrenomCli **==LIKE==** 'mi%'. 

Cette instruction permet de réaliser des comparaisons partielles. Le symbole **==%==** remplace 0 ou plusieurs caractères. Il est aussi possible d'utiliser le symbole _ qui remplace 1 seul caractère.

![[2025-01-24_11h04_37.png]]
![[2025-01-24_11h05_05.png]]

Ici, les colonnes proviennent de la table Locations.

On peut aussi voir que les différents code des films affichées sont 1, 2, 6.

Pour faire cette restriction, on utilise l'instruction **==WHERE==** CodeFilm **==IN==** (1, 2, 6). 
Cette instruction permet de définir une liste de valeur possible pour un champ. 
Elle remplace avantageusement le **==OR==** dans ce genre de situation car elle est bien plus rapide à écrire.

## Synthèse : Synthèse sur les restrictions

Une restriction permet de choisir les lignes que l'on affiche.  
Une restriction s'effectue avec l'instruction **==WHERE==**.  
Pour qu'une ligne soit affichée, elle doit respecter tous les critères de restriction indiqués avec un **==AND==**.  
Par contre avec un ==**OR**== il lui suffit de respecter au moins 1 des critères.  
Lorsque le critère de restriction contient une chaine de caractères ou une date, celles-ci doivent être entourées de guillemets.  
Lorsque l'on souhaite afficher toutes les lignes dont la valeur d'un champ entre dans un intervalle, on utilise l'instruction **==BETWEEN==**.  
L'instruction **==LIKE==** permet de comparer deux chaines de caractères.  
Dans ce cadre, **==%==** remplace 0 ou plusieurs caractères alors que _ en remplace forcement 1 seul.  
Pour comparer la valeur d'un champ à une liste de valeur on utilise l'instruction **==IN==**.

