
## Structure if else

La structure **==if==** **==else==** se traduit en français en si / sinon. Elle permet de programmer un choix, en plaçant derrière le terme **==if==** une condition.

La structure **==if==** / **==else==** se conduit de la façon suivante :

![[2025-01-28_16h00_46.png]]
![[2025-01-28_16h02_44.png]]

![[2025-01-28_16h02_58.png]]
![[2025-01-28_16h04_42.png]]


La condition est une comparaison, elle est toujours entre parenthèses. Ici on compare si $nb_a est supérieure à $nb_b 

La structure du programme est la suivante : 

![[2025-01-28_16h07_50.png]]

Lorsque l'on ouvre une accolade, on décale le code ( tabulation ) vers la droite pour avoir une écriture lisible, à la fermeture de l'accolade on revient avec une tabulation vers la gauche.

Si les 2 nombres sont égaux, comme la condition est fausse, on exécute ce qui est dans le bloc **==else==**

Pour éviter ce problème il faut tester le cas particulier : 

![[2025-01-28_16h13_42.png]]


![[2025-01-28_16h15_34.png]]
![[2025-01-28_16h15_46.png]]
![[2025-01-28_16h15_59.png]]

Dans ce **==if==**, on teste 2 choses : que la moyenne soit supérieure ou égale à 12 **==ET==** que la moyenne soit inférieure ou égale à 14 

On a utilisé l'opérateur logique **==&&==** pour créer un **==ET==** logique. Le résultat de notre condition est booléen ( **==TRUE==** ou **==FALSE==** )
**Attention aux parenthèses !!!** 

![[2025-01-28_16h20_47.png]]
![[2025-01-28_16h21_05.png]]
![[2025-01-28_16h21_20.png]]


Ici, chaque couple **==if==** / **==else==** ( avec son contenu ) est décalé de la même tabulation vers la droite. Sans indentation le code serait illisible. 

![[2025-01-28_16h27_01.png]]
![[2025-01-28_16h27_18.png]]
![[2025-01-28_16h27_32.png]]

Dans cet exemple, il y a 3 structures **==if-else==** et les if sont imbriqués les uns dans les autres.

Chaque couple **==if-else==** ( avec sont contenu ) est décalé de la même tabulation vers la droite. Sans indentation le code serait illisible.

## Structure Switch 

Cette instruction permet de faire **plusieurs tests** sur la valeur d'une variable, ce qui évite d'utiliser plusieurs if imbriqués et cela simplifie la lecture du code.

**Exemple :**

![[2025-01-28_16h34_17.png]]


![[2025-01-28_16h35_57.png]]
![[2025-01-28_16h36_12.png]]
![[2025-01-28_16h36_26.png]]


Switch évalue la variable $choix et exécute le code correspondant suivant les différents cas prévus ( case ).
Ici les cas sont : $choix = 1, 2, 3 ou une autre valeur.

Exemple : 

**Si $choix = "toto"** 

On exécutera le code qui correspond à **==default==** 
Il faut toujours utiliser le cas défault pour prévoir tous les cas et éviter un bug de notre programme.

Pour sortir du bloc switch, on utilise l'instruction **==break==**, qui entraine l'exécution de la prochaine instruction située à l'extérieur de l'instruction ( ou du bloc ) **==switch==** 

On aurait pu utiliser la structure **==if-else==** : 

![[2025-01-28_16h44_31.png]]

## Synthèse : conditionnelle synthèse

Les conditionnelles permettent d'exécuter des instructions en fonction d'une ou plusieurs conditions .  
Ces structures fonctionnent à partir d'un test, ce test est une expression qui doit renvoyer une valeur comprise comme un comparaison .  
  
Le plus souvent on utilise des opérateurs logiques et de booléen .  
   
L'instruction  **==if ( )==** est la structure la plus basique, elle permet d'exécuter une suite d'instructions en fonction d'une condition, la clause **==else==** peut spécifier une suite d'instructions à exécuter si la condition n'est pas réalisée.  
Il est possible d'enchaîner une série d'instructions **==if==** ( sans avoir besoin de les imbriquer ) à l'aide de l'instruction **==else==** **==if==** .  
   
Si le nombre de test sur une variable est important on peut utiliser l'instruction **==switch==** , ce qui évitera de faire plusieurs **==if==** imbriqués.  

