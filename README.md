# Wordatro Helper 🎮

**Trouveur de mots et calculateur de score pour Wordatro** — basé sur le dictionnaire officiel ODS8 (Scrabble francophone).

🔗 **[Ouvrir l'outil](https://ambrosinien.github.io/wordatro-helper/)**

---

## Fonctionnalités

### 🔍 Onglet Trouveur de mots
Trouve tous les mots jouables avec tes lettres, parmi les 168 000+ mots du dictionnaire ODS8.

- Saisie des lettres disponibles
- Support des jokers (wildcards)
- Filtres par longueur (4 à 9 lettres)
- Filtres "commence par" et "contient"
- Tri par longueur, score Scrabble ou ordre alphabétique

### 🎯 Onglet Calculateur de score
Calcule le score exact de chaque mot en tenant compte de toute la mécanique de Wordatro.

**Saisie de ta main :**
- Lettres avec leur valeur en points (modifiable)
- État de chaque lettre : Normal, Gras, Italique, Souligné, Jaune (J), Joker (*)
- Lettre spéciale § (point d'exclamation) : placée librement en début/fin de mot

**Barre de jeu :**
- 10 cases configurables
- Multi permanents par case (clic gauche +1, clic droit −1)
- Cases spéciales 5 (lettre verte 🟢), 7 (lettre jaune ⭐), 9 (énergie ⚡) colorées

**Formule de calcul :**
- `score = cumul_points × cumul_multi`
- Cumul lettre par lettre de gauche à droite
- **Gras** : points et multi de case × 2 (× 4 avec Extra Gras)
- **Italique** : +3 multi sur la case (permanent) — +5 avec bonus Horizontal
- **Souligné** : cumul_multi × 1.5 après la case (× 2 avec bonus Souligné+)
- **Lettre jaune** : vaut 10 pts, +5 pts permanents sur les futures lettres identiques
- **§** : vaut 10 pts, testée automatiquement en début et/ou fin de mot

**Optimisation automatique :**
- Si tu as un A gras et un A normal, le gras est placé sur la meilleure case (énergie > jaune > verte > multi italique)
- Les § sont testés dans toutes les combinaisons devant/derrière le mot

**Variantes :**
- Si plusieurs états sont possibles pour une même lettre (gras vs italique), le meilleur score est affiché
- Un badge ⚠️ indique le nombre de variantes — clic sur le mot pour les voir toutes

**Contexte mot précédent :**
- 1ère lettre et longueur du mot précédent (pour les bonus Déjà Vu, Jumeaux, Yo-yo)

### Bonus supportés (30+)

| Section | Bonus |
|---|---|
| **Points** | Consonne, Voyelle, Mot Long, Huit, P.O.I.N.T., Triple, Déjà Vu, Amélio. Spé., Stock Exchange, Jumeaux |
| **Multiplicateurs** | Boost, M.U.L.T., × Consonne, × Voyelle, Mot Court, Carré, Six, Horizontal, Stock, Économie, Servi, Yo-yo, Zorro, Cash Machine, Perec, Mimic |
| **Lettres** | Extra Gras, Souligné+, Dos au Mur |

Les bonus cumulatifs (Déjà Vu, Servi, Zorro...) ont un champ pour saisir leur valeur actuelle. Le calculateur affiche aussi la nouvelle valeur de ces bonus après le mot joué.

---

## Dictionnaire

Basé sur l'**ODS8** (Officiel du Scrabble, édition 8), la référence officielle du Scrabble francophone utilisée par Wordatro.

411 430 mots au total · 168 447 mots de 4 à 9 lettres indexés.

---

## Déploiement GitHub Pages

1. Fork ce repo
2. Va dans **Settings → Pages**
3. Source : **Deploy from a branch** → `main` → `/ (root)`
4. Ton site sera disponible sur `https://[ton-username].github.io/wordatro-helper/`

## Structure

```
wordatro-helper/
├── index.html   # Application principale
├── words.js     # Dictionnaire ODS8 (mots 4-9 lettres)
└── README.md
```

---

*Projet non officiel, non affilié à Wordatro! ou Abiding Bridge.*
