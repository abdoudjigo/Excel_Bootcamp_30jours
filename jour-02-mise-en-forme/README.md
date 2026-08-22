# Jour 02 : Mise en forme (nombres, %, devise, dates, fusion)

## Objectifs
- Maîtriser les formats de cellules : nombres, pourcentages, devises, dates
- Savoir fusionner des cellules et comprendre les risques
- Appliquer ces compétences sur un dataset réel d'élèves

---

## Partie théorique

### 1. Comment formater un nombre avec 2 décimales ?
**Réponse :** Sélectionner les cellules → Onglet Accueil → Groupe Nombre → Augmenter/Diminuer les décimales ou choisir "Nombre" avec 2 décimales.  
**Raccourci :** `Ctrl+Maj+1` pour le format Nombre avec séparateur de milliers.

### 2. Comment afficher un nombre en pourcentage ?
**Réponse :** Sélectionner les cellules → Accueil → % ou `Ctrl+Maj+5`.  
**Effet :** Multiplie automatiquement la valeur par 100 et ajoute le signe %.

**Cas particulier :** Si la colonne contient déjà des décimales (0,95), le format % affiche directement 95%.

### 3. Comment formater une cellule en devise (€) ?
**Réponse :** Accueil → € (symbole devise) ou clic droit → Format de cellule → Devise → choisir €.  
**Raccourci :** `Ctrl+Maj+4` (pour $) ou personnaliser en €.

### 4. Comment changer le format d'une date ?
**Réponse :** Clic droit → Format de cellule → Date → choisir un format (jj/mm/aaaa, jj mmmm aaaa, etc.).  
**Important :** Excel stocke les dates en nombre (ex: 01/01/1900 = 1). Le format n'est qu'un affichage.

### 5. Qu'est-ce que la fusion de cellules et quels sont ses risques ?
**Réponse :** La fusion combine plusieurs cellules en une seule.  
**Risques :**
- Perte de données (seule la valeur de la cellule en haut à gauche est conservée)
- Problèmes avec les tris et filtres
- Difficultés avec les formules (recherches, plages incohérentes)
- Recommandé uniquement pour les titres, jamais pour les données structurées

---

## Partie pratique

### Exercice 1 : Mise en forme des notes (Math, Excel, Python)
**Instruction :** Formater les colonnes Math, Excel, Python avec **1 décimale**.

**Réalisation :** Sélection des colonnes → Accueil → Diminuer les décimales → 1 décimale.

---

### Exercice 2 : Calcul et affichage de la moyenne
**Instruction :** Créer une colonne "Moyenne" avec `=MOYENNE(B2:D2)` puis formater avec **1 décimale**.

**Réalisation :** 
- En E1 : `Moyenne`
- En E2 : `=MOYENNE(B2:D2)`
- Étirer vers le bas
- Format : 1 décimale

---

### Exercice 3 : Format pourcentage pour la présence
**Instruction :** Formater la colonne "Presence" en pourcentage.

**Réalisation :** 
- La colonne contient déjà des décimales (0,95 = 95%)
- Sélection → Accueil → `%`

---

### Exercice 4 : Format devise pour les frais payés
**Instruction :** Formater la colonne "Frais_payes" en devise € avec 2 décimales.

**Réalisation :** Clic droit → Format de cellule → Devise → € → 2 décimales.

---

### Exercice 5 : Format des dates d'inscription
**Instruction :** Formater la colonne "Date_inscription" en `jj/mm/aaaa`.

**Réalisation :** Clic droit → Format de cellule → Date → `14/03/2022`.

---

### Exercice 6 : Fusion pour le titre "Bulletin Scolaire 2025"
**Instruction :** En ligne 1, fusionner les cellules A1 à H1 et écrire "📊 Bulletin Scolaire 2025".

**Réalisation :** 
- Sélection A1:H1 → Fusionner et centrer
- Titre : gras, taille 14, bleu

**⚠️ Attention :** Fusion uniquement pour les titres, pas sur les données.

---

## Mini-projet : Bulletin Scolaire

### Réalisations :

| Élément | Formule / Action |
|---------|------------------|
| **Moyenne** | `=MOYENNE(B2:D2)` |
| **Taux présence** | Format % sur colonne Presence |
| **Statut** | `=SI(E2>=10;"Admis";"Non admis")` |
| **Mention** | `=SI(E2>=16;"Très Bien";SI(E2>=14;"Bien";SI(E2>=12;"Assez Bien";SI(E2>=10;"Passable";"Non admis")))` |
| **Mise en forme conditionnelle** | Admis → vert, Non admis → rouge |
| **Titres** | Gras, centrés, fond bleu ciel |
| **Devises** | € avec 2 décimales |
| **Dates** | jj/mm/aaaa |

---

## Points de friction (pièges à éviter)

| Problème | Solution |
|----------|----------|
| Formater 0,95 en % donne 95% | C'est correct, pas besoin de diviser par 100 |
| Fusionner des cellules contenant des données | Perte de données → fusionner seulement les titres |
| Dates affichées en nombre (ex: 45678) | Appliquer format Date, ne pas taper manuellement |
| Devise en $ au lieu de € | Changer dans Format de cellule → Devise → € |

---

## Statut
✅ Théorie faite  
✅ Exercices faits  
✅ Mini-projet fait  
✅ Points de friction compris