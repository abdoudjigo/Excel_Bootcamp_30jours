# Jour 12 : XLOOKUP

## Objectifs
- Comprendre l'utilité de XLOOKUP
- Maîtriser ses arguments essentiels
- Savoir gérer les valeurs inexistantes
- Faire des recherches vers la gauche

---

## Partie théorique

### 1. À quoi sert XLOOKUP ?
**Réponse :** XLOOKUP est une fonction de recherche qui remplace VLOOKUP, HLOOKUP et RECHERCHE. Elle permet de chercher une valeur dans une colonne et de renvoyer une valeur d'une autre colonne.

### 2. Quels sont ses arguments essentiels ?
**Réponse :** 
| Argument | Description |
|----------|-------------|
| **Valeur_cherchée** | Ce qu'on cherche |
| **Tableau_recherche** | Colonne où chercher |
| **Tableau_retour** | Colonne à renvoyer |
| **Si_introuvable** | Message si valeur inexistante (optionnel) |

### 3. Quelle différence entre VLOOKUP et XLOOKUP ?
**Réponse :** 
| VLOOKUP | XLOOKUP |
|---------|---------|
| Cherche uniquement dans la 1ère colonne | Cherche dans n'importe quelle colonne |
| Nécessite un numéro d'index | Utilise directement la colonne de retour |
| Ne peut pas chercher vers la gauche | Peut chercher vers la gauche |
| Erreur #N/A si non trouvé | Gère si_introuvable |

### 4. Pourquoi XLOOKUP n'a-t-il pas besoin d'un numéro d'index de colonne ?
**Réponse :** On indique directement la colonne à retourner, pas un numéro. Plus simple et moins d'erreurs.

### 5. Que se passe-t-il si la valeur recherchée n'existe pas ?
**Réponse :** Par défaut, XLOOKUP retourne `#N/A`. Mais on peut utiliser l'argument `si_introuvable` pour afficher un message personnalisé.

### 6. Quel avantage XLOOKUP offre-t-il lorsqu'on veut rechercher vers la gauche ?
**Réponse :** VLOOKUP cherche uniquement de gauche à droite. XLOOKUP peut chercher dans n'importe quelle direction.

---

## Partie pratique

### Dataset
1. Créer une feuille **"Pratique_XLOOKUP"**
2. Saisir le tableau :

| ID | Nom | Filière | Math | Python |
|----|-----|---------|------|--------|
| ST001 | Awa Ndiaye | Data | 15 | 17 |
| ST002 | Mamadou Diop | Développement | 12 | 14 |
| ST003 | Fatou Fall | IA | 18 | 16 |
| ST004 | Cheikh Ba | Data | 10 | 13 |
| ST005 | Mariama Sow | Cybersécurité | 14 | 11 |

---

### Exercice 1 — Première recherche

**Instructions :**
1. En A10 : `ID recherché`
2. En B10 : `ST003`
3. En A11 : `Nom`
4. En B11 : `=XLOOKUP(B10;A2:A6;B2:B6)`

**Résultat :** Fatou Fall

---

### Exercice 2 — Changer la valeur retournée

**Instructions :**
| Cellule | Formule | Résultat |
|---------|---------|----------|
| B12 | `=XLOOKUP(B10;A2:A6;C2:C6)` | IA |
| B13 | `=XLOOKUP(B10;A2:A6;D2:D6)` | 18 |
| B14 | `=XLOOKUP(B10;A2:A6;E2:E6)` | 16 |

---

### Exercice 3 — Valeur inexistante

**Instructions :**
1. En B15 : `ST999`
2. En B16 : `=XLOOKUP(B15;A2:A6;B2:B6)` → `#N/A`
3. En B17 : `=XLOOKUP(B15;A2:A6;B2:B6;"Étudiant introuvable")` → `Étudiant introuvable`

---

### Exercice 4 — Recherche vers la gauche

**Instructions :**
1. Créer un petit tableau :

| Nom | ID | Filière |
|-----|----|---------|
| Awa Ndiaye | ST001 | Data |
| Mamadou Diop | ST002 | Développement |
| Fatou Fall | ST003 | IA |

2. En B20 : `ST002`
3. En B21 : `=XLOOKUP(B20;G2:G4;F2:F4)` → `Mamadou Diop`

**Question :** Pourquoi ce type de recherche est problématique avec VLOOKUP ?

**Réponse :** VLOOKUP cherche uniquement dans la première colonne. Avec XLOOKUP, on peut chercher dans n'importe quelle colonne.

---

## Mini-projet — Système de recherche d'étudiants

### Étape 1 — Feuille Étudiants
Reprendre 100 étudiants du dataset du Jour 3.

### Étape 2 — Feuille Recherche
Créer l'interface :

| Information | Valeur |
|-------------|--------|
| ID recherché | ST0042 |
| Nom | `=XLOOKUP(B3;Etudiants!A:A;Etudiants!B:B;"Introuvable")` |
| Sexe | `=XLOOKUP(B3;Etudiants!A:A;Etudiants!C:C;"Introuvable")` |
| Ville | `=XLOOKUP(B3;Etudiants!A:A;Etudiants!D:D;"Introuvable")` |
| Filière | `=XLOOKUP(B3;Etudiants!A:A;Etudiants!E:E;"Introuvable")` |
| Math | `=XLOOKUP(B3;Etudiants!A:A;Etudiants!F:F;"Introuvable")` |
| Excel | `=XLOOKUP(B3;Etudiants!A:A;Etudiants!G:G;"Introuvable")` |
| Python | `=XLOOKUP(B3;Etudiants!A:A;Etudiants!H:H;"Introuvable")` |

### Challenge
Recherche par Nom → ID :
- En B25 : `Fatou Fall`
- En B26 : `=XLOOKUP(B25;Etudiants!B:B;Etudiants!A:A;"Introuvable")`

---

## Points de friction

| Problème | Solution |
|----------|----------|
| XLOOKUP pas disponible | Mettre à jour Excel (version 2019 ou 365) |
| Résultat vide | Vérifier le paramètre si_introuvable |
| Recherche ne fonctionne pas | Vérifier que les colonnes sont bien alignées |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris