# 🧹 Préparation des Données pour un Organisme de Santé Publique  

**Projet de préparation et d’analyse de données nutritionnelles issues d’Open Food Facts pour un organisme de santé publique.**

---

## 🎯 Objectif  
Ce projet a été réalisé dans le cadre d’une mission de **data cleaning et préparation de données** pour **Santé publique France**.  
L’objectif est d’**améliorer la qualité de la base Open Food Facts** afin de faciliter la création d’un **système de suggestion automatique** pour les contributeurs.

---

## 🧩 Contenu du projet  
Le dépôt contient :  

- **Notebook Jupyter** :  
  - Nettoyage et filtrage des variables (`features`)  
  - Identification et traitement des valeurs aberrantes (approche métier et statistique)  
  - Identification et imputation des valeurs manquantes  
  - Analyses univariées, bivariées et multivariées  
  - Modélisation et validation du modèle de classification (KNN)  

- **Présentation PowerPoint** résumant la démarche, les méthodes statistiques utilisées et les résultats de performance.

---

## 🧪 Méthodologie  

1. **Nettoyage & filtrage des données**
   - 320 000+ produits initiaux → 55 896 après sélection  
   - 14 variables retenues (11 quantitatives, 3 qualitatives)  

2. **Traitement des valeurs aberrantes**
   - Méthode interquartile (IQR) appliquée par groupes (`pnns_groups_1` / `pnns_groups_2`)  
   - Règles métier : `Salt > Sodium`, `Fat > Saturated Fat`, etc.  

3. **Traitement des valeurs manquantes**
   - Imputation comparée (moyenne, médiane, itération, KNN)  
   - Méthode retenue : **KNN Imputer**, sauf pour `Carbohydrates` (itération).  

4. **Analyses statistiques**
   - Analyses uni/bivariées, ACP, ANOVA, Kruskal-Wallis  
   - Tests de normalité et d’homoscedasticité pour choix des tests adaptés  

5. **Modélisation**
   - **K Neighbors Classifier**
   - Précision : **96 % après traitement** (contre 87 % avant nettoyage)  

---

## 📊 Résultats principaux  

| Catégorie alimentaire | Précision (avant) | Précision (après) |
|------------------------|------------------|-------------------|
| Beverages              | 98 %             | 98 %              |
| Sugary snacks          | 91 %             | 99 %              |
| Milk and dairy         | 89 %             | 98 %              |
| Fat and sauces         | 85 %             | 95 %              |
| Total accuracy         | **87 % → 96 %**  |                   |

---

## 🛠️ Technologies utilisées  

- **Python** : Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn  
- **Environnement** : Jupyter Notebook  
- **Tests statistiques** : Levene, Shapiro-Wilk, Kruskal-Wallis, Kolmogorov-Smirnov  
- **Modélisation** : KNN Classifier  

---

## 📂 Structure du dépôt  

```text
preparation_donnees_sante_publique
│
├── Martineau_Alexandre_1_notebook_032024.ipynb      # Notebook principal
├── Martineau_Alexandre_2_presentation_032024.pptx   # Présentation PowerPoint
└── README.md
```
