# Jour 10 : Fonctions de date

## Objectifs
- Comprendre la gestion des dates dans Excel
- Maîtriser TODAY, NOW, YEAR, MONTH, DAY
- Calculer des durées avec DATEDIF
- Construire un système de gestion des congés

---

## Partie théorique

### 1. Quelle différence entre TODAY() et NOW() ?
**Réponse :** 
- **TODAY()** : renvoie la **date actuelle** (sans l'heure)
- **NOW()** : renvoie la **date et l'heure** actuelles

### 2. Que renvoient YEAR, MONTH et DAY ?
**Réponse :** 
- **YEAR** : extrait l'année d'une date
- **MONTH** : extrait le mois d'une date (1 à 12)
- **DAY** : extrait le jour d'une date (1 à 31)

### 3. Pourquoi Excel peut-il effectuer des calculs avec des dates ?
**Réponse :** Excel stocke les dates sous forme de **nombres** (le nombre de jours depuis le 01/01/1900). Donc on peut additionner, soustraire et comparer des dates.

### 4. À quoi sert DATEDIF ?
**Réponse :** `DATEDIF` calcule la **différence entre deux dates** en jours, mois ou années.

### 5. Quelle différence entre une date de début, une date de fin et une durée ?
**Réponse :** 
- **Date de début** : point de départ
- **Date de fin** : point d'arrivée
- **Durée** : la différence entre les deux

---

## Partie pratique

### Exercice 1 — Date actuelle

**Instructions :**
1. Créer une feuille **"Pratique_Dates"**
2. En **A1** : `=AUJOURDHUI()` → affiche la date du jour
3. En **A2** : `=MAINTENANT()` → affiche la date et l'heure

**Question :** Quelle différence observes-tu entre les deux ?

**Réponse :** `AUJOURDHUI()` affiche seulement la date, `MAINTENANT()` affiche la date et l'heure.

---

### Exercice 2 — Extraire une date

**Instructions :**
1. En **A4** : saisir `15/08/2026`
2. En **B4** : `=ANNEE(A4)` → 2026
3. En **C4** : `=MOIS(A4)` → 8
4. En **D4** : `=JOUR(A4)` → 15

---

### Exercice 3 — Calculer une durée

**Instructions :**
1. En **A6** : saisir `01/08/2026` (Date début)
2. En **B6** : saisir `15/08/2026` (Date fin)

3. En **C6** : `=DATEDIF(A6;B6;"d")` → 14 jours
4. En **D6** : `=DATEDIF(A6;B6;"m")` → 0 mois (moins d'un mois)
5. En **E6** : `=DATEDIF(A6;B6;"y")` → 0 ans (moins d'un an)

**Explication des paramètres :**
| Paramètre | Signification |
|-----------|---------------|
| "d" | Jours complets |
| "m" | Mois complets |
| "y" | Années complètes |

---

## Mini-projet — Système de gestion des congés

### Contexte
Une entreprise suit les congés de ses employés.

### Instructions
1. Créer une feuille **"Conges"**
2. Saisir 20 employés avec les colonnes suivantes :

| Colonne | Description |
|---------|-------------|
| A | ID |
| B | Nom |
| C | Date_embauche |
| D | Debut_conge |
| E | Fin_conge |

### Exemple de données (5 lignes) :

| ID | Nom | Date_embauche | Debut_conge | Fin_conge |
|----|-----|---------------|-------------|-----------|
| EMP001 | Awa Ndiaye | 12/03/2023 | 10/08/2026 | 20/08/2026 |
| EMP002 | Mamadou Diop | 05/06/2022 | 01/09/2026 | 15/09/2026 |
| EMP003 | Fatou Fall | 15/01/2024 | 05/10/2026 | 12/10/2026 |
| EMP004 | Ibrahima Sarr | 20/11/2021 | 15/07/2026 | 25/07/2026 |
| EMP005 | Astou Ndiaye | 08/09/2023 | 20/11/2026 | 30/11/2026 |

### Étape 1 — Durée du congé
- **Colonne F** : `Duree_conge`
- Formule : `=DATEDIF(D2;E2;"d")`

### Étape 2 — Extraire les informations
- **Colonne G** : `Annee_conge` → `=ANNEE(D2)`
- **Colonne H** : `Mois_conge` → `=MOIS(D2)`
- **Colonne I** : `Jour_conge` → `=JOUR(D2)`

### Étape 3 — Ancienneté
- **Colonne J** : `Anciennete`
- Formule : `=DATEDIF(C2;AUJOURDHUI();"y")`

### Étape 4 — Date du jour
- En **K1** : `Date du jour`
- En **L1** : `=AUJOURDHUI()`
- En **K2** : `Dernière mise à jour`
- En **L2** : `=MAINTENANT()`

### 🌟 Challenge — Statut du congé
- **Colonne K** : `Statut`
- Formule :
```
=SI(AUJOURDHUI()<D2;"À venir";SI(AUJOURDHUI()<=E2;"En cours";"Terminé"))
```

### Résultat attendu

| ID | Nom | Date_embauche | Debut_conge | Fin_conge | Duree | Annee | Mois | Anciennete | Statut |
|----|-----|---------------|-------------|-----------|-------|-------|------|------------|--------|
| EMP001 | Awa Ndiaye | 12/03/2023 | 10/08/2026 | 20/08/2026 | 10 | 2026 | 8 | 3 | En cours |

---

## Points de friction

| Problème | Solution |
|----------|----------|
| DATEDIF ne fonctionne pas en anglais | Utiliser `DATEDIF` (pas de traduction) |
| Date affichée en nombre | Appliquer le format Date |
| DATEDIF avec date de fin < date de début | Retourne `#NOMBRE!` → vérifier les dates |
| AUJOURDHUI() ne s'actualise pas | Le calcul se fait automatiquement à l'ouverture |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris