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
