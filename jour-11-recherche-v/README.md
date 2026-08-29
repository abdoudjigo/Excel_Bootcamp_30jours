# Jour 11 : RECHERCHEV (VLOOKUP)

## Objectifs
- Comprendre l'utilité de RECHERCHEV
- Maîtriser les 4 arguments de la fonction
- Différencier recherche exacte et approximative
- Construire un catalogue de produits avec recherche automatique

---

## Partie théorique

### 1. À quoi sert RECHERCHEV ?
**Réponse :** RECHERCHEV (VLOOKUP) permet de **chercher une valeur dans la première colonne d'un tableau** et de renvoyer une valeur dans la même ligne, à partir d'une colonne spécifiée.

### 2. Quels sont les 4 arguments principaux de RECHERCHEV ?
**Réponse :** 
| Argument | Description |
|----------|-------------|
| **Valeur_cherchée** | Ce qu'on cherche (ex: P001) |
| **Table_matrice** | Le tableau dans lequel on cherche |
| **No_col_index** | Le numéro de la colonne à renvoyer (1, 2, 3...) |
| **Valeur_proche** | VRAI = recherche approximative, FAUX = recherche exacte |

### 3. Que représente le numéro d'index de colonne ?
**Réponse :** C'est la position de la colonne dans le tableau. Ex: si le tableau a 4 colonnes (Product_ID, Produit, Prix, Stock), le numéro 3 renvoie la colonne Prix.

### 4. Quelle est la différence entre une recherche exacte et approximative ?
**Réponse :** 
- **Exacte (FAUX)** : cherche la valeur exacte. Utilisée pour les identifiants.
- **Approximative (VRAI)** : trouve la valeur la plus proche (les données doivent être triées). Utilisée pour des seuils (ex: tranches de notes).

### 5. Pourquoi la valeur recherchée doit-elle se trouver dans la première colonne de la table ?
**Réponse :** RECHERCHEV ne cherche **que dans la première colonne** du tableau. C'est une limitation de la fonction.

### 6. Que se passe-t-il si Excel ne trouve pas la valeur recherchée ?
**Réponse :** Excel retourne l'erreur `#N/A` (Non disponible).

---

## Partie pratique

### Exercice 1 — Première recherche

**Instructions :**
1. Créer une feuille **"Pratique_VLOOKUP"**
2. Saisir le tableau des produits :

| Product_ID | Produit | Prix |
|------------|---------|------|
| P001 | Ordinateur | 450000 |
| P002 | Souris | 15000 |
| P003 | Clavier | 25000 |
| P004 | Écran | 120000 |
| P005 | Casque | 30000 |

3. Dans une autre zone (ex: A10), saisir `P003`
4. En B10 : `=RECHERCHEV(A10;A2:C6;2;FAUX)` → retourne `Clavier`
5. En C10 : `=RECHERCHEV(A10;A2:C6;3;FAUX)` → retourne `25000`

---

### Exercice 2 — Recherche exacte

**Instructions :**
1. Rechercher `P004` → retourne `Écran`
2. Rechercher `P999` → retourne `#N/A`

**Question : Pourquoi une recherche exacte est-elle généralement plus adaptée avec des identifiants ?**

**Réponse :** Les identifiants doivent correspondre parfaitement. Une recherche approximative pourrait renvoyer un mauvais produit si les données ne sont pas triées.

---

### Exercice 3 — Changer la colonne retournée

**Instructions :**
- `=RECHERCHEV(A10;A2:C6;2;FAUX)` → Produit
- `=RECHERCHEV(A10;A2:C6;3;FAUX)` → Prix

---

### Exercice 4 — Recopier la formule

**Instructions :**
1. Dans A10:A14, saisir : P001, P003, P005, P002, P004
2. En B10 : `=RECHERCHEV(A10;A2:C6;2;FAUX)`
3. Étirer vers le bas
4. Observer que les références du tableau ne bougent pas (les bloquer avec `$` si besoin)

---

## Mini-projet — Catalogue de produits

### Étape 1 — Créer le catalogue
1. Créer une feuille **"Catalogue"**
2. Générer 50 produits

### Étape 2 — Créer la zone de recherche
1. Créer une feuille **"Recherche_Produit"**
2. L'utilisateur saisit un Product_ID
3. Les informations s'affichent automatiquement

### Challenge
- Tester avec plusieurs ID dont `P999` pour voir `#N/A`

---

## Points de friction

| Problème | Solution |
|----------|----------|
| #N/A retourné | Vérifier que la valeur existe et que le tableau est bien référencé |
| Résultat d'une autre colonne | Vérifier le numéro d'index de colonne |
| Les références bougent en recopiant | Utiliser `$` pour figer le tableau (ex: `$A$2:$C$6`) |
| Recherche approximative mal utilisée | Utiliser FAUX pour les identifiants |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris