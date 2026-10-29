# Commande 2 — Préparer le dossier 2_contenu/

> Étape 2 : à partir de tout ce qui est dans `1_import/` (en vrac), produire un dossier `2_contenu/` complet, structuré, prêt à alimenter le site.
> Principe : **le quoi avant le comment**. L'IA lit, propose, questionne ; l'utilisateur valide ; l'IA exécute. Un seul cycle, pas de va-et-vient.

## Objectif

Transformer le vrac de `1_import/` en dossier `2_contenu/` :
- **complet** (rien d'important oublié)
- **structuré** (mêmes règles pour tout le monde)
- **clair** (l'IA n'aura plus aucune question métier à poser au moment de produire le site)

L'utilisateur ne trie pas à la main. L'IA ne range pas dans le vide. On fait un cycle : lecture → proposition → questions → validation → exécution → bilan.

## Quand lancer cette commande

Dès que `1_import/` contient la matière en vrac (images, textes, PDFs, liens).

## La commande (à donner à l'IA)

```
Je veux préparer le dossier « 2_contenu/ » de mon site à partir de tout ce qui est
dans « 1_import/ ».

Avant de créer ou déplacer quoi que ce soit, fais-moi valider en 3 temps.

ÉTAPE A — Lecture + dispatch proposé
Lis tout ce qui est dans 1_import/. Avant de proposer le dispatch, détermine la
structure de 2_contenu/ en posant les bonnes questions :

1. DÉTECTION DU TYPE DE SITE (pose-moi la question, ne suppose pas) :
   - Un seul projet avec des composantes (ateliers, prestations, formats...) ?
     → structure avec `ateliers/` (ou `formats/`, `prestations/` selon le métier)
   - Plusieurs projets indépendants (portfolio, artiste avec plusieurs œuvres) ?
     → structure avec `projects/` (1 dossier par projet)
   - Un autre cas ? Décris-le moi et propose la structure.

2. FILTRE AUTOMATIQUE (écarte sans me demander, mais dis-le) :
   - Fichiers contenant du contexte technique interne (serveurs, sync, config,
     architecture, logbook, notes de fonctionnement) → archive, pas pour le site.
   - Doublons (deux fichiers au contenu quasi identique) → garde le plus complet,
     archive l'autre. Signale-le.

3. POUR CHAQUE FICHIER RESTANT :
   - Identifie ce que c'est (texte de présentation, photo, fiche technique,
     lien vidéo, contacts, atelier, dossier poétique...)
   - Propose où il doit aller dans 2_contenu/ selon la structure détectée.
   - Si un fichier est ambigu, marque-le « à clarifier ».

ÉTAPE B — Questions de complétion
Vérifie point par point qu'on a bien :
1. L'IDENTITÉ — nom/prénom, métier, nom de scène si différent, texte de
   présentation (court + long), photo de profil.
2. LES PROJETS — liste des projets (1 dossier par projet), pour chacun : titre,
   description, images, éventuel lien externe (vidéo, article...).
3. LES CONTACTS — email de contact, réseaux sociaux (Instagram, YouTube,
   LinkedIn, TikTok, Facebook...), ville / zone d'action, disponibilités.
4. LES FICHES TECHNIQUES / SERVICES — ce que je propose à mes clients
   (prestations, tarifs éventuels, démarche).
5. LES MÉDIAS — images exploitables vs floues/à retirer, dossiers de
   présentation, liens vidéos YouTube.
6. LES SECTIONS / PAGES — Accueil, À propos, Projets, Contact... Quelles pages,
   dans quel ordre.

Pour chaque point : dis-moi ce qui est OK, ce qui manque, ce qui est flou.
Pose-moi les questions une par une, pas toutes d'un coup.

ÉTAPE C — Plan d'action
Une fois mes réponses validées :
1. Liste-moi exactement ce que tu vas faire (déplacer X vers Y, créer Z, renommer W).
2. Je valide le plan.
3. Tu exécutes : tu déplaces les fichiers de 1_import/ vers 2_contenu/, tu crées
   les sous-dossiers nécessaires, tu écartes les images floues.
4. Tu ne supprimes rien, tu ne crées rien, tu ne complètes pas mes textes.

À la fin, tu me donnes un bilan :
- Ce qui est prêt pour la production
- Ce qui reste à compléter (par ordre de priorité)
- Ce qui a été écarté et pourquoi

Tu ne touches pas encore au site.
```

## Ce que produit cette commande

| Livrable | Où |
|---|---|
| Plan de dispatch + questions de complétion | à l'écran, pour validation |
| Dossier `2_contenu/` complet et structuré | `2_contenu/` |
| Dossier `1_import/` vidé ou archivé | `1_import/` |
| Bilan de complétion | à l'écran |

## Critères de réussite
- Chaque projet a son dossier + ses images
- Contacts complets (email + tous les réseaux sociaux + ville)
- Un texte de présentation en 2 tailles (court pour accueil, long pour À propos)
- Les images floues sont écartées, pas conservées par politesse
- Aucune question métier laissée ouverte pour l'étape production
- `1_import/` est vide à la fin

## Pièges
- L'IA qui génère du contenu à la place de l'utilisateur : non, elle ne fait que ranger et questionner.
- L'IA qui suppose la structure (projects/ vs ateliers/) sans demander : non, elle pose la question et propose selon ce qu'elle voit dans 1_import/.
- Conserver des fichiers techniques internes (serveurs, sync, logbook) : non, on les écarte automatiquement, le site est public.
- Garder un doublon "au cas où" : non, on garde le plus complet et on archive l'autre.
- Les images non nommées (`IMG_1234.jpg`) : demander à l'utilisateur ce qu'elles représentent avant de les ranger.
- Les PDFs sans contexte : demander s'ils sont publics (à mettre en ligne) ou privés (à garder pour info).
- Conserver des images floues "au cas où" : non, on les écarte maintenant.
- Garder un projet "en attendant" : si on n'a pas la matière, on ne le met pas sur le site.
- **Images lourdes (> 25 MB)** : refusées par Cloudflare Pages. Redimensionner à max 2000 px de large + compresser en JPG/WebP qualité 80 avant de ranger dans 2_contenu/medias/. Objectif : < 1 MB par photo pour que le repo GitHub reste léger.
- Trop de questions d'un coup : l'utilisateur se noie. On pose par bloc, on valide, on continue.
