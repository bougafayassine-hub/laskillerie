# La Skillerie, site de la formation

Page de vente de la formation Meta Ads de La Skillerie (créée par l'agence Y&N Growth). C'est un site statique en HTML, CSS et JavaScript, sans dépendance ni étape de build, publié par Netlify.

## Structure

```
public/               dossier publié par Netlify
  index.html          la page (styles et script inclus dans le fichier)
  404.html            page affichée pour une adresse inexistante
  robots.txt
  favicon.svg, favicon-32.png, apple-touch-icon.png   (monogramme « S » provisoire, en attendant le logo)
  assets/img/         photo et logos (WebP)
netlify.toml          dossier publié, en-têtes de sécurité et de cache
```

## Mettre en ligne sur Netlify

1. Netlify → **Add new site** → **Import an existing project** → GitHub → `laskillerie`.
2. Laisser **Build command** vide : le dossier `public` est déjà indiqué dans `netlify.toml`.
3. **Deploy**. Ensuite, chaque push sur `main` redéploie le site automatiquement.
4. **Domain management** pour brancher le domaine définitif.

## Prévisualiser sans déployer sur Netlify

Netlify ne redéploie le site que pour un push sur `main`. Pour voir une modification sans consommer de crédits :

1. Pousser sur une autre branche (par exemple la branche de travail de Claude).
2. Ouvrir la page via raw.githack.com, qui sert les fichiers du dépôt GitHub (public) comme un vrai site :

   `https://raw.githack.com/bougafayassine-hub/laskillerie/NOM-DE-LA-BRANCHE/public/index.html`

   ou, pour figer une version précise, remplacer le nom de branche par l'identifiant du commit.
3. Une fois satisfait, fusionner dans `main` : un seul déploiement Netlify.

githack garde la page en cache quelques minutes : si une modification n'apparaît pas, attendre un peu ou utiliser le lien avec l'identifiant du commit. Ne pas ouvrir de pull request tant qu'on teste si les « Deploy Previews » sont activées dans Netlify : chaque pull request déclenche alors un déploiement.

## À compléter avant le lancement

- **Les cases roses** : témoignages, note Trustpilot, durées et nombre de vidéos, `[mois année]`, `[nom]` de la communauté, `[moyen de paiement]`, `[15 minutes]`, `[email]`, `[WhatsApp]`, etc.
- **Les liens provisoires** (`href="#…"`) : `#calendly`, `#whatsapp`, `#trustpilot`, `#video`, `#video-temoignage`, `#paiement`, `#espace-eleve`, `#attestation`, `#journal`, `#blog`, `#mentions`, `#cgv`, `#confidentialite`.
- **Le domaine** : dans `index.html`, décommenter les balises `canonical` et `og:url` et y mettre l'adresse définitive.
- **Indexation** : tant que des cases roses sont visibles, on peut activer le bloc `noindex` prévu en bas de `netlify.toml`.

## Modifier la page

- **Textes** : directement dans `public/index.html`. Les styles sont écrits sur chaque élément, comme dans la maquette.
- **Palette** : attribut `data-palette="sable"` sur la `div` `#top`. Les valeurs `lilas` et `nuit` donnent les deux autres palettes.
- **Extraits de l'aperçu** (bouton « Prévisualiser ») : tableau `P` dans le script en bas de `index.html`.
- **Images** : dans `public/assets/img/`. Pour remplacer une image, garder les mêmes proportions et donner un nouveau nom au fichier (les images restent 7 jours en cache chez les visiteurs).

## Différences avec la maquette Claude Design

Le texte et le rendu sur ordinateur sont identiques. Ajouts pour la mise en ligne :

- balise viewport, titre, description, Open Graph et favicon ;
- sur téléphone : marges latérales de 16 px sous 480 px de large et paddings des cartes resserrés (sur ordinateur, rien ne change) ;
- grilles et cartes témoignages qui ne débordent plus sur les petits écrans ;
- carte flottante du hero recalée entre 1 101 et 1 240 px pour ne pas être coupée ;
- « Parlons-en » ne se coupe plus au trait d'union ;
- aperçu des extraits : fermeture aussi avec la touche Échap.

Vérifié de 320 à 1 920 px de large : aucun défilement horizontal.

Polices : Archivo, Inter et Newsreader, chargées depuis Google Fonts comme dans la maquette.
