# Jour 03 : Tri et filtres

## Objectifs
- Maîtriser les tris simples et personnalisés
- Savoir utiliser les filtres simples, multiples et personnalisés
- Appliquer ces compétences sur une base de 1000 étudiants

---

## Partie théorique

### 1. Quelle est la différence entre trier et filtrer ?
**Réponse :** 
- **Trier** = réorganiser l'ordre des lignes selon une ou plusieurs colonnes (ex: du plus grand au plus petit).
- **Filtrer** = afficher uniquement les lignes qui répondent à un critère, les autres sont cachées (pas supprimées).

### 2. Que se passe-t-il lorsqu'on trie une seule colonne au lieu de tout le tableau ?
**Réponse :** Les données deviennent incohérentes. Les valeurs de la colonne triée ne correspondent plus aux autres colonnes de la même ligne. Il faut toujours sélectionner tout le tableau avant de trier.

### 3. Quelle est la différence entre un filtre simple et un filtre utilisant plusieurs critères ?
**Réponse :** 
- **Filtre simple** : un seul critère sur une colonne (ex: Ville = Dakar).
- **Filtres multiples** : plusieurs critères sur plusieurs colonnes (ex: Ville = Dakar ET Math >= 10). Excel combine les filtres avec un "ET" logique.

### 4. À quoi sert un filtre personnalisé ?
**Réponse :** Permet d'appliquer des conditions plus complexes : 
- Entre deux valeurs
- Supérieur à / Inférieur à
- Commence par / Contient (pour le texte)
- Dates (avant/après)

### 5. Dans quel cas utilise-t-on un tri sur plusieurs colonnes ?
**Réponse :** Quand on veut classer par un premier critère, puis par un second critère à l'intérieur du premier (ex: trier par Filière, puis par Note décroissante dans chaque filière).

---

## Partie pratique

### Exercice 1 — Trier les données

**Instructions :** Effectue les tris suivants sur le fichier `student_data_1000.xlsx`.

1. **Trier par Math** du plus grand au plus petit.
2. **Trier par Nom** de A à Z.
3. **Trier par Date_inscription** de la plus ancienne à la plus récente.

**Réalisations :** 
- Tri 1 : Sélectionner tout le tableau → Données → Trier → Colonne Math → Décroissant
- Tri 2 : Sélectionner tout le tableau → Données → Trier → Colonne Nom → Croissant
- Tri 3 : Sélectionner tout le tableau → Données → Trier → Colonne Date_inscription → Du plus ancien au plus récent

**Point de friction :** Il faut toujours sélectionner **TOUT** le tableau avant de trier, sinon les lignes sont désynchronisées.

---

### Exercice 2 — Utiliser les filtres

**Instructions :** Trouve les étudiants répondant aux critères suivants. Enlève le filtre avant chaque nouvelle recherche.

**Résultats obtenus :**

| Filtre | Nombre d'étudiants |
|--------|-------------------|
| Filière = Data | **260** |
| Presence > 90 % | **695** |
| Python < 10 | **178** |

**Réalisations :**
1. Filtrer colonne Filière → sélectionner "Data" → 260 enregistrements
2. Filtrer colonne Presence → Filtres numériques → Supérieur à → 90 → 695 enregistrements
3. Filtrer colonne Python → Filtres numériques → Inférieur à → 10 → 178 enregistrements

---

### Exercice 3 — Filtres multiples

**Instructions :** Trouve les étudiants qui respectent simultanément les conditions suivantes.

**Résultats obtenus :**

| Cas | Condition | Nombre d'étudiants |
|-----|-----------|-------------------|
| 1 | Filiere = Data ET Presence > 90 % | **18** |
| 2 | Python >= 15 ET Excel >= 15 | **220** |
| 3 | Ville = Dakar ET Math < 10 | **39** |

**Réalisations :**
1. Filtrer Filière = Data + Filtrer Presence > 90% → 18 enregistrements
2. Filtrer Python >= 15 + Filtrer Excel >= 15 → 220 enregistrements
3. Filtrer Ville = Dakar + Filtrer Math < 10 → 39 enregistrements

**Observation :** Excel combine les filtres sur plusieurs colonnes avec un **ET logique** (toutes les conditions doivent être vraies).

---

### Exercice 4 — Filtres personnalisés

**Instructions :** Utilise les filtres numériques pour trouver :

**Résultats obtenus :**

| Filtre | Nombre d'étudiants |
|--------|-------------------|
| Math entre 10 et 15 | **488** |
| Presence entre 80 % et 90 % | **338** |
| Frais_payes > 100 000 FCFA | **262** |

**Réalisations :**
1. Filtrer Math → Filtres numériques → Entre → 10 et 15 → 488 enregistrements
2. Filtrer Presence → Filtres numériques → Entre → 80 et 90 → 338 enregistrements
3. Filtrer Frais_payes → Filtres numériques → Supérieur à → 100000 → 262 enregistrements

---

### Exercice 5 — Trier selon plusieurs colonnes

**Instructions :** Effectue un tri personnalisé à plusieurs niveaux.

**Classement 1 :**
1. Trier par **Filiere** de A à Z
2. Puis par **Python** du plus grand au plus petit

**Classement 2 :**
1. Trier par **Ville**
2. Puis par **Presence** décroissante
3. Puis par **Math** décroissante

**Réalisations :**
- Données → Trier → Ajouter un niveau → Définir les colonnes et ordres

** Point de friction :** Plusieurs tris simples successifs ne donnent pas le même résultat qu'un tri personnalisé. Le dernier tri simple efface les précédents.

---

## Mini-projet — Identifier les meilleurs étudiants

**Contexte :** École qui veut identifier rapidement ses étudiants les plus performants.

### Analyse 1 — Top 10 étudiants Python

**Objectif :** Trouver les 10 meilleurs étudiants en Python.

**Résultat :** 10 étudiants ont **20/20** en Python.

**Liste des 10 meilleurs :**
| # | Nom | Note Python |
|---|-----|-------------|
| 1 | Sokhna Diallo | 20 |
| 2 | Abdoulaye Diallo | 20 |
| 3 | Mamadou Ba | 20 |
| 4 | Ibrahima Sarr | 20 |
| 5 | Astou Ndiaye | 20 |
| 6 | Coumba Faye | 20 |
| 7 | Ousmane Ndiaye | 20 |
| 8 | Ibrahima Kane | 20 |
| 9 | Alioune Fall | 20 |
| 10 | *(à vérifier - doublon possible)* | 20 |

**Réalisation :** Trier par Python décroissant → prendre les 10 premiers.

---

### Analyse 2 — Étudiants réguliers

**Objectif :** Trouver les étudiants ayant : **Presence >= 90 % ET Math >= 15 ET Python >= 15**

**Résultat : 54 étudiants**

**Réalisation :** Filtrer Presence >= 90 + Math >= 15 + Python >= 15

---

### Analyse 3 — Étudiants à accompagner

**Objectif :** Identifier les étudiants ayant : **Math < 10 OU Python < 10**

**Résultat : 84 étudiants** (Math < 10 OU Python < 10)

**Réalisation :** 
- Filtrer Math < 10 → noter les étudiants
- Enlever le filtre
- Filtrer Python < 10 → noter les étudiants
- Fusionner les deux listes

** Point de friction :** Le OU logique est impossible avec les filtres standards. Il faut faire deux opérations séparées.

---

### Analyse 4 — Classement par filière

**Objectif :** Pour chaque filière, identifier les **3 meilleurs en Python**.

**Résultats :**

| Filière | Top 3 (Python) |
|---------|----------------|
| **Cybersécurité** | Sokhna Diallo, Abdoulaye Diallo, Mamadou Ba |
| **Data** | Ousmane Ndiaye, Mamadou Seck, Alioune Fall |
| **Développement** | Coumba Faye, *(2e à vérifier)*, Sokhna Diop |
| **IA** | Ibrahima Sarr, Alioune Fall, Babacar Cisse |

**Réalisation :** 
1. Filtrer la filière
2. Trier par Python décroissant
3. Prendre les 3 premiers
4. Enlever le filtre
5. Répéter pour chaque filière

---

### Challenge — Top 20 performance globale

**Question :** Sans utiliser de formule (sauf pour la moyenne), comment identifier les 20 étudiants ayant la meilleure performance globale ?

**Résultat :** 20 étudiants avec des moyennes entre 20 et 18,875.

**Top 20 :**
| # | Nom | Moyenne |
|---|-----|---------|
| 1 | Babacar Fall | 20 |
| 2 | Fatou Fall | 20 |
| 3 | Khadija Gueye | 20 |
| 4 | Mariama Sarr | 20 |
| 5 | Awa Diallo | 20 |
| 6 | Pape Gueye | 19,995 |
| 7 | Sokhna Ndour | 19,85 |
| 8 | Astou Seck | 19,81 |
| 9 | Khadija Faye | 19,7825 |
| 10 | Ousmane Ndour | 19,6675 |
| 11 | Rokhaya Ndour | 19,6675 |
| 12 | Mariama Gueye | 19,6275 |
| 13 | Ibrahima Kane | 19,4125 |
| 14 | Ousmane Ndiaye | 19,295 |
| 15 | Coumba Sy | 19,1925 |
| 16 | Mamadou Sow | 19,1 |
| 17 | Abdoulaye Ndour | 19,0675 |
| 18 | Abdoulaye Sarr | 19,055 |
| 19 | Pape Sow | 19 |
| 20 | Mamadou Ba | 18,9575 |

**Réalisation :** 
1. Créer une colonne `Moyenne` = MOYENNE(Math, Excel, Python, Statistiques)
2. Trier par `Moyenne` décroissant
3. Prendre les 20 premiers

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Trier une seule colonne | Sélectionner TOUT le tableau avant de trier |
| Filtres multiples = ET logique | Pour un OU, il faut faire plusieurs filtres séparés |
| Plusieurs tris simples successifs | Utiliser un tri personnalisé à plusieurs niveaux |
| Oublier d'enlever un filtre | Toujours réinitialiser les filtres avant une nouvelle recherche |
| Colonnes avec des pourcentages | Utiliser les valeurs décimales (0,9 = 90%) pour les filtres |

---

## Statut
✅ Théorie faite  
✅ Exercices faits  
✅ Mini-projet fait  
✅ Points de friction compris