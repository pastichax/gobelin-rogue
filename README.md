# Gobelin Rogue

Petit rogue-like pixel art en un seul fichier HTML (`index.html`), sans dépendance.
Ouvrez simplement `index.html` dans un navigateur.

## Concept

Vous êtes un gobelin. Des aventuriers, guerriers et magiciens ont envahi vos
donjons et vos villages : éliminez-les tous, gagnez des niveaux, et choisissez
à chaque niveau une amélioration parmi 3 tirées au hasard d'un pool de 54.

## Contrôles

| Touche | Action |
|---|---|
| ZQSD / WASD / Flèches | Se déplacer |
| Espace / E | Attaquer au corps-à-corps (orienté selon le personnage) |
| Clic souris / visée | Arme à distance : tire vers la souris |
| Maj | Dash (si débloqué) |
| Tab | Panneau de caractéristiques et améliorations |
| 1 / 2 / 3 ou clic | Choisir une amélioration |
| M | Musique on/off |
| Entrée | Démarrer / recommencer |
| Marcher sur un coffre | Ouvrir le coffre (équipement ou arme à comparer) |
| 1 / 2 / Échap (offre d'arme) | Garder l'actuelle / prendre la trouvée / garder |

## Systèmes

- **Statistiques** : santé (PV), armure (réduction physique), armure magique
  (réduction magique), agilité (vitesse de déplacement et d'attaque), pouvoir
  (dégâts magiques), force (dégâts physiques). Régénération de base de 1 PV/s,
  accélérable via plusieurs améliorations.
- **Coffres** : 1 à 2 coffres par étage ; marchez dessus pour ouvrir. Ils
  contiennent une arme dans ~75 % des cas, et un écran de comparaison s'affiche
  alors (dégâts de base et effectifs, cadence, DPS, palier, effets spéciaux) :
  gardez votre arme (1) ou prenez la nouvelle (2). Sinon : bonus de
  statistique ou soin complet.
- **4 types d'étages en cycle** : donjons (génération procédurale de salles +
  couloirs, ambiance sombre), villages (maisons, arbres, palissades),
  bibliothèques de mage (rayonnages de livres, tables de lecture, ambiance
  violette, mages en nombre) et intérieurs de taverne (comptoir, tonneaux,
  tables, ambiance chaleureuse, belliqueux).
- **Ennemis** : aventurier (mêlée rapide), guerrier (lent, blindé), mage
  (projectiles magiques à distance), archer (flèches à distance), plus des
  **élites** (couronnées, bien plus dures) qui lâchent une arme du palier
  supérieur : il y en a autant que le numéro de l'étage (1 à l'étage 1,
  2 à l'étage 2…), et elles apparaissent toujours loin du joueur. Chaque
  ennemi affiche son niveau au-dessus de lui, et les ennemis ne se
  chevauchent pas entre eux.
- **Armes** : 27 armes en 4 paliers (mêlée et distance, physiques ou magiques).
  Les arcs ont des effets variés : perforant (traverse les ennemis), givre
  (ralentit), feu (brûlure), triple tir (Arc de la tempête). Une arme de départ
  aléatoire, de meilleures via l'amélioration « Coffre d'armurier », les coffres
  ou en tuant une élite (équipée seulement si elle est meilleure). Mêlée :
  attaque orientée selon le personnage, avec un arc de frappe animé couvrant
  la zone touchée ; distance : tir vers la souris.
- **Améliorations (55)** : statistiques, compétences (dash, esprits compagnons,
  projectiles arcaniques, boule de feu, auras de gel/poison, bouclier runique,
  vol de vie, critiques, régénération…) et équipement.
- **Objectif** : tuer tous les ennemis d'un étage pour ouvrir l'escalier, et
  descendre le plus loin possible.

## Technique

- Canvas 480×270 mis à l'échelle en `image-rendering: pixelated`.
- Sprites et tuiles dessinés en pixel art procédural (aucun asset externe).
- Effets sonores générés via WebAudio.
