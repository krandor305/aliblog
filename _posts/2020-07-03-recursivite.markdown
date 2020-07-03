---
layout: post
title:  "La recursivité"
date:   2020-07-03 00:00:00 +0530
categories: Algorithmes Concepts
---

La récursivité est l’appel d’une fonction à l’intérieur d’elle-même. C’est un élément très important à la fois en programmation car il permet la répétition de la même fonction pour résoudre un problème mais c’est aussi une manière de penser pour résoudre un problème.Tout ceci est vague ? Pas de panique, cet article vous explique ce concept d’une manière simple et grâce à un exemple détaillé.

## Entamons un exemple : 

Nous voulons renvoyer la somme de 3 chiffres : 10, 20 et 30
Puis, pour accéder à chaque élément de ces trois chiffres nous avons des indices soit l’indice 1 pour la valeur 10, l’indice 2 pour la valeur 20 et l’indice 3 pour la valeur 30.
Jusque-là, si nous appliquons cette logique à notre fonction, celle-ci agira comme ceci :

•	Fonction(1) retournera 10
•	Fonction(2) retournera 20
•	Fonction(3) retournera 30

Dans ce cas-là, nous devrions appliquer la formule Fonction(1) + Fonction(2) + Fonction(3) qui retournera sans doute 60. 
Mais comme nous sommes paresseux notre objectif est de n’utiliser qu’une seule fonction qui appellera les autres et appliquera la formule. Donc nous devons faire en sorte que Fonction s’appelle par elle-même ce qui se ferait si Fonction(1) prenait les valeurs de Fonctions(2) et fonction(3) comme ceci :

1.	Fonction(1) appelle Fonction(2) qui appelle Fonction(3)
2.	Fonction(3) retourne 30 car l’indice 3 est le dernier
3.	Fonction(2) prend en compte la valeur retournée par Fonction(3) et l’ajoute à sa valeur donc 20+30
4.	Fonction(1) prend la somme retournée par Fonction(2) et l’ajoute à sa valeur donc 10+50
5.	Et nous revoilà avec une somme de 60

Prenons ces étapes et appliquons-les dans un algorithme :



```
Procédure Fonction(n):

	Si n est égal à 3 alors :

		Retourner la valeur de l’indice n 

	Sinon :

		Retourner valeur de l’indice n + Fonction(n+1)
```



Donc si nous commençons avec Fonction(1), comme 1 n’est pas égal à 3 alors nous allons ajouter la valeur de l’indice 1(10) à la valeur retournée par Fonction(2) soit Fonction(n+1) et comme n est egale à 1 à ce stade,je vous laisse deviner la suite. Mais nous n’avons toujours pas la valeur de Fonction(2) qui doit à son tour être appelée pour retourner une valeur.

La Fonction(1) reste en stand-by en attendant la valeur de Fonction(2).

La Fonction(2) est donc appelée (à l’intérieur de la Fonction 1) et fait la même chose que Fonction(1):comme n est diffèrent de 3, celle-ci retourne la valeur de l’indice 2(20) plus la valeur que devra retourner Fonction(3).

Fonction(2) est maintenant en stand-by en attendant la valeur de Fonction(3).

Enfin, Fonction(3) retournera sa valeur(30) car n est égale à 3.

C’est fini ? Non restez encore, nous avons toujours des fonctions en stand-by. C’est-à-dire les fonctions qui ne sont toujours pas terminées et qui attendent le retour d’une fonction soit Fonction(1) et Fonction(2).

La dernière Fonction en stand-by est Fonction(2), celle-ci attendait la Fonction(3) pour l’ajouter à sa valeur donc Fonction(2) retournera 50.Encore une fois, nous avons une autre fonction en stand-by qui attendait la Fonction(2), nous parlons bien évidemment de Fonction(1) qui retournera 10+50 qui est finalement égale à 60.

Comme Fonction(1) est la première que l’on a appelé et qu’il n’y a plus de fonction en attente (ou stand-by) ,60 est la dernière valeur retournée.

Je vous invite à simuler la Procédure/l'algorithme Fonction(1) comme si vous étiez vous-même la machine qui la faisait marcher. Pour une meilleure compréhension simulez donc Fonction(2), puis Fonction(1).

## Conclusion :

Dans notre cas, la récursivité a été utilisée pour calculer une somme qui peut être calculée plus simplement avec 10+20+30 et même si celles-ci étaient les valeurs dans un tableau une boucle aurait suffit. Tout cela pour préciser que cet article était une explication de la recursivité. Dans d’autres cas la récursivité est un outil indispensable pour tout codeur,que ce soit pour la suite de fibonnaci ou pour afficher des permutations.
