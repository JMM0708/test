# Observatoire de l'habitat — note de synthèse territoriale

Version narrative et interactive de la page « Programmation de logements » de
l'Observatoire de l'habitat de l'AGORAH (La Réunion, 2020-2025).

`story.html` est la source de la vue publiée. La page est autonome : un seul
fichier, aucune dépendance hors la police Inter (Google Fonts) et les flux WFS
PEIGEO interrogés à la demande.

## Structure

| # | Section | Objet |
|---|---------|-------|
| 01 | Cadre méthodologique | sources, pondérations, conventions de lecture |
| 02 | **Explorateur territorial** | carte cliquable EPCI → commune → quartier PLH → opération |
| 03 | Volume et rythme | production annuelle par catégorie, réhabilitation |
| 04 | Atteinte des objectifs PLH | département et cinq EPCI, par catégorie |
| 05 | Différenciation communale | atteinte globale / atteinte du locatif social |
| 06 | Rattrapage SRU | contrat de mixité sociale de la CIVIS |
| 07 | Foncier mobilisable | emplacements réservés, réserves foncières EPF |
| 08 | Densification et renouvellement | production en QPV, foncier EPF en zones U / AU |
| 09 | Gisements et zonages | dents creuses, mutabilité BIMBY, friches, vacance, enveloppe urbaine, zones ouvertes — flux PEIGEO |
| 10 | Marchés immobiliers | prix médians PERVAL, seuil de diffusion à 11 transactions |
| 11 | Programmation à venir | programmation pluriannuelle CINOR |
| 12 | Qualité de la donnée | précision de localisation, limites d'interprétation |
| 13 | Synthèse | chiffres-clés et rôle de l'observatoire |

## Explorateur

Quatre niveaux emboîtés, sélection au clic sur la carte, fil d'Ariane pour
remonter. Quatre indicateurs cartographiables (logements produits, atteinte PLH,
atteinte du locatif social, part du logement social), trois couches activables
(opérations aidées, emplacements réservés, quartiers prioritaires). Le panneau
restitue pour le périmètre courant : composition de la production, réalisé /
objectif par catégorie, foncier mobilisable, production en QPV, programmation à
venir et liste des opérations ; la fiche d'opération donne opérateur, produit,
millésime, quartier, adresse, parcelle et précision de localisation.

## Données

Les chiffres sont recalculés à partir du fichier source du tableau de bord
(736 opérations, 15 307 permis privés, 24 communes, 124 quartiers PLH, 179
emplacements réservés, 1 194 acquisitions EPF, 57 QPV), selon la méthodologie du
tableau de bord : logements aidés neufs hors réhabilitation, marché libre estimé
par les permis pondérés selon l'état d'avancement, PTZ rattachés à l'accession
sociale, atteinte PLH rapportée aux objectifs par catégorie. L'appartenance aux
quartiers prioritaires et le zonage du foncier EPF sont calculés par intersection
géométrique.

Sources : Opefin 2020-2025 (DEAL) · Sit@del2 géolocalisé 2020-2025 (SDES) ·
PTZ 2020-2024 · PLH des cinq EPCI · contrat de mixité sociale CIVIS 2023-2025 ·
inventaire SRU 2022 · PLU en vigueur et emplacements réservés · densités SCOT ·
EPF Réunion · programmation pluriannuelle CINOR au 26/11/2025 · QPV 2024 ·
quartiers PLH 2022 — traitements AGORAH.

## Flux PEIGEO

Les couches dents creuses 2025, mutabilité BIMBY 2025, friches urbaines 974,
logements vacants ZLV 2026, enveloppe urbaine 2025, POS/PLU et PERVAL 2022-2025
ne sont pas embarquées : elles sont interrogées en WFS sur
`geoserver.peigeo.re`, puis intersectées avec le périmètre courant de
l'explorateur. L'interrogation suppose que la page soit servie depuis un
environnement autorisé à joindre le géoserveur ; à défaut, chaque carte affiche
un état d'indisponibilité explicite.

## Tableau de bord « Logements » (RP 2017)

`logements.html` est un tableau de bord autonome construit sur le fichier détail
INSEE « Logements ordinaires » du recensement 2017 pour La Réunion
(`log_974_2017.csv`, 159 811 logements enquêtés, 369 895 logements pondérés).
Il reprend la trame des tableaux de bord de l'observatoire de l'habitat
publiés sur PEIGEO (série « 4 — Logements »).

Sélecteur de territoire (La Réunion, 5 EPCI, 24 communes, mémorisé dans
l'ancre de l'URL), six chiffres-clés, puis sept sections :

| # | Section | Indicateurs |
|---|---------|-------------|
| 01 | Le parc de logements | catégories (RP / RS / vacants), types, aspect du bâti, époque de construction, logements achevés par année 2006-2019 |
| 02 | Occupation du parc | statut d'occupation (propriétaires, parc privé, HLM, logés gratuitement), ancienneté d'emménagement, résidence un an auparavant |
| 03 | Taille, confort et équipement | nombre de pièces, surface, motorisation, eau chaude, chauffe-eau solaire, climatisation, sanitaires, assainissement, stationnement, ascenseur, densité d'occupation |
| 04 | Les ménages | taille, âge, activité, lieu de naissance et diplôme de la personne de référence |
| 05 | Comparaison territoriale | 32 indicateurs au choix, lus pour les 5 EPCI et classés pour les 24 communes |
| 06 | Tableau communal | tableau triable, copie presse-papiers |
| 07 | Méthode et sources | champ, pondération IPONDL, définitions |

Tous les effectifs sont des sommes de poids `IPONDL`. Les valeurs de chaque
territoire sont comparées à La Réunion (repère vertical sur les graphiques).

## Explorateur « Logements » (carte et filtres croisés)

`explorateur.html` est la version décisionnelle du même jeu de données, sur le
modèle des tableaux de bord Prompto (Datarocks) publiés sur PEIGEO : barre
d'application et pages en onglets (Synthèse, Parc de logements, Occupation,
Ménages, Confort, Données), barre de filtres en listes déroulantes, grille de
widgets en cartes Material avec icônes de définition, d'export CSV et de plein
écran, source sous chaque widget, carte synchronisée avec les filtres.

- **Carte** à trois mailles (24 communes, 5 EPCI, 344 IRIS), 27 indicateurs
  cartographiables en quintiles, zoom et déplacement, clic pour filtrer sur le
  territoire. Contours IRIS IGN (Géoplateforme) projetés dans le repère du fond
  de carte de `story.html` ; 330 des 331 codes IRIS du fichier sont appariés, La
  Plaine-des-Palmistes n'étant pas irisée.
- **Vues-filtres** : anneaux (catégorie, type, statut d'occupation, avec
  couronne externe de contexte), colonnes (époque, pièces, taille des ménages,
  âge, colonne claire de contexte), barres empilées à 100 % par EPCI (type,
  époque, statut, pièces), matrice pièces × personnes à filtre combiné, jauges
  radiales de confort et de profil, classement des communes en sucettes avec
  repère réunionnais. Un clic sur un segment, une colonne, une case ou une
  commune filtre toutes les vues ; les filtres actifs s'affichent en puces
  retirables.
- **Cartes d'indicateurs** avec écart à La Réunion ; un clic cartographie
  l'indicateur.
- **Pages** Parc, Ménages, Confort, Données (tableau communal triable et copiable,
  méthode).

Les données sont embarquées sous forme de deux cubes agrégés : commune × 7
dimensions (32 282 cellules) et IRIS × 5 dimensions (26 749 cellules), avec les
mesures de confort et de profil des ménages. Les poids IPONDL sont conservés à
la décimale près par arrondi cumulatif, de sorte que les totaux sont exacts.
