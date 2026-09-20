# Commande 5 — Autonomie : mettre à jour et revenir en arrière

> Étape 5 : vérifier que le participant peut mettre à jour son site **seul**, avec ou sans IA.
> Principe : c'est le test ultime de la promesse pédagogique. Si on ne peut pas mettre à jour seul, l'atelier a échoué.

## Prérequis

- **Git installé** sur l'ordinateur (vérifier : `git --version` dans un terminal)
- **Compte GitHub** configuré (le repo du site existe déjà)
- **Le repo cloné en local** : `git clone <url-du-repo>` (une fois, au début)
- OU accès à l'interface web GitHub (si pas de git local)

## Objectif

Tester 3 gestes que le participant fera dans la vraie vie :
1. **Modifier un texte** (changer un mot, une date, une info)
2. **Ajouter quelque chose** (un projet, un événement, une image)
3. **Revenir en arrière** si quelque chose casse

À la fin, le participant sait refaire ces 3 gestes **sans la doc sous les yeux**.

---

## Test 1 — Modifier un texte

### Méthode sans IA (tutoriel pas-à-pas)

1. Ouvrir le fichier HTML dans un éditeur de texte (Bloc-notes Windows, TextEdit Mac, ou VS Code)
2. Modifier le texte (ex: changer un mot dans la section À propos)
3. Sauvegarder le fichier
4. Dans un terminal, à la racine du repo :
```bash
git add .
git commit -m "Modifie le texte de la section À propos"
git push
```
5. Attendre 1-2 min, Cloudflare Pages re-déploie automatiquement
6. Vérifier sur le site en ligne : le texte est changé

### Méthode avec IA (prompt à copier-coller)

```
Je veux modifier le texte suivant sur mon site : [texte actuel] → [nouveau texte].
Dis-moi exactement quel fichier ouvrir, quelle ligne modifier, et donne-moi les
commandes git pour pousser la mise à jour.
```

---

## Test 2 — Ajouter quelque chose

### Méthode sans IA (tutoriel pas-à-pas)

1. **Ajouter une image** : placer le fichier image dans `assets/images/` (compresser avant si > 1 MB)
2. **Modifier le HTML** : dupliquer la section la plus proche du format voulu
   - Pour un atelier : dupliquer un bloc `<details class="atelier">...</details>`
   - Pour un événement : ajouter une ligne dans la section agenda
3. Adapter le contenu (titre, description, image)
4. Pousser :
```bash
git add .
git commit -m "Ajoute [nom de l'élément]"
git push
```
5. Vérifier en ligne

### Méthode avec IA (prompt à copier-coller)

```
Je veux ajouter [description de l'élément] sur mon site.
Voici le contenu : [texte/images].
Guide-moi pour : modifier le HTML, où placer l'élément, et pousse la mise à jour
avec git. Dis-moi chaque étape avant de la faire.
```

---

## Test 3 — Revenir en arrière

C'est le morceau qui rassure le plus. **3 méthodes**, de la plus simple à la plus manuelle.

### Méthode A — Via le site web GitHub (recommandé, le plus simple)

1. Aller sur la page GitHub du repo, onglet **Commits** (history)
2. Repérer le commit qui a cassé quelque chose
3. Cliquer sur les **...** à droite du commit → **Revert**
4. GitHub crée un commit inverse automatiquement
5. Le site re-déploie le contenu d'avant

**Avantage** : pas de terminal, pas de risque, git gère tout.

### Méthode B — En CLI avec git revert (sûre, crée un commit inverse)

```bash
# Voir l'historique des commits
git log --oneline -5

# Annuler le dernier commit (crée un commit inverse, n'efface rien)
git revert HEAD

# Pousser
git push
```

**Avantage** : sûr, l'historique est conservé.

### Méthode C — En CLI avec git reset (plus direct, écrase l'historique)

⚠️ **À utiliser avec précaution** : cette méthode réécrit l'historique. Pour un site perso, c'est acceptable. Pour un projet collaboratif, préférer la méthode A ou B.

```bash
# Revenir au commit d'avant le problème (le ~1 = commit précédent)
git reset --hard HEAD~1

# Forcer le push (nécessaire car on réécrit l'historique)
git push --force
```

**Pour revenir à un commit précis** (pas forcément le précédent) :
```bash
git log --oneline -10          # voir l'historique
git reset --hard <sha-du-commit>   # remplacer par le sha choisi
git push --force
```

### Méthode avec IA (prompt à copier-coller)

```
J'ai cassé quelque chose sur mon site avec mon dernier commit.
Aide-moi à revenir en arrière :
1. Montre-moi l'historique des commits récents
2. Propose-moi la méthode la plus simple pour annuler
3. Si j'utilise git reset --hard, rappelle-moi les précautions
```

---

## Test rapide de validation (à faire à la fin)

Pour vérifier que tout le monde sait le faire :

1. **Supprimer** volontairement une section (ex: la section Agenda)
2. Commit + push → vérifier en ligne qu'elle a disparu
3. **Revenir en arrière** avec la méthode de son choix (A, B ou C)
4. Vérifier en ligne que la section est revenue

Si les 4 étapes passent : le participant est autonome.

---

## Critères de réussite

- L'utilisateur a fait les 3 gestes **sans que l'IA tape à sa place** (méthode sans IA)
- L'utilisateur sait refaire chaque geste sans la doc sous les yeux
- Le retour arrière a été testé au moins une fois (idéalement méthode A pour la simplicité)

## Pièges

- L'IA qui tape à la place de l'utilisateur pendant le test : non, c'est un test d'autonomie.
- Oublier de tester le retour arrière : c'est le morceau qui rassure le plus, on ne le saute pas.
- Ne pas vérifier en ligne après chaque commit : on attend le déploiement Cloudflare (1-2 min) avant de valider.
- `git push --force` sans réfléchir (méthode C) : si on se trompe de commit, on peut perdre du travail. Toujours `git log --oneline` avant.
- Modifier le repo directement sur GitHub web (sans pull local avant) : risque de conflit. Toujours pull avant de push.
- Oublier `git add .` avant le commit : rien n'est poussé.


