# Jour 17 : Nettoyage des données

## Objectifs
- Identifier et supprimer les doublons
- Traiter les valeurs manquantes
- Corriger les formats incohérents
- Standardiser les textes
- Construire une base de données fiable

---

## Partie théorique

### 1. Qu'est-ce qu'un doublon ?
**Réponse :** Une ligne qui est identique à une autre sur toutes les colonnes, ou qui partage le même identifiant unique.

### 2. Est-ce que deux lignes ayant le même client sont forcément des doublons ?
**Réponse :** Non. Un client peut avoir plusieurs commandes. Il faut vérifier l'identifiant unique (ex: `order_id`).

### 3. Différence entre cellule vide et "N/A" ?
**Réponse :** 
- **Cellule vide** : donnée manquante (absence d'information)
- **"N/A"** : valeur explicite signifiant "Non Applicable" (information existe mais non pertinente)

### 4. Différentes façons de traiter une valeur manquante ?
**Réponse :**
- Supprimer la ligne
- Remplacer par une valeur (0, moyenne, médiane)
- Laisser vide
- Imputer avec une valeur calculée

### 5. Pourquoi remplacer par 0 est dangereux ?
**Réponse :** 0 est une valeur qui modifie les calculs (moyennes, sommes). Si la donnée est manquante, 0 peut fausser l'analyse.

### 6. Pourquoi "Dakar", "dakar", "Dakar " posent problème ?
**Réponse :** Excel les considère comme différentes valeurs. Il faut standardiser (même casse, sans espaces).

### 7. Comment reconnaître un nombre stocké comme texte ?
**Réponse :** Le nombre est aligné à gauche (au lieu de droite), ou il y a un petit triangle vert en haut à gauche de la cellule.

### 8. Pourquoi conserver une copie des données originales ?
**Réponse :** Pour pouvoir revenir en arrière, comparer, ou recommencer si une erreur est commise.

### 9. Pourquoi vérifier avant et après le nettoyage ?
**Réponse :** Pour mesurer l'impact du nettoyage et s'assurer qu'on n'a pas introduit d'erreurs.

---

## Partie pratique

### Dataset
1. Créer une feuille **"Pratique_Nettoyage"**
2. Saisir le tableau volontairement "sale" :

| ID | Nom | Ville | Salaire | Date |
|----|-----|-------|---------|------|
| 001 | Awa Ndiaye | Dakar | 350000 | 12/01/2026 |
| 002 | Mamadou Diop | dakar | 400000 | 2026-01-15 |
| 003 | Fatou Fall | Thiès | | 18/01/2026 |
| 003 | Fatou Fall | Thiès | | 18/01/2026 |
| 004 | Cheikh Ba | Dakar | 450000 | 20/01/2026 |
| 005 | Mariama Sow | Dakar | 325000 | 2026/01/22 |

---

### Exercice 1 — Identifier les doublons

**Instructions :**
1. Sélectionner les données
2. Données → **Supprimer les doublons**
3. Observer : combien de doublons ?

**Résultat :** 1 doublon (la ligne de Fatou Fall qui apparaît 2 fois)

---

### Exercice 2 — Valeurs manquantes

**Instructions :**
1. Identifier les cellules vides
2. Décider du traitement :
   - Laisser vide ?
   - Remplacer par 0 ?
   - Remplacer par une moyenne ?

**Réponse :** Remplacer par la moyenne des salaires existants (car le salaire de Fatou peut être estimé).

---

### Exercice 3 — Formats incohérents

**Instructions :**
1. Standardiser les villes : `Dakar`, `dakar` → `Dakar` (majuscule)
2. Utiliser : `=MAJUSCULE(SUPPRESPACE(A1))` ou `=PROPER()`

---

## Mini-projet — Nettoyage d'une vraie base

### Dataset : Ecommerce Orders (3 047 lignes)

### Structure :
- **Raw_Data** : données brutes (NE PAS MODIFIER)
- **Clean_Data** : données nettoyées

### Étapes :

#### Étape 1 — Diagnostiquer
- Doublons (`order_id`)
- Valeurs manquantes
- Formats incohérents (pays, dates, devises, unités)

#### Étape 2 — Nettoyer
- Supprimer les vrais doublons
- Standardiser les textes
- Traiter les valeurs manquantes
- Corriger les dates
- Vérifier les unités

#### Étape 3 — Contrôle qualité

| Contrôle | Avant | Après |
|----------|-------|-------|
| Nombre de lignes | | |
| Doublons | | |
| Valeurs manquantes | | |
| Formats incohérents | | |

### Challenge
Répondre à :
- Combien de doublons supprimés ?
- Combien de valeurs manquantes ?
- Quelles colonnes problématiques ?
- Quelles transformations ?

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Supprimer un doublon important | Vérifier l'identifiant unique avant suppression |
| Remplacer une valeur manquante par 0 | Utiliser une moyenne ou laisser vide |
| Problème de casse | Standardiser avec MAJUSCULE ou PROPER |
| Dates dans plusieurs formats | Utiliser l'Assistant de conversion |

---

## Statut
⬜ Théorie faite
⬜ Exercices faits
⬜ Mini-projet fait
⬜ Points de friction compris