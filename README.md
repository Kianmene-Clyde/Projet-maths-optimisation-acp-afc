# 📊 Mathématiques pour le Big Data — Optimisation, ACP, AFC

> Projet séminaire ESGI 5A Big Data — Résolution complète sous R/RStudio

---

## 🎯 Objectif du projet

Ce projet couvre les fondamentaux mathématiques appliqués au Big Data à travers 8 exercices résolus intégralement en R (sans fonctions prédéfinies pour les parties demandées) :

| # | Thème | Méthodes |
|---|-------|----------|
| 1 | **Moindres carrés** | Régression linéaire, ajustement exponentiel, prédiction |
| 2 | **Optimisation sans contrainte** | Gradient, Hessienne, valeurs propres, points critiques |
| 3 | **Optimisation sous contraintes** | Lagrangien, multiplicateurs, Hessienne bordée |
| 4 | **SVD & Pseudo-inverse** | Décomposition en valeurs singulières, Moore-Penrose, résolution de systèmes |
| 5 | **ACP** | Analyse en Composantes Principales (données protéiques européennes) |
| 6 | **Test du Chi-deux** | Test d'adéquation, distribution théorique vs observée |
| 7 | **AFC — Cas 1** | Analyse Factorielle des Correspondances (professions & sympathie) |
| 8 | **AFC — Cas 2** | Élection présidentielle française 2007 par région |

---

## 📁 Structure du projet

```
├── Projet_Complet.Rmd        # Fichier RMarkdown principal (tous les exercices)
├── donnees1.txt               # Données ACP : consommation protéique en Europe
├── donnees2.txt               # Données AFC : professions et qualités de sympathie
├── election 2007.csv          # Données AFC : résultats élection 2007 par région
└── README.md
```

---

## 🚀 Installation et exécution

### Prérequis

- [R](https://cran.r-project.org/) (≥ 4.0)
- [RStudio](https://posit.co/download/rstudio-desktop/)

### 1. Cloner le dépôt

```bash
git clone https://github.com/<ton-username>/maths-bigdata-optimisation-acp-afc.git
cd maths-bigdata-optimisation-acp-afc
```

### 2. Installer les packages R nécessaires

```r
install.packages(c("FactoMineR", "factoextra", "corrplot", "ggplot2", "gridExtra", "knitr", "rmarkdown"))
```

### 3. Générer le rapport

Ouvrir `Projet_Complet.Rmd` dans RStudio, puis :

- **Knit → Knit to HTML** (recommandé, pas besoin de LaTeX)
- ou **Knit → Knit to PDF** (nécessite LaTeX / TinyTeX)

Pour installer TinyTeX si besoin :
```r
install.packages("tinytex")
tinytex::install_tinytex()
```

---

## 📝 Détail des exercices

### Exercice 1 — Moindres carrés
Ajustement d'un modèle exponentiel de dépréciation d'un article. Transformation logarithmique, droite de régression par moindres carrés (calcul manuel), estimation à 10 ans.

### Exercice 2 — Optimisation sans contrainte
Étude de trois fonctions multivariées : calcul analytique du gradient, des points critiques, de la matrice Hessienne et de ses valeurs propres pour déterminer la nature des extrema (minimum, maximum, point selle). Tracés 3D et courbes de niveau.

### Exercice 3 — Optimisation sous contraintes
Cinq problèmes d'optimisation avec contraintes d'égalité résolus par la méthode des multiplicateurs de Lagrange. Construction du Lagrangien, Hessienne bordée, analyse des mineurs principaux. Graphiques avec courbes de niveau et contraintes.

### Exercice 4 — SVD et pseudo-inverse
- **Cas 1** : Décomposition en valeurs singulières de deux matrices (4×4 et 4×5), étape par étape.
- **Cas 2** : Construction des pseudo-inverses (Moore-Penrose), vérification des 4 propriétés, résolution de systèmes linéaires `Ax = b` et `Bx = b`.

### Exercice 5 — ACP
Analyse en Composantes Principales sur les données de consommation protéique de 25 pays européens durant la guerre froide :
- Matrice de corrélation et graphiques de couples de variables
- Valeurs propres, cercle des corrélations, carte des individus, biplot
- Interprétation des axes, qualité de représentation, cas du Portugal
- Variable supplémentaire EST (bloc de l'Est) et valeurs test

### Exercice 6 — Test du Chi-deux
Test d'adéquation pour valider une étude de marché sur la fréquentation d'un restaurant. Calcul manuel de la statistique Q, comparaison avec la valeur critique χ².

### Exercice 7 — AFC (Cas 1)
Analyse Factorielle des Correspondances sur un tableau de contingence croisant catégories professionnelles et qualités de sympathie. Profils lignes/colonnes, contributions, cos², interprétation du biplot.

### Exercice 8 — AFC (Cas 2)
AFC sur les résultats du premier tour de l'élection présidentielle 2007 en France par région. Test du Chi-deux d'indépendance, cartes factorielles des régions et candidats, interprétation des clivages territoriaux.

---

## 📊 Aperçu des résultats

<details>
<summary><b>Exercice 1 — Modèle exponentiel</b></summary>

- Droite d'ajustement : `Z(t) = -0.2005 × t + 4.5003`
- Modèle : `X(t) = 90.04 × exp(-0.2005t)`
- Estimation à 10 ans : **12.12 centaines d'euros**
</details>

<details>
<summary><b>Exercice 2 — Points critiques</b></summary>

- `f(x,y)` : point selle en (0, 1)
- `g(x,y,z)` : minimum local en (-1, 0, 0)
- `h(x,y,z)` : deux points selles en (e, e, e) et (1/e, 1/e, 1/e)
</details>

<details>
<summary><b>Exercice 5 — ACP</b></summary>

- Axe 1 (44.5%) : opposition produits animaux (Ouest) vs céréales (Est)
- Axe 2 (18.2%) : gradient méditerranéen (poisson, fruits/légumes)
- 2 axes retenus → 62.7% d'inertie expliquée
</details>

---

## 🛠 Technologies

- **Langage** : R
- **IDE** : RStudio
- **Packages** : FactoMineR, factoextra, corrplot, ggplot2, gridExtra
- **Format** : RMarkdown (.Rmd) → HTML / PDF

---

## 📄 Licence

Projet académique — ESGI 5A Big Data.
