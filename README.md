# Souper d'accueil du CIA — les trois jeux 🎮

L'application maîtresse du **Souper d'accueil du CIA** (Club d'Intelligence Artificielle, Université Laval) — **ven. 11 sept., 17 h → 21 h au Pub U**. Un seul lien, un seul code QR : l'écran d'accueil présente les **trois jeux maison** de la soirée, et on **touche un jeu** pour y jouer.

**Page en ligne : https://ulyssegagne.github.io/cia-souper-accueil/**

## Les trois jeux

| Jeu | Présente | Identité |
|---|---|---|
| [Hot Takes](hot-takes/) | les **membres** | feu / orange |
| [Coupable!](coupable/) | les **leaders** | noir + rouge |
| [The Bluff Game](bluff/) | les **projets** | bleu roi |

Une **flèche de retour au menu** est ajoutée dans chaque jeu : en haut à **gauche** sur l'accueil du jeu, et en haut à **droite** à la **fin** de la partie (Coupable! n'a pas d'écran de fin — sa fin se joue dans la salle — donc seulement la flèche d'accueil).

## Architecture

Dépôt **autonome**. L'accueil (`index.html`) est *inspiré de* l'affiche « Trois jeux, une poutine » : les trois écrans-téléphones (feu · noir · bleu roi), chacun cliquable. Les jeux vivent dans leurs sous-dossiers (`hot-takes/`, `coupable/`, `bluff/`) — ce sont des **copies** des dépôts individuels ([`cia-hot-takes`](https://github.com/ulysseGagne/cia-hot-takes) · [`cia-coupable`](https://github.com/ulysseGagne/cia-coupable) · [`cia-bluff`](https://github.com/ulysseGagne/cia-bluff)), avec en plus la flèche de retour.

Les liens sont **relatifs** (`./hot-takes/`, `../`) : rien n'est codé en dur, tout fonctionne quel que soit le nom du dépôt. Chaque page est statique, un seul fichier, zéro dépendance sauf les polices Google (Bricolage Grotesque, IBM Plex Mono). Hébergé sur GitHub Pages depuis `main`.
