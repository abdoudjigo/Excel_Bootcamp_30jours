# Jour 13 : INDEX et MATCH

## Objectifs
- Comprendre INDEX et MATCH individuellement
- Maîtriser la combinaison INDEX + MATCH
- Savoir faire des recherches flexibles
- Construire une interface RH

---

## Partie théorique

### 1. Que fait INDEX ?
**Réponse :** INDEX retourne la valeur d'une cellule à une position donnée dans une plage.
- `=INDEX(plage; position)` → retourne la valeur à cette position

### 2. Que renvoie MATCH ?
**Réponse :** MATCH retourne la **position** d'une valeur dans une plage.
- `=MATCH(valeur; plage; type)` → retourne un numéro (ex: 4)

### 3. Quelle différence entre la position d'une valeur et la valeur elle-même ?
**Réponse :** 
- **Position** : l'endroit où se trouve la valeur (ex: ligne 4)
- **Valeur** : le contenu de la cellule (ex: "Cheikh Ba")

### 4. Pourquoi INDEX et MATCH peuvent-ils être combinés ?
**Réponse :** 
1. MATCH trouve la position de la valeur recherchée
2. INDEX utilise cette position pour retourner la valeur dans une autre colonne

### 5. Quelle est la principale limite de VLOOKUP que INDEX + MATCH permet d'éviter ?
**Réponse :** VLOOKUP ne cherche que dans la **première colonne** et ne peut pas chercher vers la gauche. INDEX + MATCH peut chercher dans n'importe quelle colonne.

### 6. Quelle différence entre MATCH(...,0) et une recherche approximative ?
**Réponse :** 
- `0` : recherche exacte (identifiants, noms)
- `1` ou `-1` : recherche approximative (les données doivent être triées)

---

## Partie pratique

### Dataset
1. Créer une feuille **"Pratique_INDEX_MATCH"**
2. Saisir le tableau :

| ID | Nom | Département | Salaire |
|----|-----|-------------|---------|
| E001 | Awa Ndiaye | Data | 350000 |
| E002 | Mamadou Diop | Finance | 400000 |
| E003 | Fatou Fall | RH | 375000 |
| E004 | Cheikh Ba | IT | 450000 |
| E005 | Mariama Sow | Marketing | 325000 |

---

### Exercice 1 — INDEX

**Instructions :** Récupérer le 3ème élément de la colonne Nom.

**Formule :** `=INDEX(B2:B6;3)` → `Fatou Fall`

**Réalisation :**
1. En A8 : `INDEX`
2. En B8 : `=INDEX(B2:B6;3)`

---

### Exercice 2 — MATCH

**Instructions :** Trouver la position de `E004` dans la colonne ID.

**Formule :** `=EQUIV(A10;A2:A6;0)` → `4`

**Réalisation :**
1. En A10 : `E004`
2. En B10 : `=EQUIV(A10;A2:A6;0)`

---

### Exercice 3 — INDEX + MATCH

**Instructions :** À partir de E004, retrouver le nom.

**Formule :** `=INDEX(B2:B6;EQUIV(A12;A2:A6;0))`

**Réalisation :**
1. En A12 : `E004`
2. En B12 : `=INDEX(B2:B6;EQUIV(A12;A2:A6;0))` → `Cheikh Ba`

---

### Exercice 4 — Plusieurs informations

**Instructions :** À partir de E004, retrouver :
- Nom : `=INDEX(B2:B6;EQUIV(A14;A2:A6;0))`
- Département : `=INDEX(C2:C6;EQUIV(A14;A2:A6;0))`
- Salaire : `=INDEX(D2:D6;EQUIV(A14;A2:A6;0))`

---

### Comparaison VLOOKUP vs INDEX + MATCH

| Critère | VLOOKUP | INDEX + MATCH |
|---------|---------|---------------|
| Facilité | Simple à écrire | Plus complexe |
| Recherche exacte | Oui | Oui |
| Recherche vers la gauche | Non | Oui |
| Dépendance au numéro de colonne | Oui | Non |
| Flexibilité | Moins flexible | Très flexible |

---

## Mini-projet — Base RH

### Étape 1 — Base des employés
Créer une feuille **"Employes"** avec 100 employés.

### Étape 2 — Interface de recherche
Créer une feuille **"Recherche_RH"** avec INDEX + MATCH.

### Challenge
Recherche par Nom → ID.

---

## Points de friction

| Problème | Solution |
|----------|----------|
| #N/A avec MATCH | Vérifier que la valeur existe et que le type est 0 |
| #REF! avec INDEX | Vérifier que la position est dans la plage |
| Résultat faux | Vérifier que les plages sont bien alignées |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris