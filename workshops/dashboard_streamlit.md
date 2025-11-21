# Exercice Python & Streamlit  
### 1 - Dashboard d’analyse des données sur le transport

---

## 🎯 Objectif de l’exercice

Dans cet exercice, vous allez concevoir une application **Streamlit** permettant de visualiser et d’analyser la **régularité / ponctualité du métro parisien (RATP)** à partir de données ouvertes.  

L’objectif est de :

- Charger des données issues de l’**open data RATP**  (ou tout autre source de données sur les transports en France) 
- Les préparer correctement (qualité, formats, granularité)  
- Construire un **dashboard clair et lisible** (graphique + filtres)  
- Soigner le **design de la dataviz** (choix des couleurs, légendes, titres)  
- Écrire un **code Python simple, structuré et maintenable**  

---

## 📁 Données

Vous utiliserez les données disponibles sur l’Open Data RATP :  

- Portail Open Data RATP :  
  - <https://data.ratp.fr/explore/>  
- Page d’accès aux données temps réel / voyageurs (API, datasets) :  
  - <https://data.ratp.fr/pages/temps-reel/>  
- Plateforme Régionale d'Information pour la Mobilité (PRIM):
  - <https://prim.iledefrance-mobilites.fr/fr/catalogue-data>
---

### Consigne : 
Le choix de données proposé n'est pas obligatoire. Vous êtes entièrement libres de sélectionner les données de transport qui vous intéressent : métro RATP, trafic IDFM,  bus/tram, ou tout autre opérateur disponible en open data.
Vous pouvez télécharger un fichier CSV ou utiliser une API si vous êtes à l’aise.

---

## 🧩 Cadre de l’exercice

Vous travaillez dans le contexte d’un **POC (Proof of Concept)** pour une équipe Data & Digital qui souhaite :

- Suivre la **régularité du métro** dans le temps  
- Visualiser les **lignes les plus perturbées ou les plus régulières**  
- Identifier les **plages horaires problématiques** (heures de pointe, soirées, week-ends, etc.)  

Votre dashboard Streamlit doit permettre à un utilisateur non technique de :

- **Filtrer** les données (par ligne, par période, par jour/heure)  
- **Comprendre rapidement** l’état de la régularité  
- Explorer quelques **visualisations interactives** (courbes, barres, heatmaps, etc.)

---

## 🛠️ Instructions et exigences techniques

### 1. Préparation des données (obligatoire)

- Vérifiez les **types de colonnes** (dates, nombres, catégories).  
- Gérez les **valeurs manquantes** (suppression ou imputation simple).  
- Renommez les colonnes pour plus de **clarté** si nécessaire (ex : `date`, `ligne`, `taux_reg`).  
- Créez éventuellement des **variables dérivées** :  
  - Année, mois, jour à partir d’une colonne de date.  
  - Catégories (heures de pointe vs heures creuses, etc. si pertinent).

> L’étape de préparation des données doit être **clairement structurée** dans votre code (fonctions ou bloc dédié).

### 2. Application Streamlit

Créer un fichier Python (par exemple `app.py`) contenant une application Streamlit minimaliste mais propre :

- Titre et sous-titre de l’application (`st.title`, `st.subheader`).  
- Chargement des données (via `pandas`).  
- Widgets d’interaction :  
  - `st.selectbox` pour choisir une **ligne**.  
  - `st.slider` ou `st.date_input` pour filtrer la période.  
- Affichage de plusieurs visualisations :  
  - Graphique d’évolution temporelle.  
  - Graphique comparatif entre lignes.  
- Affichage de tableaux résumés (ex : `st.dataframe`).

### 3. Qualité du code Python

- Code **simple, lisible et commenté avec parcimonie**.  
- Utiliser des **fonctions** pour séparer :  
  - la préparation des données,  
  - la création des graphiques,  
  - la partie interface utilisateur.  
- Éviter la duplication de code (DRY – *Don’t Repeat Yourself*).

### 4. Choix des couleurs et lisibilité

- Choisir une **palette de couleurs cohérente** (par exemple, une palette de couleurs discrètes pour les lignes, ou une palette adaptée aux daltoniens).  
- Veiller à :  
  - Avoir des **labels clairs** sur les axes,  
  - Des **titres explicites** pour chaque graphique,  
  - Des **légendes** si plusieurs lignes sont affichées,  
  - Une **taille de police suffisante**.

---

##  Outils de visualisation recommandés

Vous pouvez utiliser :

- **Plotly** (recommandé pour l’interactivité dans Streamlit)  
- **Seaborn** (pour des graphiques statistiques classiques)  
- **Matplotlib** (pour les bases ou des besoins spécifiques)

L’important est de :  
- garder une **cohérence graphique**,  
- éviter de multiplier trop de styles différents dans la même app.

---

##  Résultats attendus

À la fin de l’exercice, vous devez livrer :

1. Un fichier Streamlit fonctionnel (`app.py`) qui :  
   - se lance avec `streamlit run app.py`,  
   - charge les données,  
   - propose au moins **2 visualisations** principales et **1 tableau** de données filtrées.

2. Des visualisations :  
   - lisibles,  
   - cohérentes,  
   - interprétables sans explication orale supplémentaire.

3. Un court texte (dans l’app ou dans un fichier séparé `README.md`) résumant :  
   - votre choix de visualisations,  
   - les principaux enseignements des données.

---

## Ressources utiles

- **Documentation Streamlit** :  
  - https://docs.streamlit.io  

- **Documentation Plotly (Python)** :  
  - https://plotly.com/python  

- **Documentation Seaborn** :  
  - https://seaborn.pydata.org  

---

##  Les 5 règles d’or d’une data viz réussie

- **Clarté** : le message doit être immédiatement compréhensible.  
- **Pertinence** : choisir le bon type de graphique pour le bon type de données.  
- **Simplicité** : éviter la surcharge visuelle, aller à l’essentiel.  
- **Cohérence visuelle** : palettes de couleurs, styles et typographies homogènes.  
- **Lisibilité & honnêteté** : axes bien définis, échelles non trompeuses, légendes explicites.

---

##  Pour aller plus loin (optionnel)

- Ajouter un **système d’onglets** dans Streamlit (`st.tabs`) pour séparer :  
  - Vue globale toutes lignes,  
  - Focus sur une ligne,  
  - Comparaison de plusieurs lignes.  
- Intégrer des **indicateurs clés** (KPI) avec `st.metric`.  
- Tester un **déploiement** de l’app (Streamlit Community Cloud, par exemple).
