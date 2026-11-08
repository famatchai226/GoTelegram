# GoTelegram Landing Page

## Structure

```
gotelegram-landing-page/
├── index.html          # Main landing page
├── i18n.js             # Internationalization script
├── locales/
│   ├── fr.json         # French translations
│   └── en.json         # English translations
├── assets/
│   ├── hero caroussel/ # Carousel images (0.jpeg to 5.jpeg)
│   ├── proofs/         # Proof images (1.jpeg to 6.jpeg)
│   ├── video/          # Tutorial video (guide.mp4)
│   └── moyens-paiement.png  # Payment methods image
├── .gitignore
└── how.md              # This file
```

## How to use

1. Open `index.html` in a browser.
2. The page auto-detects the browser language (French or English).
3. Click the language toggle button (FR/EN) to switch manually.

## Customization

- **Text content**: Edit `locales/fr.json` and `locales/en.json`.
- **Checkout link**: Replace the `href` in all CTA buttons pointing to the MyMaketou checkout.
- **Assets**: Replace images in `assets/` folders with your own.
- **Video**: Place your tutorial video at `assets/video/guide.mp4`.

## Sections

1. **Navbar** — Logo + language toggle + CTA button
2. **Hero** — Headline, description, price, trust badges, image carousel
3. **Video** — Tutorial video section
4. **Stats strip** — Key metrics
5. **Offer** — What you get (3 cards + total value)
6. **Why Telegram** — Features list + visual card
7. **Testimonials** — 3 customer reviews
8. **Proofs** — Screenshots of satisfied customers
9. **FAQ** — Accordion-style questions
10. **CTA** — Call to action with price and payment info
11. **Upsell** — Cross-sell other products (Baltazar, Kera, BD)
12. **Footer** — Contact info
13. **Float bar** — Sticky bottom bar with promo

---

## Visuels des cartes d'upsell (`#upsell`)

La section « Nos Offres Premium Exclusives » (`#upsell`, en bas de page) présente 3 offre(s) :
**Collection Premium Baltazar** · **Pack Influenceuse (KERA)** · **Pack +14 838 BD & Mangas pour Adultes**.

Chaque carte affiche le visuel du produit en vignette carrée, à gauche du texte.

| Élément | Rôle |
| --- | --- |
| `.upsell-grid` | pile verticale des cartes (max 850 px, centrée) |
| `.upsell-card` | carte flex, fond `--surface-container-lowest`, bordure `--outline-variant`, rayon 1.75 rem, léger soulèvement au survol |
| `img.upsell-thumb` | visuel produit : 152 × 152 px, `object-fit: cover`, `object-position: center 20%` (les affiches sont en portrait), `loading="lazy"` + `decoding="async"` |
| `.upsell-body` | titre `h3`, description `p` et bouton de la carte |

- **Mobile (≤ 640 px)** : la carte passe en colonne et le visuel devient un bandeau
  `aspect-ratio: 16 / 9` sur toute la largeur de la carte.
- **Images distantes** : les visuels sont servis par les Workers frères, toujours en **URL
  absolue** (aucun visuel n'est embarqué dans ce dépôt) :
  - Collection Premium Baltazar : `https://balta.famatchai226.workers.dev/assets/hero%20caroussel/0.jpeg`
  - Pack Influenceuse (KERA) : `https://kera.famatchai226.workers.dev/assets/hero%20caroussel/0.jpeg`
  - Pack +14 838 BD & Mangas pour Adultes : `https://bd.famatchai226.workers.dev/assets/hero%20caroussel/0.jpg`
- **Modifier / ajouter une carte** : dupliquer un bloc `.upsell-card`, changer
  `img.upsell-thumb` (attributs `src` et `alt`), les `data-i18n` et le lien du bouton, puis
  ajouter les clés `upsell.<produit>_title` / `_desc` / `_btn` dans **`locales/fr.json` et
  `locales/en.json`** (les deux fichiers, sinon la traduction retombe sur le texte du HTML).
- **Vérification** : ouvrir `index.html` et faire défiler jusqu'à « Nos Offres Premium
  Exclusives » ; les vignettes doivent s'afficher. Elles viennent d'un autre domaine : si le
  réseau ou le DNS bloque ce domaine, les cartes restent sans image alors que le texte est là.

---
