# 📊 Excel Bootcamp — 30 Jours

![Statut](https://img.shields.io/badge/statut-en%20cours-yellow)
![Jour](https://img.shields.io/badge/jour-01%20%2F%2030-blue)
![Environnement](https://img.shields.io/badge/environnement-Windows%20%2B%20Excel-0A66C2)

Challenge personnel de maîtrise Excel avancé, sur 30 jours consécutifs.
Objectif : passer d'un usage basique à un usage **professionnel niveau entreprise**
(RH, finance, reporting) — formules avancées, TCD, Power Query, dashboards, VBA.

| | |
|---|---|
| 🎯 **Format** | 1 dossier par jour : théorie (recherche) + pratique (fichier Excel) |
| 🧭 **Programme source** | Bootcamp d'un ami (template Notion) — contenu recopié jour par jour ici |
| 🧑‍🏫 **Coaching** | Sessions avec Claude, cas métier réalistes (RH/finance/reporting), lien systématique avec Pandas/SQL |
| 💻 **Environnement** | Windows + Excel · Git Bash · VS Code |

---

## 📁 Structure du repo

```
excel-bootcamp-30-jours/
├── README.md                          <- ce fichier (tableau de bord)
├── .gitignore
├── jour-01-references-cellules/
│   ├── README.md                      <- objectifs + questions du jour + réponses
│   └── exercices/                     <- fichiers .xlsx du jour
├── jour-02-.../
│   ├── README.md
│   └── exercices/
└── ...
```

Chaque dossier `jour-XX-.../README.md` suit toujours le même plan :
1. **Objectifs du jour** (copiés du programme Notion)
2. **Questions théoriques** + mes réponses
3. **Exercices pratiques** + ce que j'ai observé/compris
4. **Points de friction / erreurs commises** (le plus important pour progresser)

---

## 📈 Suivi de progression

`Semaine 1` ▓░░░░░░░░░░░░░░░░░░░░░░░░░░░░░ `1 / 30 jours`

| Jour | Thème | Statut |
|:----:|-------|:------:|
| [01](jour-01-references-cellules/) | Environnement & références (relative / absolue / mixte) | 🔄 En cours |
| 02 | *(à venir)* | ⬜ |
| 03 | *(à venir)* | ⬜ |
| 04 | *(à venir)* | ⬜ |
| 05 | *(à venir)* | ⬜ |
| 06 | *(à venir)* | ⬜ |
| 07 | *(à venir)* | ⬜ |
| 08–30 | *(à venir)* | ⬜ |

Légende : ⬜ à faire · 🔄 en cours · ✅ terminé · ⏭️ sauté (à rattraper)

> Ajoute une ligne au tableau à chaque nouveau jour, avec un lien vers son dossier — pas besoin de préremplir les 30 lignes à l'avance.

> Je mets à jour ce tableau à chaque fin de journée, avant le commit.

---

## 🔁 Workflow quotidien

Routine à chaque session de travail :

```bash
# 1. Créer le dossier du jour (si pas déjà fait)
mkdir -p jour-XX-nom-du-theme/exercices

# 2. Travailler : théorie dans le README.md du jour, fichiers .xlsx dans exercices/

# 3. Mettre à jour le tableau de progression dans le README principal

# 4. Commit + push en fin de journée
git add .
git commit -m "Jour XX : nom-du-theme"
git push
```

**Convention de commit** : `Jour 01 : références relatives, absolues et mixtes`
(numéro sur 2 chiffres, thème court en français, pas de majuscule après les deux-points)

---

## 🛠️ Stack

- Excel (Windows) — Microsoft 365
- Git for Windows + Git Bash
- VS Code (édition des README / notes)
- GitHub (hébergement du repo)

---

## 🔗 Ressources

- Programme complet : template Notion (privé — non lié directement, contenu recopié au fil des jours)
- Coaching Excel : historique de conversation avec Claude (cas RH/finance/reporting)
