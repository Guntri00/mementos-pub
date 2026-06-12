# Déploiement du site vitrine Mementos-Memorie

Site statique (HTML/CSS/JS, sans build) : `index.html` (landing) + `maquette.html` (démo) + `logo-memento.svg`.
Pas de domaine personnalisé → on utilise l'URL gratuite **`*.vercel.app`**.

Le dépôt git local est prêt (initialisé + premier commit). 2 étapes côté toi (authentification requise).

## 1. Pousser sur GitHub

Sur https://github.com/new : crée un dépôt **vide** (par ex. `mementos-pub`). Puis :

```bash
git remote add origin https://github.com/Guntri00/mementos-pub.git
git push -u origin main
```

> Dans cette session Claude Code, tu peux lancer la commande avec le préfixe `!` pour voir la sortie ici.

## 2. Importer dans Vercel

1. https://vercel.com/new → **Import** le dépôt `mementos-pub`.
2. Framework preset : **Other** (site statique). Aucun réglage de build nécessaire.
3. Deploy. Vercel attribue une URL du type `https://mementos-pub.vercel.app`
   (parfois avec un suffixe si le nom est déjà pris, ex. `mementos-pub-xyz.vercel.app`).

## 3. Après le 1er déploiement — ajuster l'URL

Si l'URL Vercel diffère de `https://mementos-pub.vercel.app`, mets-la à jour dans `index.html` :
- balise `<link rel="canonical" …>`
- balise `<meta property="og:url" …>`

(Ce sont les 2 seuls endroits avec l'URL en dur.)

## Notes
- Les 3 cartes « Occasions » (Mariage / Anniversaire / Teambuilding) pointent vers les apps déjà en ligne
  (`memorie-one.vercel.app`, `aniversaire.vercel.app`, `soir-e-alpha.vercel.app`) — liens absolus, rien à changer.
- **Formspree** : `FORMSPREE_ID` est encore sur `VOTRE_ID_FORMSPREE` → le formulaire de devis bascule sur l'e-mail
  (`mailto:` vers `mementos.memorie@gmail.com`). Pour un envoi direct, crée un formulaire sur formspree.io et colle l'ID.
- **Vercel Web Analytics** : pour suivre les visites, active *Analytics* dans le projet Vercel.
