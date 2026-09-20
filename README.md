# Repo starter — Atelier création de sites internet avec l'IA

> Repo de départ fourni à chaque participant de l'atelier. À cloner et remplir.

## Structure

```
repo_starter/
├── documentation/      ← Tutoriels pas-à-pas (avec et sans IA) pour chaque étape
│   ├── 01_preparer_contenu.md
│   ├── 02_inspiration.md
│   ├── 03_production.md
│   ├── 04_deploiement.md
│   └── 05_autonomie.md
├── skills/             ← Prompts IA prêts à coller (renvoient vers la documentation)
│   └── README.md
├── import/             ← À remplir : ta matière brute en vrac (images, textes, PDFs) — étape 1
├── contenu/            ← À remplir : toutes les infos du site (étape 1)
├── inspiration/        ← À remplir : sites exemples + template (étape 2)
└── production/         ← À remplir : les versions du site (étape 3)
```

## Le parcours

1. **Préparer le contenu** (`documentation/01`) — structurer les infos dans `contenu/`
2. **S'inspirer** (`documentation/02`) — trouver un template dans `inspiration/`
3. **Produire le site** (`documentation/03`) — co-créer avec l'IA dans `production/`
4. **Déployer** (`documentation/04`) — mettre en ligne via GitHub + Cloudflare Pages
5. **Être autonome** (`documentation/05`) — mettre à jour et revenir en arrière

## Principe pédagogique

Chaque étape est livrée en doublon :
- Un **tutoriel pas-à-pas** (sans IA) dans `documentation/`
- Un **prompt IA** (avec IA) dans la section "La commande (à donner à l'IA)" du même fichier

Le participant reste maître : avec ou sans IA, il sait refaire. À la fin du stage, il repart avec cette documentation complète.

## Prérequis techniques

- Un ordinateur (Windows, Mac ou Linux)
- Git installé (`git --version` doit répondre)
- Un compte GitHub (gratuit)
- Un compte Cloudflare (gratuit)
- OpenCode installé + une clé OpenRouter (crédits à ta charge, quelques euros suffisent)
- Murmure (dictée vocale) si tu veux l'utiliser — 16 Go de RAM recommandés
- Un nom de domaine (optionnel — l'URL `*.pages.dev` gratuite suffit pour commencer)

## Confidentialité

`contenu/`, `inspiration/` et `import/` sont exclus du dépôt git (voir `.gitignore`) : seule la version publiée dans `production/` part sur GitHub. Tes contenus privés restent sur ta machine.
