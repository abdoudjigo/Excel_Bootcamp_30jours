# Jour 22 : Power Query avancé

## Objectifs
- Créer des colonnes personnalisées avec Power Query
- Comprendre le langage M (lire et modifier une formule simple)
- Utiliser des paramètres pour rendre un pipeline configurable
- Automatiser l'actualisation d'un pipeline complet

---

## Partie théorique

### 1. Qu'est-ce qu'une colonne personnalisée ?
**Réponse :** Une colonne créée dans Power Query avec une formule spécifique (ex: calcul, condition).

### 2. Différence avec une colonne calculée Excel ?
**Réponse :** 
- **Excel** : colonne calculée dans une feuille
- **Power Query** : colonne calculée dans la requête, reproductible et actualisable

### 3. Qu'est-ce que le langage M ?
**Réponse :** Le langage de programmation utilisé par Power Query pour transformer les données.

### 4. Qu'est-ce qu'un paramètre Power Query ?
**Réponse :** Une valeur configurable (ex: seuil, année) qui peut être modifiée sans toucher à la requête.

### 5. Que se passe-t-il lorsqu'on actualise ?
**Réponse :** Power Query relit les sources et réexécute toutes les étapes automatiquement.

---

## Partie pratique

### Exercice 1 — Colonne CA
Créer une colonne personnalisée :
```
CA = Quantité × Prix
```

### Exercice 2 — Colonne Segment
Créer une colonne avec condition :
- CA < 10 000 → Petit
- CA entre 10 000 et 50 000 → Moyen
- CA > 50 000 → Grand

### Exercice 3 — Colonne Contrôle
Créer une colonne avec condition :
- Quantité ≤ 0 → ERREUR
- Prix ≤ 0 → ERREUR
- Sinon → OK

### Exercice 4 — Paramètre Seuil_CA
Créer un paramètre :
- Nom : `Seuil_CA`
- Valeur : `50000`

Utiliser dans une colonne personnalisée :
```
if [CA] >= Seuil_CA then "Important" else "Normal"
```

### Exercice 5 — Actualisation
Ajouter 100 nouvelles ventes et actualiser.

---

## Mini-projet — Pipeline commercial paramétrable

### Structure :
```
Sources → Importation → Nettoyage → Transformation
    ↓
Fusion Produits → Fusion Vendeurs
    ↓
Calcul CA → Segmentation → Contrôle qualité
    ↓
Table finale
```

### Table finale :
Vente_ID, Date, Produit, Catégorie, Vendeur, Région, Quantité, Prix, CA, Segment, Contrôle

### Challenge :
- Ajouter des anomalies (quantité négative, prix zéro, produit inexistant, etc.)
- Créer une colonne Contrôle (OK / ERREUR)
- Créer une requête séparée pour les erreurs

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Langage M incompréhensible | Lire ligne par ligne, comprendre chaque étape |
| Paramètre non reconnu | Vérifier le nom exact du paramètre |
| Actualisation qui ne prend pas | Vérifier le chemin des sources |

---

## Statut
✅ Colonnes personnalisées
✅ Langage M
✅ Paramètres
✅ Actualisation
✅ Mini-projet