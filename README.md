# Walterre — reconstruction du site walterre.fr

Le site WordPress original a été piraté. Ce dépôt contient la reconstruction du site en HTML/CSS/JS statique, à partir du mapping de contenu extrait de la sauvegarde WordPress (voir `docs/mapping-site-walterre.md`).

## État actuel (itération 1)

- [x] Structure du site : `index.html`, `css/style.css`, `js/main.js`
- [x] Page d'accueil complète (toutes les sections du site d'origine : hero, chiffres clés, services, "vous êtes...", valeurs, équipe, partenaires, CTA final)
- [x] Header/nav sticky avec menu mobile, footer réutilisable
- [ ] Médias (logo, photos d'équipe, vidéo hero) — aucun visuel disponible pour l'instant, la page utilise des icônes/avatars en CSS en attendant les fichiers d'origine
- [ ] Pages restantes : Le DPC + AMEx (fusionnées), 4 pages cibles (Bailleurs/Tertiaires/Copropriétaires/Syndicat, un seul gabarit), Contact, Blog (liste + 37 articles), Newsletter, Études de cas
- [ ] Formulaire de contact : intégration Web3Forms prévue pour la page `/contact/`

## Décisions prises

- **Dépôt :** ce dépôt (`perso`), le site n'a pas de rapport avec l'outil de chiffrage interne (`Walterre_Chiffrage`).
- **URLs :** on garde les mêmes adresses que le site d'origine quand c'est possible (ex. `/contact/`, `/blog/`), en corrigeant `/newletter/` → `/newsletter/`.
- **Formulaire de contact :** Web3Forms (à connecter à la prochaine itération).
- **Médias :** aucun fichier fourni pour l'instant — reconstruction avec des placeholders (icônes, initiales) en attendant les visuels originaux (logo, photos, vidéo hero, images d'articles).

## Prochaines étapes suggérées

1. Fournir les fichiers médias (`wp-content/uploads/`) pour les intégrer.
2. Construire le gabarit commun des 4 pages "cible" et la page DPC/AMEx fusionnée.
3. Construire `/contact/` avec le formulaire Web3Forms.
4. Construire `/blog/` et les 37 articles.
5. Construire `/newsletter/` et `/etudes-de-cas/`.
