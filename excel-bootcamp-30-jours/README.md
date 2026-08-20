# 📊 Excel Bootcamp — 30 Jours

Challenge personnel de maîtrise Excel avancé, sur 30 jours consécutifs.
Objectif : passer d'un usage basique à un usage **professionnel niveau entreprise**
(RH, finance, reporting) — formules avancées, TCD, Power Query, dashboards, VBA.

- 🎯 **Format** : 1 dossier par jour, théorie (recherche) + pratique (fichier Excel)
- 🧭 **Programme source** : bootcamp ami (template Notion) — contenu recopié jour par jour dans ce repo
- 🧑‍🏫 **Coaching complémentaire** : sessions avec Claude pour approfondir chaque notion avec des cas métier réalistes (jeux de données volumineux, pas d'exemples jouets) et faire le lien avec Pandas/SQL
- 💻 **Environnement** : Windows + Excel (basculé depuis Linux pour ce projet) + Git Bash + VS Code

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

| Jour | Thème | Statut |
|:----:|-------|:------:|
| 01 | Environnement & références (relative / absolue / mixte) | 🔄 En cours |
| 02 | *(à venir)* | ⬜ |
| 03 | *(à venir)* | ⬜ |
| 04 | *(à venir)* | ⬜ |
| 05 | *(à venir)* | ⬜ |
| ... | ... | ⬜ |
| 30 | *(à venir)* | ⬜ |

Légende : ⬜ à faire · 🔄 en cours · ✅ terminé · ⏭️ sauté (à rattraper)

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
