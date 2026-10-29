# Commande 3 — Inspiration et choix d'un template

> Étape 3 : remplir `3_inspiration/` en regardant ce qui existe, puis choisir **un seul template** à télécharger pour la production.
> Principe : on n'invente pas le design. On regarde, on note ce qui nous parle, on retient 1 template.

## Objectif

Construire un dossier `3_inspiration/` qui contient :
- des **liens vers des sites exemples** (artistes, intermittents, métier similaire)
- une **fiche par site** remplie avec la grille de lecture
- **un template HTML** téléchargé (un seul) + sa fiche
- une **synthèse "ce que je veux / ne veux pas"**

## Flow (important)

```
Fouille large (5-10 templates/sites vus en ligne)
    ↓
Fiches sur les 2-3 qui plaisent le plus (grille de lecture)
    ↓
1 template téléchargé pour la production
```

On regarde large, on note serré, on télécharge un seul. Le participant apprend à regarder (pédagogie) sans se noyer dans 3 templates à adapter en parallèle (friction). Les 2 fiches non retenues restent en réserve.

## Quand lancer cette commande

Après la commande 2 (contenu prêt), avant la production (commande 4).

## Sources pour fouiller

### Templates HTML gratuits

| Source | URL | Pourquoi | Friction |
|---|---|---|---|
| **Aura.build** | aura.build/browse/components/free-templates | Moderne, pro, original. Export HTML/CSS possible. Templates créatifs (studios, ateliers, culture...) | **Compte gratuit requis** pour exporter |
| **HTML5UP** | html5up.net | Référence solide, responsive, CC BY 3.0 (crédit à conserver). Templates variés | Téléchargement direct, aucun compte |
| **Freefolio** | github.com/OSSPhilippines/freefolio | Pur HTML/CSS, MIT, zéro build. Templates créatifs (Aurora, Flower, Outlines...) | Un peu geek, à garder en réserve |
| **FreeHTML5** | freehtml5.co | Correct, templates responsive | Téléchargement direct |

### Sites exemples (à chercher soi-même)

Chercher des sites d'artistes/compagnies/intermittents du spectacle, dans le même univers que ton projet. Pas besoin d'en trouver 20 : 5 à 10 suffisent pour se forger un regard.

## Grille de lecture d'un site/template

Pour chaque site ou template regardé, remplir la grille (note 1-5 ou commentaire libre) :

| Critère | Question à se poser | Note / Commentaire |
|---|---|---|
| **Ton** | Sérieux, ludique, poétique, institutionnel ? Correspond à mon projet ? | |
| **Couleurs** | Palette, contraste, ambiance. Plutôt sobre ou coloré ? | |
| **Typo** | Lisible, avec caractère, taille confortable. Une typo ou deux ? | |
| **Disposition** | Une colonne, plusieurs, sections claires, menu simple, footer présent ? | |
| **Lisibilité mobile** | Sur téléphone, ça reste lisible ? | |
| **Place des images** | Grande place, petite, galerie, hero image ? | |
| **Adaptabilité** | Facile à adapter pour mon métier ? | |
| **Friction** | Y a-t-il des trucs qui me dérangent (trop corporate, trop complexe...) ? | |

Pour les sites exemples (pas templates) : même grille, en ajoutant "Est-ce que je veux m'en inspirer pour mon site ?"

## La commande (à donner à l'IA)

```
On va remplir le dossier « 3_inspiration/ ».

Étape A — Sites exemples
À partir de mon métier et de mon contenu (dans 2_contenu/), propose-moi 5 à 10 sites
d'artistes/intermittents dont le style pourrait me correspondre. Pour chaque site,
dis-moi pourquoi tu le proposes. Je les regarde et je te dis lesquels je garde.

Pour chaque site gardé, crée une fiche dans 3_inspiration/sites/<nom-du-site>.md
avec la grille de lecture remplie.

Étape B — Templates HTML
Je vais fouiller sur les banques de templates (Aura.build, HTML5UP, Freefolio, FreeHTML5).
Je te donne les 2-3 templates qui me plaisent le plus. Pour chacun, tu crées une
fiche dans 3_inspiration/templates/<nom>.md avec la grille de lecture remplie.

Je choisis ensuite UN seul template à télécharger. Tu le télécharges dans
3_inspiration/templates/<nom>/ (fichiers HTML/CSS).

Étape C — Synthèse
À la fin, tu rédiges 3_inspiration/synthese.md :
- Ce que je veux (ton, couleurs, typo, disposition, sections...)
- Ce que je ne veux pas
- Le template retenu et pourquoi
```

## Ce que produit cette commande

| Livrable | Où |
|---|---|
| Fiches sites exemples (grille remplie) | `3_inspiration/sites/<nom>.md` |
| Fiches templates (grille remplie) | `3_inspiration/templates/<nom>.md` |
| 1 template téléchargé | `3_inspiration/templates/<nom>/` (fichiers HTML/CSS) |
| Synthèse "ce que je veux" | `3_inspiration/synthese.md` |

## Critères de réussite
- Au moins 3 fiches sites complétées avec la grille
- Au moins 2 fiches templates remplies avec la grille
- **1 template téléchargé** (un seul)
- Une synthèse "ce que je veux / ne veux pas" rédigée à la fin

## Pièges
- Trop de sites = noyade. 5 à 10 vus, on en garde 3 à 5 en fiches.
- Télécharger plusieurs templates "pour comparer" : non. On regarde, on note, on en télécharge **un seul**.
- Télécharger un template sans le regarder = non. On le feuillette, on remplit la grille.
- **Aura.build demande un compte gratuit** pour exporter en HTML. Le créer prend 2 min, c'est noté dans la fiche.
- Oublier la licence : les templates gratuits ont souvent une licence à respecter (crédit HTML5UP à conserver par exemple), on la note dans la fiche.
