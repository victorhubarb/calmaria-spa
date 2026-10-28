# Calmaria Spa

A responsive landing page for a fictional spa, in plain HTML, CSS and JavaScript. It has a hero with a call to action, two sections about the space, service cards, a discount signup, and a contact area with a short FAQ. The page is in Portuguese.

**Live demo:** [calmaria-spa-livid.vercel.app](https://calmaria-spa-livid.vercel.app)

## What's inside

- **Accessible modals.** The signup and contact modals use `role="dialog"` and `aria-modal`. Tab and Shift+Tab loop inside an open modal, Escape closes it, and focus goes back to the element that opened it.
- **FAQ accordion.** One answer is open at a time, and `aria-expanded` and `aria-hidden` are updated from JavaScript.
- **Dropdown menu.** The "Nosso espaço" submenu opens on hover and on click, and Escape closes it.
- **Responsive layout.** Styles are written for mobile first, with `min-width` media queries at 768 px and 1440 px.
- **CSS split by section.** One stylesheet per page section (`container--primeiro`, `--secao`, `--cards`, `--inscricao`, `--contato`), BEM-style class names, and custom properties for colors, gradients and fonts.
- **Image sets per screen size.** `assets/` has separate Desktop, Tablet and Mobile folders.

No framework, no build step and no dependencies. A version of this page with its styles organized in Sass is in [calmaria-spa-sass](https://github.com/victorhubarb/calmaria-spa-sass).

## Run it

Clone the repo and open `index.html` in a browser, or serve the folder locally:

```bash
git clone https://github.com/victorhubarb/calmaria-spa.git
cd calmaria-spa
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Project structure

```
index.html            Single page
main.js               Modals, focus handling, dropdown menu, accordion
styles/
├── style.css         Variables, base styles, header and menu, accordion
└── container--*.css  One file per page section
assets/               Images and icons (Desktop, Tablet, Mobile) and Figma exports
```

## Known gaps

- The signup and contact buttons open a confirmation modal, but nothing is validated or sent. The fields are not wrapped in `<form>` elements, so the native `required` checks never run.
- Several menu links are placeholders (`#`), and "Nossa história" points to `quem-somos.html`, which is not in the repository.
- Clicking a menu item that has no submenu (Início, Serviços, Contato) logs a `TypeError` in the console, because the click handler assumes every item has one. Navigation still works.
- `assets/` also holds the original Figma export folder, which the page does not use.

---

Victor Hugo Barbosa · [GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
