# Jour 24 : DAX — construire des mesures

## Objectifs
- Comprendre ce qu'est une mesure DAX
- Différencier colonne calculée et mesure
- Utiliser SUMX, CALCULATE, FILTER
- Comprendre le contexte de filtre
- Construire des KPI commerciaux

---

## Partie théorique

### 1. Qu'est-ce que DAX ?
**Réponse :** Data Analysis Expressions — le langage de calcul de Power Pivot et Power BI.

### 2. Pourquoi DAX est utilisé dans Power Pivot ?
**Réponse :** Pour créer des mesures dynamiques qui s'adaptent au contexte d'analyse.

### 3. Qu'est-ce qu'une mesure ?
**Réponse :** Un calcul dynamique qui s'adapte au contexte (filtres, lignes, colonnes).

### 4. Différence entre mesure et colonne calculée ?
**Réponse :**
- **Colonne calculée** : figée, stockée dans la table
- **Mesure** : calculée au moment de l'analyse, s'adapte au contexte

### 5. Pourquoi utiliser SUMX plutôt que SUM ?
**Réponse :** SUMX fait un calcul **ligne par ligne** puis additionne. SUM additionne simplement.

### 6. Que signifie le X dans SUMX ?
**Réponse :** "eXpression" — indique qu'il faut évaluer une expression pour chaque ligne.

### 7. À quoi sert CALCULATE ?
**Réponse :** À modifier le contexte de filtre d'une mesure.

### 8. Qu'est-ce que le contexte de filtre ?
**Réponse :** L'ensemble des filtres actifs quand une mesure est évaluée.

### 9. Comment CALCULATE modifie-t-il ce contexte ?
**Réponse :** En ajoutant, remplaçant ou supprimant des filtres.

### 10. À quoi sert FILTER ?
**Réponse :** À créer une table filtrée ligne par ligne.

### 11. Pourquoi peut-on utiliser FILTER dans CALCULATE ?
**Réponse :** Pour appliquer un filtre complexe qui ne peut pas être exprimé simplement.

---

## Partie pratique

### Exercice 1 — CA Total (SUMX)
```dax
CA Total := SUMX(FACT_VENTES; FACT_VENTES[Quantité] * RELATED(DIM_PRODUITS[Prix]))
```

### Exercice 2 — Mesures simples
```dax
Quantité Totale := SUM(FACT_VENTES[Quantité])
Nombre de Ventes := COUNTROWS(FACT_VENTES)
CA Moyen := DIVIDE([CA Total]; [Nombre de Ventes])
```

### Exercice 3 — CALCULATE
```dax
CA Dakar := CALCULATE([CA Total]; DIM_VENDEURS[Région] = "Dakar")
```

### Exercice 4 — CALCULATE + FILTER
```dax
CA Grosses Ventes := CALCULATE(
    [CA Total];
    FILTER(FACT_VENTES; FACT_VENTES[Quantité] >= 10)
)
```

---

## Points de friction

| Problème | Solution |
|----------|----------|
| RELATED ne fonctionne pas | Vérifier que la relation existe |
| DIVIDE par zéro | Utiliser DIVIDE qui gère le cas |
| Filtre non reconnu | Vérifier le nom exact de la colonne |

---

## Statut
## Statut
✅ Théorie
✅ SUMX
✅ Mesures simples
✅ CALCULATE
✅ CALCULATE + FILTER
✅ Mini-projet