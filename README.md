# Frenchly Speaking — Website

A bilingual (EN/FR) one-page website for **Frenchly Speaking — Karina Vitiello**, a private French-language teacher based in Montrollet, France.

## Folder structure

```
frenchly-speaking/
├── index.html
├── images/
│   ├── logo.png
│   ├── hero-collage.jpg
│   └── karina-portrait.jpg
├── README.md
└── .gitignore
```

No build step, no dependencies — open `index.html` in a browser to view.

## Brand

- **Violet** `#7B1360` (primary)
- **Blue** `#1E23AF`
- **Red** `#CE031A`
- **Grey** `#A8A8A8`
- Pricing card opacity ladder: violet at 100% / 75% / 50% / 30%

## Fonts (Google Fonts, free)

- **Manrope** — used for body text and headings. Closest free match to Avenir Next.
- **Saira Condensed** — used for brand-style elements ("TEACHING FRENCH SINCE 2002" badge, section eyebrows). Close free match to Bank Gothic.
- The logo wordmark (BlairMdITC TT Medium) is part of the logo PNG, so no web font needed for that.

> **Note on the fonts Karina originally requested:** BlairMdITC TT Medium, Bank Gothic, and Avenir Next are commercial fonts requiring paid licensing for web use. The above are free Google Fonts substitutes chosen for very close visual match. If Karina wants the exact commercial fonts on the live site, she'll need to license them (Adobe Fonts, Monotype, etc.).

## Image references

Image paths are **not hard-coded** in the HTML. Every `<img>` tag uses
`data-src-key` and looks up its real path from a single config object
at the top of the inline `<script>` block:

```js
const IMAGES = {
    logo: 'images/logo.png',
    heroCollage: 'images/hero-collage.jpg',
    karinaPortrait: 'images/karina-portrait.jpg'
};
```

```html
<img data-src-key="logo" alt="Frenchly Speaking" class="logo-img">
```

To rename a file or move the images folder, change a path in `IMAGES` — markup stays untouched.

## Features

- **Bilingual EN ↔ FR** toggle (driven by `data-en` / `data-fr` attributes; no i18n library)
- **Responsive** layout (breakpoints at 1024 / 968 / 768 / 480 px)
- **Sections**: Hero · About Me · The Lessons · Options & Pricing · Reviews · FAQ · Contact
- **Testimonials carousel** — 17 testimonials, auto-rotating, swipe/keyboard/dots/arrows
- **Pricing tiers** — violet opacity ladder (100% / 75% / 50% / 30%) across the 4 options, with €/£/$ currency conversion lines
- **Legal compliance modals**: Terms & Conditions of Sale · Legal Notice (IONOS host info) · Data Protection (GDPR) · Cookie Policy
- **CNIL-compliant cookie banner** with Accept All / Reject All / Customize + floating 🍪 button

## Hosting

Site is hosted on **GitHub Pages** (free static hosting by GitHub, Inc.).

- Default URL: `https://<username>.github.io/<repo>/`
- Optional custom domain (e.g. `frenchlyspeaking.com`): add a `CNAME` file at the repo root containing the domain, then point a DNS A record (or `ALIAS`/`ANAME`) at GitHub Pages' IPs as documented at <https://docs.github.com/pages>.

## Deployment

### Local preview
Open `index.html` in any modern browser.

### Push to GitHub
```bash
git init && git add . && git commit -m "Initial commit"
git remote add origin git@github.com:<username>/<repo>.git
git branch -M main && git push -u origin main
```

### GitHub Pages preview
Settings → Pages → Source: `main` / `/ (root)` → Save.

## Still to do before going live

- [ ] Karina to review the **French translations** of the legal modals (Terms & Conditions, Data Protection)
- [ ] Optional: wire the contact form to a real backend (Formspree, Web3Forms, EmailJS, or PHP mailer)

## Credits

Site by **Elliot** — built for Karina Vitiello / Frenchly Speaking.

---

© 2026 Frenchly Speaking. All rights reserved.
