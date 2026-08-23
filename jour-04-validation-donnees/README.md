# Jour 04 : Validation des données

## Objectifs
- Comprendre l'utilité de la validation des données
- Maîtriser les listes déroulantes
- Savoir limiter les valeurs numériques, les dates
- Construire un formulaire d'inscription complet

---

## Partie théorique

### 1. Qu'est-ce que la validation des données dans Excel ?
**Réponse :** La validation des données est un outil qui permet de **contrôler ce que l'utilisateur peut saisir** dans une cellule. Elle permet de restreindre les valeurs à un certain type (nombre, date, texte) ou à une liste prédéfinie.

### 2. Quelle différence entre une liste déroulante et une restriction numérique ?
**Réponse :** 
- **Liste déroulante** : l'utilisateur choisit parmi une liste de valeurs prédéfinies (ex: Data, IA, Cybersécurité).
- **Restriction numérique** : l'utilisateur doit saisir un nombre dans une plage donnée (ex: entre 0 et 20 pour une note).

### 3. Pourquoi la validation des données améliore-t-elle la qualité d'un dataset ?
**Réponse :** 
- Évite les erreurs de saisie (fautes de frappe, valeurs incohérentes)
- Garantit que les données sont dans le bon format
- Facilite l'analyse et les tris/filtres
- Rend les données exploitables plus facilement

### 4. Quelle différence entre un message d'entrée et un message d'erreur ?
**Réponse :** 
- **Message d'entrée** : s'affiche **avant** la saisie (indique à l'utilisateur ce qui est attendu).
- **Message d'erreur** : s'affiche **après** une saisie incorrecte (alerte l'utilisateur).

### 5. La validation empêche-t-elle toujours l'utilisateur de saisir une valeur incorrecte ?
**Réponse :** Non, la validation peut être **contournée** par copier-coller ou par importation de données. Elle empêche la saisie manuelle incorrecte mais pas les données importées.

---

## Partie pratique

### Exercice 1 — Liste déroulante

**Instructions :**
1. Créer une feuille appelée **"Pratique"**
2. En **B2**, créer une liste déroulante avec les valeurs :
   - Data
   - Développement
   - Cybersécurité
   - IA

**Réalisation :**
1. Sélectionner B2
2. Données → Validation des données
3. Autoriser : **Liste**
4. Source : taper `Data;Développement;Cybersécurité;IA` (ou sélectionner une plage)
5. Valider

**Question : Que se passe-t-il lorsqu'une valeur non autorisée est saisie ?**
**Réponse :** Excel affiche un message d'erreur (par défaut) et bloque la saisie. L'utilisateur ne peut pas saisir une valeur qui n'est pas dans la liste.

---

### Exercice 2 — Limiter une note

**Instructions :**
1. En **B4**, créer une validation : **Nombre décimal entre 0 et 20**
2. Ajouter un message d'erreur : "La note doit être comprise entre 0 et 20."
3. Tester les valeurs : 15,5 ✅ / 20 ✅ / 21 ❌ / -2 ❌

**Réalisation :**
1. Sélectionner B4
2. Données → Validation des données
3. Autoriser : **Nombre décimal**
4. Minimum : **0**
5. Maximum : **20**
6. Onglet **Message d'erreur** : Titre "Note invalide", Message "La note doit être comprise entre 0 et 20."

---

### Exercice 3 — Limiter un âge

**Instructions :**
1. En **B6**, autoriser uniquement un **nombre entier entre 18 et 60**

**Réalisation :**
1. Sélectionner B6
2. Données → Validation des données
3. Autoriser : **Nombre entier**
4. Minimum : **18**
5. Maximum : **60**

---

### Exercice 4 — Contrôler une date

**Instructions :**
1. En **B8**, autoriser uniquement une date comprise entre **01/01/2025** et **31/12/2026**
2. Ajouter un message d'entrée : "Saisissez votre date d'inscription."

**Réalisation :**
1. Sélectionner B8
2. Données → Validation des données
3. Autoriser : **Date**
4. Date de début : **01/01/2025**
5. Date de fin : **31/12/2026**
6. Onglet **Message d'entrée** : Titre "Date d'inscription", Message "Saisissez votre date d'inscription."

---

## Mini-projet — Formulaire d'inscription

**Contexte :** Construire un formulaire d'inscription à une formation.

### Instructions
1. Créer une feuille **"Formulaire"**
2. Construire le formulaire suivant :

| Champ | Emplacement | Validation |
|-------|-------------|------------|
| Nom complet | A2 | Texte libre |
| Sexe | A4 | Liste déroulante (Masculin / Féminin) |
| Âge | A6 | Entier entre 18 et 60 |
| Ville | A8 | Liste déroulante (Dakar, Thiès, Saint-Louis, Kaolack, Ziguinchor, Touba) |
| Filière | A10 | Liste déroulante (Data, Développement, Cybersécurité, IA) |
| Niveau | A12 | Liste déroulante (Débutant, Intermédiaire, Avancé) |
| Date d'inscription | A14 | Date valide (01/01/2025 - 31/12/2026) |
| Email | A16 | Texte libre |

### Mise en forme
- Mettre les **champs** en gras (colonnes A)
- Ajouter des messages d'entrée pour chaque champ
- Ajouter des messages d'erreur pour les restrictions
- Ajouter un titre : "📋 Formulaire d'inscription" en fusionné en ligne 1

---

## Points de friction

| Problème | Solution |
|----------|----------|
| La liste déroulante n'affiche rien | Vérifier la source : taper avec `;` entre chaque valeur |
| Impossible de saisir une valeur pourtant valide | Vérifier le type de validation (liste, nombre, date) |
| La validation est contournée par copier-coller | La validation ne fonctionne que sur la saisie manuelle |
| Le message d'erreur n'apparaît pas | Vérifier que l'onglet "Message d'erreur" est bien rempli |

---

## Statut
✅ Théorie faite
✅ Exercices faits
✅ Mini-projet fait
✅ Points de friction compris