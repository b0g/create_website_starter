# Commande 4 — Production du site avec l'IA

> Étape 4 : co-créer le site en pur HTML dans `4_production/`, en itératif (V1, V2...).
> Principe : l'IA propose, l'utilisateur valide ou demande des ajustements. On itère version par version, on ne cherche pas le one-shot parfait.

## Objectif

Générer dans `4_production/` une première version du site (V1) en pur HTML statique, basée sur `2_contenu/` + `3_inspiration/`. Puis itérer (V2, V3...) jusqu'à satisfaction.

## Quand lancer cette commande

Après les commandes 2 et 3 (contenu prêt + inspiration prête).

## La commande (à donner à l'IA)

```
On va créer mon site dans « 4_production/ ».

Sources :
- 2_contenu/ : tout ce qui va sur le site
- 3_inspiration/ : le style, les sites exemples, les templates choisis
- Le site doit être en PUR HTML statique (pas d'Astro, pas de build).
- Tu n'as pas à modifier 2_contenu/ ni 3_inspiration/, tu lis et tu produis dans 4_production/.

Crée 4_production/V1/ avec :
- index.html (page d'accueil)
- Une page HTML par section (À propos, Projets, Contact...)
- Un dossier assets/ pour CSS, images, JS si besoin
- Un style cohérent avec ce qu'on a noté dans 3_inspiration/synthese.md

Avant de générer, fais-moi valider :
1. La liste des pages et leur ordre dans le menu
2. Le choix technique de base (un seul fichier CSS ou un par page, typo web safe
   ou Google Fonts, framework CSS léger ou css pur)

Une fois validé, génère V1. Ensuite on itère.
```

## Itérations typiques après V1

```
V1 : structure + contenu brut + style de base
V2 : ajustements de couleurs / typo / marges
V3 : ajout de sections manquantes (calendrier, vidéos...)
V4 : responsive (mobile / tablette)
V5 : polish, micro-interactions, liens, footer
```

Pour chaque itération, l'utilisateur dit ce qui ne va pas, l'IA propose une V suivante dans un nouveau dossier `4_production/V2/` (ou en modifiant V1 si l'utilisateur préfère).

## Ce que produit cette commande

| Livrable | Où |
|---|---|
| Site V1 (HTML + CSS + assets) | `4_production/V1/` |
| Versions suivantes | `4_production/V2/`, `V3/`... |
| Décisions techniques notées | `4_production/_decisions.md` |

## Critères de réussite (V1)
- Toutes les pages validées sont présentes
- Tout le contenu de `2_contenu/` est utilisé (pas de projet oublié)
- Le site s'ouvre en double-clic sur `index.html` (test Windows)
- Responsive basique (ça passe sur mobile)

## Barrière technique à surveiller
- **Carte Leaflet en pur HTML** : si on en a besoin, tester en local avec `python -m http.server` (le double-clic `index.html` casse le fetch sur Windows). Prévoir un `.bat` cliquable ou servir via un mini serveur local.

## Pièges
- L'IA qui change le contenu pour "améliorer" : non, on respecte ce qui est dans `2_contenu/`.
- L'IA qui veut ajouter un build (Astro, Vite...) : non, on reste en HTML pur. C'est un choix assumé du projet.
- Vouloir tout régler en V1 : non, on itère. V1 = structure + contenu, le style se raffine après.
- Oublier de tester en double-clic `index.html` sur Windows avant de dire "V1 finie".
