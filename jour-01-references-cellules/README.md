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
   l'intersection d'une ligne et d'une colonne (ex: B4), unité de base qui contient une valeur, une formule ou du texte.

2. Qu'est-ce qu'une plage de cellules ?
   un ensemble contigu de cellules, notée début:fin (ex: A1:C5). Sert à appliquer une formule ou une mise en forme à plusieurs cellules d'un coup.

3. Quelle est la différence entre un classeur et une feuille de calcul ?
   le classeur (.xlsx) est le fichier entier, il peut contenir plusieurs feuilles (onglets en bas). Une feuille = un seul tableau/espace de travail à l'intérieur du classeur. Équivalent Pandas : un classeur ≈ un fichier Excel avec plusieurs sheet_name, une feuille ≈ un seul DataFrame.

4. Qu'est-ce qu'une référence relative et comment se comporte-t-elle lors de la recopie d'une formule ?
   change automatiquement quand tu recopies la formule, en fonction du décalage. Si =A1+B1 en C1 devient =A2+B2 en C2 — c'est le comportement par défaut.

5. Qu'est-ce qu'une référence absolue, quel symbole l'identifie, et quel est son comportement lors de la recopie ?
   le $ fige la colonne ET la ligne. Peu importe où tu recopies la formule, elle continue de pointer vers exactement la même cellule.
   

6. Qu'est-ce qu'une référence mixte ? Quelle est la différence de comportement entre `$A1` et `A$1` ?
   Un seul des deux éléments est figé. $A1 fige la colonne A (mais la ligne bouge), A$1 fige la ligne 1 (mais la colonne bouge). Le $ juste avant la lettre bloque la colonne, juste avant le chiffre bloque la ligne.

7. À quoi sert la poignée de recopie (recopie incrémentée) ?
   le petit carré en bas à droite de la cellule sélectionnée. Tu cliques-glisses dessus pour dupliquer une formule (ou continuer une série comme 1,2,3...) sur plusieurs cellules sans retaper.

8. Dans quel cas pratique est-il indispensable d'utiliser une référence absolue ?
   quand une formule doit toujours pointer vers une seule valeur fixe partagée par toutes les lignes — typiquement un taux de TVA, un taux de change, ou un coefficient unique en haut du tableau. Si tu laisses en relatif, la référence "glisse" et va chercher une cellule vide ou fausse dès la 2e ligne → #VALEUR! ou résultat à 0.

9. Dans quel cas pratique est-il utile d'utiliser une référence mixte ?
   les tableaux à double entrée (matrices), genre une table de multiplication ou un tableau de sensibilité (ex: prix selon plusieurs taux de TVA en colonnes ET plusieurs produits en lignes). Tu veux que la ligne reste fixe quand tu étires horizontalement, et que la colonne reste fixe quand tu étires verticalement — une seule formule mixte couvre toute la matrice.

---

## 🧪 Partie pratique — Exercices

Fichier de travail : `exercices/jour01_references.xlsx`
(1 onglet par exercice, ou 1 fichier par exercice — à toi de voir, mais reste cohérent)

- [ ] **1. Référence relative** — série A1:A5 / B1:B5, `=A1+B1` étiré sur C1:C5.
      Qu'observe-t-on dans C2 à C5 ?
      > _réponse_ : Dans C2 on voit =A2+B2, dans C3 =A3+B3, etc. Les références de lignes s'ajustent automatiquement car elles sont relatives.

- [ ] **2. Référence absolue** — coefficient en D1, `=A1*$D$1` étiré horizontalement et verticalement.
      Que devient `$D$1` partout où on le recopie ?
      > _réponse_ :  $D$1 reste toujours $D$1 dans toutes les cellules recopiées, que ce soit vers le bas ou vers la droite. Elle est complètement figée.

- [ ] **3. Références mixtes** — table de multiplication avec `=$A2*B$1` étirée sur B2:E5.
      Rôle du `$` devant la colonne vs devant la ligne ?
      > _réponse_ :  Le $ devant la colonne ($A) bloque la colonne A, donc elle ne change pas quand on étire vers la droite. Le $ devant la ligne ($1) bloque la ligne 1, donc elle ne change pas quand on étire vers le bas.


- [ ] **4. Sous-total (5 produits, Prix HT × Quantité)** — quel type de référence as-tu utilisé et pourquoi c'est le seul adapté ?
      > _réponse_ : J'ai utilisé des références relatives (=B2*C2). C'est le seul choix adapté parce qu'en étirant vers le bas, chaque ligne prend ses propres valeurs (Prix HT et Quantité de la même ligne).

- [ ] **5. Taux de TVA fixe** — `=D2*(1+H1)` vs `=D2*(1+$H$1)` étirés. Pourquoi `$H$1` est obligatoire ici ?
      > _réponse_ : $H$1 est obligatoire car le taux de TVA est unique et doit rester le même pour toutes les lignes. Avec H1 (relative), en étirant vers le bas la formule deviendrait =D3*(1+H2) puis =D4*(1+H3)... donc elle irait chercher des cellules vides.

- [ ] **6. Matrice de sensibilité TVA (J1:L1 = 10%/20%/30%)** — une seule formule mixte en J2 étirée sur J2:L6.
      Formule exacte utilisée (avec les `$`) :
      > `==$D2*(1+J$1)`


- [ ] **7. Raccourci F4** — bascule entre les 4 modes de référence.
      Ordre exact des bascules :
      > _réponse_ : A1 → $A$1 → A$1 → $A1 → puis retour à A1

- [ ] **8. Figer des valeurs aléatoires** — `=ENT(ALEA()*10)+1`, puis Collage spécial → Valeurs.
      Pourquoi ça change à chaque F9, et quelle opération fige les valeurs ?
      > _réponse_ :  Les valeurs changent à chaque F9 parce que ALEA() est une fonction volatile qui donne un nouveau nombre aléatoire à chaque recalcul.L'opération qui fige les valeurs est le Collage spécial → Valeurs. Elle remplace les formules par leurs résultats fixes, utiles pour des rapports ou tirages au sort.

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
