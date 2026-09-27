# Jour 23 : Power Pivot — construire un modèle analytique

## Objectifs
- Comprendre les relations entre tables
- Distinguer table de faits et tables de dimensions
- Construire un modèle relationnel (schéma en étoile)
- Créer des relations dans Power Pivot
- Exploiter le modèle avec un TCD

---

## Partie théorique

### 1. Pourquoi plusieurs tables doivent-elles être reliées ?
**Réponse :** Pour éviter la redondance et permettre des analyses croisées sans dupliquer les données.

### 2. Qu'est-ce qu'une clé primaire ?
**Réponse :** Un identifiant unique dans une table (ex: Produit_ID).

### 3. Qu'est-ce qu'une clé étrangère ?
**Réponse :** Un identifiant qui fait référence à la clé primaire d'une autre table.

### 4. Qu'est-ce qu'une relation 1 → plusieurs ?
**Réponse :** Une ligne dans la table de dimension correspond à plusieurs lignes dans la table de faits.

### 5. Pourquoi une clé doit-elle être unique du côté « 1 » ?
**Réponse :** Pour éviter les ambiguïtés dans les relations.

### 6. Qu'est-ce qu'un modèle relationnel ?
**Réponse :** Un ensemble de tables reliées entre elles par des relations.

### 7. Pourquoi séparer les informations dans plusieurs tables ?
**Réponse :** Pour éviter la redondance et faciliter la maintenance.

### 8. Différence entre table de faits et table de dimension ?
**Réponse :**
- **Faits** : contient les événements mesurables (ventes, quantités)
- **Dimensions** : contient les descriptions (produits, vendeurs)

### 9. Qu'est-ce qu'un schéma en étoile ?
**Réponse :** Une table de faits au centre, entourée de tables de dimensions.

### 10. Pourquoi est-il adapté à l'analyse ?
**Réponse :** Il permet des analyses multidimensionnelles rapides.

### 11. Différence entre Power Query et Power Pivot ?
**Réponse :**
- **Power Query** : prépare et nettoie les données
- **Power Pivot** : modélise et relie les données

---

## Partie pratique

### Étape 1 — Créer les 4 tables
- Ventes, Produits, Vendeurs, Dim_Date

### Étape 2 — Transformer en Tableaux
- tVentes, tProduits, tVendeurs, tDate

### Étape 3 — Ajouter au Modèle de données
- Charger les 4 tables dans Power Pivot

### Étape 4 — Créer les relations
- tProduits → tVentes (Produit_ID)
- tVendeurs → tVentes (Vendeur_ID)
- tDate → tVentes (Date)

### Étape 5 — TCD à partir du modèle
- CA par Catégorie
- CA par Région
- CA par Catégorie ET Région
- CA par Mois

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Relation impossible | Vérifier que la clé est unique du côté 1 |
| TCD vide | Vérifier les relations |
| Modèle cassé | Reconstruire proprement |

---

## Statut
✅ Théorie
✅ Tables créées
✅ Modèle
✅ Relations
✅ TCD
✅ Mini-projet