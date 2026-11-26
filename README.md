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
| Espace / E / Clic souris | Attaquer (le clic vise la souris) |
| Maj | Dash (si débloqué) |
| Tab | (réservé) |
| 1 / 2 / 3 ou clic | Choisir une amélioration |
| Entrée | Démarrer / recommencer |

## Systèmes

- **Statistiques** : santé (PV), armure (réduction physique), armure magique
  (réduction magique), agilité (vitesse de déplacement et d'attaque), pouvoir
  (dégâts magiques), force (dégâts physiques).
- **Étages alternés** : donjons (génération procédurale de salles + couloirs,
  ambiance sombre) et villages (maisons, arbres, palissades).
- **Ennemis** : aventurier (mêlée rapide), guerrier (lent, blindé), mage
  (projectiles magiques à distance), plus des **élites** (couronnées, bien plus
  dures) qui lâchent une arme du palier supérieur.
- **Armes** : 20 armes en 4 paliers (mêlée et distance, physiques ou magiques).
  Une arme de départ aléatoire, de meilleures via l'amélioration « Coffre
  d'armurier » ou en tuant une élite (équipée seulement si elle est meilleure).
- **Améliorations (54)** : statistiques, compétences (dash, esprits compagnons,
  projectiles arcaniques, boule de feu, auras de gel/poison, bouclier runique,
  vol de vie, critiques…) et équipement.
- **Objectif** : tuer tous les ennemis d'un étage pour ouvrir l'escalier, et
  descendre le plus loin possible.

## Technique

- Canvas 480×270 mis à l'échelle en `image-rendering: pixelated`.
- Sprites et tuiles dessinés en pixel art procédural (aucun asset externe).
- Effets sonores générés via WebAudio.
