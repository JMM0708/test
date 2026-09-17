# Observatoire de l'habitat — récit de données

Version *storytelling* de la page « Programmation de logements » de l'Observatoire
de l'habitat de l'AGORAH (La Réunion, 2020-2025).

## Le fichier

`AGORAH_observatoire_habitat_REUNION_storytelling.html` — page autonome (un seul
fichier, aucune dépendance hors la police Inter servie par Google Fonts). Elle
s'ouvre directement dans un navigateur ou se dépose telle quelle sur un serveur.

## Ce que la page contient

Le tableau de bord d'origine est un outil d'exploration : carte Leaflet, filtres,
recherche à la parcelle, fiches d'opération. Cette version en reprend les données
et les organise en un récit linéaire de neuf sections, à la charte AGORAH :

| # | Section | Ce qu'elle établit |
|---|---------|--------------------|
| 01 | Le volume | 41 565 logements produits, un plateau annuel sans décrochage |
| 02 | L'équilibre | 92 % de l'objectif PLH atteint, mais 54 % en locatif social et 148 % en marché libre |
| 03 | La géographie | Une carte, quatre lectures, en défilement (volume, atteinte, locatif social, semis des opérations) |
| 04 | Les communes | L'écart entre atteinte globale et atteinte du locatif social, commune par commune |
| 05 | Le rattrapage | Contrat de mixité sociale de la CIVIS : 4 627 logements manquants |
| 06 | Le foncier | 179 emplacements réservés, 4 819 logements potentiels, 11 mobilisés |
| 07 | Ce qui vient | Programmation pluriannuelle de la CINOR : 4 787 logements |
| 08 | La donnée | Précision de localisation, opérateurs, limites du jeu de données |
| 09 | Synthèse | Chiffres-clés et rôle de l'observatoire |

Cartes et graphiques sont en SVG généré à la volée, avec infobulles au survol,
tableaux de données dépliables, thème clair et sombre, et lecture à largeur
téléphone.

## Données

Tous les chiffres sont recalculés à partir du fichier source du tableau de bord
(bloc `payload` : 736 opérations, 15 633 permis, 24 communes, 124 quartiers PLH),
selon la même méthodologie : logements aidés neufs hors réhabilitation, marché
libre estimé par les permis privés pondérés par état d'avancement, PTZ ajoutés à
l'accession sociale, atteinte PLH rapportée aux objectifs par catégorie.

Sources : Opefin 2020-2025 (DEAL) · Sit@del2 géolocalisé 2020-2025 (SDES) ·
PTZ 2020-2024 · PLH des cinq EPCI · Contrat de mixité sociale CIVIS 2023-2025 ·
PLU en vigueur et emplacements réservés · EPF Réunion · Programmation
pluriannuelle CINOR au 26/11/2025 · Quartiers PLH 2022 · PEIGEO —
traitements AGORAH.

Les indicateurs servis en direct par les flux PEIGEO dans le tableau de bord
(friches, dents creuses, potentiel BIMBY, logements vacants, prix PERVAL) ne
figurent pas ici : ils ne sont pas embarqués dans le fichier source.
