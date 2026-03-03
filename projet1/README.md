# 🚉 Analyse de la Programmation des Chantiers SNCF (5 ans)

## 📋 Présentation du Projet
Ce projet consiste en la création d'un tableau de bord interactif sur Power BI pour analyser les prévisions de chantiers ferroviaires sur une période de 5 ans. L'objectif est de transformer des données brutes de planification en indicateurs stratégiques pour piloter les investissements et la charge de travail par région.
📥 **[Télécharger le dataset utilisé pour ce projet](https://ressources.data.sncf.com/explore/dataset/bulletins-des-previsions-de-marches-de-consultations-sncf-reseau/information/?sort=seuils&dataChart=eyJxdWVyaWVzIjpbeyJjaGFydHMiOlt7InR5cGUiOiJjb2x1bW4iLCJmdW5jIjoiQ09VTlQiLCJzY2llbnRpZmljRGlzcGxheSI6dHJ1ZSwiY29sb3IiOiIjRjA3OEQ4In1dLCJ4QXhpcyI6InJlZ2lvbnMiLCJtYXhwb2ludHMiOjUwLCJzb3J0IjoiIiwiY29uZmlnIjp7ImRhdGFzZXQiOiJidWxsZXRpbnMtZGVzLXByZXZpc2lvbnMtZGUtbWFyY2hlcy1kZS1jb25zdWx0YXRpb25zLXNuY2YtcmVzZWF1Iiwib3B0aW9ucyI6eyJzb3J0Ijoic2V1aWxzIn19fV0sInRpbWVzY2FsZSI6IiIsImRpc3BsYXlMZWdlbmQiOnRydWUsImFsaWduTW9udGgiOnRydWV9)**

## 🛠️ Stack Technique
* **Outil :** Power BI Desktop
* **Langages :** DAX (Data Analysis Expressions) & M (Power Query)
* **Données :** Extraits de programmation (Format JSON/CSV) comprenant des données géospatiales (Centroids).

## 🚀 Étapes de Réalisation

### 1. Préparation et Nettoyage des Données (Power Query)
* **Fusion de tables :** Jointure (`Left Outer Join`) avec un référentiel de domaines pour catégoriser les achats.
* **Traitement Géospatial :** Extraction des coordonnées `Latitude` et `Longitude` depuis le format GeoJSON `centroid`.
* **Data Cleaning :** Conversion des types de données (gestion des séparateurs décimaux "." vs ",") pour assurer la compatibilité avec le moteur cartographique Bing Maps.

### 2. Modélisation et DAX
Création de mesures dynamiques pour piloter le rapport :
* **Nombre de Marchés :** `COUNTROWS('Table')` pour suivre le volume.
* **Budget Total :** Agrégation des coûts maximums prévus.
* **Paramètres de champs :** Mise en place d'un sélecteur permettant à l'utilisateur de basculer la vue de la carte entre le **Volume de chantiers** et le **Budget total**.

### 3. Visualisation Interactive
* **Cartographie précise :** Affichage de chaque chantier par coordonnées géographiques réelles (et non par simple nom de ville).
* **Slicers temporels :** Filtrage dynamique sur la chronologie des 5 ans.
* **KPI Cards :** Affichage des chiffres clés (Total M€, Nombre de projets) synchronisés avec les filtres.

## 📊 Aperçu du Dashboard
*Cliquer sur les vidéos si elles ne se lancent pas automatiquement*  
![Results of kpi page](kpi_video.gif)  
![Results of Carte page](carte_video.gif)

## 📂 Structure du dépôt
* `chantiers_sncf.pbix` : Le fichier Power BI complet (utilisable après téléchargement).
* `chantiers_sncf.pbip` : Le projet au format dossier pour visualiser le code source (DAX/M) en clair.

---
*Projet réalisé dans le cadre d'une montée en compétence sur l'analyse de données BI.*
