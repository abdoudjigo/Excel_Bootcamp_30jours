# Jour 15 : Graphiques

## Objectifs
- Créer un histogramme, une courbe, un diagramme circulaire et un nuage de points
- Choisir le bon graphique pour répondre à une question métier
- Construire un petit dashboard commercial

---

## Partie théorique

### 1. Quelle est la différence entre un histogramme et une courbe ?
**Réponse :**
- **Histogramme** : compare des catégories (ex: CA par catégorie)
- **Courbe** : montre une évolution dans le temps (ex: CA par mois)

### 2. Quand un graphique circulaire est-il pertinent ?
**Réponse :** Pour montrer une répartition en pourcentage, avec **peu de catégories** (idéalement 3-5).

### 3. Pourquoi éviter un graphique circulaire avec beaucoup de catégories ?
**Réponse :** Les parts deviennent trop petites et illisibles. Un histogramme est plus adapté.

### 4. À quoi sert un nuage de points ?
**Réponse :** À visualiser la relation entre deux variables quantitatives (ex: Quantité vs Chiffre d'affaires).

### 5. Comment représenter l'évolution du CA sur 12 mois ?
**Réponse :** Avec une **courbe** (axe X = mois, axe Y = CA).

### 6. Comment représenter le CA par catégorie ?
**Réponse :** Avec un **histogramme** (axe X = catégories, axe Y = CA).

### 7. Comment analyser la relation entre Quantité et CA ?
**Réponse :** Avec un **nuage de points**.

---

## Partie pratique

### Dataset
1. Créer une feuille **"Pratique_Graphiques"**
2. Saisir les données :

| Mois | CA | Quantité |
|------|----|----------|
| Janvier | 4200000 | 120 |
| Février | 4500000 | 135 |
| Mars | 4800000 | 142 |
| Avril | 4300000 | 125 |
| Mai | 5100000 | 155 |
| Juin | 5500000 | 170 |

---

### Exercice 1 — Courbe

**Instructions :** Créer une courbe représentant l'évolution du CA par mois.

**Question :** Quelle tendance observes-tu ?

**Réponse :** Le CA augmente globalement sur la période, passant de 4,2M à 5,5M.

---

### Exercice 2 — Histogramme

**Instructions :** Créer un histogramme comparant les quantités vendues par mois.

---

### Exercice 3 — Diagramme circulaire

**Instructions :**
1. Créer ce tableau :

| Catégorie | CA |
|-----------|----|
| Informatique | 8500000 |
| Accessoires | 4200000 |
| Mobilier | 2800000 |
| Logiciels | 3500000 |

2. Créer un diagramme circulaire.

**Question :** Quelle catégorie représente la plus grande part du CA ?

**Réponse :** L'Informatique avec 8,5M (soit environ 45% du total).

---

### Exercice 4 — Nuage de points

**Instructions :** Créer un nuage de points avec Quantité en X et CA en Y.

**Question :** Existe-t-il une relation entre quantité et CA ?

**Réponse :** Oui, une relation positive : plus la quantité vendue est élevée, plus le CA est élevé.

---

## Mini-projet — Dashboard commercial

### Structure :

| Zone | Contenu |
|------|---------|
| En-tête | Titre + KPI (CA total, CA net, Quantité, Nb ventes) |
| Graphique 1 | Courbe → Évolution du CA |
| Graphique 2 | Histogramme → CA par catégorie |
| Graphique 3 | Circulaire → Répartition du CA |
| Graphique 4 | Nuage de points → Quantité vs CA |

### Challenge :
Ajouter une phrase de conclusion sous chaque graphique.

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Graphique vide | Vérifier la plage de données sélectionnée |
| Mauvais type de graphique | Réfléchir à la question métier avant de choisir |
| Circulaire illisible | Passer à un histogramme si > 5 catégories |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris