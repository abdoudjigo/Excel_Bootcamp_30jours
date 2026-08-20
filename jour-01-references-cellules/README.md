# Jour 01 — Environnement et références

## 🎯 Objectifs
Comprendre le fonctionnement des cellules, plages, classeurs/feuilles, et surtout
maîtriser les 3 types de références (relative, absolue, mixte) et leur comportement
lors de la recopie d'une formule — la base de toute formule Excel un peu sérieuse.

---

## 📖 Partie théorique — Recherche

Réponds ici en 1-3 phrases par question (pas besoin d'être exhaustif, l'important
c'est que tu puisses réexpliquer avec tes mots) :

1. Qu'est-ce qu'une cellule dans un tableur Excel ?
   > _réponse_

2. Qu'est-ce qu'une plage de cellules ?
   > _réponse_

3. Quelle est la différence entre un classeur et une feuille de calcul ?
   > _réponse_

4. Qu'est-ce qu'une référence relative et comment se comporte-t-elle lors de la recopie d'une formule ?
   > _réponse_

5. Qu'est-ce qu'une référence absolue, quel symbole l'identifie, et quel est son comportement lors de la recopie ?
   > _réponse_

6. Qu'est-ce qu'une référence mixte ? Quelle est la différence de comportement entre `$A1` et `A$1` ?
   > _réponse_

7. À quoi sert la poignée de recopie (recopie incrémentée) ?
   > _réponse_

8. Dans quel cas pratique est-il indispensable d'utiliser une référence absolue ?
   > _réponse_

9. Dans quel cas pratique est-il utile d'utiliser une référence mixte ?
   > _réponse_

---

## 🧪 Partie pratique — Exercices

Fichier de travail : `exercices/jour01_references.xlsx`
(1 onglet par exercice, ou 1 fichier par exercice — à toi de voir, mais reste cohérent)

- [ ] **1. Référence relative** — série A1:A5 / B1:B5, `=A1+B1` étiré sur C1:C5.
      Qu'observe-t-on dans C2 à C5 ?
      > _réponse_

- [ ] **2. Référence absolue** — coefficient en D1, `=A1*$D$1` étiré horizontalement et verticalement.
      Que devient `$D$1` partout où on le recopie ?
      > _réponse_

- [ ] **3. Références mixtes** — table de multiplication avec `=$A2*B$1` étirée sur B2:E5.
      Rôle du `$` devant la colonne vs devant la ligne ?
      > _réponse_

- [ ] **4. Sous-total (5 produits, Prix HT × Quantité)** — quel type de référence as-tu utilisé et pourquoi c'est le seul adapté ?
      > _réponse_

- [ ] **5. Taux de TVA fixe** — `=D2*(1+H1)` vs `=D2*(1+$H$1)` étirés. Pourquoi `$H$1` est obligatoire ici ?
      > _réponse_

- [ ] **6. Matrice de sensibilité TVA (J1:L1 = 10%/20%/30%)** — une seule formule mixte en J2 étirée sur J2:L6.
      Formule exacte utilisée (avec les `$`) :
      > `=...`

- [ ] **7. Raccourci F4** — bascule entre les 4 modes de référence.
      Ordre exact des bascules :
      > _réponse_

- [ ] **8. Figer des valeurs aléatoires** — `=ENT(ALEA()*10)+1`, puis Collage spécial → Valeurs.
      Pourquoi ça change à chaque F9, et quelle opération fige les valeurs ?
      > _réponse_

---

## ⚠️ Points de friction / erreurs commises

> À remplir en fin de journée : ce qui t'a bloqué, ce que tu as mal compris au début,
> les pièges dans lesquels tu es tombé. C'est cette section qui a le plus de valeur
> pour toi dans 2 semaines.

- ...

---

## ✅ Checklist fin de journée

- [ ] Les 9 questions théoriques ont une réponse dans mes propres mots
- [ ] Les 8 exercices pratiques sont faits dans `exercices/jour01_references.xlsx`
- [ ] La section "points de friction" est remplie
- [ ] Le tableau de progression du README principal est mis à jour (🔄 → ✅)
- [ ] `git add . && git commit -m "Jour 01 : références relatives, absolues et mixtes" && git push`
