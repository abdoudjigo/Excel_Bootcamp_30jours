# Jour 19 : Dashboard interactif

## Objectifs
- Comprendre la différence entre un rapport et un dashboard
- Créer des KPI (indicateurs clés)
- Utiliser des TCD et des graphiques dynamiques
- Ajouter des segments pour rendre l'analyse interactive
- Construire un dashboard RH complet

---

## Partie théorique

### 1. Qu'est-ce qu'un dashboard ?
**Réponse :** Un tableau de bord interactif qui permet de visualiser, filtrer et explorer des données pour prendre des décisions rapidement.

### 2. Différence entre rapport et dashboard ?
**Réponse :**
- **Rapport** : document statique (PDF, imprimé)
- **Dashboard** : outil interactif (cliquable, dynamique)

### 3. Qu'est-ce qu'un KPI ?
**Réponse :** Un indicateur clé de performance (Key Performance Indicator) qui mesure l'état d'un objectif (ex: effectif total, salaire moyen).

### 4. Pourquoi utiliser des segments plutôt que des filtres classiques ?
**Réponse :** Les segments sont visuels, plus intuitifs, et permettent de filtrer plusieurs TCD/graphiques à la fois.

### 5. Qu'est-ce qu'un graphique dynamique ?
**Réponse :** Un graphique qui se met à jour automatiquement quand on change les filtres ou les segments.

---

## Dashboard — Structure visuelle

```
┌──────────────────────────────────────────────────────────────────────────┐
│                          📊 DASHBOARD RH                               │
├──────────────┬──────────────┬──────────────┬───────────────────────────┤
│  EFFECTIF    │  SALAIRE     │  SALAIRE     │  NOMBRE                   │
│   TOTAL      │  MOYEN       │  MAX         │  DÉPARTEMENTS             │
│              │              │              │                           │
│    100       │  350 000     │  650 000     │     4                     │
├──────────────┴──────────────┴──────────────┴───────────────────────────┤
│                                                                          │
│  SEGMENTS :    [▼ Département]    [▼ Sexe]    [▼ Ville]                │
│                                                                          │
├─────────────────────────────┬────────────────────────────────────────────┤
│                             │                                            │
│  Effectifs / département    │  Salaire moyen / département              │
│                             │                                            │
│      ████████               │      ████████                            │
│      ████████               │      ████████                            │
│      ████████               │      ████████                            │
│      ████████               │      ████████                            │
│                             │                                            │
│       [HISTOGRAMME]        │       [HISTOGRAMME]                      │
│                             │                                            │
├─────────────────────────────┴────────────────────────────────────────────┤
│                                                                          │
│  Effectifs / sexe           │  Effectifs / ville                        │
│                             │                                            │
│       ╭────╮               │      ██████                              │
│      ╱ 50% ╲               │      ██████                              │
│     │  F  │ │  H           │      ██████                              │
│      ╲    ╱                │      ██████                              │
│       ╰────╯               │                                           │
│                             │                                            │
│       [CIRCULAIRE]         │       [HISTOGRAMME]                      │
│                                                                          │
└──────────────────────────────────────────────────────────────────────────┘
```

---

## Partie pratique

### Dataset
Utiliser la base RH du Jour 13 :
- ID, Nom, Sexe, Ville, Filiere, Math, Excel, Python, Statistiques, Presence, Frais_payes, Date_inscription

---

### Exercice 1 — KPI
Créer 4 indicateurs :
- Effectif total : `=NBVAL(Employes!B:B)-1`
- Salaire moyen : `=MOYENNE(Employes!K:K)`
- Salaire maximum : `=MAX(Employes!K:K)`
- Nombre de départements : `=NBVAL(UNIQUE(Employes!E:E))-1`

### Exercice 2 — TCD
Créer 4 TCD :
1. Effectifs par département
2. Salaire moyen par département
3. Effectifs par sexe
4. Effectifs par ville

### Exercice 3 — Segments
Ajouter des segments pour :
- Département (Filiere)
- Sexe
- Ville

### Exercice 4 — Graphiques
Créer des graphiques à partir des TCD :
- Histogramme : Effectifs / département
- Histogramme : Salaire moyen / département
- Circulaire : Effectifs / sexe
- Histogramme : Effectifs / ville

### Challenge
Tester les combinaisons :
- Data + Féminin + Dakar → combien d'employés ? salaire moyen ?
- Hommes + IT + Dakar → combien d'employés ? salaire moyen ?

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Les KPI ne se mettent pas à jour | Utiliser des TCD ou des formules dynamiques |
| Les segments ne filtrent pas tous les graphiques | Vérifier que tous les TCD partagent la même source |
| Graphique vide | Vérifier que le TCD a des données |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris