# Jour 06 : Opérateurs et calculs

## Objectifs
- Comprendre la différence entre valeur et formule
- Maîtriser les opérateurs de base (+, -, *, /)
- Savoir calculer des pourcentages
- Comprendre la priorité des opérations
- Construire un calculateur de salaire dynamique

---

## Partie théorique

### 1. Quelle est la différence entre une valeur et une formule dans Excel ?
**Réponse :** 
- **Valeur** : donnée statique saisie dans une cellule (nombre, texte, date).
- **Formule** : expression qui commence par `=` et effectue un calcul à partir d'autres cellules. Son résultat s'actualise automatiquement quand les cellules référencées changent.

### 2. Quels symboles Excel utilise-t-il pour l'addition, la soustraction, la multiplication et la division ?
**Réponse :** 
| Opération | Symbole |
|-----------|---------|
| Addition | `+` |
| Soustraction | `-` |
| Multiplication | `*` |
| Division | `/` |

### 3. Comment calcule-t-on un pourcentage dans Excel ?
**Réponse :** On divise la partie par le total, puis on applique le format **Pourcentage** (ou on multiplie par 100 et on ajoute le signe %).

**Exemple :** `=25/250` → 0,1 → format % → 10%

### 4. Pourquoi =10+5*2 ne donne-t-il pas le même résultat que =(10+5)*2 ?
**Réponse :** 
- `=10+5*2` → **10 + (5×2)** = 10 + 10 = **20** (la multiplication est prioritaire)
- `=(10+5)*2` → **15 × 2** = **30** (les parenthèses forcent l'addition d'abord)

### 5. À quoi servent les parenthèses dans une formule ?
**Réponse :** Les parenthèses permettent de **modifier l'ordre des calculs**. Tout ce qui est entre parenthèses est calculé en premier, avant le reste de la formule.

---

## Partie pratique

### Exercice 1 — Les quatre opérations

**Instructions :**
1. Créer une feuille **"Pratique"**
2. En **A1** : `100`
3. En **B1** : `20`
4. Tester les formules suivantes :

| Formule | Résultat attendu |
|---------|------------------|
| `=A1+B1` | 120 |
| `=A1-B1` | 80 |
| `=A1*B1` | 2000 |
| `=A1/B1` | 5 |

**Réalisation :** Saisir chaque formule dans une cellule différente (ex: C1, C2, C3, C4).

---

### Exercice 2 — Calculer un pourcentage

**Instructions :**
1. En **A3** : `Salaire brut` et en **B3** : `250000`
2. En **A4** : `Retenue` et en **B4** : `25000`
3. En **A5** : `Taux de retenue`
4. En **B5** : `=B4/B3`
5. Appliquer le format **Pourcentage** à B5

**Question : Quelle différence entre =25000/250000 et =25000/250000*100 lorsque la cellule est déjà formatée en pourcentage ?**

**Réponse :** 
- `=25000/250000` → 0,1 → format % → **10%**
- `=25000/250000*100` → 10 → format % → **1000%** (faux)

**Conclusion :** Quand la cellule est formatée en **%**, il ne faut **PAS** multiplier par 100. Excel le fait automatiquement.

---

### Exercice 3 — Priorité des opérations

**Instructions :** Tester les formules suivantes :

| Formule | Résultat | Explication |
|---------|----------|-------------|
| `=10+5*2` | 20 | Multiplication prioritaire |
| `=(10+5)*2` | 30 | Parenthèses forcent l'addition d'abord |
| `=100-20/2` | 90 | Division prioritaire |
| `=(100-20)/2` | 40 | Parenthèses forcent la soustraction d'abord |

**Question : Quel rôle jouent les parenthèses dans ces calculs ?**

**Réponse :** Les parenthèses permettent de **forcer l'ordre des calculs**. Tout ce qui est à l'intérieur des parenthèses est calculé en premier, modifiant ainsi le résultat final.

---

## Mini-projet — Calculateur de salaire

**Contexte :** Construire un outil de calcul automatique du salaire net.

### Instructions :

1. **Créer une feuille "Calculateur_Salaire"**

2. **Saisir les données :**

| A | B |
|---|-----|
| **Salaire de base** | 250 000 |
| **Prime de transport** | 30 000 |
| **Prime de performance** | 10% |
| **Heures supplémentaires** | 20 |
| **Taux horaire** | 2 500 |
| **Taux de retenue** | 5% |

3. **Calculs à réaliser :**

| Calcul | Formule |
|--------|---------|
| **Prime de performance** | `=B1*B3` (Salaire de base × 10%) |
| **Heures supplémentaires** | `=B4*B5` (20 × 2 500) |
| **Salaire brut** | `=B1+B2+B7+B8` (Base + Transport + Prime + Heures sup) |
| **Retenue** | `=B9*B6` (Salaire brut × 5%) |
| **Salaire net** | `=B9-B10` (Salaire brut - Retenue) |

4. **Mettre en forme :**
   - Ajouter des titres en gras
   - Formater les montants en devise (€ ou FCFA)
   - Formater les taux en pourcentage

### Challenge

**Instructions :** Change volontairement :
- le salaire de base
- le taux de retenue
- le nombre d'heures supplémentaires

**Question :** Est-ce que tous les calculs se mettent automatiquement à jour ?

**Réponse :** Oui, car toutes les formules utilisent des **références relatives aux cellules**. Quand une valeur change, tous les calculs qui en dépendent se mettent à jour automatiquement. C'est la puissance d'Excel !

---

## Points de friction

| Problème | Solution |
|----------|----------|
| Résultat faux avec le format % | Ne pas multiplier par 100 si la cellule est en % |
| Division par 0 | Vérifier que le diviseur n'est pas vide ou égal à 0 |
| Formule qui ne s'actualise pas | Vérifier que le calcul est en mode automatique |
| Priorité des opérations oubliée | Utiliser des parenthèses pour forcer l'ordre |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris