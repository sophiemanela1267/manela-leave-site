# Manela — Leave Management Website

A bilingual (English / French) one-page site presenting Manela's employee leave management offer for employers. The structure takes inspiration from wecount.io, and the branding (fonts, colours, logo) comes from manela.ca.

Live preview: https://claude.ai/artifact/SzzxtCVaMNqFkUg3NAdaSG

## Files

| Path | What it is |
|---|---|
| `index.html` | The entire site: HTML, CSS and JavaScript in one file. No build step. |
| `assets/manela-logo-en.svg`, `assets/manela-logo-fr.svg` | Full burgundy logo with tagline, used in the footer (EN / FR). |
| `assets/photo-*.jpg` | Lifestyle photos from the Manela Shutterstock Drive folder (resized to 1400px). |
| `assets/app-*.jpg` | Screenshots of app.manela.ca (guest mode), 800×500, shown in the Technology section. |

To view the site locally, open `index.html` in a browser. The `assets/` folder must stay next to it.

## Page sections

The sections appear in this order:

1. Hero
2. Problem (`#problem`)
3. Solutions (`#solutions`), with four tabs:
   - Audit
   - Gap Assessment & Standardization
   - Manager Training
   - Managed Leave Services
4. Types of Leave (`#leave`)
5. Technology (`#technology`), with the app screenshot switcher
6. Who We Support (`#who`)
7. Business Case (`#business`)
8. Why Manela (`#why`)
9. Final CTA (`#contact`)
10. Footer

## English / French toggle

- The English text is written directly in the HTML.
- Any element that has a French version carries a `data-i18n="key"` attribute. Lists use `data-i18n-list`.
- All French text is stored in the `FR` object in the `<script>` at the bottom of `index.html`.
- When the page loads, the script saves the English text from the page. Switching language then swaps each element's content between the saved English text and the `FR` entry.
- The chosen language is saved in the browser (`localStorage` key `manela-lang`). On a first visit, the page follows the browser's language.

**To edit copy:**
- To change the English wording, edit it in the HTML.
- To change the French wording, edit the matching key in `FR`.

**To add new translatable text:**
1. Give the element a new `data-i18n` key.
2. Add that key to `FR`.

**Image alt text:**
- English alt text goes in `alt`.
- French alt text goes in `data-alt-fr`.

The footer logo switches between the EN and FR SVG files automatically.

## Swapping photos and screenshots

**Photos:**
1. Replace the file in `assets/` and keep the same name, or update the `src` in the HTML.
2. Update the `alt` and `data-alt-fr` text to describe the new photo.

| File | Used in |
|---|---|
| `photo-hero.jpg` | Hero |
| `photo-window.jpg` | Problem |
| `photo-dad-nap.jpg` | Managed Leave Services tab |
| `photo-sling.jpg` | Types of Leave |
| `photo-dad-feet.jpg` | Why Manela |
| `photo-parents.jpg` | Final CTA |

**App screenshots:**
- Screenshots are listed in the `SHOTS` object in the script. Each one has an English image, a French image and alt text in both languages.
- `app-planner` has no French capture yet, so French visitors see the English image.

## Links

**Book a call** goes to the Google Calendar booking page:
https://calendar.app.google/pfvqCcCGyzBqpsce7

It is used in three places:
- the nav button
- the hero button
- the final CTA button

To change the booking page, search `index.html` for `calendar.app.google` and replace all three links.

**Footer social links:**
- LinkedIn: https://www.linkedin.com/company/manela-cie/
- Instagram: https://www.instagram.com/manelacie/
- TikTok: https://www.tiktok.com/@manelaleave

**Explore Managed Leave Services** scrolls down to the final CTA section (`#contact`).

## Branding

Fonts:
- Castoro for headings
- Nunito for body text

Both are loaded from Google Fonts.

Colours are set as CSS variables at the top of the `<style>` block:

| Variable / colour | Value |
|---|---|
| `--bg` (cream) | `#F8F3EC` |
| `--surface` | `#FCFAF7` |
| `--ink` | `#0D0503` |
| `--brand` (burgundy) | `#933A18` |
| indigo | `#221961` |
| peach | `#E1937D` |
| sage | `#8FAEA3` |
| sky | `#7DA4DB` |

The page follows the visitor's light or dark mode setting. The dark-mode values are defined just below the light ones.

## Known notes

- The footer logo's tagline ("Parental leave support") and all the photos focus on parental leave, while the site covers all leave types.
- The French copy was machine-written and should be reviewed by a native speaker before launch.
