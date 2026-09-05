# Jour 20 : Projet intermédiaire — Analyse complète d'une activité commerciale

## Objectifs
- Réaliser une analyse complète de A à Z
- Importer, nettoyer, transformer et analyser des données
- Construire un dashboard interactif
- Produire des recommandations business

---

## Contexte

**Rôle :** Data Analyst dans une entreprise de distribution.

**Mission :** Analyser les performances commerciales et construire un dashboard pour la direction.

**Dataset :** Superstore (Sample - Superstore.xls)

---

## Structure du projet

### 1. Importation des données
- Feuille `Raw_Data` (données brutes, ne pas modifier)
- Utiliser Power Query si besoin

### 2. Diagnostic et nettoyage
- Nombre de lignes / colonnes
- Doublons sur Order ID
- Valeurs manquantes
- Formats incohérents
- Valeurs incohérentes (remises, négatifs, etc.)

### 3. Base propre
- Feuille `Clean_Data`
- Transformer en tableau : `tblSales`

### 4. Variables utiles
- Année, Mois
- Marge (Profit/Sales)

### 5. Analyse exploratoire
- Feuille `Analysis`
- Performance globale (CA, Profit, Marge, Commandes, Produits, Clients)
- Analyse temporelle (CA/Profit par année/mois)
- Analyse géographique (CA/Profit par région)
- Analyse catégories (CA/Profit par catégorie/sous-catégorie)
- Analyse clients (meilleurs, moins rentables)

### 6. Insights (5 minimum)
- Un insight = observation + signification
- Exemple : "La région West génère le plus de CA, mais sa marge est inférieure à la moyenne."

### 7. Dashboard
- Feuille `Dashboard`
- KPI : CA total, Profit total, Marge, Nombre commandes, Nombre clients
- Graphiques : Évolution CA, CA par catégorie, Profit par catégorie, Performance régionale, CA vs Profit
- Segments : Année, Région, Catégorie, Segment client

### 8. Recommandations
- Feuille `Recommendations`
- 3 à 5 recommandations business
- Format : Observation → Impact → Recommandation

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Dataset trop gros | Filtrer ou utiliser Power Query |
| Doublons sur Order ID | Vérifier avant de supprimer |
| Format des dates | Uniformiser avec Power Query |
| Marge négative | Vérifier les remises et les prix |

---

## Statut
✅ Importation
✅ Nettoyage
✅ Variables
✅ Analyse
✅ Insights
✅ Dashboard
✅ Recommandations

---

## 📊 Critères d'évaluation (auto-notation)

| Critère | Points | Score |
|---------|--------|-------|
| Importation / organisation | 10 | |
| Qualité du nettoyage | 20 | |
| Structuration des données | 10 | |
| Analyse | 20 | |
| TCD / outils Excel | 10 | |
| Dashboard | 15 | |
| Insights | 10 | |
| Documentation | 5 | |
| **Total** | **100** | |