
La structure **==for==** permet d'écrire des boucles dont on connait à l'avance le nombre d'itérations à exécuter.

![[2025-01-29_13h21_47.png]]

**initialisation** : permet d'initialiser la variable représentant l'indice de la boucle. C'est la première des instructions exécutées, à l'entrée de la boucle.

( exemple : $i = 1 )

**condition** : définit la condition à vérifier pour continuer à exécuter la boucle. Elle est examinée avant chaque tour de boucle.

( exemple : $i <= 10 )

**incrément** : est l'instruction qui permet de modifier le résultat du test. Cette instruction est exécutée à la fin de chaque tour de boucle.

( exemple : $i = $i+1 ou $i++)

![[2025-01-29_13h27_01.png]]


![[2025-01-29_13h31_34.png]]
![[2025-01-29_13h32_01.png]]
![[2025-01-29_13h32_22.png]]


Dans cet exemple, pour les deux boucles for, les valeurs de $i et $j à l'initialisation sont : 
 - Pour $i il est initialisé à 0
 - Pour $j il est initialisé à 1
Pour les deux boucles for on compare les valeurs de $i et $j avant d'effectuer la boucle, la comparaison est la suivante :  
- boucle 1 : est ce que le contenu de la variable $i est inférieur à 5 ?  
- boucle 2 :est ce que le contenu de la variable $j est inférieur ou égal à 5 ?

  
Pour la première : au départ $i=0 et on exécute la boucle tant que $i est inferieur à 5.  
La boucle sera exécutée 5 fois.  
Pour la deuxième boucle $j vaut 1 au départ et on exécute la boucle tant que $j est inférieur ou égal à 5.  
La boucle sera exécutée 5 fois aussi.

  
Pour la première :  
Au départ : $i=0  
On exécute la boucle pour $i = 0 puis 1, 2 , 3, 4   
Lorsque $i=4 on exécute la boucle et on incrémente $i : $i =5  
On teste la condition et comme ce n'est plus inférieur à 5 on sort de la boucle.  
  
Pour la deuxième :
Au départ : $j=1  
On exécute la boucle pour $j = 1 puis 2, 3 , 4, 5   
Lorsque $j=5 on exécute la boucle et on incrémente $j : $j =6  
On teste la condition et comme ce n'est plus inférieur ou égal  à 5 on sort de la boucle.


On exécute la première boucle,  une fois sortie de la boucle 1 on exécute la deuxième.



![[2025-01-29_13h49_03.png]]
![[2025-01-29_13h50_20.png]]

Ici, pour l'exécution d'une fois la boucle 1 on fait 5 fois ma boucle 2

La boucle 1 est exécutée 5 fois et comme à chaque exécution de la boucle 1 on exécute 5 fois la boucle 2, la boucle 2 sera donc exécutée : 25 fois au total.




