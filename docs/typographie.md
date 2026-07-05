# Typographie du site Walterre — référence pour Claude Code

Ce fichier détaille **toutes les classes de texte et de titres** utilisées dans `css/style.css`, avec leur police, graisse, taille et couleur. À lire avant de construire une nouvelle page, pour rester cohérent avec l'existant (voir aussi `/CLAUDE.md` pour la charte graphique complète : couleurs, logo, règles générales).

## 1. Polices utilisées

| Police | Rôle | Où elle est chargée |
|---|---|---|
| **Montserrat** | Toute la typographie du site (titres et texte courant) | Google Fonts, chargée dans le `<head>` de chaque page : `<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap">` |
| **Prelia** | Réservée au logotype "walterre" lui-même | **Jamais chargée en CSS** — le mot "walterre" n'est jamais recomposé en texte, toujours en image (`assets/logo/*.png`). Ne pas essayer de simuler Prelia avec une autre police. |

Montserrat est chargée avec 5 graisses (poids) : 300 (Light), 400 (Regular), 500 (Medium — non utilisé actuellement), 600 (SemiBold, utilisé comme "Medium"), 700 (Bold).

`body` définit la police par défaut pour tout le document :
```css
body{ font-family:'Montserrat',Arial,sans-serif; font-weight:300; }
```
Donc **tout texte hérite de Montserrat Light (300)** sauf s'il appartient à une classe qui précise une autre graisse (titres, boutons, labels...).

## 2. Hiérarchie des titres (h1 à h4)

Règle commune à tous les titres :
```css
h1,h2,h3,h4{ font-family:'Montserrat',Arial,sans-serif; color:var(--navy); line-height:1.25 }
```

| Balise | Graisse Montserrat | Usage |
|---|---|---|
| `h1` | 700 (Bold) | Un seul par page — le titre principal (ex. dans le hero) |
| `h2` | 600 (Medium/SemiBold) | Titres de section (ex. `.section-title`) |
| `h3` | 400 (Regular) | Sous-titres de bloc (cartes, features) |
| `h4` | 400 (Regular) | Petits titres (ex. nom dans une carte équipe) |

Couleur par défaut des titres : `var(--navy)` = `#003C70`, **sauf** sur fond sombre (hero, CTA final) où ils passent en blanc via une règle spécifique (`.hero h1{color:#fff}`, `.cta-final h2{color:#fff}`).

## 3. Classes de titres et de texte — détail complet

### Titres de section (structure générale d'une page)

| Classe | Élément | Taille | Graisse | Couleur | Usage |
|---|---|---|---|---|---|
| `.eyebrow` | `<span>` | 12px | 700 | `var(--green)` sur fond `var(--lg)` | Petit label au-dessus d'un titre de section (majuscules, arrondi façon badge) |
| `.section-title` | `h2` | `clamp(24px,3vw,34px)` (responsive) | 600 (hérité de h2) | `var(--navy)` | Titre principal de chaque section de page |
| `.section-text` | `p` | 16px | 300 (hérité de body) | `var(--muted)` = `#5C6880` | Paragraphe d'introduction sous un `.section-title`, largeur max 720px |

### Hero (bandeau du haut de l'accueil, à réutiliser sur les pages qui en ont un)

| Classe | Élément | Taille | Graisse | Couleur |
|---|---|---|---|---|
| `.hero-tag` | `<span>` | 12px | 700 | blanc, fond translucide |
| `.hero h1` | `h1` | `clamp(30px,4.2vw,46px)` | 700 (hérité de h1) | blanc |
| `.hero p` | `p` | 18px | 300 (hérité de body) | blanc à 85% d'opacité |

### Chiffres clés (bandeau stats)

| Classe | Taille | Graisse | Couleur |
|---|---|---|---|
| `.stat-num` | `clamp(28px,3.4vw,40px)` | 700 | `var(--orange)` |
| `.stat-label` | 14px | 300 (hérité) | blanc à 75% d'opacité |

### Cartes (features, audience, valeurs, équipe, partenaires)

| Classe | Élément | Taille | Graisse | Couleur |
|---|---|---|---|---|
| `.feature-card h3` | `h3` | 18px | 400 (hérité de h3) | `var(--navy)` |
| `.feature-card p` | `p` | 14.5px | 300 | `var(--muted)` |
| `.audience-card h3` | `h3` | 16px | 400 | `var(--navy)` |
| `.audience-card p` | `p` | 14px | 300 | `var(--muted)` |
| `.audience-card .link` | `a` | 13px | **700** (surchargé, plus gras que le texte courant) | `var(--blue)` |
| `.value-card h3` | `h3` | 16px | 400 | `var(--navy)` |
| `.value-card p` | `p` | 14px | 300 | `var(--muted)` |
| `.team-card h4` | `h4` | 14.5px | 400 (hérité de h4) | `var(--black)` (pas navy, volontairement plus neutre) |
| `.team-card p` | `p` | 12.5px | 300 | `var(--muted)` |
| `.partner-card h3` | `h3` | 16px | 400 | `var(--navy)` |
| `.partner-card p` | `p` | 14px | 300 | `var(--muted)` |

### Boutons

| Classe | Taille | Graisse | Notes |
|---|---|---|---|
| `.btn` (toutes variantes : `.btn-primary`, `.btn-navy`, `.btn-outline`) | 14px | **700** | Toujours en gras, quelle que soit la couleur de fond |

### Navigation (header)

| Classe | Taille | Graisse | Couleur |
|---|---|---|---|
| `.nav-links a` | 14px | **600** | blanc à 78% d'opacité, blanc plein au survol |

### CTA final (bandeau vert de fin de page)

| Classe | Élément | Taille | Graisse | Couleur |
|---|---|---|---|---|
| `.cta-final h2` | `h2` | `clamp(24px,3.4vw,36px)` | 600 (hérité) | blanc |

### Footer

| Classe | Élément | Taille | Graisse | Couleur |
|---|---|---|---|---|
| `.site-footer` (texte par défaut) | — | 13.5px | 300 (hérité) | blanc à 70% d'opacité |
| `.footer-grid h4` | `h4` | 13px | 400 (hérité) mais **majuscules forcées** (`text-transform:uppercase`) | blanc plein |
| `.footer-grid a` | `a` | hérite 13.5px | 300 | blanc à 65% d'opacité |
| `.footer-bottom` | — | 12.5px | 300 | blanc à 45% d'opacité |

### Bannière de développement

| Classe | Taille | Couleur |
|---|---|---|
| `.build-note` | 13px | texte brun sur fond orange clair — **à retirer une fois le site terminé**, ce n'est pas un composant de charte définitif |

## 4. Règles à respecter pour toute nouvelle page

1. Ne jamais écrire de CSS de police inline (`style="font-family:..."` ou `font-weight:...`) — toujours passer par une classe existante de `css/style.css`, ou en créer une nouvelle dans la feuille de style commune si un besoin nouveau apparaît (ne pas créer de feuille de style par page).
2. Un seul `h1` par page.
3. Utiliser `.eyebrow` + `.section-title` + `.section-text` comme en-tête de chaque section de contenu, pour garder la même respiration visuelle que l'accueil.
4. Le texte courant (paragraphes) est en Montserrat Light (300) par héritage — ne pas le repasser en 400 "pour que ce soit plus lisible", c'est un choix de charte assumé.
5. Les liens/CTA doivent rester en gras (700), jamais en poids normal, pour rester repérables.
6. Ne jamais utiliser Prelia ni tenter de la simuler : le mot "walterre" reste toujours une image du dossier `assets/logo/`.
