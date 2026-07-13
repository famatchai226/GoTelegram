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
