# 🗂️ Fiches Communales — Déploiement Équipements

> **Cdc Normandie Cabourg Pays d'Auge** · Direction de la maîtrise des déchets

Dashboard interactif de suivi du déploiement des équipements de collecte (bacs, points d'apport volontaire, points de regroupement) sur les **39 communes** du territoire NCPA, Calvados.

---

## ✨ Fonctionnalités

### 📋 Vue Fiche commune
La vue principale. Sélectionnez une commune dans le panneau latéral pour accéder à sa fiche complète :
- **Bandeau synthétique** — zone territoriale, priorité, littoral, habilitation DT/DICT, population INSEE et DGF
- **4 indicateurs clés** — résidences secondaires, commerces, hébergements/AirBnB, taux de dotation en bacs
- **Infrastructure actuelle** — adresses conteneurisables, points de regroupement (PDR), colonnes EMB et verre, textiles, cabanes à cartons, compostage, points d'attention (voies non livrables, marches arrière)
- **Déploiement prévu** — nouvelles colonnes PAV à créer (tableau triable), récapitulatif enfouissement, cabanes et textiles à installer
- **Positionnement territorial** — comparaison densité, résidences secondaires, taux de dotation par rapport à la moyenne NCPA
- **Synthèse des actions** et **contacts** (Maire, élu déchets, contact services techniques)

### 📊 Vue Avancement
Vue d'ensemble du déploiement sur l'ensemble du territoire :
- **3 indicateurs globaux** — taux de dotation global, communes P1 (urgentes), communes P2 (importantes)
- **Classement par zone** (Littorale · Périurbaine · Rurale) avec taux moyen par zone et barre de progression par commune
- Clic sur une ligne → bascule directement vers la fiche de la commune

### 🗺️ Vue Carte
Cartographie interactive du territoire NCPA :
- **Deux fonds de carte** — vue plan ou vue satellite
- **Thème de couleur** — limites seules ou dégradé selon le taux de dotation
- **Couche PDR** (marqueurs violets) — tous les points de regroupement existants, avec panneau tableau filtrable (commune, statut, adresse, actions requises)
- **Couche Nouveaux équipements** (marqueurs colorés) — colonnes PAV à créer, distinguées par flux (OMR · Emballages & papiers · Verre)
- **Couche Adresses non conteneurisables** (marqueurs orange) — adresses à desservir via PDR
- Clic sur une commune → panneau d'information rapide + lien vers la fiche

### 📄 Export PDF
- **Fiche individuelle** — export PDF 2 pages de la commune sélectionnée
- **Export complet** — toutes les communes en un seul fichier PDF (2 pages par commune)

---

## 🚀 Utilisation

Le dashboard est un **fichier HTML autonome** — aucune installation, aucun serveur requis.

1. Ouvrez `index.html` dans votre navigateur
2. Glissez-déposez le fichier Excel `BASE_POUR_BILAN_INTERACTIF.xlsx`
3. Le dashboard se charge instantanément

> 💡 Le fichier Excel n'est jamais transmis à un serveur externe. Tout le traitement se fait localement dans le navigateur.

---

## 📁 Structure du fichier Excel

Le dashboard lit **6 onglets** du fichier Excel :

| Onglet | Contenu |
|--------|---------|
| `01_Identité_Démographie` | Population, résidences, commerces, contacts |
| `02_Collecte_Infrastructure` | Adresses, PDR, colonnes PAV, compostage, marches arrière |
| `03_Déploiement_Prévu` | Bacs distribués, taux dotation, actions planifiées |
| `04_PDR` | Points de regroupement avec coordonnées GPS |
| `05_Nouveauxequip` | Nouvelles colonnes AV à créer avec coordonnées GPS |
| `06_Nonconteneurisables` | Adresses non conteneurisables avec coordonnées GPS |

> ⚠️ Le parsing est positionnel (par index de colonne). Tout décalage de colonne dans Excel casse la lecture des données.

---

## 🛠️ Technologies

Fichier HTML entièrement autonome, sans dépendance serveur, s'appuyant sur des librairies CDN :

| Librairie | Usage |
|-----------|-------|
| [XLSX.js](https://github.com/SheetJS/sheetjs) | Lecture du fichier Excel côté navigateur |
| [Chart.js](https://www.chartjs.org/) | Graphiques |
| [Leaflet.js](https://leafletjs.com/) + CartoDB | Carte interactive |
| [jsPDF](https://github.com/parallax/jsPDF) + html2canvas | Export PDF |
| [Font Awesome 6](https://fontawesome.com/) | Icônes |
| [DM Sans + JetBrains Mono](https://fonts.google.com/) | Typographie |

---

## 📍 Territoire

**Communauté de communes Normandie Cabourg Pays d'Auge (NCPA)**  
Calvados (14) · 39 communes · 3 zones territoriales : Littorale, Périurbaine, Rurale

---

*Dashboard développé pour la Direction de la maîtrise des déchets — NCPA*
