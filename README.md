# Ocean Navigator
<p align="center">
  <img src="jeu.png" width="45%" />
  <img src="jeu3.png" width="45%" />
</p>

*Projet réalisé à trois : Antoine Dupuy, Leonardo Dib, Raphaël Ducournau* 

>**Note :** La version la plus à jour du projet se trouve sur la branche **`movementv1`**.

**Développé dans le cadre du module Hands on 3D Technologies à l'ESIEE Paris, ce projet consistait à créer un environnement maritime interactif complet au sein d'une équipe de 3 personnes.**

## Répartition de l'équipe
Pour ce projet, nous avons divisé les différentes parties :

* **Antoine Dupuy :** Développement de la physique avancée (flottabilité, traînée) et logique de navigation.
* **Raphaël Ducournau :** Création de l'aspect visuel de l'eau, des vagues et des shaders.
* **Leonardo Dib :** Level Design, gestion du brouillard et implémentation des ennemis (requins et krakens) et caméra (third person).

## Détails techniques Leonardo Dib

* **IA et Ennemis : Implémentation des comportements des requins et des krakens.**
* **Système de Vue : Développement d'une caméra à la troisième personne, centrée sur le bateau et contrôlée par l'utilisateur via la souris.**
* **Atmosphère et Éclairage : Conception de l'ambiance visuelle via un système de brouillard volumétrique (fog) pour instaurer une esthétique "Horreur".**
* **Level Design : Intégration d'assets 3D externes et structuration de l'environnement de jeu.**

## Détails techniques Antoine Dupuy
J'ai implémenté :

* **Simulation de Flottabilité (`buoy.gd`) :** Système de points d'ancrage synchronisé avec les vagues.
* **Physique des Fluides (`boat_buoyancy.gd`) :** Modèle de traînée directionnelle (Drag) sur 3 axes.
* **Algèbre Vectorielle :** Stabilisation et calculs de couples pour le comportement du navire.


## Détails techniques : Raphaël Ducournau
J'ai implémenté une simulation d'océan dynamique synchronisant le rendu visuel et la détection de hauteur :

* **Ondes de Gerstner (`water.gdshader`) :** Simulation de vagues réalistes par déplacement de sommets, permettant d'obtenir des crêtes pointues contrairement aux sinusoides classiques.
* **Calcul de Normales Analytiques (`water.gdshader`) :** Utilisation des dérivées partielles pour calculer la normale exacte de la surface et générer des reflets (PBR) cohérents.
* **Algorithme d'Approximation (`water.gd`) :** Implémentation d'une fonction de recherche itérative pour calculer la hauteur précise de l'eau sur le CPU, indispensable pour la flottabilité des objets.
