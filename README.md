# Walterre — reconstruction du site walterre.fr

Le site WordPress original a été piraté. Ce dépôt contient la reconstruction du site en HTML/CSS/JS statique, à partir du mapping de contenu extrait de la sauvegarde WordPress (voir `docs/mapping-site-walterre.md`).

## État actuel (itération 2)

- [x] Structure du site : `index.html`, `css/style.css`, `js/main.js`
- [x] Page d'accueil complète (toutes les sections du site d'origine : hero, chiffres clés, services, "vous êtes...", valeurs, équipe, partenaires, CTA final)
- [x] Header/nav sticky avec menu mobile, footer réutilisable
- [x] Médias intégrés sur la page d'accueil : vidéo hero (`assets/img/hero/`), 15 photos d'équipe (`assets/img/team/`), 6 logos partenaires (`assets/img/partners/`)
- [x] Bibliothèque complète des médias du site d'origine, organisée par page, disponible dans `assets/media/` pour construire les pages restantes
- [ ] Pages restantes : Le DPC + AMEx (fusionnées), 4 pages cibles (Bailleurs/Tertiaires/Copropriétaires/Syndicat, un seul gabarit), Contact, Blog (liste + 37 articles), Newsletter, Études de cas
- [ ] Formulaire de contact : intégration Web3Forms prévue pour la page `/contact/`

## Médias

Tous les médias sont maintenant optimisés pour le web (redimensionnés, compressés — la bibliothèque est passée de 195 Mo à 24 Mo) et rangés par page, prêts à être référencés directement dans le HTML :

- `assets/img/hero/` : vidéo hero (utilisée sur l'accueil).
- `assets/img/team/` : 15 photos d'équipe (utilisées sur l'accueil).
- `assets/img/partners/` : 6 logos partenaires (utilisés sur l'accueil).
- `assets/img/pages/<slug>/` : un dossier par page du site, avec les images propres à cette page — les noms de dossier correspondent aux URLs prévues dans `docs/mapping-site-walterre.md` (`dpc`, `amex`, `expertise`, `bailleurs`, `tertiaires`, `coproprietaires`, `syndicat`, `contact`, `newsletter`, `etudes-de-cas`, `accueil` pour le reste des visuels d'accueil non encore utilisés — pictogrammes, bannières génériques).
- `assets/img/pages/blog/<slug-de-larticle>/` : un dossier par article de blog (37 au total), avec son image de couverture — le nom de dossier est directement le slug d'URL final de l'article (ex. `le-confort-thermique`).
- Les pages `dpc`, `amex`, `contact` et `etudes-de-cas` n'avaient pas d'image identifiable dans le contenu d'origine — un fichier `LIRE-MOI.txt` l'indique dans leur dossier.
- Deux photos wallpaper en doublon quasi-identique (anciennes versions plus lourdes, orthographe différente) ont été supprimées pour ne garder que la version la plus récente et éviter les conflits de nom sur Mac (système de fichiers insensible à la casse).
- ⚠️ **À vérifier :** deux membres de l'équipe s'appellent "Jules" dans le contenu d'origine (CTO et Responsable R&D). Les photos `Jules-CTO.png` / `Jules-RD.png` ont été attribuées de mon mieux à partir des noms de fichiers (`JulesC` / `JulesM`), mais cette correspondance n'a pas pu être confirmée avec certitude — à vérifier visuellement sur la page et à inverser si besoin (fichiers dans `assets/img/team/`).

## Décisions prises

- **Dépôt :** ce dépôt (`perso`), le site n'a pas de rapport avec l'outil de chiffrage interne (`Walterre_Chiffrage`).
- **URLs :** on garde les mêmes adresses que le site d'origine quand c'est possible (ex. `/contact/`, `/blog/`), en corrigeant `/newletter/` → `/newsletter/`.
- **Formulaire de contact :** Web3Forms (à connecter à la prochaine itération).

## Prochaines étapes suggérées

1. Construire le gabarit commun des 4 pages "cible" et la page DPC/AMEx fusionnée (visuels déjà disponibles et optimisés dans `assets/img/pages/`).
2. Construire `/contact/` avec le formulaire Web3Forms.
3. Construire `/blog/` et les 37 articles (images de couverture déjà dans `assets/img/pages/blog/<slug>/`).
4. Construire `/newsletter/` et `/etudes-de-cas/`.
5. Vérifier l'attribution des deux photos "Jules" (voir section Médias ci-dessus).
