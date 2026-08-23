# Jour 05 : Mise en forme conditionnelle

## Objectifs
- Comprendre le principe de la mise en forme conditionnelle
- Maîtriser les règles simples (couleurs, barres, icônes)
- Savoir utiliser les échelles de couleurs et barres de données
- Construire un tableau de suivi visuel professionnel

---

## Partie théorique

### 1. Qu'est-ce que la mise en forme conditionnelle ?
**Réponse :** La mise en forme conditionnelle est un outil qui applique automatiquement un format (couleur, icône, barre) à une cellule en fonction de sa valeur. Elle permet de visualiser rapidement les tendances et les anomalies.

### 2. Quelle différence entre une mise en forme normale et une mise en forme conditionnelle ?
**Réponse :** 
- **Mise en forme normale** : statique, appliquée une fois et ne change pas.
- **Mise en forme conditionnelle** : dynamique, s'adapte automatiquement quand la valeur change.

### 3. Une règle modifie-t-elle la valeur de la cellule ou uniquement son apparence ?
**Réponse :** La mise en forme conditionnelle ne modifie **que l'apparence** de la cellule. La valeur reste inchangée.

### 4. Dans quel cas utiliser une barre de données plutôt qu'une échelle de couleurs ?
**Réponse :** 
- **Barre de données** : pour comparer des valeurs sur une même colonne (la longueur de la barre donne une idée immédiate de l'ordre de grandeur).
- **Échelle de couleurs** : pour identifier rapidement les valeurs faibles, moyennes, élevées (dégradé de couleurs).

### 5. Quel est le risque d'utiliser trop de couleurs ou trop d'icônes ?
**Réponse :** 
- Crée de la confusion et du "bruit" visuel.
- Rend le tableau difficile à lire et contre-productif.
- L'utilisateur passe plus de temps à décoder le visuel qu'à analyser les données.

---

## Partie pratique

### Dataset
1. Créer un nouveau fichier `jour05_mise_en_forme.xlsx`
2. Créer une feuille **"Notes"**
3. Copier **50 à 100 étudiants** depuis le dataset du Jour 3 (`student_data_1000.xlsx`)
   - Sélectionner 50 à 100 lignes (ex: A1:L101)
   - Copier → Coller dans la feuille "Notes"

---

### Exercice 1 — Créer des règles simples

**Instructions :** Appliquer des règles sur les colonnes de notes (Math, Excel, Python, Statistiques)

1. **Note < 10** → fond **rouge clair**, texte **rouge foncé** (étudiants en difficulté)
2. **Note >= 15** → fond **vert clair**, texte **vert foncé** (bonnes performances)

**Réalisation :**
1. Sélectionner la colonne **Math** (F2:F101)
2. Accueil → Mise en forme conditionnelle → Nouvelle règle
3. **Règle 1** : "Format UNIQUEMENT les cellules qui contiennent" → Valeur de cellule < 10 → Format rouge
4. **Règle 2** : "Format UNIQUEMENT les cellules qui contiennent" → Valeur de cellule >= 15 → Format vert
5. Répéter pour **Excel** (colonne G), **Python** (colonne H), **Statistiques** (colonne I)

**Question : Si la note passe de 9 à 16, que devient la mise en forme ?**
**Réponse :** La mise en forme change automatiquement. La cellule passe du rouge (difficulté) au vert (bonne performance) car la mise en forme conditionnelle est dynamique.

---

### Exercice 2 — Échelle de couleurs

**Instructions :** Sur la colonne **Presence** (colonne J), appliquer une échelle de couleurs.

**Réalisation :**
1. Sélectionner la colonne **Presence** (J2:J101)
2. Accueil → Mise en forme conditionnelle → Échelles de couleurs
3. Choisir un dégradé (ex: Rouge → Jaune → Vert)

**Question : Sans lire précisément les chiffres, quelles informations peux-tu déjà observer ?**
**Réponse :** 
- Les cellules rouges = présence faible
- Les cellules jaunes = présence moyenne
- Les cellules vertes = présence élevée
- On identifie immédiatement les tendances sans lire les chiffres.

---

### Exercice 3 — Barres de données

**Instructions :** Sur la colonne **Python** (colonne H), appliquer des barres de données.

**Réalisation :**
1. Sélectionner la colonne **Python**
2. Accueil → Mise en forme conditionnelle → Barres de données
3. Choisir une couleur de barre

**Question : Quel étudiant semble avoir la meilleure note avant même de lire les valeurs ?**
**Réponse :** Celui dont la barre est la plus longue. La barre de données donne une comparaison visuelle immédiate.

---

### Exercice 4 — Jeux d'icônes

**Instructions :** Appliquer un jeu d'icônes sur une colonne de notes au choix (ex: Math).

**Réalisation :**
1. Sélectionner la colonne **Math**
2. Accueil → Mise en forme conditionnelle → Jeux d'icônes
3. Choisir : 3 feux tricolores (vert/jaune/rouge) ou 3 flèches
4. Modifier les règles : 
   - ≥ 15 → vert (performance élevée)
   - 10 à 14,99 → jaune (moyen)
   - < 10 → rouge (faible)

**Question : Dans quel cas les icônes permettent-elles une lecture plus rapide qu'une simple couleur ?**
**Réponse :** 
- Quand il y a plusieurs catégories à distinguer (ex: 3 niveaux ou plus)
- Quand le tableau est dense et qu'il faut repérer les anomalies d'un coup d'œil
- Quand les utilisateurs sont habitués aux systèmes de notation (ex: feux tricolores)

---

## Mini-projet — Tableau de suivi des notes

**Contexte :** Tableau pour un responsable pédagogique.

### À faire :

1. **Créer une feuille "Suivi_Notes"**
2. **Copier les mêmes 50 à 100 étudiants** avec toutes leurs colonnes

### Règles à appliquer :

#### 1. Notes (Math, Excel, Python, Statistiques)
| Condition | Format |
|-----------|--------|
| < 10 | Fond rouge clair + texte rouge foncé |
| 10 à 14,99 | Fond jaune clair + texte orange foncé |
| >= 15 | Fond vert clair + texte vert foncé |

#### 2. Présence (colonne Presence)
- Échelle de couleurs (Rouge → Jaune → Vert)

#### 3. Une matière au choix (ex: Python)
- Barres de données pour comparer les performances

#### 4. Indicateur global (ex: Math)
- Jeu d'icônes (3 feux tricolores)

### Challenge

**Question :** Ton tableau contient maintenant des couleurs, des barres et des icônes. Est-ce que chaque élément visuel apporte réellement une information ?

**Réflexion :** 
- La mise en forme doit **réduire l'effort de lecture**, pas ajouter du bruit.
- Si plusieurs formats se superposent sur les mêmes colonnes, ils deviennent redondants.
- Un Data Analyst doit toujours se demander : "Est-ce que ce visuel aide à comprendre ou il distrait ?"

**Bonnes pratiques :**
- Éviter de mettre des barres ET des icônes sur la même colonne
- Choisir un format par colonne (soit couleur, soit barres, soit icônes)
- Garder le tableau lisible

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Les règles s'appliquent mal | Vérifier que la plage sélectionnée est la bonne |
| Les couleurs ne sont pas cohérentes | Utiliser la même palette pour les mêmes conditions |
| La règle s'applique à tout le tableau | Utiliser des plages relatives (ex: $F$2:$F$101) |
| Trop de règles sur une même cellule | Gérer les règles dans le gestionnaire pour définir l'ordre de priorité |
| Le format ne s'actualise pas | Vérifier que la cellule contient bien une valeur numérique |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris