# Récap du mapping du site walterre.fr — pour reconstruction en HTML

*Document préparé à partir de la sauvegarde WordPress (fichiers + base de données) trouvée dans le dossier "www". Objectif : servir de base de référence pour recréer le site en HTML pur, sans rien oublier d'important.*

## 1. Ce qu'était le site jusqu'ici

- **Nom du site :** Walterre
- **Slogan / description :** "Assistant à Maîtrise d'Exploitation" (AMEx)
- **Adresse actuelle :** https://walterre.fr
- **Technologie actuelle :** WordPress, avec un éditeur visuel appelé **Oxygen Builder** pour construire les pages (c'est lui qui stocke le texte des pages, pas l'éditeur classique de WordPress — d'où le travail d'extraction fait pour ce document).
- **Contenu total publié :**
  - 13 pages "statiques" (accueil, services, contact, etc.)
  - 37 articles de blog
  - 1 formulaire de contact
  - 189 fichiers médias (images, vidéo de fond du hero, logo, etc.)

Ce document liste **toutes les pages, tous les textes clés, le menu et les articles de blog**, pour que tu puisses tout reprendre dans ton nouveau site HTML sans repartir de rien.

---

## 2. Menu principal (barre de navigation)

Le menu s'appelle "Principal" et contient, dans l'ordre :

| Ordre | Libellé | Destination | Type |
|---|---|---|---|
| 1 | Accueil | Page d'accueil | Page |
| 2 | Services | Ancre vers la section "Économies et Transition Énergétique" de la page d'accueil | Lien interne (ancre `#section-50-94`) |
| 3 | Équipe | Ancre vers la section "L'équipe de Walterre" de la page d'accueil | Lien interne (ancre `#section-84-94`) |
| 4 | Nos Formations | https://www.asder.asso.fr/chaufferie-technique-contrat-et-suivi-de-performance/ | Lien externe (partenaire ASDER) |
| 5 | Blog | Page listant les articles | Page |
| 6 | Newsletter | Page d'inscription newsletter | Page |
| 7 | Contact | Page de formulaire de contact | Page |

**À retenir pour le nouveau site :** "Services" et "Équipe" ne sont pas des pages séparées, ce sont des ancres qui font défiler la page d'accueil. Tu peux garder ce principe en HTML avec des liens `#services` et `#equipe`.

---

## 3. Plan du site (sitemap) — toutes les pages

| Titre | URL actuelle (slug) | Rôle |
|---|---|---|
| Accueil Walterre | `/accueil-walterre/` (page d'accueil du site) | Page d'accueil |
| Le DPC | `/diagnostiqueperformancechauffagetimeline-dpc/` | Présentation du Diagnostic de Performance Chauffage |
| L'AMEx | `/suivi-des-installations-amex/` | Présentation du service de suivi/AMEx |
| Diagnostic de performance chauffage | `/expertise/` | Page très proche du contenu de "Le DPC" (quasi doublon, à fusionner) |
| Les Bailleurs | `/les-bailleurs-contract/` | Page dédiée à la cible "Bailleurs" |
| Les tertiaires | `/les-tertiaires/` | Page dédiée à la cible "Tertiaire" |
| Les copropriétaires | `/les-coproprietaires/` | Page dédiée à la cible "Copropriétaires" |
| Syndicat de copropriété | `/syndicat-de-copropriete/` | Page dédiée à la cible "Syndicats de copropriété" |
| Contact | `/contact/` | Formulaire de contact |
| Blog | `/blog/` | Liste des articles |
| Les bons conseils et infos de Walterre | `/les-bons-conseils-et-infos-de-walterre/` | Page d'accroche pour la newsletter |
| Newsletter | `/newletter/` | Page d'inscription (note : le slug contient une faute — "newletter" au lieu de "newsletter", à corriger dans le nouveau site) |
| Etudes de cas | `/etudes-de-cas/` | Page qui liste les 2 articles catégorisés "Étude de cas" |

**Remarque importante :** les 4 pages "vous êtes" (Bailleurs, Tertiaires, Copropriétaires, Syndicat) suivent exactement le même modèle (Besoin → La Solution → Comment nous agissons → Suivi/Résultat → boutons Retour/Étude de cas/Contact). Idem pour "Le DPC" et "Diagnostic de performance chauffage" qui sont quasi identiques. C'est une bonne nouvelle : en HTML, tu peux créer **un seul gabarit (template) réutilisable** pour ces pages plutôt que du code dupliqué.

---

## 4. Contenu détaillé, page par page

### 4.1 Page d'accueil — "Accueil Walterre"

Structure en sections, dans l'ordre d'affichage :

**Section Hero (bandeau du haut, avec vidéo en fond)**
- Titre : *"Agissez sur la performance de vos installations de Chauffage, Ventilation et Climatisation"*
- Texte : *"Walterre, Assistant à Maîtrise d'Exploitation®, vous fait faire des économies !"*
- Bouton : "Découvrir nos services"

**Section "Agir"**
- Titre : *"Pour l'environnement, Agissez dès maintenant"*
- Texte : *"Walterre, Assistant à Maîtrise d'Exploitation®, vous accompagne pour réduire votre facture énergétique et agir en faveur de l'environnement. Economisez jusqu'à 40% sur votre consommation d'énergie. (Re) - Prenez le contrôle de votre installation dès maintenant!"*
- Boutons : "Contact", "Découvrir Waltapp"

**Section chiffres clés**
- 23 512 → "Le nombre de lots d'habitation"
- 19% → "Moyenne des économies générées sur les bâtiments suivis"
- 2 006 000 → "Le nombre de m² de bâtiments tertiaires"

**Section "Services" (ancre du menu)**
- Titre : *"Économies et Transition Énergétique"*
- Texte : *"Notre mission est d'expertiser les installations, de dresser un plan de progrès technique, une trajectoire de décarbonation et de vous accompagner dans la réalisation. Vous pouvez réaliser des économies considérables en toute simplicité et êtes acteur de la transition énergétique."*
- Bouton : "En savoir plus"
- Bloc "Expertise" → "Identifier & comprendre" — *"Diagnostic de performance CVC et étude de décarbonnation"*
- Bloc "Suivi d'Exploitation" → "Décider, Améliorer & Décarbonner" — *"Assistance à maitrise d'Exploitation®, accompagnement"*

**Section "Vous êtes..."** (cartes vers les 4 pages cibles)
- Copropriétaire — *"Réduisez vos charges et agissez pour l'environnement !"*
- Syndicats de copropriété — *"Optimisez les charges de chauffage collectif de vos copropriétaires. Gagnez du temps. Assurez-vous de la conformité réglementaires des installations."*
- Bailleur — *"Optimisez la gestion de votre parc immobilier. Facilitez le suivi de vos installations. Améliorez la transparence entre les parties en présence."*
- Tertiaire — *"Optimisez la performance énergétique de votre parc tertiaire grâce à notre expertise technique. Répondez en partie aux exigences du décret tertiaire."*
- Exploitant de chauffage — *"Devenez un expert en exploitation de chauffage grâce à notre outil métier spécialisé."*

**Section valeurs**
- Respect de l'environnement — *"Chaque kWh économisé est une victoire pour l'environnement"*
- Pragmatisme — *"Raisonner d'abord avec ce qui est disponible reste frugal dans l'innovation"*
- Excellence Opérationnelle — *"Une approche systémique qui s'appuie sur plus de 25 années d'expérience"*

**Section "Équipe" (ancre du menu) — "L'équipe de Walterre"**
- Accroche recrutement : *"Si tu veux postuler, c'est ici"* → bouton "Rejoignez-nous"
- Trombinoscope (nom — poste) :
  - Maxence — Co-fondateur & directeur général
  - Tony — Co-fondateur & président
  - Jules — Co-fondateur & CTO
  - Claire — Responsable Administrative
  - Eddy — Directeur commercial
  - Adelaïde — Responsable du développement
  - Luke — Ingénieur commercial
  - Franck — Responsable Amex
  - Laurent — Expert Technique
  - Nicolas — Expert Technique
  - Pierre Emmanuel — Expert Technique
  - Lou — Ingénieur efficacité énergétique
  - Jules — Responsable R&D
  - Renan — Doctorant Data Scientist
  - Gabriel — Développeur fullstack

**Section témoignages** (widget "Trustfolio" — vide dans l'extraction, probablement des avis chargés dynamiquement, à vérifier visuellement sur le site en ligne avant de refaire cette section)

**Section partenaires**
- *"Notre Réseaux Partenaires"* — *"Explorez notre réseau de partenaires."*
- *"Nos formations"* — *"Via l'ASDER - Partageons l'énergie"*

**Section finale (Call-to-action)**
- Titre : *"Déjà 2700 tonnes de CO2 économisées"*
- Boutons : "Contactez-nous", "Retour en haut"

---

### 4.2 "Le DPC" (`/diagnostiqueperformancechauffagetimeline-dpc/`)

- Intro : *"Chez Walterre, nous savons que les installations les plus récentes ne sont pas toujours les plus performantes."* Près de 99% des installations sont surpuissantes ou mal optimisées, soit environ 12% de surconsommation.
- "La Solution" : expertise complète de l'installation, accompagnement à la décision, assistance technique quotidienne pendant 3 ans minimum.
- "Comment nous agissons" : experts techniques + Diagnostic de Performance Chauffage.
- Bloc "Transformez votre chauffage en source d'économies" — grâce à WaltApp®, jusqu'à 40% d'économies.
- Boutons de bas de page : Retour, Étude de cas, Contact.

*(Meta description SEO à conserver : "Walterre a développé le premier Diagnostic de Performance Chauffage (DPC) qui génère des économies immédiates sur vos dépenses énergétiques.")*

### 4.3 "L'AMEx" (`/suivi-des-installations-amex/`)

- "Optimisation" : optimiser les installations pour réduire les dépenses, prolonger leur durée de vie, réduire l'impact environnemental.
- "La Solution" / "Comment nous agissons" : suivi minimum 3 ans après le diagnostic, maîtrise budgétaire, optimisation continue via WaltApp®.
- "Suivi des installations" : accompagnement sur le suivi de l'installation, jusqu'à 40% d'économies avec WaltApp®.
- Boutons : Retour, Étude de cas, Contact.

*(Meta description SEO : "Walterre, assistant à maîtrise d'exploitation (AMEx) qui génère des économies immédiates sur vos dépenses énergétiques.")*

### 4.4 "Diagnostic de performance chauffage" (`/expertise/`)

Contenu quasiment identique à "Le DPC" et reprend aussi des passages de "L'AMEx" (sections Waltapp, Suivi des installations). **Recommandation : à fusionner avec "Le DPC" dans le nouveau site**, pour éviter le contenu dupliqué (mauvais pour le référencement Google).

### 4.5 Les 4 pages "cible" (même structure)

Chacune suit ce plan : **Besoin de la cible → La Solution → Comment nous agissons → Bénéfices/Résultat → boutons Retour / Étude de cas / Contact.**

**Les Bailleurs** (`/les-bailleurs-contract/`)
- Besoin : *"Vous manquez de temps et de ressources pour gérer votre parc immobilier et souhaitez améliorer la visibilité ainsi que la compréhension de vos installations et fournisseurs."*
- Accompagnement : stratégie d'exploitation/optimisation, préparation au décret tertiaire, contrats de maintenance, budgets OPEX/CAPEX CVC, visites virtuelles, climatisation/ventilation, suivi via WaltApp®.
- Bénéfice : *"Obtenez une vision homogène de votre parc, établissez des budgets pour la maintenance et les investissements (OPEX & CAPEX CVC), et réalisez des gains environnementaux à moyen terme."*

**Les tertiaires** (`/les-tertiaires/`)
- Besoin : optimiser les coûts de chauffage collectif, gagner du temps, respecter les obligations réglementaires (décret tertiaire).
- Accompagnement : rapports standardisés, budgets OPEX/CAPEX CVC, contrats de maintenance, visites virtuelles, WaltApp®.
- Bénéfice : contrat d'exploitation suivi, réduction des pannes, gains financiers et environnementaux à moyen terme.

**Les copropriétaires** (`/les-coproprietaires/`)
- Besoin : *"Vos charges de chauffage augmentent. Vous cherchez des solutions pour réduire vos factures et agir pour l'environnement."*
- Plan d'action DPC puis AMEx® : rapport technique/environnemental/financier, priorités sur 3 ans minimum, protocole avec l'exploitant, rapports de suivi annuel, contrats de maintenance sur demande.
- Bénéfice : réduction des charges, décisions éclairées sur le système CVC.

**Syndicat de copropriété** (`/syndicat-de-copropriete/`)
- Besoin : optimiser les charges de chauffage collectif, gagner du temps, obligations réglementaires.
- Accompagnement : expertise technique complète, rapport + plan d'amélioration validé avec le syndicat, préparation des assemblées générales, suivi via WaltApp®.
- Bénéfice : accompagnement technique, gain de temps, anticipation.

### 4.6 Contact (`/contact/`)

Formulaire (outil "Forminator" côté WordPress) avec les champs suivants :

| Champ | Type |
|---|---|
| Prénom | Texte |
| Nom | Texte |
| Adresse de messagerie | Email |
| Numéro de téléphone | Téléphone |
| Message | Texte long |
| Anti-spam | Captcha (hCaptcha) |

*(Meta description SEO : "Besoin de conseils ou d'informations sur nos services ? Contactez-nous dès maintenant via notre formulaire de contact.")*

**Pour le nouveau site en HTML pur :** un formulaire HTML classique ne peut pas envoyer d'email tout seul. Il faudra soit un petit script serveur, soit un service externe simple (ex. Formspree, Web3Forms, ou autre service d'envoi de formulaire) pour recevoir les messages sans avoir à gérer de base de données.

### 4.7 Etudes de cas (`/etudes-de-cas/`)

Page qui liste dynamiquement les articles de la catégorie "Étude de cas" (voir section blog ci-dessous — 2 articles). En HTML statique, il faudra soit lister ces 2 articles à la main, soit prévoir un petit système de "cartes" réutilisable si tu comptes en ajouter d'autres.

### 4.8 Newsletter (`/newletter/`) et "Les bons conseils et infos de Walterre" (`/les-bons-conseils-et-infos-de-walterre/`)

Page d'accroche pour l'inscription à la newsletter :
- Titre : *"Les bons conseils de Walterre 🔥"*
- Texte : *"Pour faire le plein d'actus, d'infos et de conseils utiles pour votre le climat et votre portefeuille ✅, c'est par ici:"*
- Texte : *"En vous inscrivant à cette newsletter, promis pas de spam, juste des infos intéressantes ou utiles. Parce qu'on peut tous devenir les Rangers du Climat (pour ceux qui ont la ref) !"*

**Remarque :** le slug actuel `/newletter/` contient une faute de frappe ("newsletter" mal orthographié) — à corriger dans les nouvelles URLs.

### 4.9 Blog (`/blog/`)

Page qui liste les articles du blog (voir section 5).

---

## 5. Le blog — 37 articles publiés

Les articles se regroupent naturellement en 5 grandes familles de contenu. Ça peut t'aider à organiser les catégories/menus de blog dans le nouveau site.

### A. Fondamentaux techniques du chauffage collectif (15 articles pédagogiques)
Ce sont des articles "cours" qui expliquent le vocabulaire et les équipements d'une chaufferie.

| Date | Titre | URL (slug) |
|---|---|---|
| 2023-04-12 | Les vannes 3 voies | `les-vannes-3-voies-circuits-hydrauliques-systemes-de-chauffage` |
| 2023-04-25 | Le confort thermique | `le-confort-thermique` |
| 2023-04-26 | L'équilibrage hydraulique des réseaux | `lequilibrage-hydraulique-des-reseaux` |
| 2023-04-26 | Les postes de facturation (P1, P2, P3) | `les-postes-de-facturation-p1-p2-p3` |
| 2023-04-26 | Les contrats d'exploitation | `les-contrats-dexploitation` |
| 2023-04-26 | Individualisation des frais de chauffage | `individualisation-des-frais-de-chauffage` |
| 2023-04-26 | Les Chaudières | `les-chaudieres-chaufferie-fluide-caloporteur` |
| 2023-05-03 | Surdimensionner une chaudière | `surdimensionner-une-chaudiere` |
| 2023-05-03 | La chaudière, c'est quoi ? | `cest-quoi-une-chaudiere` |
| 2023-05-03 | De l'eau de qualité pour ça performance | `de-leau-de-qualite` |
| 2023-05-03 | La Chaufferie en Copropriété : les différentes difficultés | `chaufferie-source-de-difficulte-comprendre-son-fonctionnement-et-eviter-les-tensions` |
| 2023-05-03 | Circulateurs bien dimensionnés | `circulateurs-bien-dimensionnes` |
| 2023-05-03 | Le rôle du circulateur dans une chaufferie | `role-du-circulateur-dans-une-chaufferie` |
| 2023-05-03 | L'importance du vase d'expansion | `limportance-du-vase-dexpansion` |
| 2023-05-03 | C'est quoi la régulation ? | `la-regulation` |
| 2023-05-03 | Le suivi des températures en chauffage collectif | `le-suivi-des-temperatures-en-chauffage-collectif` |
| 2023-05-03 | Ma première visite en chaufferie | `ma-premiere-visite-en-chaufferie-une-prise-de-conscience-de-lecart-entre-theorie-et-realite` |

### B. Études de cas / retours d'expérience clients (4 articles)

| Date | Titre | URL (slug) | Catégorie WP |
|---|---|---|---|
| 2023-05-03 | Optimisation énergétique dans un ensemble de 649 logements sociaux | `optimisation-energetique-dans-un-ensemble-de-649-logements-sociaux` | Non classé |
| 2023-05-03 | Réhabilitation énergétique d'un bâtiment (bâtiment classé, -20% et 150 000€ sur 10 ans) | `rehabilitation-energetique-dun-batiment` | **Étude de cas** |
| 2023-05-03 | Améliorer l'efficacité énergétique d'un parc immobilier vieillissant | `efficacite-energetique-dun-parc` | **Étude de cas** |
| 2024-03-27 | Les aventures de Walterre : mission économie d'énergie dans une église classée (Haute-Savoie) | `walterre-mission-eglise-haute-savoie` | Non classé |
| 2024-04-30 | Walterre : économies d'énergie et confort pour un hôtel de département du Puy-en-Velay | `walterre-economies-energie-hotel-departement-puy-en-velay` | Non classé |

*(Seuls 2 articles sont officiellement classés "Étude de cas" dans WordPress — les 3 autres retours d'expérience n'étaient pas catégorisés, à corriger dans le nouveau site si tu veux une vraie rubrique "Études de cas" complète.)*

### C. Éco-gestes grand public / cuisine (5 articles, série 2024)

| Date | Titre | URL (slug) |
|---|---|---|
| 2024-07-10 | Les Méthodes de Cuisson Énergétiquement Autonomes | `les-methodes-de-cuisson-autonomes` |
| 2024-08-12 | Économisez de l'Énergie en Cuisine : L'Importance d'Utiliser un Couvercle | `utiliser-couvercle-cuisson` |
| 2024-08-15 | Utilisation Optimale de votre Four | `utilisation-optimale-de-votre-four` |
| 2024-09-17 | Pourquoi Privilégier le Micro-Ondes et les Bouilloires Modernes ? | `chauffer-eau-eco-responsable` |
| 2024-09-17 | Débrancher Vos Appareils en Veille est Essentiel | `economiser-energie-debrancher-appareils-veille` |

### D. Transition écologique / actualité généraliste (4 articles)

| Date | Titre | URL (slug) |
|---|---|---|
| 2021-03-31 | L'efficacité énergétique : la clé de voûte de la transition écologique ? | `efficacite-energetique-cle-de-voute-transition-ecologique` |
| 2022-04-26 | Le piège du carbone : dépasser la vision tunnel pour une transition écologique holistique | `transition-ecologique-holistique-carbone` |
| 2022-12-12 | Confort et économies d'énergie : 1°C en moins = 7% d'économies ? | `confort-economies-energie-1-degre-en-moins` |
| 2024-04-29 | L'énergie solaire thermique en Europe : état des lieux en 2021 | `energie-solaire-thermique-europe-etat-des-lieux-2021` |

### E. Actualité produit / vie de l'entreprise (2 articles)

| Date | Titre | URL (slug) |
|---|---|---|
| 2024-08-05 | Walternative - Découvrez le nouveau module d'étude d'opportunité ! | `nouveau-module-etude-opportunite-walterre` |
| 2024-08-08 | Walterre: Votre Source de Contenu Énergétique sur YouTube | `walterre-sur-youtube-contenu-energetique` |

### F. Autres articles (rénovation / enjeux copropriété)

| Date | Titre | URL (slug) |
|---|---|---|
| 2024-03-19 | Chaufferie : les 4 moments clés de l'année pour votre copropriété | `mooc-renovation-performante-risques-et-bons-reflexes` |
| 2024-03-22 | Rénovation de chaufferie : la clé d'une rénovation énergétique rentable ? | `renovation-chaufferie-rentable` |
| 2024-04-08 | Chaufferies récentes : attention aux dérives énergétiques ! | `chaufferies-recentes-derives-energetiques` |
| 2024-04-12 | Le chauffage dans la copropriété : un enjeu majeur à ne pas négliger ! | `le-chauffage-dans-la-copropriete-un-enjeu-majeur-a-ne-pas-negliger` |

*(Note : le titre WordPress de l'article `mooc-renovation-performante-risques-et-bons-reflexes` ne correspond plus à son URL d'origine — l'article a probablement été réécrit sans changer le slug. Pas grave, mais à savoir si tu retrouves le contenu complet.)*

---

## 6. Ce qui tournait "sous le capot" (pour référence, pas à reproduire en HTML statique)

Le site utilisait ces outils WordPress, qui n'auront plus de raison d'être une fois en HTML pur — mais ça explique certaines fonctionnalités à recréer autrement :

- **Forminator** → le formulaire de contact (à remplacer par un formulaire HTML + service d'envoi externe)
- **Yoast SEO** → gérait les titres et meta descriptions pour Google (déjà repris dans ce document, à remettre directement dans le `<head>` de tes pages HTML)
- **Wordfence, hCaptcha** → sécurité et anti-spam (moins nécessaire en HTML statique, mais garde un captcha sur le formulaire de contact si tu gardes un vrai formulaire)
- **LiteSpeed Cache, Google Site Kit** → performance et statistiques (à remplacer par un outil simple comme Google Analytics ou Plausible si tu veux garder des statistiques)
- **Oxygen Builder** → l'éditeur visuel qui construisait les pages (remplacé par ton code HTML/CSS directement)

---

## 7. Recommandations pour la reconstruction en HTML

1. **Garde les mêmes adresses de page (URLs)** autant que possible. Google connaît déjà ces adresses ; si tu changes tout, tu perds le référencement acquis. Exemple : garde `/contact/`, `/blog/`, `/le-confort-thermique/`, etc.
2. **Corrige les deux petits problèmes repérés :** le slug `/newletter/` (faute de frappe) et le doublon entre "Le DPC" et "Diagnostic de performance chauffage" — choisis une seule page.
3. **Réutilise un seul gabarit HTML** pour les 4 pages "cible" (Bailleurs / Tertiaires / Copropriétaires / Syndicat) puisqu'elles ont exactement la même structure — tu ne changes que le texte.
4. **Recopie les titres et meta descriptions** listés dans ce document dans les balises `<title>` et `<meta name="description">` de chaque page HTML, pour ne rien perdre côté référencement.
5. **Prévois une solution simple pour le formulaire de contact** (un service externe gratuit d'envoi de formulaire, puisqu'il n'y aura plus de serveur PHP).
6. **Récupère les images et vidéos** dans le dossier `wp-content/uploads/2021/`, `2022/`, `2023/`, `2024/` du dossier "www" — c'est là que sont stockés tous les visuels du site (logo, vidéo du hero, photos d'équipe, etc.).
7. **Si tu changes une adresse malgré tout**, mets en place une redirection (redirection 301) de l'ancienne vers la nouvelle pour ne pas perdre les visiteurs qui ont l'ancien lien en favori ou via Google.
