# Jour 14 : Tableaux Excel

## Objectifs
- Transformer une plage en tableau structuré
- Maîtriser les références structurées
- Ajouter des colonnes calculées automatiquement
- Comprendre les avantages des tableaux pour l'analyse

---

## Partie théorique

### 1. Quelle est la différence entre une plage classique et un tableau Excel ?
**Réponse :** 
- **Plage classique** : simple ensemble de cellules. Pas de dynamisme.
- **Tableau Excel** : structure dynamique qui s'agrandit automatiquement, avec des références nommées et des formules qui se recopient.

### 2. Pourquoi donner un nom à un tableau ?
**Réponse :** Pour faciliter les références dans les formules. Au lieu de `=SOMME(A2:A100)`, on utilise `=SOMME(tblVentes[Chiffre_Affaires])`.

### 3. Qu'est-ce qu'une référence structurée ?
**Réponse :** C'est une façon de référencer les colonnes d'un tableau par leur nom, comme `=[@Quantité]` ou `=tblVentes[Chiffre_Affaires]`.

### 4. Quelle différence entre =C2*D2 et =[@Quantite]*[@Prix_Unitaire] ?
**Réponse :** 
- `=C2*D2` : référence absolue à une cellule. Si la structure change, la formule peut se briser.
- `=[@Quantite]*[@Prix_Unitaire]` : référence structurée. Peu importe où on se trouve, Excel prend la bonne colonne.

### 5. Que se passe-t-il lorsqu'on ajoute une nouvelle ligne à un tableau structuré ?
**Réponse :** Le tableau s'agrandit automatiquement, les formules sont recopiées, et les références structurées incluent la nouvelle ligne.

### 6. Pourquoi les tableaux structurés sont-ils utiles pour les bases de données ?
**Réponse :** Ils rendent les données plus robustes, évitent les erreurs de plage, et facilitent l'analyse.

---

## Partie pratique

### Exercice 1 — Créer un tableau

**Instructions :**
1. Créer une feuille **"Pratique_Tableaux"**
2. Saisir les données :

| Date | Produit | Catégorie | Quantité | Prix_Unitaire |
|------|---------|-----------|----------|---------------|
| 01/09/2026 | Laptop | Informatique | 2 | 450000 |
| 02/09/2026 | Souris | Informatique | 5 | 15000 |
| 03/09/2026 | Clavier | Informatique | 3 | 25000 |
| 04/09/2026 | Casque | Accessoires | 4 | 30000 |
| 05/09/2026 | Écran | Informatique | 2 | 120000 |

3. Sélectionner les données → **Insertion** → **Tableau**
4. Cocher : "Mon tableau comporte des en-têtes"
5. Nommer le tableau : **Ventes**

---

### Exercice 2 — Ajouter une colonne calculée

**Instructions :**
1. Ajouter une colonne **Chiffre_Affaires**
2. En F2 (ou première ligne) : `=[@Quantité]*[@Prix_Unitaire]`
3. La colonne se remplit automatiquement

---

### Exercice 3 — Référence à une colonne entière

**Instructions :**
1. En A8 : `Chiffre d'affaires total`
2. En B8 : `=SOMME(Ventes[Chiffre_Affaires])`

---

### Exercice 4 — Ajouter une ligne

**Instructions :**
1. Ajouter une nouvelle ligne sous le tableau
2. Observer l'extension automatique

---

### Exercice 5 — Filtrer le tableau

**Instructions :**
1. Filtrer par **Catégorie = Informatique**
2. Filtrer par **Produit = Souris**

---

## Mini-projet — Base de ventes

### Structure :

| Colonne | Type |
|---------|------|
| Date | Date |
| Vente_ID | Texte |
| Produit | Texte |
| Catégorie | Texte |
| Vendeur | Texte |
| Quantité | Nombre |
| Prix_Unitaire | Nombre |
| Chiffre_Affaires | Formule |
| Remise | Pourcentage |
| Montant_Net | Formule |

### Indicateurs :
- Chiffre d'affaires brut : `=SOMME(tblVentes[Chiffre_Affaires])`
- Chiffre d'affaires net : `=SOMME(tblVentes[Montant_Net])`
- Quantité totale : `=SOMME(tblVentes[Quantité])`

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Les références ne fonctionnent pas | Vérifier le nom du tableau et des colonnes |
| La colonne ne se remplit pas | Vérifier que c'est bien un tableau |
| Les filtres ne s'affichent pas | Activer l'option "Filtres" du tableau |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris