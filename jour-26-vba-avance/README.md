# Jour 26 : VBA avancé — Formulaires & génération de rapports

## Objectifs
- Créer un UserForm (formulaire VBA)
- Récupérer les données saisies
- Automatiser plusieurs opérations
- Générer un rapport automatiquement
- Concevoir une application proche du réel

---

## Partie théorique

### 1. Qu'est-ce qu'un UserForm ?
**Réponse :** Une fenêtre de dialogue personnalisée pour saisir des données.

### 2. À quoi servent TextBox, ComboBox, Label, CommandButton ?
**Réponse :**
- **TextBox** : champ de saisie
- **ComboBox** : liste déroulante
- **Label** : texte fixe
- **CommandButton** : bouton cliquable

### 3. Comment récupérer la valeur d'un TextBox ?
**Réponse :** `TextBox.Value`

### 4. Comment déclencher du code au clic d'un bouton ?
**Réponse :** Avec l'événement `Private Sub btnNom_Click()`.

### 5. Comment une macro enchaîne plusieurs tâches ?
**Réponse :** En appelant plusieurs Sub ou en exécutant les instructions à la suite.

### 6. Comment trouver la dernière ligne ?
**Réponse :** `Cells(Rows.Count, 1).End(xlUp).Row`

### 7. Comment créer une feuille avec VBA ?
**Réponse :** `Sheets.Add`

### 8. Comment supprimer une feuille ?
**Réponse :** `Sheets("Nom").Delete`

### 9. Comment éviter les erreurs ?
**Réponse :** Avec `On Error Resume Next` ou des vérifications.

### 10. Comment générer des KPI ?
**Réponse :** En calculant puis écrivant dans des cellules.

### 11. Comment écrire dans une feuille ?
**Réponse :** `Cells(ligne, colonne).Value = valeur`

### 12. Comment mettre en forme ?
**Réponse :** `.Font.Bold`, `.Font.Size`, `.Interior.Color`, etc.

### 13. Comment générer un rapport ?
**Réponse :** En parcourant les données, calculant, et écrivant dans une feuille.

---

## Partie pratique

### Formulaire de saisie des ventes

**Structure :**
- Vente ID → TextBox
- Date → TextBox
- Produit → ComboBox
- Quantité → TextBox
- Prix → TextBox
- Enregistrer → CommandButton
- Annuler → CommandButton

### Logique d'enregistrement
```vba
Private Sub btnEnregistrer_Click()
    Dim ligne As Long
    ligne = Sheets("Ventes").Cells(Rows.Count, 1).End(xlUp).Row + 1
    Sheets("Ventes").Cells(ligne, 1).Value = txtVenteID.Value
    Sheets("Ventes").Cells(ligne, 2).Value = txtDate.Value
    Sheets("Ventes").Cells(ligne, 3).Value = cboProduit.Value
    Sheets("Ventes").Cells(ligne, 4).Value = txtQuantite.Value
    Sheets("Ventes").Cells(ligne, 5).Value = txtPrix.Value
    MsgBox "Vente enregistrée."
End Sub
```

### Validation
```vba
If txtQuantite.Value <= 0 Then
    MsgBox "La quantité doit être supérieure à 0."
    Exit Sub
End If
```

---

## Mini-projet — Sales Reporting Automation

### Structure :
```
sales_automation.xlsm
│
├── Accueil
├── Ventes
├── Produits
└── Rapport
```

### Boutons sur Accueil :
- [Ajouter une vente] → UserForm
- [Générer le rapport] → Macro
- [Actualiser] → Relance traitements

---

## Statut
✅ Théorie
✅ UserForm
✅ Formulaire
✅ Validation
✅ Génération rapport
✅ Mini-projet