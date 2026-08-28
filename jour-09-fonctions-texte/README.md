# Jour 09 : Fonctions de texte

## Objectifs
- Maîtriser LEFT, RIGHT, MID pour extraire des portions de texte
- Utiliser LEN pour mesurer la longueur des chaînes
- Nettoyer des données avec TRIM
- Concaténer avec CONCAT et TEXTJOIN
- Construire un mini-projet de nettoyage de base clients

---

## Partie théorique

### 1. Quelle différence entre LEFT, RIGHT et MID ?
**Réponse :** 
- **LEFT** : extrait les caractères **depuis le début** (gauche)
- **RIGHT** : extrait les caractères **depuis la fin** (droite)
- **MID** : extrait les caractères **à partir d'une position donnée** (milieu)

### 2. Que renvoie LEN ?
**Réponse :** `LEN` renvoie le **nombre de caractères** dans une chaîne de texte (espaces compris).

### 3. Pourquoi TRIM est-il utile dans une base réelle ?
**Réponse :** `TRIM` supprime les **espaces inutiles** (au début, à la fin et les doubles espaces). Utile pour nettoyer des données saisies manuellement.

### 4. Quelle différence entre CONCAT et TEXTJOIN ?
**Réponse :** 
- **CONCAT** : assemble des textes sans séparateur (ou avec séparateur manuel)
- **TEXTJOIN** : assemble des textes avec un **séparateur personnalisé** et peut ignorer les cellules vides

### 5. Que se passe-t-il lorsqu'on concatène du texte avec des espaces ou des séparateurs ?
**Réponse :** Les espaces et séparateurs doivent être **ajoutés manuellement** dans la formule (ex: `=CONCAT(A2;" ";B2)`).

---

## Partie pratique

### Dataset
1. Créer un fichier `jour09_texte.xlsx`
2. Dans la feuille **"Pratique_Texte"** , saisir les données suivantes :

| A |
|---|
| CLI-2026-0001 |
| CLI-2026-0002 |
| CLI-2026-0003 |

---

### Exercice 1 — LEFT

**Instructions :** Extraire les 3 premiers caractères de `CLI-2026-0001`

**Formule :** `=GAUCHE(A2;3)` → `CLI`

**Réalisation :**
1. En **B2** : `=GAUCHE(A2;3)`
2. Étirer vers le bas

---

### Exercice 2 — RIGHT

**Instructions :** Extraire les 4 derniers caractères de `CLI-2026-0001`

**Formule :** `=DROITE(A2;4)` → `0001`

**Réalisation :**
1. En **C2** : `=DROITE(A2;4)`
2. Étirer vers le bas

---

### Exercice 3 — MID

**Instructions :** Extraire `2026` de `CLI-2026-0001`

**Formule :** `=STXT(A2;5;4)` → `2026`
(compte : C=1, L=2, I=3, -=4, 2=5...)

**Réalisation :**
1. En **D2** : `=STXT(A2;5;4)`
2. Étirer vers le bas

**Question :** Quelle est la différence entre une extraction depuis le début, la fin et le milieu d'un texte ?

**Réponse :** 
- **Début (LEFT)** : on extrait les premiers caractères
- **Fin (RIGHT)** : on extrait les derniers caractères
- **Milieu (MID)** : on extrait à partir d'une position précise

---

### Exercice 4 — LEN

**Instructions :** Calculer le nombre de caractères dans `CLI-2026-0001`

**Formule :** `=NBCAR(A2)` → `13`

**Réalisation :**
1. En **E2** : `=NBCAR(A2)`
2. Étirer vers le bas

**Question :** Est-ce que LEN compte également les tirets et les espaces ?

**Réponse :** Oui, `LEN` compte **tous les caractères** : lettres, chiffres, tirets, espaces, etc.

---

### Exercice 5 — TRIM

**Instructions :** Nettoyer les valeurs suivantes :

| A |
|---|
| "  Awa Ndiaye" |
| "Mamadou Diop   " |
| "   Fatou   Fall   " |

**Formule :** `=SUPPRESPACE(A2)`

**Réalisation :**
1. En **A1** : `"  Awa Ndiaye"`
2. En **A2** : `"Mamadou Diop   "`
3. En **A3** : `"   Fatou   Fall   "`

4. En **B1** : `=SUPPRESPACE(A1)` → `Awa Ndiaye`
5. En **B2** : `=SUPPRESPACE(A2)` → `Mamadou Diop`
6. En **B3** : `=SUPPRESPACE(A3)` → `Fatou Fall`

---

### Exercice 6 — CONCAT

**Instructions :** Utiliser les données :

| Prénom | Nom |
|--------|-----|
| Awa | Ndiaye |
| Mamadou | Diop |
| Fatou | Fall |

**Formule :** `=CONCAT(A2;" ";B2)` → `Awa Ndiaye`

**Réalisation :**
1. En **C2** : `=CONCAT(A2;" ";B2)`
2. Étirer vers le bas

---

### Exercice 7 — TEXTJOIN

**Instructions :** Utiliser les données :

| Ville | Pays | Région |
|-------|------|--------|
| Dakar | Sénégal | Afrique |
| Paris | France | Europe |

**Formule :** `=JOINDRE.TEXTE(" - ";VRAI;A2;C2;E2)` → `Dakar - Sénégal - Afrique`

**Réalisation :**
1. En **F2** : `=JOINDRE.TEXTE(" - ";VRAI;A2;C2;E2)`
2. Étirer vers le bas

---

## Mini-projet — Nettoyage d'une base clients

### Contexte
Une entreprise a 100 clients avec des données incohérentes. Tu dois les nettoyer.

### Dataset
Créer un fichier avec les colonnes :

| Client_ID | Prenom | Nom | Email | Telephone | Ville | Pays |
|-----------|--------|-----|-------|-----------|-------|------|

### Étapes

#### Étape 1 — Nettoyer les noms
- **Prenom_Propre** : `=SUPPRESPACE(B2)`
- **Nom_Propre** : `=SUPPRESPACE(C2)`

#### Étape 2 — Créer le nom complet
- **Nom_Complet** : `=CONCAT(D2;" ";E2)`

#### Étape 3 — Extraire les informations du Client_ID
- **Prefixe** : `=GAUCHE(A2;3)`
- **Annee** : `=STXT(A2;5;4)`
- **Numero** : `=DROITE(A2;4)`

#### Étape 4 — Vérifier les identifiants
- **Longueur_ID** : `=NBCAR(A2)`

#### Étape 5 — Construire une localisation
- **Localisation** : `=JOINDRE.TEXTE(" - ";VRAI;H2;I2)` (Ville et Pays)

### Résultat attendu

| Client_ID | Prenom_Propre | Nom_Propre | Nom_Complet | Prefixe | Annee | Numero | Longueur_ID | Localisation |
|-----------|---------------|------------|-------------|---------|-------|--------|-------------|--------------|
| CLI-2026-0001 | Awa | Ndiaye | Awa Ndiaye | CLI | 2026 | 0001 | 13 | Dakar - Sénégal |

---

### Challenge
Certains identifiants peuvent avoir une structure différente (ex: CLI-26-0001 ou CLIENT-2026-001). Utilise `LEN` pour les détecter.

---

## Points de friction

| Problème | Solution |
|----------|----------|
| CONCAT sans espace | Ajouter `" "` entre les références |
| MID avec position incorrecte | Compter les caractères un par un |
| TRIM ne supprime pas les espaces insécables | Utiliser SUBSTITUE ou nettoyer manuellement |
| TEXTJOIN avec cellules vides | Utiliser VRAI pour ignorer les cellules vides |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris