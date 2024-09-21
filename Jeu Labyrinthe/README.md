
# LE LABYRINTHE

Un jeu en deux manches, où deux joueurs s'affrontent. 

La première manche consiste à attraper 10 items le plus rapidement possible. Le premier à 10 se voit donner le choix d'être le chasseur ou la proie dans la manche suivant. 

Dans la manche 2, le but du chasseur est de capturer la proie : durant environ 10 secondes il n'y a pas d'issue pour la proie, mais passé ce laps de temps, des trous se forment dans les murs extérieurs. La proie peut donc enfin s'échapper.
Un jeu stressant et amusant.

Déplacez vous de haut en bas et de gauche à droite avec les touches e,s,d,f ou les flèches directionnelles.

## Auteur

- Romain Miguet n°12308514


## Fonctionnement du code

#### Le menu titre
Plusieurs calculs entrent en compte :
Il y a une interpolation de deux formes en arrière plan. Puis un "easterEgg" est caché dans le jeu, vous trouverez la façon pour faire tomber les lettres et réveler un beau message. 

Pour faire tomber les lettres :
- Chaque lettre est en fait une particule à qui lui est attribuée une masse nulle, une force nulle, une vitesse nulle, ainsi qu'une position dans l'espace.
- Au déclanchement du "easterEgg", une masse lui est donnée ainsi qu'une force qui dépend de d'une constante de gravité et une vitesse en x aléatoire et rectiligne en y.
- Il y a un système de collision qui, à chaque fois qu'une lettre touche le sol, le vecteur vitesse change de direction et est ralenti par une constante de friction.

#### L'algorithme du labyrinthe
Le programme utilise un algorithme précis pour générer un labyrinthe de façon aléatoire :
- Le labyrinthe est un tableau de nombres
- A l'initialisation, il est constitué de 0 (vide) et de -1 (mur)
- On place une entrée et une sortie aux deux bords, c'est à dire qu'on donne le même chiffre à deux cellules adjacentes pour créer soit une entrée, soit une sortie.
- On place ensuite des chiffres différents dans chaque cellule vide.
- Puis des cellules sont tirées aléatoirement : si leurs deux cellules voisines ne possèdent pas le même nombre, on les fusionne et on donne un même chiffres à toutes les cellules qui constituent le chemin.
- Une fois terminée, la génération s'arrête puis on casse quelques murs afin de rendre le labyrinthe plus complèxe. En effet, celui ci ne possédait qu'un seul chemin pour entrer et sortir.

#### Manche 1
- Deux joueur s'affrontent dans une boucle while, une fois le score arrivé à 10, la boucle s'arrête.
- Leurs positions sont initialement aux entrées et aux sorties du labyrinthe.

#### Choix stratégique 
- Le joueur gagnant de la première manche choisit entre être attaquant ou proie.
- Un système d'interpolation de la taille de l'image est activé au survol de la du curseur de la souris.

#### Manche 2
- Le chasseur doit rattraper la proie dans deux boucles while : une où le labyrinthe est fermé, durant 10 secondes, l'autre où ce dernier possède plusieurs sorties.

#### Fin du jeu
- La proie sort du labyrinthe ou le chasseur attrape la proie
- Arrivée sur une page "Vous avez gagné" qui reste 5 secondes à l'écran
- Un écran de fin qui demande si vous souhaitez rejouer, ce qui relance la boucle entière, ou si vous voulez quitter, ce qui fait sortir de la boucle principale.

Le jeu est codé avec plusieurs boucles while qui permettent de passer d'une interface à une autre.

Les système de temps sont codés avec la fonction elapsedTime().

Les changements de couleur au survol se vont en fonction de la position de la souris.
## Mises à jour
### Semaine du 18 mars
Début du labyrinthe : 
- Développement du tableau de cellules, positions, dessin des cases en fonction de la taille de la fenêtre.
- Découverte d'un algorithme de génération automatique de labyrinthe. Cependant pas d'explications profondes, nécessité de réfléchir longuement.
- Premiers essais non concluants : l'algorithme de génération ne s'arrêtait pas au moment voulu. 
### Semaine du 25 mars
Améliorations :
- Le labyrinthe se génère automatiquement, une entrée, une sortie.
- Ajout d'une fonction qui supprime quelques murs afin de rendre le labyrinthe complexe.
### Semaine du 1 avril
Nouveautés
- Ajout des joueurs et des items.
- Ajout des fonctions qui gèrent les "collisions".
### Semaine du 8 avril
Améliorations :
- Travail sur l'ergonomie du programme, ajout de commentaires, de lignes de debug.
- Prototypage des fonctions pour plus de lisibilité et de facilité à naviguer dans le programme.
### Semaine du 15 avril 
Beaucoup de nouveautés et d'améliorations :
- Ajout d'une page de titre.
- Ajout d'une page "choix".
- Ajout d'une page "vainqueur".
- Ajout d'une page "quitter ou rejouer".
- Ajout du système de manches dans la partie.
- Ajout du programme de "chasseur/proie"

## Documentation

[Vidéo YouTube | CRÉER ET RÉSOUDRE UN LABYRINTHE AUTOMATIQUEMENT - Dimension code](https://www.youtube.com/watch?v=K7vaT8bZRuk)

