# Commande 4 — Déploiement sur GitHub + Cloudflare Pages

> Étape 4 : mettre le site en ligne via GitHub + Cloudflare Pages, avec un nom de domaine propre.
> Principe : le site vit dans un repo GitHub, Cloudflare Pages le déploie automatiquement à chaque commit. Pas de serveur à maintenir.

## Objectif

1. Créer un repo GitHub contenant le site (depuis la version finale de `production/`).
2. Brancher Cloudflare Pages sur ce repo → déploiement automatique.
3. Brancher un nom de domaine propre.

## Quand lancer cette commande

Après la commande 3, quand une version de `production/` est validée comme "version à mettre en ligne".

## La commande (à donner à l'IA)

```
Je veux mettre en ligne la version <VX> de production/.

Étape A — Préparation du repo
1. Liste-moi exactement les fichiers/dossiers à envoyer sur GitHub (et ceux à
   exclure : contenu/, import/, inspiration/, versions précédentes...).
2. Crée un .gitignore à la racine du repo pour exclure ce qui n'est pas public.
3. Valide avec moi la structure du repo GitHub avant de pousser.

Étape B — Création du repo GitHub
4. Dis-moi la commande pour créer le repo (depuis l'interface GitHub ou en CLI).
5. Donne-moi les commandes git pour initier le repo, premier commit, push.

Étape C — Branchement Cloudflare Pages
6. Donne-moi les étapes pour connecter le repo à Cloudflare Pages (compte,
   autorisations, choix de la branche, dossier de build = aucun, dossier de
   sortie = /).
7. Une fois branché, vérifie que le site est accessible sur l'URL Cloudflare
   (*.pages.dev).

Étape D — Nom de domaine
8. Donne-moi les étapes pour brancher un nom de domaine : registrar, DNS
   (CNAME vers *.pages.dev), propagation, vérification.

Ne fais rien sans me demander de valider à chaque étape. C'est moi qui clique
sur GitHub et Cloudflare, tu me guides.
```

## Ce que produit cette commande

| Livrable | Où |
|---|---|
| Repo GitHub du site | github.com/<user>/<site> |
| Site déployé sur Cloudflare Pages | `<projet>.pages.dev` |
| Nom de domaine branché | selon registrar |
| `.gitignore` | à la racine du repo |

## Critères de réussite
- Le site est visible sur l'URL `*.pages.dev`
- Le nom de domaine propre pointe bien vers le site (propagation DNS vérifiée)
- Un nouveau commit sur la branche principale re-déploie automatiquement le site

## Barrière technique à surveiller
- **Nom de domaine + DNS** : prévoir du temps, vérifier la propagation avec `dig` ou un outil en ligne (whatsmydns.net).
- **Compte GitHub** : à créer avant cette étape (gratuit).

## Pièges
- Pousser `contenu/` ou `import/` sur GitHub : non, c'est privé. Le `.gitignore` les exclut.
- Oublier de dire à Cloudflare Pages "pas de build" : on est en HTML pur, build = aucun, output = `/`.
- **Choisir Workers au lieu de Pages** dans l'interface Cloudflare : Pages est branché sur Git (auto-déploiement à chaque push), Workers non (déploiement manuel via wrangler). Vérifier l'URL : `*.pages.dev` = Pages (bon), `*.workers.dev` = Workers (pas ce qu'on veut).
- **Images > 25 MB** : refusées par Cloudflare Pages. Compresser avant le push (voir commande 01).
- Attendre la propagation DNS (peut prendre jusqu'à 24-48h, souvent quelques minutes) : on vérifie avant de dire "c'est en ligne".
- Supprimer les versions précédentes de production/ du repo : on garde l'historique via git, pas besoin de pousser V1, V2... sur GitHub.
