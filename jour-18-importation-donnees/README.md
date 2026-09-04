# Jour 18 : Importation de données

## Objectifs
- Importer un fichier CSV
- Importer un fichier Excel
- Importer plusieurs fichiers depuis un dossier
- Comprendre l'importance d'un pipeline reproductible
- Construire un système d'importation automatique

---

## Partie théorique

### 1. Différence entre importer un CSV et ouvrir un fichier Excel ?
**Réponse :** 
- **Ouvrir** : affiche le fichier tel quel, sans contrôle
- **Importer** : permet de choisir le séparateur, l'encodage, le format des données

### 2. Pourquoi contrôler les types de données après importation ?
**Réponse :** Pour éviter que des nombres soient traités comme du texte, ou des dates comme du texte.

### 3. Que peut-il arriver aux accents, séparateurs, dates lors d'une importation CSV ?
**Réponse :** 
- **Accents** : peuvent devenir des caractères bizarres (problème d'encodage)
- **Séparateurs** : si le fichier utilise `;` et Excel attend `,`
- **Dates** : peuvent être inversées (MM/JJ vs JJ/MM)

### 4. Pourquoi éviter le copier-coller manuel ?
**Réponse :** C'est long, source d'erreurs, et pas reproductible. Si on reçoit le même fichier chaque mois, il faut tout refaire.

### 5. Qu'est-ce qu'un pipeline d'importation ?
**Réponse :** Un processus automatisé qui va de la source de données jusqu'à la table finale, en passant par le nettoyage et la transformation.

### 6. Pourquoi importer plusieurs fichiers est utile ?
**Réponse :** Pour centraliser des données mensuelles, par région, par produit, etc.

### 7. Que signifie actualiser une source de données ?
**Réponse :** Mettre à jour les données importées en relisant les fichiers sources.

---

## Partie pratique

### Exercice 1 — Importer un CSV

**Instructions :**
1. Créer un fichier **"Jour_18_Importation.xlsx"**
2. Feuille **"Import_CSV"**
3. Données → **À partir d'un fichier texte/CSV**
4. Choisir le fichier CSV du Jour 17
5. Vérifier : séparateur, encodage, types

---

### Exercice 2 — Importer un fichier Excel

**Instructions :**
1. Données → **Obtenir des données** → **À partir d'un fichier** → **Classeur Excel**
2. Choisir un fichier Excel (ex: Jour 14)
3. Sélectionner la feuille avec les ventes
4. Charger

---

### Exercice 3 — Importer plusieurs fichiers

**Instructions :**
1. Créer 3 fichiers : `ventes_janvier.xlsx`, `ventes_fevrier.xlsx`, `ventes_mars.xlsx`
2. Données → **Obtenir des données** → **À partir d'un dossier**
3. Sélectionner le dossier
4. **Combiner et transformer**

---

## Mini-projet — Pipeline de ventes

### Structure :
```
project/
└── ventes/
    ├── janvier.xlsx
    ├── février.xlsx
    ├── mars.xlsx
    ├── avril.xlsx
    ├── mai.xlsx
    └── juin.xlsx
```

### Étapes :
1. Créer 6 fichiers avec 50-100 ventes chacun
2. Importer depuis le dossier
3. Combiner avec Power Query
4. Charger dans **"Toutes_Ventes"**
5. Transformer en tableau

### Challenge :
Ajouter un 7ème fichier (`juillet.xlsx`) et actualiser.

---

## Points de friction

| Problème | Solution |
|----------|----------|
| CSV avec accents bizarres | Choisir l'encodage UTF-8 |
| Fichiers avec colonnes différentes | Vérifier les en-têtes avant combinaison |
| L'actualisation ne fonctionne pas | Vérifier le chemin du dossier source |
| Power Query ne voit pas les nouveaux fichiers | Vérifier que le dossier est bien sélectionné |

---

## Statut
⬜ Théorie faite
⬜ Exercices faits
⬜ Mini-projet fait
⬜ Points de friction compris