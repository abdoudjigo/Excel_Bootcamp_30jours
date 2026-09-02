# Jour 16 : Tableaux Croisés Dynamiques (TCD)

## Objectifs
- Créer un TCD à partir d'une base de données
- Placer les champs dans Lignes, Colonnes, Valeurs et Filtres
- Aggréger des données (SUM, COUNT, AVERAGE)
- Regrouper des dates
- Utiliser des segments pour rendre l'analyse interactive

---

## Partie théorique

### 1. À quoi sert un tableau croisé dynamique ?
**Réponse :** À résumer et analyser rapidement de grandes quantités de données sans écrire de formules. Il permet de synthétiser, croiser et filtrer des données.

### 2. Différence entre Lignes, Colonnes, Valeurs et Filtres ?
**Réponse :**
| Zone | Rôle |
|------|------|
| Lignes | Éléments en lignes (ex: Catégorie) |
| Colonnes | Éléments en colonnes (ex: Vendeur) |
| Valeurs | Données à analyser (ex: SOMME de CA) |
| Filtres | Filtrer l'ensemble du tableau |

### 3. Pourquoi un TCD est-il utile avec une grande base de données ?
**Réponse :** Il permet de résumer des milliers de lignes en quelques clics, sans formules complexes.

### 4. Différence entre SUM, COUNT et AVERAGE dans un TCD ?
**Réponse :**
- **SUM** : somme des valeurs
- **COUNT** : nombre de valeurs
- **AVERAGE** : moyenne des valeurs

### 5. Qu'est-ce que le regroupement de dates ?
**Réponse :** Permet de regrouper des dates par mois, trimestre, année pour une analyse temporelle.

### 6. À quoi sert un segment ?
**Réponse :** C'est un filtre visuel interactif qui permet de filtrer un TCD en un clic.

### 7. Différence entre un filtre classique et un segment ?
**Réponse :**
- **Filtre** : dans le TCD, moins visible
- **Segment** : visuel, interactif, plus intuitif

### 8. Pourquoi une base structurée est-elle nécessaire ?
**Réponse :** Un TCD nécessite des colonnes avec des en-têtes et des données cohérentes.

---

## Partie pratique

### Dataset
Utilise la base `tblVentes` du Jour 14.

---

### Exercice 1 — CA par catégorie

**Instructions :**
1. Créer une feuille **"TCD"**
2. Insertion → **Tableau croisé dynamique**
3. Configuration :
   - Lignes : **Catégorie**
   - Valeurs : **Chiffre_Affaires** (Somme)

---

### Exercice 2 — CA par vendeur

**Instructions :**
1. Lignes : **Vendeur**
2. Valeurs : **Chiffre_Affaires** (Somme)
3. Trier du plus grand au plus petit

---

### Exercice 3 — Vendeur × catégorie

**Instructions :**
1. Lignes : **Vendeur**
2. Colonnes : **Catégorie**
3. Valeurs : **Chiffre_Affaires** (Somme)

---

### Regrouper les dates

**Instructions :**
1. Lignes : **Date**
2. Valeurs : **Chiffre_Affaires** (Somme)
3. Clic droit sur une date → **Regrouper** → choisir **Mois** ou **Trimestre**

---

### Segments

**Instructions :**
1. Sélectionner le TCD
2. Insertion → **Segment**
3. Choisir : **Catégorie**, **Vendeur**

---

## Mini-projet — Analyse des ventes

### Structure :

| Feuille | Contenu |
|---------|---------|
| CA_Categorie | TCD : CA et Quantité par catégorie |
| Performance_Vendeurs | TCD : CA et Quantité par vendeur |
| Evolution_CA | TCD : CA par mois + courbe |
| Vendeur_Categorie | TCD : Vendeur × Catégorie |

### Segments :
- Catégorie
- Vendeur

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Les dates s'affichent en nombre | Regrouper par mois |
| Les valeurs ne s'additionnent pas | Vérifier que le champ est en "Somme" |
| Le TCD ne se met pas à jour | Clic droit → Actualiser |

---

## Statut
⬜ Théorie faite
⬜ Exercices faits
⬜ Mini-projet fait
⬜ Points de friction compris