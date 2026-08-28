# 🚀 Excel Bootcamp — 30 Jours

![Statut](https://img.shields.io/badge/Statut-En%20Cours-yellow)
![Jour](https://img.shields.io/badge/Jour-10%20sur%2030-blue)
![Excel](https://img.shields.io/badge/Excel-Microsoft%20365-217346?logo=microsoft-excel&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-11-0078D4?logo=windows&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?logo=github&logoColor=white)

---

## 📖 Présentation

Challenge personnel de **30 jours consécutifs** pour maîtriser Excel de manière **professionnelle**.  
Objectif : passer d'un usage basique à un niveau **entreprise** — formules avancées, tableaux croisés dynamiques, Power Query, dashboards et VBA.

| | |
|---|---|
| 🎯 **Format** | 1 dossier par jour : théorie + pratique (fichier Excel) |
| 🧭 **Programme** | Bootcamp d'un ami (template Notion) — contenu recopié jour par jour |
| 🧑‍🏫 **Coaching** | Sessions avec notre coach Dev DATA, cas métier réalistes (RH/finance/reporting) |
| 💻 **Environnement** | Windows + Excel · Git Bash · VS Code · GitHub |

---

## 📂 Structure du dépôt

```
excel-bootcamp-30-jours/
├── 📄 README.md                          # Tableau de bord principal
├── 📄 .gitignore                         # Ignore les fichiers temporaires Excel
├── 📁 jour-01-references-cellules/
│   ├── 📄 README.md                      # Objectifs + questions + réponses
│   └── 📁 exercices/                     # Fichiers .xlsx du jour
├── 📁 jour-02-mise-en-forme/
│   ├── 📄 README.md
│   ├── 📁 data/                          # Dataset original
│   └── 📁 exercices/                     # Copie de travail
├── 📁 jour-03-tri-filtres/
│   ├── 📄 README.md
│   ├── 📁 data/                          # Dataset original (1000 étudiants)
│   └── 📁 exercices/                     # Copie de travail
├── 📁 jour-04-validation-donnees/
│   ├── 📄 README.md
│   └── 📁 exercices/                     # Fichiers .xlsx du jour
├── 📁 jour-05-mise-en-forme-conditionnelle/
│   ├── 📄 README.md
│   └── 📁 exercices/                     # Fichiers .xlsx du jour
├── 📁 jour-06-operateurs-calculs/
│   ├── 📄 README.md
│   └── 📁 exercices/                     # Fichiers .xlsx du jour
├── 📁 jour-07-fonctions-statistiques/
│   ├── 📄 README.md
│   └── 📁 exercices/                     # Fichiers .xlsx du jour
├── 📁 jour-08-fonctions-logiques/
│   ├── 📄 README.md
│   └── 📁 exercices/                     # Fichiers .xlsx du jour
├── 📁 jour-09-fonctions-texte/
│   ├── 📄 README.md
│   ├── 📁 data/                          # Dataset original (clients)
│   └── 📁 exercices/                     # Copie de travail
├── 📁 jour-10-fonctions-date/
│   ├── 📄 README.md
│   └── 📁 exercices/                     # Fichiers .xlsx du jour
└── 📁 jour-XX-.../
    ├── 📄 README.md
    └── 📁 exercices/
```

**Chaque README du jour suit toujours le même plan :**

1. 🎯 **Objectifs du jour** (copiés du programme Notion)
2. ❓ **Questions théoriques** + mes réponses
3. 🧪 **Exercices pratiques** + observations
4. ⚠️ **Points de friction / erreurs commises** (le plus important pour progresser)

---

## 📊 Progression

### 🗓️ Semaine 1 — Fondations

```
[█████████████████████████████] 33 % — Jour 10 / 30
```

### Tableau de bord

| Jour | Thème | Compétences clés | Statut |
|:----:|-------|------------------|:------:|
| [01](jour-01-references-cellules/) | Environnement & références | Relative / Absolue / Mixte | ✅ Terminé |
| [02](jour-02-mise-en-forme/) | Mise en forme essentielle | Nombres, %, €, Dates, Fusion | ✅ Terminé |
| [03](jour-03-tri-filtres/) | Tri et filtres | Tris simples/personnalisés, filtres multiples | ✅ Terminé |
| [04](jour-04-validation-donnees/) | Validation des données | Listes déroulantes, restrictions numériques/date | ✅ Terminé |
| [05](jour-05-mise-en-forme-conditionnelle/) | Mise en forme conditionnelle | Règles, échelles, barres, icônes | ✅ Terminé |
| [06](jour-06-operateurs-calculs/) | Opérateurs et calculs | +, -, *, /, %, priorité des opérations | ✅ Terminé |
| [07](jour-07-fonctions-statistiques/) | Fonctions statistiques | SUM, AVERAGE, MAX, MIN, COUNT, COUNTIF, COUNTIFS | ✅ Terminé |
| [08](jour-08-fonctions-logiques/) | Fonctions logiques | IF, IFS, AND, OR, NOT, IFERROR | ✅ Terminé |
| [09](jour-09-fonctions-texte/) | Fonctions de texte | LEFT, RIGHT, MID, LEN, TRIM, CONCAT, TEXTJOIN | ✅ Terminé |
| [10](jour-10-fonctions-date/) | Fonctions de date | TODAY, NOW, YEAR, MONTH, DAY, DATEDIF | ✅ Terminé |
| 11 | *(à définir)* | — | ⬜ À faire |

*Les jours 11 à 30 seront ajoutés au fur et à mesure.*

**Légende :**  
⬜ À faire · 🔄 En cours · ✅ Terminé · ⏭️ Sauté (à rattraper)

---

## 🔁 Workflow quotidien

```bash
# 1. Créer le dossier du jour
mkdir -p jour-XX-nom-du-theme/exercices
mkdir -p jour-XX-nom-du-theme/data

# 2. Travailler : théorie dans README.md, Excel dans exercices/

# 3. Mettre à jour le tableau de progression (README principal)

# 4. Commit + push en fin de journée
git add .
git commit -m "Jour XX : nom-du-theme"
git push
```

### Convention de commit

```
Jour 01 : références relatives, absolues et mixtes
Jour 02 : mise en forme (nombres, %, devise, dates, fusion)
Jour 03 : tri et filtres
Jour 04 : validation des données
Jour 05 : mise en forme conditionnelle
Jour 06 : opérateurs et calculs
Jour 07 : fonctions statistiques essentielles
Jour 08 : fonctions logiques
Jour 09 : fonctions de texte
Jour 10 : fonctions de date
```

> Numéro sur 2 chiffres · thème court en français · pas de majuscule après les deux‑points

---

## 🛠️ Stack technique

| Outil | Utilisation |
|-------|-------------|
| 📊 **Excel Microsoft 365** | Travail principal (fichiers .xlsx) |
| 🖥️ **Windows 11** | Environnement de travail |
| 🐚 **Git Bash** | Commandes Git |
| 📝 **VS Code** | Édition des README et notes |
| 🐙 **GitHub** | Hébergement du dépôt |
---

## 🧠 Compétences visées

**Niveau 1 — Fondations (Jours 1-10)**
- Références (relative/absolue/mixte) ✅
- Mise en forme (nombres, %, dates, devise) ✅
- Tri et filtres (simples, multiples, personnalisés) ✅
- Validation des données (listes, nombres, dates) ✅
- Mise en forme conditionnelle (règles, échelles, barres, icônes) ✅
- Opérateurs et calculs (+, -, *, /, %, priorité) ✅
- Fonctions statistiques (SUM, AVERAGE, MAX, MIN, COUNT, COUNTIF, COUNTIFS) ✅
- Fonctions logiques (IF, IFS, AND, OR, NOT, IFERROR) ✅
- Fonctions de texte (LEFT, RIGHT, MID, LEN, TRIM, CONCAT, TEXTJOIN) ✅
- Fonctions de date (TODAY, NOW, YEAR, MONTH, DAY, DATEDIF) ✅

**Niveau 2 — Intermédiaire (Jours 11-20)**
- Tableaux croisés dynamiques
- Fonctions avancées (INDEX/EQUIV, SOUS.TOTAL)
- Scénarios et simulations

**Niveau 3 — Avancé (Jours 21-30)**
- Power Query
- VBA / Macros
- Dashboards interactifs
- Automatisation

---

## 📎 Liens utiles

- 📁 [Dépôt GitHub](https://github.com/abdoudjigo/Excel_Bootcamp_30jours)
- 🧑‍🏫 Programme source : template Notion (privé, contenu recopié au fil des jours)
---

## 🏁 Dernière mise à jour

> **28 août 2026** — Jour 10 terminé ✅

---

🔥 **30 jours pour devenir un pro Excel — un jour à la fois.**