# Comparaison OSM vs IGN (BD TOPO) — Notebook Python

Notebook de comparaison entre des données **OpenStreetMap (API Overpass)** et **IGN BD TOPO (WFS)**, basé sur la **géométrie** (points / lignes / polygones) + une analyse **attributaire** et **spatiale**.  
**Auteurs** : Amélie Joret, Saïd Khatir, Antoine Le Doeuff, Antoine Soumet (Master SIGAT Rennes 2, 2023–2024)

---

## Objectif
Comparer OSM et BD TOPO sur une commune (code INSEE) via des indicateurs simples :
- **quantité d’entités**
- **qualité attributaire** (taux de remplissage)
- **indicateurs spatiaux** (répartition, longueurs/surfaces, agrégation par sections cadastrales, recouvrement)

---

## Données & sources
- **OSM** : requêtes Overpass (`overpass`), par thème.
- **IGN BD TOPO** : flux **WFS** (`https://data.geopf.fr/wfs/ows?`) + filtres CQL.
- **Cadastre Etalab** : communes/sections/parcelles via `https://cadastre.data.gouv.fr/bundler/cadastre-etalab`.

Thèmes disponibles (`THEMES`) :
- `view_point` (points)
- `bar_resto` (points)
- `hedge` (lignes)
- `parkings` (polygones)

---

## Installation
```bash
pip install geojson overpass mapclassify contextily matplotlib_scalebar
