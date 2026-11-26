# Gobelin Rogue

Petit rogue-like pixel art en un seul fichier HTML (`index.html`), sans dépendance.
Ouvrez simplement `index.html` dans un navigateur.

## Concept

Vous êtes un gobelin. Des aventuriers, guerriers et magiciens ont envahi vos
donjons et vos villages : éliminez-les tous, gagnez des niveaux, et choisissez
à chaque niveau une amélioration parmi 3 tirées au hasard d'un pool de plus
de 230 améliorations réparties en 55 familles et 5 rangs (jusqu'à Légendaire).

## Contrôles

| Touche | Action |
|---|---|
| ZQSD / WASD / Flèches | Se déplacer |
| Espace / E | Attaquer au corps-à-corps (une pression = une attaque) |
| Clic souris / visée | Arme à distance : tire vers la souris |
| Maj | Dash (si débloqué) |
| Tab | Panneau de caractéristiques et améliorations (met le jeu en pause) |
| 1 / 2 / 3 ou clic | Sélectionner une amélioration, puis Entrée ou bouton « Valider » |
| Survol d'une carte | Affiche le descriptif de l'amélioration |
| M | Musique on/off |
| Entrée | Démarrer / recommencer |
| Marcher sur un coffre | Ouvrir le coffre (équipement ou arme à comparer) |
| 1 / 2 / Échap (offre d'arme) | Sélectionner garder l'actuelle / prendre la trouvée, puis Entrée ou bouton « Valider » |

## Systèmes

- **Statistiques** : santé (PV), armure (réduction physique), armure magique
  (réduction magique), agilité (vitesse de déplacement et d'attaque), pouvoir
  (dégâts magiques), force (dégâts physiques). Régénération de base de 1 PV/s,
  accélérable via plusieurs améliorations.
- **Coffres** : 1 à 2 coffres par étage ; marchez dessus pour ouvrir. Ils
  contiennent une arme dans ~75 % des cas, et un écran de comparaison s'affiche
  alors (dégâts de base et effectifs, cadence, DPS avec les caractéristiques de
  scaling, rang, effets spéciaux) : sélectionnez votre choix (1 ou 2, ou clic
  sur une carte) puis validez avec le bouton ou Entrée. Sinon : bonus de
  statistique ou soin complet. Le rang des armes trouvées
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
- **Ennemis** : assassin (très rapide, frappe lourdement au corps-à-corps
  mais tombe en quelques coups), guerrier (lent, robuste), mage (baguette
  magique, projectiles à distance), archer (flèches à distance), bébé
  (inoffensif, uniquement dans les villages), paysan (faible, villages et
  tavernes, fourche en main), prêtre (rare, présent partout : soigne les
  autres ennemis à courte portée mais jamais lui-même, illumine ses
  cobayes d'une lueur verte pendant toute la durée du soin ; seul le
  prêtre élite attaque, avec de lents projectiles), chevalier (à cheval, rapide,
  attaque par charge de lance en ligne droite, tourne difficilement),
  **chien** (attaque en meutes, très rapide, morsure qui fait saigner sur la
  durée), **barde** (taverne et villages : projectile magique lent et large
  qui immobilise une demi-seconde à l'impact — une seconde pour le barde
  élite — avec 4 s de recharge) et **garde** (châteaux et villages : frappe
  à la hallebarde en ligne droite sur 30 px devant lui), plus des
  **élites** (couronnées, bien plus
  dures, reconnaissables à leur teinte rougeâtre) qui lâchent une arme à
  comparer : il y en a 1 par étage, et 2 à partir de l'étage 5. Leur puissance
  (PV, dégâts, niveau, XP) croît nettement plus vite que celle des ennemis
  normaux dans les étages élevés, et elles apparaissent toujours loin du
  joueur. Dans les villages peut apparaître (très rarement) un **bébé doré** :
  inoffensif et couronné, il octroie une bénédiction unique (PV, Force,
  Pouvoir, Agilité, armures) quand on arrive à l'attraper. Chaque ennemi
  affiche son niveau au-dessus de lui, et les ennemis ne se chevauchent pas ;
  les armes à distance infligent nettement moins de recul que la mêlée, les
  dégâts infligés s'affichent en blanc et passent en rouge sur un coup
  critique
  entre eux.
- **Armes** : 36 armes en 5 rangs — Basique, Amélioré, Puissant, Épique,
  Légendaire — reprenant les rangs des améliorations (mêlée et distance,
  physiques ou magiques). Les légendaires : Croc du Roi gobelin (mêlée
  physique), Lame du Jugement (mêlée magique enflammée), Arc du Vide
  (perforant, tir double), Sceptre du Réveille-Morts (distance magique) et
  Masse du Séisme (frappe tous les ennemis autour de vous dans une très
  large zone à 360°). Elles apparaissent à partir de l'étage 12 (élites) ou
  13 (coffres). Les armes de mêlée magiques (Lame d'écaille, Glaive de braise,
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
  une animation couvrant exactement la zone touchée (dorée ou violette pour
  le magique) ; distance : tir vers la souris. Chaque famille de mêlée a sa
  zone d'effet : dagues et griffes un petit arc rapide (~69-80°), épées un
  arc large (~126°), espadon ~149°, gourdin ~132°, haches un très grand arc
  (~183°), faucheuses et faux un arc quasi complet (~206°), tandis que la
  lance (~46°) et le trident (~57°) frappent en **poussée linéaire** animée,
  longue et étroite. Les dégâts des armes de mêlée sont légèrement
  augmentés pour compenser la perte de couverture. L'arme actuellement équipée ne peut
  jamais retomber. Les rangs d'armes utilisent le même code couleur que les
  améliorations (gris, bleu, violet, or), visible sur les cartes de comparaison
  et dans le HUD.
- **Améliorations à rangs** : 55 familles (statistiques, compétences et
  équipement), chacune déclinée en 5 rangs — Basique, Amélioré, Puissant,
  Épique, Légendaire — des versions de plus en plus fortes. Un rang
  n'apparaît qu'après avoir obtenu le rang immédiatement inférieur, et les
  rangs supérieurs ont un taux d'apparition plus faible (poids 100 % / 70 % /
  50 % / 35 % / 25 %). Les 14 améliorations **Légendaires** (dorées)
  fusionnent deux améliorations Épiques en une seule version bien plus
  puissante, et n'apparaissent qu'une fois au moins deux améliorations
  Épiques obtenues. Chaque rang ne peut être pris qu'une fois.
- **Auras visuelles** : l'aura de gel (anneau bleu avec flocons orbitants)
  et l'aura de poison (anneau vert à rayon croissant avec la puissance)
  s'affichent en continu autour du gobelin, avec un rayon correspondant
  exactement à la portée réelle de l'effet.
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
