# Souper d'accueil du CIA — les trois jeux 🎮

Application maîtresse du **Souper d'accueil du CIA** (Club d'Intelligence Artificielle, Université Laval) — **ven. 11 sept. 2026, 17 h → 21 h, Grande Salle du Pub U**. Un seul lien, un seul code QR : l'écran d'accueil présente les **trois jeux maison** de la soirée, et on **touche un jeu** pour y jouer.

**Page en ligne : https://ulyssegagne.github.io/cia-souper-accueil/**

---

## 🗓️ Plan de la soirée

**Un seul QR pour la soirée** → l'app maîtresse. Le monde scanne une fois (à la diapo « Trois jeux… ») et touche un jeu pour jouer. Aucune inscription, aucune donnée, ça roule sur chaque téléphone.

Chaque jeu présente une facette du Club :

- **The Bluff Game** → les **projets**. À chaque table : un joueur ignore la réponse, un la connaît, les autres bluffent. L'ignorant doit démasquer les menteurs. Chaque manche tourne autour d'un vrai projet du CIA, révélé à la fin.
- **Coupable!** → les **leaders**. Un *fun fact* d'un leader s'affiche, la salle vote pour qui l'a écrit (couleur sur le téléphone), on révèle le coupable. Mauvaise réponse = tu t'assois; dernier debout gagne.
- **Hot Takes** → **brise-glace**. Questions/opinions rapides sur le téléphone (ton choix s'affiche en gros = un prétexte pour jaser), avec rotations entre les tables. À la fin, chacun copie son profil dans un fil Discord.

### Déroulement

- **16h00** — Montage : test AV (projecteur + micro + son + l'app sur l'ordi du projecteur), tape A/B/C/D sur chaque siège, nametags, assignation des rôles admin.
- **16h40** — Photo de l'équipe admin.
- **16h55** — Accueil (nametags, placement, on va vers les personnes seules).
- **17h15** — Diapo **« Présentation du club »** : Cyrille — bienvenue, remerciements, mission, **consentement photo**.
- **17h30** — Ulysse embarque, diapo **« Trois jeux… »** (le QR!) : déroulement de la soirée, puis explique **Bluff** → on joue.
- **18h15** — Fin de Bluff, **poutine servie**.
- **18h30** — Diapo **« Rencontres »** : Cyrille — partenaires, responsable (Isabeau Prémont-Schwarz), équipe. Ulysse explique **Coupable!** → on joue.
- **19h00** — Fin de Coupable!, Ulysse explique **Hot Takes** → on joue (rotations entre les tables).
- **20h00** — Diapo **« Poutine gratuite »** : prochaines activités + formulaire **AWS** (QR à l'écran).
- **20h15** — Fin du temps structuré. · **21h15** — départ. · **21h30** — salle vide et propre.

### Rôles à combler (arrivée 16h30, chandail du Club)

- Animation : Ulysse + Cyrille
- Son/AV **+ laptop de secours avec prise HDMI**
- Présences (2 personnes)
- **Poutine** : surveiller le stock, compter et **avertir la cuisine d'avance** (~5 pers./poutine)
- **Repas halal / végé**
- Prix pour le gagnant de Coupable!
- Remercier les partenaires + gérer leur consommation offerte (équipe partenariats)
- Tous les admins : s'asseoir **éparpillés** parmi les membres, jaser, aider les tables

### À confirmer avant vendredi

- Tables de **4 à 7 personnes** (requis pour Bluff)
- Fil Discord prêt pour les profils Hot Takes
- **Musique** de la soirée à déterminer
- Nombre final de participants + nb de poutines donné à la cuisine

---

## 🎮 Les trois jeux

| Jeu | Présente | Identité |
|---|---|---|
| [Hot Takes](hot-takes/) | les **membres** | feu / orange |
| [Coupable!](coupable/) | les **leaders** | noir + rouge |
| [The Bluff Game](bluff/) | les **projets** | bleu roi |

Une **flèche de retour au menu** est présente dans chaque jeu (en haut à **gauche** sur l'accueil du jeu; en haut à **droite** à la **fin** de la partie — Coupable! n'a pas d'écran de fin, donc seulement la flèche d'accueil). **The Bluff Game** accepte des tables de **4 à 7 joueurs**.

## 🖥️ Mode présentation (projecteur)

Ajout local à cette app maîtresse (absent des dépôts individuels). Sur l'ordi du projecteur : ouvrir l'app, **triple-cliquer sur le pied de page** de l'accueil, taper le mot de passe **`cia`**. Les quatre phrases de l'accueil (« Présentation du club », « Trois jeux… », « Rencontres », « Poutine gratuite ») deviennent des **décks de diapos** projetables (logo + mission, QR de l'app, partenaires / responsable / équipe, prochaine activité + QR AWS). En prime :

- **Coupable!** devient une série de diapos (fun fact → la couleur du coupable remplit l'écran), dans l'ordre de la clé animateur.
- **The Bluff Game** ajoute l'exemple des règles (2 tours joués, révélation **blanc = bonne réponse / noir = fausse**).

Le drapeau est **local à l'appareil** (`localStorage`, clé `cia-present`) : les téléphones des membres ne voient jamais le mode présentation. Triple-clic à nouveau sur le pied de page pour en sortir.

## 🧩 Architecture

Dépôt **autonome**, pages statiques (HTML/CSS/JS), zéro dépendance sauf les polices Google (Bricolage Grotesque, IBM Plex Mono). L'accueil (`index.html`) est *inspiré de* l'affiche « Trois jeux, une poutine » et porte le mode présentation + les décks; les images vivent dans `assets/`, le QR de l'app dans `qr.svg`, le QR des formations AWS dans `assets/qr-aws.svg`. Les jeux vivent dans leurs sous-dossiers (`hot-takes/`, `coupable/`, `bluff/`) — des **copies** des dépôts individuels ([`cia-hot-takes`](https://github.com/ulysseGagne/cia-hot-takes) · [`cia-coupable`](https://github.com/ulysseGagne/cia-coupable) · [`cia-bluff`](https://github.com/ulysseGagne/cia-bluff)), avec en plus la flèche de retour et les ajouts du mode présentation.

Les liens sont **relatifs** (`./hot-takes/`, `../`) : rien n'est codé en dur, tout fonctionne sous le sous-chemin `/cia-souper-accueil/` de GitHub Pages. Hébergé depuis `main`.
