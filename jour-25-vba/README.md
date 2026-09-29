# Jour 25 : VBA — Automatiser Excel

## Objectifs
- Comprendre ce qu'est VBA et une macro
- Déclarer et utiliser des variables
- Écrire des conditions (If...Then...Else)
- Utiliser des boucles (For...Next, Do While)
- Manipuler des cellules avec VBA
- Créer une macro pour automatiser une tâche réelle

---

## Partie théorique

### 1. Qu'est-ce que VBA ?
**Réponse :** Visual Basic for Applications — le langage de programmation intégré à Excel.

### 2. Différence entre VBA, macro et formule Excel ?
**Réponse :**
- **Formule Excel** : calcul dans une cellule
- **VBA** : langage de programmation
- **Macro** : programme VBA qui exécute des instructions automatiquement

### 3. Où écrit-on du code VBA dans Excel ?
**Réponse :** Dans l'éditeur VBA (Alt+F11).

### 4. Qu'est-ce qu'un Sub ?
**Réponse :** Une procédure (bloc de code) qui exécute une tâche.

### 5. Comment exécuter une macro ?
**Réponse :** Alt+F8 → sélectionner la macro → Exécuter.

### 6. Qu'est-ce qu'une variable ?
**Réponse :** Un espace mémoire pour stocker une valeur.

### 7. À quoi servent Dim, String, Integer, Double, Boolean ?
**Réponse :**
- `Dim` : déclare une variable
- `String` : texte
- `Integer` : entier
- `Double` : nombre décimal
- `Boolean` : Vrai/Faux

### 8. Différence entre numérique et chaîne ?
**Réponse :** Numérique = calculs, Chaîne = texte.

### 9. Comment fonctionne If...Then...Else ?
**Réponse :** Exécute un bloc si la condition est VRAIE, sinon un autre bloc.

### 10. Comment combiner plusieurs conditions ?
**Réponse :** Avec `And` (ET) ou `Or` (OU).

### 11. Pourquoi utiliser une boucle ?
**Réponse :** Pour répéter une action sur plusieurs lignes/éléments.

### 12. Différence entre For...Next et Do While ?
**Réponse :**
- `For...Next` : nombre d'itérations connu
- `Do While` : répète tant que la condition est vraie

### 13. Comment parcourir les lignes d'un tableau ?
**Réponse :** Avec une boucle `For i = 2 To derniereLigne`.

---

## Partie pratique

### A. Variables
```vba
Dim nom As String
Dim age As Integer
Dim salaire As Double
Dim actif As Boolean
```

### B. Conditions
```vba
If salaire >= 300000 Then
    MsgBox "Salaire élevé"
Else
    MsgBox "Salaire inférieur"
End If
```

### C. Boucles
```vba
Dim i As Integer
For i = 2 To 10
    Cells(i, 1).Value = i
Next i
```

---

## Mini-projet — Automatiser un rapport

### Structure de la macro :
1. Parcourir toutes les lignes
2. Calculer CA = Quantité × Prix
3. Classer chaque vente (Petite/Moyenne/Grande)
4. Créer une feuille Rapport avec les KPI
5. Afficher un message de succès

### Challenge :
- Détecter automatiquement la dernière ligne
- Ajouter une colonne Anomalie
- Générer le rapport automatiquement

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Macro ne s'exécute pas | Vérifier que les macros sont activées |
| Erreur de compilation | Vérifier la syntaxe VBA |
| Cells(i, j) ne fonctionne pas | Vérifier les indices (ligne, colonne) |

---

## Statut
⬜ Théorie
⬜ Variables
⬜ Conditions
⬜ Boucles
⬜ Première macro
⬜ Mini-projet