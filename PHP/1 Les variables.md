
## Support de cours : C'est quoi le php ?

Le php est un langage serveur (c'est à dire qu'il est exécuté sur une machine serveur) et permet de générer des pages au format _**html.**_

Un client exécute un fichier **php** sur le serveur qui lui renvoi une page au format **html**. 

Par exemple le client exécute le fichier php en tapant dans un navigateur l'adresse suivante  (URL): 

**_https://monsiteweb/accueil.php_**

Le serveur génère alors la page au format **html** pour l'afficher dans le **navigateur.**

![[2025-01-28_12h55_32.png]]


Ce langage permet de réaliser des pages web dynamiques.

Le code PHP est inséré entre les balises :

![[2025-01-28_13h00_49.png]]


Dans les exercices/cours qui vont suivre on considèrera que le code PHP est toujours inséré entre les balises d'ouverture/fermeture ![[2025-01-28_13h01_40.png]]

![[2025-01-28_13h01_57.png]]


![[2025-01-28_13h03_25.png]]
![[2025-01-28_13h04_49.png]]
![[2025-01-28_13h05_10.png]]

Dans cet exemple, l'instruction qui permet d'afficher le texte à l'écran est **==echo==** 

En PHP chaque instruction doit se terminer par un point virgule **==(  ;  )==** (comme beaucoup de langages).

Pour ajouter un commentaire il faut mettre **//** sur la ligne après l'instruction.

Pour ajouter un commentaire sur plusieurs lignes il faut l'insérer entre les caractères : / * et  * /


![[2025-01-28_13h14_04.png]]
![[2025-01-28_13h14_19.png]]
![[2025-01-28_13h14_36.png]]

Dans cet exemple, les instructions qui permettent d'afficher une chaine de caractères sont **==echo==** et **==print==**.

Pour afficher du texte l'un en dessous de l'autre, on utilise du code HTML, qui sera interpreté ( parsé ) par le navigateur. Ici nous avons encadré le texte que nous voulions afficher entre les balises ![[2025-01-28_13h19_05.png]]


![[2025-01-28_13h19_28.png]]
![[2025-01-28_13h19_46.png]]
![[2025-01-28_13h20_07.png]]


Dans cet exemple, on remarque une variable. Une variable que l'on désigne par un ==**nom**== contient une ==**donnée**==.    
Si on écrit x=3   ( x représente la variable et 3 la donnée )  
On affecte à une variable une valeur, qui pourra au cours du programme être modifiée.

Ici, la variable a pour nom : **==$nb==**  

Au départ, on affecte à la variable $nb la valeur 3, puis ensuite on modifie cette valeur à -5.

Dès que l'on a besoin de stocker une information dans un programme, on utilise une variable.

## **4 types de données à stocker :** 

- Les nombres entiers : int ( integer )
- Les nombres réels : float ou double
- Les booléens : boolean ( TRUE, FALSE )
- Les chaines de caractères : string 

## **Noms de variables** 

Les variables en PHP se trouvent sous la forme : **==$nom_variable==** 

 - Ils doivent commencer par une lettre ( majuscule ou minuscule ) ou un _  ( pas par un chiffre )
 - Ils peuvent comporter des lettres, des chiffres et le caractère __ ( les espaces ne sont pas autorisés )
 - **Attention aux minuscules et aux majuscules !!!** 


## Synthèse : Les variables synthèse

  
On distingue 4 types de variables, en PHP les variables ne sont pas typées c'est à dire qu'il n'est pas nécessaire de les déclarer dans le programme.  
  
Le nom d'une variable commence par un **==$==** et  doit commencer par une lettre ou le caractère _.  
  
en faisant attention à la casse .  
Le nom d'une variable ne peut  comporter un espace.



![[2025-01-28_13h37_19.png]]
![[2025-01-28_13h37_40.png]]
![[2025-01-28_13h37_56.png]]


Ici la variable chaine est du type "**==string==**", en PHP on ne déclare pas une variable, le typage se fait automatiquement lors de l'affectation de la valeur à la variable.

La variable s'appelle **==$chaine==**, en PHP une variable commence toujours par un $ 


![[2025-01-28_13h42_42.png]]
![[2025-01-28_13h42_56.png]]
![[2025-01-28_13h43_09.png]]

Pour afficher le contenu d'une variable en PHP, a l'intérieur d'une chaine entre guillemet les valeurs sont remplacées par leur valeur.

A l'intérieur d'une chaîne entre guillemet simple les variables ne sont pas remplacées par leur valeur.

Pour afficher des guillemet dans une chaine de caractère, on utilise le caractère d'échappement \ 

Le . ( point ) permet de concaténer une chaîne de caractères.


## Synthèse : Les chaines de caractères synthèse

1) Dans une chaine délimitée par des guillemets simples , les variables ne sont pas remplacées.  
   
2) Dans une chaine délimitée par des guillemets doubles , les variables sont remplacées.  
   
3) Pour afficher un caractère protégé on utilise le caractère \  
4) En PHP deux chaînes séparées par un .  
   (point) sont concaténées .


![[2025-01-28_13h50_10.png]]
![[2025-01-28_13h50_36.png]]
![[2025-01-28_13h50_50.png]]


## Support de cours : Les entiers (integer)

Les entiers (integer) permettent de stocker un nombre entier signé sur 32 ou 64 bits . En cas de dépassement de capacité dans un calcul le nombre est automatiquement converti en réel (nombre à virgule flottante):

• Le décimal   :   $pos_x   = 123  ; 

• L'hexadécimal   :   $pos_y   = 0x7B  ; 

• L'octal   :   $delta  = 026  ;


![[2025-01-28_14h07_11.png]]
![[2025-01-28_14h07_26.png]]
![[2025-01-28_14h07_39.png]]


## Support de cours : Les Réels

Les réels (float) permettent de stocker un nombre à virgule flottante. 

Un nombre à virgule flottante comporte soit un point soit un "e" (majuscule ou minuscule) pour séparer l'exposant

  $nombre = 3.14159;

  $nombre = 8e5;

  $nombre = 1.000;


![[2025-01-28_14h34_47.png]]
![[2025-01-28_14h35_03.png]]
![[2025-01-28_14h35_20.png]]


Pour écrire un nombre avec un exposant, on utilise le caractère **==e==** pour séparer l'exposant. Ainsi 8e-5 correspond au chiffre : 0.00008


## Support de cours : Les Booléens

**Le type de variable booléen accepte deux états:**

•**True** **(vrai) :** **1** **correspondant à une valeur vraie**

•**False** **(faux) :** **0** **correspondant à une valeur fausse**

$bool = TRUE

$bool = FALSE

True et False sont des mots clés insensibles à la casse


![[2025-01-28_14h47_14.png]]
![[2025-01-28_14h47_28.png]]
![[2025-01-28_14h47_44.png]]


Ici, les variables $bool1 et $bool2 sont des variables booléennes qui ne peuvent prendre que deux valeurs : true ou false ( true et false sont insensibles à la casse )

La fonction **==var_dump==** affiche les informations d'une variable : type, valeur.


