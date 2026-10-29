# Repo starter — Atelier création de sites internet avec l'IA

> Ce dépôt est le point de départ pour créer ton site internet toi-même, avec ou sans IA. Tu le clones, tu remplis tes dossiers, tu publies. Chaque étape a son numéro, son dossier et son tutoriel pas-à-pas (sans IA) doublé d'un prompt prêt à coller (avec IA), dans `0_documentation/`. À la fin, tu sais refaire, avec ou sans l'IA.

## Structure

Les numéros disent l'ordre. Un dossier = une étape ; `0_documentation/` contient le mode d'emploi de chacune.

```
repo_starter/
├── 0_documentation/    ← Les 6 étapes : tutoriel + prompt IA
│   ├── 01_import.md
│   ├── 02_contenu.md
│   ├── 03_inspiration.md
│   ├── 04_production.md
│   ├── 05_deploiement.md
│   └── 06_autonomie.md
├── 1_import/           ← À remplir : ta matière brute en vrac (images, textes, PDFs)
├── 2_contenu/          ← À remplir : toutes les infos du site, rangées
├── 3_inspiration/      ← À remplir : sites exemples + template choisi
├── 4_production/       ← À remplir : les versions du site
└── skills/             ← Prompts IA prêts à coller
```

Deux étapes n'ont pas de dossier parce qu'elles se passent en ligne : le déploiement (05) et l'autonomie (06).

## Le parcours

1. **Remplir le vrac** (`0_documentation/01`) — déposer la matière dans `1_import/`
2. **Préparer le contenu** (`0_documentation/02`) — ranger et compléter dans `2_contenu/`
3. **S'inspirer** (`0_documentation/03`) — trouver un template dans `3_inspiration/`
4. **Produire le site** (`0_documentation/04`) — co-créer avec l'IA dans `4_production/`
5. **Déployer** (`0_documentation/05`) — mettre en ligne via GitHub + Cloudflare Pages
6. **Être autonome** (`0_documentation/06`) — mettre à jour et revenir en arrière

## Principe pédagogique

Chaque étape est livrée en doublon :
- Un **tutoriel pas-à-pas** (sans IA) dans `0_documentation/`
- Un **prompt IA** (avec IA) dans la section "La commande (à donner à l'IA)" du même fichier

Le participant reste maître : avec ou sans IA, il sait refaire. À la fin du stage, il repart avec cette documentation complète.

## Prérequis techniques

- Un ordinateur (Windows, Mac ou Linux)
- Git installé (`git --version` doit répondre)
- Un compte GitHub (gratuit)
- Un compte Cloudflare (gratuit)
- OpenCode installé : https://opencode.ai
- Un accès IA, à ta charge et à l'usage (quelques euros suffisent, pas d'abonnement obligatoire) :
  - **GreenPT** (recommandé) : https://www.greenpt.com — inférence en Europe, énergie renouvelable, tes données ne servent pas à entraîner les modèles. Tu colles ta clé API, le modèle apparaît, rien à configurer.
  - Modèle conseillé si tu ne sais pas quoi prendre : **DeepSeek V4.1 Flash**.
  - (Tips radin peu scrupuleux : Opencode à un modèle **DeepSeek V4.1 Flash Free**, mais quand c’est gratuit ... C’est toi le produit)
- Murmure (dictée vocale), si tu veux l'utiliser, c’est super cool : https://murmure.al1x-ai.com
- Un nom de domaine (optionnel — l'URL `*.pages.dev` gratuite suffit pour commencer), va chez Cloudflare pour que ça soit facile à configurer avec Cloudflare pages ensuite.

## Confidentialité

`1_import/`, `2_contenu/` et `3_inspiration/` sont exclus du dépôt git (voir `.gitignore`) : seule la version publiée dans `4_production/` part sur GitHub. Tes contenus privés restent sur ta machine. 