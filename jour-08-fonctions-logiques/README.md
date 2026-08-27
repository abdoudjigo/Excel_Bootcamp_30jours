# Jour 08 : Fonctions logiques

## Objectifs
- Comprendre les conditions logiques (VRAI/FAUX)
- Maîtriser IF, IFS, AND, OR, NOT
- Savoir utiliser IFERROR pour gérer les erreurs
- Construire un système d'admission automatisé

---

## Partie théorique

### 1. Qu'est-ce qu'une condition logique ?
**Réponse :** Une condition logique est une expression qui renvoie **VRAI** ou **FAUX** (ex: `A1>=10`). Elle permet de tester si une situation est vraie ou fausse.

### 2. Quelle est la différence entre IF et IFS ?
**Réponse :** 
- **IF** : teste **une seule condition** (ex: `=SI(A1>=10;"Admis";"Non admis")`)
- **IFS** : teste **plusieurs conditions** (ex: `=SI.CONDITIONS(A1>=16;"Excellent";A1>=14;"Bien")`)

### 3. Quelle différence entre AND et OR ?
**Réponse :** 
- **AND** : toutes les conditions doivent être **VRAI** (ET logique).
- **OR** : au moins une condition doit être **VRAI** (OU logique).

### 4. Que fait NOT ?
**Réponse :** `NOT` inverse une condition logique.
- `NOT(VRAI)` → FAUX
- `NOT(FAUX)` → VRAI

### 5. Pourquoi utiliser IFERROR ?
**Réponse :** Pour remplacer les messages d'erreur (ex: `#DIV/0!`) par un message personnalisé, ce qui rend le tableau plus lisible et professionnel.

---

## Partie pratique

### Dataset
1. Créer un nouveau fichier `jour08_logiques.xlsx`
2. Copier les **1 000 étudiants** depuis le dataset du Jour 3
3. Créer une feuille **"Pratique_Logique"** avec toutes les données

---

### Exercice 1 — IF

**Instructions :** Ajouter une colonne **"Resultat"** après Python.

**Règle :**
- Python >= 10 → **Admis**
- Sinon → **Non admis**

**Formule :**
```
=SI(H2>=10;"Admis";"Non admis")
```

**Réalisation :**
1. En **I1** (ou colonne suivante) : tape `Resultat`
2. En **I2** : `=SI(H2>=10;"Admis";"Non admis")`
3. Étirer vers le bas

---

### Exercice 2 — AND

**Instructions :** Ajouter une colonne **"Profil_Eligible"**.

**Règle :** Un étudiant est éligible si :
- Math >= 12
- Python >= 12
- Presence >= 80%

**Formule :**
```
=SI(ET(F2>=12;H2>=12;J2>=0,8);"Eligible";"Non eligible")
```

**Réalisation :**
1. En colonne suivante : tape `Profil_Eligible`
2. Formule avec AND
3. Étirer vers le bas

---

### Exercice 3 — OR

**Instructions :** Ajouter une colonne **"Alerte"**.

**Règle :** Un étudiant doit être signalé si :
- Math < 10 **OU** Python < 10

**Formule :**
```
=SI(OU(F2<10;H2<10);"A surveiller";"RAS")
```

**Réalisation :**
1. En colonne suivante : tape `Alerte`
2. Formule avec OR
3. Étirer vers le bas

---

### Exercice 4 — NOT

**Instructions :** Ajouter une colonne **"Statut_Filiere"**.

**Règle :**
- Si **n'est pas** dans Data → "Hors Data"
- Sinon → "Data"

**Formule :**
```
=SI(NON(E2="Data");"Hors Data";"Data")
```

**Réalisation :**
1. En colonne suivante : tape `Statut_Filiere`
2. Formule avec NOT
3. Étirer vers le bas

**Objectif :** Comprendre que `NON(VRAI)` → FAUX et `NON(FAUX)` → VRAI.

---

### Exercice 5 — IFS

**Instructions :** Ajouter une colonne **"Niveau"** basée sur Python.

**Règle :**

| Note Python | Niveau |
|-------------|--------|
| >= 16 | Excellent |
| >= 14 | Très bien |
| >= 12 | Bien |
| >= 10 | Passable |
| < 10 | Insuffisant |

**Formule :**
```
=SI.CONDITIONS(H2>=16;"Excellent";H2>=14;"Très bien";H2>=12;"Bien";H2>=10;"Passable";VRAI;"Insuffisant")
```

**⚠️ Attention :** L'ordre des conditions est important. Excel s'arrête à la première condition vraie.

**Réalisation :**
1. En colonne suivante : tape `Niveau`
2. Formule avec IFS
3. Étirer vers le bas

---

### Exercice 6 — IFERROR

**Instructions :** Dans une feuille séparée **"Erreurs"**, créer :

| Total | Nombre | Moyenne |
|-------|--------|---------|
| 100 | 10 | |
| 200 | 20 | |
| 150 | 0 | |
| 300 | 15 | |

**Formule sans IFERROR :** `=A2/B2` → erreur `#DIV/0!` pour la ligne 3

**Formule avec IFERROR :**
```
=SIERREUR(A2/B2;"Non disponible")
```

**Question : Quelle différence entre corriger une erreur et simplement la masquer avec IFERROR ?**

**Réponse :** 
- **Corriger** : résoudre la cause du problème (ex: éviter de diviser par 0).
- **Masquer** : afficher un message personnalisé à la place de l'erreur. Utile pour la lisibilité, mais il faut quand même comprendre pourquoi l'erreur existe.

---

## Mini-projet — Système d'admission

### Contexte
Une école automatise sa décision d'admission à partir de 3 critères.

### Étape 1 — Créer la feuille

1. Créer une feuille **"Systeme_Admission"**
2. Copier uniquement les colonnes :
   - A : ID
   - B : Nom
   - E : Filiere
   - F : Math
   - H : Python
   - J : Presence
3. Ajouter 3 colonnes vides : Decision, Mention, Alerte

---

### Étape 2 — Décision d'admission

**Règles :**
- **Admis** si : Math >= 12 ET Python >= 12 ET Presence >= 80%
- **Admis sous condition** si : Math >= 10 ET Python >= 10 (mais pas toutes les conditions ci-dessus)
- **Refusé** dans tous les autres cas

**Formule :**
```
=SI(ET(F2>=12;H2>=12;J2>=0,8);"Admis";
   SI(ET(F2>=10;H2>=10);"Admis sous condition";"Refusé"))
```

---

### Étape 3 — Attribuer une mention (IFS)

**Règle :** Basée sur Python

```
=SI.CONDITIONS(H2>=16;"Excellent";
               H2>=14;"Très bien";
               H2>=12;"Bien";
               H2>=10;"Passable";
               VRAI;"Insuffisant")
```

---

### Étape 4 — Créer une alerte (IF + OR)

**Règle :**
- **A surveiller** si : Math < 10 OU Python < 10 OU Presence < 70%
- **RAS** sinon

```
=SI(OU(F2<10;H2<10;J2<0,7);"A surveiller";"RAS")
```

---

### Étape 5 — Utiliser NOT

**Règle :**
- Si **n'est pas** dans Data → "Autre filière"
- Sinon → "Data"

```
=SI(NON(E2="Data");"Autre filière";"Data")
```

---

### Résultat attendu

| ID | Nom | Decision | Mention | Alerte |
|----|-----|----------|---------|--------|
| ST0001 | Awa Ndiaye | Admis | Très bien | RAS |
| ST0002 | ... | Refusé | Passable | A surveiller |

---

## Points de friction

| Problème | Solution |
|----------|----------|
| IFS ne fonctionne pas | Vérifier l'ordre des conditions (du plus restrictif au moins restrictif) |
| Résultat #N/A avec IFS | Ajouter VRAI en dernière condition pour capturer tous les autres cas |
| AND/OR avec plusieurs conditions | Bien placer les parenthèses |
| IFERROR masque tout | Ne pas utiliser pour masquer des erreurs sans les comprendre |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris