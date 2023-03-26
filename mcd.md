# Retour MCD #

## Correction ##

Ton MCD est presque parfait, il y a juste un soucis de relation entre ta table User et ta table Product.
Sur ton MCD, un utilisateur peut liker 1 et 1 seul produit, et chaque produit peut être liké par 1 et 1 seul utilisateur, ce qui n'est pas cohérent avec le système à mettre en place.
Pour qu'un utilisateur puisse liker aucun ou plusieurs produits, et qu'un produit puisse être liké par aucun ou plusieurs utilisateurs, il est nécessaire de mettre en place une relation de type N,N (plusieurs à plusieurs) en utilisant une table de jonctions.

Tu dois donc créer une troisième table, par exemple "Likes", qui contient les clés étrangères de la table User et de la table Product pour chaque like. La cardinalité entre les tables User et Likes est alors de 0,N (un utilisateur peut avoir zéro, un ou plusieurs likes), tout comme la cardinalité entre les tables Product et Likes (un produit peut avoir zéro, un ou plusieurs likes).

## Outils ##

Si tu souhaites, tu peux travailler tes MCD à l'aide de Merise, Lucidchart ou looping, qui sont les standards du domaine.

Merise est une méthode de conception de bases de données relationnelles qui s'appuie sur des standards et des normes reconnus. Elle propose une approche structurée pour la modélisation des données et la gestion de projets informatiques.

Lucidchart est une plateforme de création de diagrammes en ligne qui permet de réaliser des MCD de manière intuitive et collaborative. Avec ses outils de dessin conviviaux et ses fonctionnalités de partage en temps réel, Lucidchart est idéal pour les équipes travaillant à distance.

Looping est un outil open source de modélisation de bases de données relationnelles. Il propose une interface graphique simple et intuitive pour dessiner des schémas de bases de données et générer automatiquement du code SQL. Looping est idéal pour les développeurs qui souhaitent concevoir rapidement des bases de données tout en respectant les normes et les bonnes pratiques.