# Calmaria Spa 🌿

![Status](https://img.shields.io/badge/status-completed-green?style=for-the-badge)
![Stack](https://img.shields.io/badge/HTML5%20%7C%20CSS3%20%7C%20JavaScript-no%20frameworks-blue?style=for-the-badge)

A responsive landing page for a fictional spa, built with plain HTML, CSS and JavaScript — with accessible modals, an accordion FAQ and a layout that scales from mobile to desktop.

**Live demo:** [calmaria-spa-livid.vercel.app](https://calmaria-spa-livid.vercel.app)

---

## Overview

Calmaria Spa is a one-page site for a made-up spa: a hero with a call to action, two sections about the space, three service cards, a newsletter signup, and a contact area with a short FAQ. The page content is in Brazilian Portuguese. The visual design and image assets come from Alura's course material; this repository is the front-end implementation, with no framework, no build step and no dependencies.

Most of the effort went into interaction details. Modals keep keyboard focus inside while they're open, close with Escape, and hand focus back to the element that opened them. The FAQ accordion keeps one answer open at a time and updates its ARIA attributes as it changes. The layout starts from the mobile design and grows through tablet and desktop breakpoints.

---

## Architecture

```
calmaria-spa/
├── index.html                      # Single page: header, hero, content, cards, signup, contact, FAQ
├── main.js                         # Modals, focus management, dropdown menu, accordion
├── styles/
│   ├── style.css                   # Variables, base styles, header and nav, accordion
│   ├── container--primeiro.css     # Hero section
│   ├── container--secao.css        # Content sections
│   ├── container--cards.css        # Service cards
│   ├── container--inscricao.css    # Newsletter signup
│   └── container--contato.css      # Contact section and modals
└── assets/
    ├── Desktop/ Tablet/ Mobile/    # Image sets per breakpoint
    └── *.png, *.svg                # Images used by the page
```

### Concepts Applied

| Area | How it shows up |
|---|---|
| **Responsive layout** | Base styles first, then `min-width` media queries at 768px and 1440px |
| **Modal accessibility** | `role="dialog"` and `aria-modal`; Tab and Shift+Tab loop inside the modal; Escape closes it; focus returns to the trigger |
| **Accordion** | One item open at a time, with `aria-expanded` and `aria-hidden` kept in sync from JavaScript |
| **Dropdown menu** | Opens on hover and on click, closes on Escape; `aria-haspopup` and `aria-expanded` on the trigger |
| **CSS organization** | One stylesheet per page section, BEM-style class names, custom properties for colors and fonts |
| **Semantic HTML** | `lang="pt-br"`, descriptive `alt` text, a `label` tied to every form field |

---

## Technologies

- **HTML5**
- **CSS3** — custom properties, media queries
- **Vanilla JavaScript**
- **Google Fonts** — Montserrat, Krona One, Open Sans — and Material Symbols icons
- **Vercel** — deployment

---

## How to Run

No installation needed.

```bash
git clone https://github.com/victorhubarb/calmaria-spa.git
cd calmaria-spa
```

Open `index.html` in a browser, or serve the folder locally:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

---

## What I'd Improve Next

- **Real form handling.** The signup and contact buttons open a confirmation modal, but nothing is validated or sent. The fields aren't wrapped in `<form>` elements yet, so the native `required` checks never run. Next step: proper forms with validation, connected to a small backend or a form service.
- **Finish the navigation.** Several menu items (Serviços, Localização, Equipe) are placeholders, and "Nossa história" points to a page that isn't in the repository.

---

## Author

**Victor Hugo Barbosa**
[GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
