# Gobelin Rogue

Petit rogue-like pixel art en un seul fichier HTML (`index.html`), sans dépendance.
Ouvrez simplement `index.html` dans un navigateur.

## Concept

Vous êtes un gobelin. Des aventuriers, guerriers et magiciens ont envahi vos
donjons et vos villages : éliminez-les tous, gagnez des niveaux, et choisissez
à chaque niveau une amélioration parmi 3 tirées au hasard d'un pool de plus
de 200 améliorations réparties en 55 familles et 4 rangs.

## Contrôles

| Touche | Action |
|---|---|
| ZQSD / WASD / Flèches | Se déplacer |
| Espace / E | Attaquer au corps-à-corps (une pression = une attaque) |
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
  alors (dégâts de base et effectifs, cadence, DPS avec les caractéristiques de
  scaling, rang, effets spéciaux) : gardez votre arme (1) ou prenez la nouvelle
  (2). Sinon : bonus de statistique ou soin complet. Le rang des armes trouvées
  progresse lentement avec l'étage (Basique jusqu'à l'étage 3, puis un palier
  tous les 3 étages).
- **8 types d'étages en cycle** : donjon (salles procédurales + couloirs,
  ambiance sombre), forêt (bouquets d'arbres et clairières reliées par un
  sentier), ferme (champs cultivés clôturés, grange, arbres), village
  (maisons, arbres, palissades), bibliothèque de mage (rayonnages de livres,
  tables de lecture, ambiance violette, mages en nombre), intérieur de
  taverne (comptoir, tonneaux, tables, ambiance chaleureuse, belliqueux),
  cour de château-fort (muraille, chemins de pierre, donjon central) et
  intérieur de château-fort (dalles de pierre, piliers).
- **Ennemis** : aventurier (mêlée rapide), guerrier (lent, blindé), mage
  (projectiles magiques à distance), archer (flèches à distance), bébé
  (inoffensif, uniquement dans les villages), paysan (faible, villages et
  tavernes), prêtre (rare, présent partout : soigne les autres ennemis à
  courte portée mais jamais lui-même, et lance aussi de lents projectiles
  magiques peu puissants) et chevalier (à cheval, rapide, attaque par charge
  de lance
  en ligne
  droite, tourne difficilement), plus des **élites** (couronnées, bien plus
  dures, reconnaissables à leur teinte rougeâtre) qui lâchent une arme à
  comparer : il y en a 1 par étage, et 2 à partir de l'étage 5. Leur puissance
  (PV, dégâts, niveau, XP) croît nettement plus vite que celle des ennemis
  normaux dans les étages élevés, et elles apparaissent toujours loin du
  joueur. Dans les villages peut apparaître (très rarement) un **bébé doré** :
  inoffensif et couronné, il octroie une bénédiction unique (PV, Force,
  Pouvoir, Agilité, armures) quand on arrive à l'attraper. Chaque ennemi
  affiche son niveau au-dessus de lui, et les ennemis ne se chevauchent pas
  entre eux.
- **Armes** : 31 armes en 4 rangs — Basique, Amélioré, Puissant, Épique —
  reprenant les rangs des améliorations (mêlée et distance, physiques ou
  magiques). Les armes de mêlée magiques (Lame d'écaille, Glaive de braise,
  Espadon runique, Faucheuse astrale) frappent en ignorant l'armure et scalent
  sur le Pouvoir ; certaines appliquent leurs effets (brûlure, givre) aussi au
  corps-à-corps. Les arcs ont des effets variés : perforant (traverse les
  ennemis), givre (ralentit), feu (brûlure), triple tir (Arc de la tempête).
  Les armes de mêlée ont des dégâts par coup élevés, les armes à distance une
  meilleure sécurité. Une arme de départ aléatoire, de meilleures via
  l'amélioration « Coffre d'armurier », les coffres ou en tuant une élite.
  Toute arme trouvée (coffre, élite, amélioration « Coffre d'armurier ») ouvre
  un écran de comparaison affichant le rang, le DPS et le scaling (Force ou
  Pouvoir pour les dégâts, Agilité pour la cadence) : gardez la vôtre (1) ou
  prenez la nouvelle (2). Mêlée : attaque orientée selon le personnage, avec
  un arc de frappe animé (doré ou violet pour le magique) couvrant la zone
  touchée ; distance : tir vers la souris. L'arme actuellement équipée ne peut
  jamais retomber. Les rangs d'armes utilisent le même code couleur que les
  améliorations (gris, bleu, violet, or), visible sur les cartes de comparaison
  et dans le HUD.
- **Améliorations à rangs** : 55 familles (statistiques, compétences et
  équipement), chacune déclinée en 4 rangs — Basique, Amélioré, Puissant,
  Épique — des versions de plus en plus fortes. Un rang n'apparaît qu'après
  avoir obtenu le rang immédiatement inférieur, et les rangs supérieurs ont
  un taux d'apparition plus faible (poids 100 % / 70 % / 50 % / 35 %).
  Chaque rang ne peut être pris qu'une fois.
- **Objectif** : tuer tous les ennemis d'un étage pour ouvrir l'escalier, et
  descendre le plus loin possible.

## Technique

- Monde rendu en 480×270 puis agrandi sans lissage ; interface (textes,
  jauges, panneaux) dessinée par-dessus à la résolution native de l'écran :
  texte parfaitement net.
- Sprites et tuiles dessinés en pixel art procédural (aucun asset externe).
  Le gobelin a un sprite propre à chaque direction (haut, bas, gauche,
  droite) avec jambes animées en marchant, peau verte et grand nez.
- Effets sonores générés via WebAudio.
