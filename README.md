# Meat the Greek — site

Site vitrine statique pour **Meat the Greek**, pitta grill, Chaussée de Vleurgat 7, 1050 Ixelles (Bruxelles), à 300 m de la place Flagey.
Ouvrir `index.html` dans un navigateur. Aucune dépendance, aucun build. Les polices viennent de Google Fonts. Le site est prévu pour être mis en ligne sur https://meat-the-greek.be/ (canonical, sitemap, Open Graph et données structurées pointent vers ce domaine : à adapter si le domaine change).

## Fichiers

- `index.html` — tout le site (HTML + CSS + quelques lignes de JS pour la navigation collante de la carte), aux couleurs de base du client (voir ci-dessous). C'est la version validée par le client, avec la section Questions fréquentes.
- `index-v1-cobalt.html` — ancienne V1 bleu cobalt / papier / doré, conservée pour mémoire, plus mise à jour depuis le 27 septembre 2026.
- `traiteur.html` — page Traiteur & événements (mêmes couleurs que `index.html`), liée depuis la navigation et le pied de page des deux index. Les coordonnées de contact traiteur (e-mail, téléphone, SMS/WhatsApp) sont pour l'instant celles du restaurant : à remplacer dans le bloc repéré par le commentaire `CONTACT TRAITEUR` quand le client les communique.
- `book/Meat-the-Greek-Book-noir-blanc-bleu.pdf` — book de présentation du site aux couleurs du client (13 pages A4 paysage), avec sa source `book/Meat-the-Greek-Book-noir-blanc-bleu.html` (ouvrir dans Chrome puis imprimer en PDF pour le régénérer)
- `book/Meat-the-Greek-Book.pdf` — ancien book, version bleu cobalt / papier / doré
- `assets/img/photo-*.jpg` — vraies photos du restaurant (shooting de septembre 2026, originaux dans le Drive `current photo/meat the greek`, fichiers DSC02104 à DSC02166), recadrées pour le web : `photo-pitta-gyros` (hero), `photo-pitta-table`, `photo-scampis-maison`, `photo-gambas-grillees` (bande de l'intro), `photo-terrasse` (section restaurant), `photo-facade` (section contact), `photo-table-partage` (page traiteur)
- `assets/img/` — les autres photos (`pitta.jpg`, `souvlaki.jpg`, `mezze.jpg`, `moussaka.jpg`, `plat.jpg`, `grill-pitta.jpg`…) viennent de meat-the-greek.be et ne sont plus utilisées par le site ; logos : `logo-nfb.png` = logo noir pour fond blanc, `logo-bft.png` = logo blanc pour fond sombre

## Couleurs du client (`index.html`)

Relevées sur meat-the-greek.be et sur le logo officiel. Elles sont déclarées en haut du CSS, dans `:root`.

| Couleur | Valeur | Origine | Usage |
|---|---|---|---|
| Noir | `#141615` | fond du logo | hero, pied de page, textes |
| Blanc | `#FFFFFF` | fond du site, en-tête | fond, navigation |
| Gris clair | `#F2F2F2` | fonds de sections du site | section carte |
| Bleu | `#1A2598` | boutons du site | accents, section avis |
| Bleu vif | `#1D62F0` | début du dégradé des boutons | boutons Commander |

Le bandeau reprend le méandre grec du logo. Retour client du 27 septembre 2026 : la signature s'écrit « Pitta grill restaurant » (comme sur la porte du restaurant), et les mots « Opa ! » et « Yamas ! » ont été retirés du titre et du bandeau. Le book PDF dans `book/` date d'avant ces changements (anciennes photos, « Opa ! » encore présent) : le régénérer si le client en a besoin.

## Sources du contenu

| Quoi | Source |
|---|---|
| Textes, adresse, téléphone 02 771 21 27, e-mail, horaires (fermé le mardi), lien de commande Pickup, avis clients, photos, logo « By Bouloux » | https://meat-the-greek.be |
| Carte complète avec prix (68 articles, 10 catégories) | Uber Eats Belgique, septembre 2026 |
| 60 couverts, terrasse, chiens acceptés, Wi-Fi, moyens de paiement | ixelles.city et Privateaser |
| Note 4,5 / 5 sur près de 900 avis | Uber Eats |

Les prix sont ceux de la carte à emporter en ligne. Ils peuvent être un peu plus élevés qu'en salle.

## Mettre à jour

Les plats et prix sont dans la section `#carte` de `index.html`. Chaque plat est un `<li class="dish">`. Penser à répercuter les changements de carte dans `llms.txt`.

## Référencement (SEO / GEO)

Le site vise autant les recherches « restaurant à Ixelles / Flagey / Bruxelles, terrasse, ouvert le dimanche, à emporter, groupe, traiteur » que « restaurant grec ». Ce vocabulaire est dans le titre, la description, la section « À Flagey » (`#quartier`), la FAQ, les `keywords` du JSON-LD et `llms.txt`.

Chaque page a un `canonical`, des balises Open Graph et Twitter, et un bloc JSON-LD (schema.org) : `Restaurant` complet (adresse, GPS, horaires, cuisine, paiement, lien de commande), `WebSite`, `WebPage`, `FAQPage` sur l'accueil, `Service` traiteur et `BreadcrumbList` sur la page traiteur. La section Questions fréquentes de l'accueil et le JSON-LD `FAQPage` reprennent les mêmes questions : modifier les deux ensemble. `robots.txt`, `sitemap.xml` et `llms.txt` (résumé en texte brut pour les robots des IA) sont à la racine. La fiche Google Maps du restaurant (`https://maps.google.com/?cid=2784927230192950489`, lien court `https://maps.app.goo.gl/VQvbJH7mwynnV7Xj6`) est référencée dans `hasMap` et `sameAs` du JSON-LD, dans le bouton Itinéraire et dans le bouton « Voir nos avis sur Google » de la section avis. La note 4,5 / 5 n'est volontairement pas mise dans le JSON-LD : Google n'accepte pas les notes reprises d'un site tiers dans les données structurées d'un commerce.

Crédit « Site réalisé par Ascension Agency » (https://www.ascensionagency.fr/) dans le pied de page des deux pages.
