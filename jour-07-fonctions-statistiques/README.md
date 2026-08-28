# Jour 07 : Fonctions statistiques essentielles

## Objectifs
- Comprendre la différence entre formule et fonction
- Maîtriser SUM, AVERAGE, MAX, MIN, COUNT
- Savoir utiliser COUNTIF et COUNTIFS
- Produire un résumé statistique complet

---

## Partie théorique

### 1. Quelle est la différence entre une formule et une fonction dans Excel ?
**Réponse :** 
- **Formule** : toute expression qui commence par `=` (ex: `=A1+B1`).
- **Fonction** : une formule préprogrammée avec un nom (ex: `=SOMME(A1:A10)`). Les fonctions simplifient les calculs complexes.

### 2. Que calcule SUM ?
**Réponse :** `=SUM(plage)` calcule la **somme** de toutes les valeurs numériques dans la plage sélectionnée.

### 3. Quelle différence entre COUNT et le nombre total de lignes d'un tableau ?
**Réponse :** 
- **COUNT** : compte uniquement les cellules contenant des **valeurs numériques**.
- **Nombre total de lignes** : compte toutes les lignes, même celles avec des cellules vides ou du texte.

### 4. Quelle différence entre COUNTIF et COUNTIFS ?
**Réponse :** 
- **COUNTIF** : compte les cellules qui répondent à **1 condition** (ex: `=COUNTIF(H2:H1001;">=15")`).
- **COUNTIFS** : compte les cellules qui répondent à **plusieurs conditions simultanément** (ex: `=COUNTIFS(H2:H1001;">=15";F2:F1001;">=15")`).

### 5. Dans quel cas utiliser AVERAGE, MAX et MIN ?
**Réponse :** 
- **AVERAGE** : pour connaître la **moyenne** d'une série (niveau général).
- **MAX** : pour connaître la **meilleure performance**.
- **MIN** : pour connaître la **plus faible performance**.

---

## Partie pratique

### Dataset
1. Créer un nouveau fichier `jour07_statistiques.xlsx`
2. Copier les **1 000 étudiants** depuis `jour-03-tri-filtres/data/student_data_1000.xlsx`
3. Créer une feuille **"Pratique"** avec toutes les données

---

### Exercice 1 — Statistiques descriptives

**Instructions :** Sur la colonne **Python** (colonne H), calcule :

| Indicateur | Formule | Résultat |
|------------|---------|----------|
| Somme des notes | `=SUM(H2:H1001)` |  |
| Moyenne | `=AVERAGE(H2:H1001)` |  |
| Note maximale | `=MAX(H2:H1001)` | 20 |
| Note minimale | `=MIN(H2:H1001)` |  |
| Nombre de notes | `=COUNT(H2:H1001)` | 1000 |

**Réalisation :**
- En **A2** : "Somme Python"
- En **B2** : `=SUM(H2:H1001)`
- En **A3** : "Moyenne Python"
- En **B3** : `=AVERAGE(H2:H1001)`
- En **A4** : "Max Python"
- En **B4** : `=MAX(H2:H1001)`
- En **A5** : "Min Python"
- En **B5** : `=MIN(H2:H1001)`
- En **A6** : "Nb notes Python"
- En **B6** : `=COUNT(H2:H1001)`

**Question : Quelle différence y a-t-il entre COUNT et COUNTA ? Pourquoi COUNT peut-il être insuffisant pour compter les étudiants d'un dataset ?**

**Réponse :** 
- `COUNT` compte uniquement les **valeurs numériques**.
- `COUNTA` compte toutes les **cellules non vides** (nombres + texte).
- `COUNT` peut être insuffisant car si un étudiant n'a pas de note (cellule vide), il n'est pas compté. Pour compter les étudiants, il vaut mieux utiliser `COUNTA` sur une colonne qui contient toujours des données (ex: ID ou Nom).

---

### Exercice 2 — Compter selon une condition

**Instructions :** Utilise `COUNTIF` pour trouver :

| Condition | Formule | Résultat |
|-----------|---------|----------|
| Python >= 15 | `=COUNTIF(H2:H1001;">=15")` | |
| Math < 10 | `=COUNTIF(F2:F1001;"<10")` | |
| Presence >= 90% | `=COUNTIF(J2:J1001;">=0,9")` | |

**Réalisation :**
- En **A8** : "Python >= 15"
- En **B8** : `=COUNTIF(H2:H1001;">=15")`
- En **A9** : "Math < 10"
- En **B9** : `=COUNTIF(F2:F1001;"<10")`
- En **A10** : "Presence >= 90%"
- En **B10** : `=COUNTIF(J2:J1001;">=0,9")`

---

### Exercice 3 — Compter avec plusieurs conditions

**Instructions :** Utilise `COUNTIFS` pour trouver :

| Condition | Formule | Résultat |
|-----------|---------|----------|
| Python >= 15 ET Math >= 15 | `=COUNTIFS(H2:H1001;">=15";F2:F1001;">=15")` | 220 |
| Presence >= 90% ET Python >= 15 | `=COUNTIFS(J2:J1001;">=0,9";H2:H1001;">=15")` | |
| Math < 10 ET Presence < 80% | `=COUNTIFS(F2:F1001;"<10";J2:J1001;"<0,8")` | |

**Réalisation :**
- En **A12** : "Python >= 15 ET Math >= 15"
- En **B12** : `=COUNTIFS(H2:H1001;">=15";F2:F1001;">=15")`
- En **A13** : "Presence >= 90% ET Python >= 15"
- En **B13** : `=COUNTIFS(J2:J1001;">=0,9";H2:H1001;">=15")`
- En **A14** : "Math < 10 ET Presence < 80%"
- En **B14** : `=COUNTIFS(F2:F1001;"<10";J2:J1001;"<0,8")`

---

## Mini-projet — Analyse des notes d'une promotion

### Contexte
Produire un résumé statistique pour le responsable pédagogique.

### Instructions
1. Créer une feuille **"Analyse_Notes"**
2. Copier les 1 000 étudiants

---

### Étape 1 — Résumé général

**Créer ce tableau :**

| Indicateur | Résultat |
|------------|----------|
| Nombre de notes en Math | |
| Moyenne Math | |
| Note maximale Math | |
| Note minimale Math | |
| Nombre de notes en Python | |
| Moyenne Python | |
| Note maximale Python | |
| Note minimale Python | |

**Formules à utiliser :**
- `=COUNT(F2:F1001)`
- `=AVERAGE(F2:F1001)`
- `=MAX(F2:F1001)`
- `=MIN(F2:F1001)`
- Idem pour Python (colonne H)

---

### Étape 2 — Identifier les bonnes performances

**Créer ce tableau :**

| Indicateur | Résultat |
|------------|----------|
| Étudiants avec Python >= 15 | |
| Étudiants avec Math >= 15 | |
| Étudiants avec Présence >= 90% | |

**Formules :** `COUNTIF`

---

### Étape 3 — Identifier les profils performants

**Créer ce tableau :**

| Indicateur | Résultat |
|------------|----------|
| Math >= 15 ET Python >= 15 | |
| Python >= 15 ET Présence >= 90% | |
| Math < 10 ET Présence < 80% | |

**Formules :** `COUNTIFS`

---

### Résultat attendu

À la fin, ta feuille doit permettre de répondre immédiatement à :

| Question | Réponse |
|----------|---------|
| Quel est le niveau moyen en Math et Python ? | |
| Quelle est la meilleure et la plus faible performance ? | |
| Combien d'étudiants ont de bonnes performances ? | |
| Combien combinent bonne performance et bonne présence ? | |
| Combien d'étudiants nécessitent une attention particulière ? | |

---

### 🌟 Challenge

> Combien d'étudiants ont obtenu **au moins 15 dans Math ou Python** ?

**Indice :** `COUNTIF` ne peut pas faire de "OU". Il faut combiner plusieurs formules.

**Solution possible :**
```
=COUNTIF(F2:F1001;">=15") + COUNTIF(H2:H1001;">=15") - COUNTIFS(F2:F1001;">=15";H2:H1001;">=15")
```
(Éviter les doublons d'étudiants qui sont >= 15 dans les deux matières)

---

## Points de friction

| Problème | Solution |
|----------|----------|
| COUNT compte les cellules vides | Utiliser COUNTA pour compter toutes les cellules non vides |
| Pourcentage avec COUNTIF | Utiliser les valeurs décimales (0,9 pour 90%) |
| COUNTIF avec plusieurs conditions | Utiliser COUNTIFS |
| Résultat 0 avec COUNTIF | Vérifier les guillemets et le signe comparateur |
| "OU" logique avec COUNTIF | Combiner plusieurs COUNTIF et soustraire les doublons |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris