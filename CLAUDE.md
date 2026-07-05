# Walterre — charte graphique (à appliquer à chaque page)

Ce fichier fait référence pour **toute** page ou composant ajouté à ce site. Avant de construire une nouvelle page, relis cette charte — ne réinvente pas de couleurs, polices ou styles de logo différents de ce qui est décrit ici. Source : `docs/Charte_Graphique_Walterre_2023.pdf` (charte officielle, janvier 2023).

## Couleurs

Toujours ces valeurs exactes (déjà en variables CSS dans `css/style.css`) :

| Rôle | Couleur | Hex |
|---|---|---|
| Orange (accent, CTA, barre au-dessus du logo) | Orange | `#F3953F` |
| Bleu (liens, barre sous le logo, éléments interactifs) | Bleu | `#136DBD` |
| Bleu Marine (fond header/footer, titres) | Bleu Marine | `#003C70` |
| Noir / Blanc | — | logo décliné en noir pur ou blanc pur selon le fond |

Ne pas introduire d'autres teintes dominantes. Le vert (`--green`) et le violet (`--purple`) présents dans `style.css` sont des teintes de support (valeurs/éco-responsabilité, CTA final) hérités du design existant — à utiliser avec parcimonie, jamais à la place de l'orange/bleu/marine qui restent les couleurs de marque.

## Typographie

- **Prelia** : réservée au logotype "walterre" lui-même (voir logo ci-dessous, toujours utilisé comme image, jamais recomposé en texte). Le fichier de police n'a pas été fourni — ne pas tenter de le simuler avec une autre police en la faisant passer pour Prelia. Si un jour le fichier de police est fourni, il pourra aussi servir aux très grands titres d'accroche (hero).
- **Montserrat** : police de travail pour tout le reste. Déjà chargée via Google Fonts dans chaque page (`Montserrat:wght@300;400;500;600;700`).
  - `h1` → Montserrat **Bold** (700)
  - `h2` → Montserrat **Medium** (600 dans notre implémentation Google Fonts, l'équivalent le plus proche du "Medium" de la charte)
  - `h3`/`h4` → Montserrat **Regular** (400)
  - Texte courant/paragraphes → Montserrat **Light** (300) — c'est le poids par défaut sur `body` dans `css/style.css`, ne pas le surcharger en 400 pour du texte de contenu.

## Le logo

Fichiers disponibles dans `assets/logo/` (fonds transparents, prêts à intégrer) :

| Fichier | Usage |
|---|---|
| `walterre-onnavy.png` | Logo blanc + barres couleur (orange/bleu), à utiliser sur fond bleu marine `#003C70` — **c'est la version du header et du footer du site**. |
| `walterre-color.png` | Logo noir + barres couleur, sur fond clair/blanc. |
| `walterre-white.png` | Logo tout blanc (sans couleur), pour usage sur photo/fond sombre où les couleurs de marque ne doivent pas dominer. |
| `walterre-black.png` | Logo tout noir, version mono sur fond clair. |
| `walterre-icon.png` | Monogramme "w" seul dans un carré bleu marine arrondi (barres orange/bleu) — source pour favicons et usages compacts (réseaux sociaux, app icon). |

Favicons déjà générés dans `assets/favicon/` (`favicon.ico`, `favicon-16x16.png`, `favicon-32x32.png`, `apple-touch-icon.png`, `android-chrome-192x192.png`, `android-chrome-512x512.png`) — à référencer dans le `<head>` de **chaque** page HTML (copier le bloc `<link rel="icon"...>` de `index.html`).

**Règles strictes (charte "Les interdits") :**
- Ne jamais recolorer les barres orange/bleu dans une autre teinte.
- Ne jamais étirer, incliner ou déformer le logo (respecter le ratio d'origine).
- Ne jamais séparer le monogramme "w" de ses deux barres, ni changer leur couleur.
- Toujours garder une zone de protection autour du logo (au moins la hauteur du "w" du monogramme, ne rien coller contre le logo).
- Toujours utiliser le fichier logo tel quel (`<img>`), jamais recomposer "walterre" en texte + CSS.

## Inspiration produit : waltapp.io

WaltApp est l'outil logiciel "sœur" de Walterre (même univers CVC/décarbonation). Le site vitrine walterre.fr doit s'inspirer de son langage visuel pour les pages produit/expertise :

- Fond navy/charcoal en alternance avec des sections blanches — pas tout en couleur, la marque reste sobre.
- Sections modulaires en cartes (feature cards), grilles à deux colonnes qui alternent texte/visuel.
- Espacements généreux, air entre les blocs — éviter le remplissage dense.
- CTA primaires bien visibles (bouton plein, couleur orange de la marque), actions secondaires en lien texte.
- Ton professionnel et rassurant mais pas froid — approche "expert technique accessible", pas "startup gadget".
- Navigation fixe/sticky simple, peu d'éléments.

## Gabarit de page

Chaque nouvelle page HTML doit reprendre tel quel :
1. Le bloc `<head>` de `index.html` (favicons, police Google Fonts Montserrat, `css/style.css`) en adaptant `<title>` et `<meta name="description">`.
2. Le header (`<header class="site-header">`) et le footer (`<footer class="site-footer">`) copiés depuis `index.html`, sans modification de structure — seul le contenu entre les deux change.
3. Les classes existantes de `css/style.css` (`.section`, `.container`, `.feature-card`, `.audience-card`, etc.) plutôt que du CSS inline ou dupliqué — étendre `style.css` si un nouveau composant est nécessaire, ne pas créer de feuille de style par page.
