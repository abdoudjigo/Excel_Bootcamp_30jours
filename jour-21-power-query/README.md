# Jour 21 : Power Query — construire un pipeline ETL

## Objectifs
- Comprendre le concept ETL (Extract, Transform, Load)
- Importer plusieurs sources avec Power Query
- Fusionner des tables avec des jointures
- Créer un pipeline reproductible et actualisable
- Identifier et traiter les anomalies

---

## Partie théorique

### 1. Que signifie ETL ?
**Réponse :** ETL = **Extract** (extraire), **Transform** (transformer), **Load** (charger). C'est un processus de traitement des données.

### 2. Différence entre importer et transformer ?
**Réponse :** 
- **Importer** = charger les données brutes
- **Transformer** = nettoyer, fusionner, calculer, structurer

### 3. Pourquoi utiliser Power Query plutôt que modifier manuellement ?
**Réponse :** Power Query est reproductible, actualisable, et moins source d'erreurs.

### 4. Qu'est-ce qu'une requête Power Query ?
**Réponse :** Une séquence d'étapes qui extrait, transforme et charge des données.

### 5. Qu'est-ce qu'une étape dans Power Query ?
**Réponse :** Une action individuelle (ex: changer un type, supprimer une colonne, fusionner).

### 6. Différence entre Fusionner et Ajouter des requêtes ?
**Réponse :**
- **Fusionner** = joindre deux tables (comme un JOIN SQL)
- **Ajouter** = empiler les lignes (comme UNION)

### 7. Qu'est-ce qu'une jointure ?
**Réponse :** Une opération qui combine deux tables à partir d'une clé commune.

### 8. Différence entre jointure gauche et interne ?
**Réponse :**
- **Jointure gauche** : toutes les lignes de la table de gauche + correspondances à droite
- **Jointure interne** : seulement les lignes qui ont une correspondance dans les deux tables

### 9. Pourquoi les clés de jointure doivent-elles être cohérentes ?
**Réponse :** Si une clé est "P001" et l'autre "P001 " (avec un espace), la jointure échoue.

### 10. Que se passe-t-il lors de l'actualisation ?
**Réponse :** Power Query relit les sources et réexécute toutes les étapes automatiquement.

---

## Partie pratique

### Dataset
Créer 3 fichiers dans `data/` :
- `ventes.xlsx`
- `produits.xlsx`
- `vendeurs.xlsx`

---

### Pratique 1 — Importation
1. Créer un fichier `Day-21-PowerQuery.xlsx`
2. Données → Obtenir des données → À partir d'un classeur
3. Importer les 3 fichiers

### Pratique 2 — Transformation
- Vérifier les types de données
- Ajouter une colonne CA (après fusion)

### Pratique 3 — Fusionner
- Fusionner Ventes + Produits sur Produit_ID (jointure gauche)
- Fusionner Ventes + Vendeurs sur Vendeur_ID (jointure gauche)

### Pratique 4 — Anomalie
Ajouter V004 avec P999 (inexistant) et observer

---

## Mini-projet — Pipeline ETL commercial

### Architecture :
```
ventes.xlsx → Power Query ← produits.xlsx
                    ↓
              Fusion + Jointure
                    ↓
         Table commerciale consolidée
```

### Transformations :
- Nettoyage (types, espaces)
- Jointures (produits, vendeurs)
- Calcul (CA = Quantité × Prix)

### Challenge :
- Ajouter 5 anomalies (produit inexistant, vendeur inexistant, etc.)
- Créer une table des anomalies

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Jointure qui ne fonctionne pas | Vérifier les clés (espaces, casse) |
| Erreur de type | Définir les types dès l'importation |
| Actualisation non prise en compte | Vérifier le chemin des fichiers sources |

---

## Statut
⬜ Importation
⬜ Transformation
⬜ Fusion Produits
⬜ Fusion Vendeurs
⬜ Anomalie
⬜ Mini-projet