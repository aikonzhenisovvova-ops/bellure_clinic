# Bellure Clinic — Team Website

**Assignment #2 — Advanced CSS (Flexbox & Grid)**

| | |
|---|---|
| **Topic** | Medical cosmetology clinic |
| **Live website** | https://aikonzhenisovvova-ops.github.io/bellure_clinic/ |
| **Repository** | https://github.com/aikonzhenisovvova-ops/bellure_clinic |
| **Team size** | 4 members |
| **Pages** | Home, Services, About, Contact |

## Project goal

To build a multi-page website for a medical cosmetology clinic in Astana that helps a visitor understand the clinic's approach, compare treatments and prices, get to know the doctors, and book a consultation.

**Target audience:** adults (roughly 20–50) in Astana who are considering cosmetic skin treatments and want a doctor-led, transparent clinic rather than a "sales menu".

## Team and page ownership

| Member | GitHub | Page | Main sections and page-specific components |
|---|---|---|---|
| Nurakysheva Ayaulym | `aikonzhenisovvova-ops` | `index.html` — Home | Hero with two calls to action, "Why patients choose us" trust cards (Flexbox), popular treatments preview (Grid), patient reviews (`blockquote`), team preview |
| Bekbolat Adina | `adinabek` | `services.html` — Services | Category jump-navigation, three treatment catalogues with 9 service cards (Grid), course pricing `table`, consultation call to action |
| Nazymkyzy Aizada | `Aizzadamsn` | `about.html` — About | Clinic story, team of four doctors (Grid), "How a visit works" process timeline (`ol`, Flexbox column), clinic values (`aside` cards, Flexbox) |
| Khabibullina Aigerim | `aigerim-kh` | `contact.html` — Contact | Booking form with labelled inputs, contact info card, form + info layout (Grid), results gallery with `figure`/`figcaption` (Grid), FAQ (`details`/`summary`) |

Shared work (header, navigation, footer, `style.css`, `responsive.css`, testing and deployment) was done by the whole team.

## Page map

| Page | Question it answers for the visitor | Unique component |
|---|---|---|
| Home | "Why should I trust this clinic?" | Hero + trust cards + reviews |
| Services | "What treatments exist and how much do they cost?" | Category navigation, service catalogue, pricing table |
| About | "Who are the doctors and what happens during a visit?" | Team grid, process timeline |
| Contact | "How do I book and where are you?" | Booking form, results gallery, FAQ accordion |

## Project structure

```
bellure_clinic/
├── index.html          Home
├── services.html       Services and pricing
├── about.html          About and team
├── contact.html        Booking, gallery, FAQ
├── css/
│   ├── style.css       design tokens, layout, shared components
│   └── responsive.css  tablet and phone breakpoints, mobile navigation
├── images/             logo, hero illustration, team and gallery SVGs
└── README.md
```

All paths are relative (`css/style.css`, `images/team-1.svg`), so the site works both locally and on GitHub Pages. No CSS frameworks (Bootstrap etc.) and no JavaScript are used.

## Semantic HTML

Every page has a valid HTML5 skeleton, a unique `<title>` and meta description, exactly one `<h1>`, and at least three content sections. Across the site we use more than 40 different element types, including:

`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`, `h1`–`h3`, `p`, `ul`, `ol`, `li`, `a`, `img`, `figure`, `figcaption`, `blockquote`, `address`, `table`, `thead`, `tbody`, `tr`, `th`, `td`, `form`, `label`, `input`, `select`, `option`, `textarea`, `button`, `details`, `summary`.

Every form input is connected to its `<label>` with `for`/`id`, and uses the correct type (`text`, `email`, `tel`). All images have meaningful `alt` text. The current page in the navigation is marked with `aria-current="page"`.

## Design system

Defined once in `css/style.css` with CSS custom properties in `:root`:

- **Colors:** ink `#2A2230`, paper `#FBF7F7`, rose `#C13E72` (accent), blue `#8FA3D9`, blush `#F3AFC0`
- **Typography:** Fraunces (headings), Manrope (body text), from Google Fonts with system fallbacks
- **Shape:** border radius `22px` for cards and `14px` for inputs; pill-shaped buttons
- **Reusable classes:** `.wrap`, `.section`, `.card`, `.btn`, `.btn-o`, `.flex-row`, `.grid`, `.grid-2/3/4`
- `box-sizing: border-box` is applied to all elements
- Visible `:hover` and `:focus-visible` states on links, buttons and form fields

## Flexbox

| Component | Class | Properties used | Why Flexbox |
|---|---|---|---|
| Main navigation | `.bar`, `.main-nav ul` | `display:flex`, `justify-content:space-between`, `align-items:center`, `gap` | One row: logo, links and button aligned on one axis |
| Trust cards, reviews, values | `.flex-row` | `flex-wrap:wrap`, `flex:1 1 240px`, `gap` | Cards share the row equally and wrap when space runs out |
| Footer columns | `.footer-cols` | `justify-content:space-between`, `flex-wrap:wrap` | Three columns spread across one row |
| Form fields and actions | `.field`, `.form-actions` | `flex-direction:column`, `align-items:center`, `gap` | Label above input; button and note side by side |
| Process timeline | `.timeline` | `flex-direction:column` | Steps stacked vertically along one line |

**Responsive Flexbox:** on phones (`max-width: 640px`) `.flex-row`, `.footer-cols` and the navigation list switch to `flex-direction: column`.

## CSS Grid

| Layout | Page | Grid | Desktop → Tablet → Phone |
|---|---|---|---|
| Service catalogue (9 cards in 3 categories) | Services | `.grid-3` | 3 → 2 → 1 columns |
| Popular treatments preview | Home | `.grid-3` | 3 → 2 → 1 columns |
| Team of doctors | About | `.grid-4` | 4 → 2 → 1 columns |
| Team preview | Home | `.grid-4` | 4 → 2 → 1 columns |
| Booking form + contact card | Contact | `.grid-2` | 2 → 2 → 1 columns |
| Results gallery | Contact | `.grid-4` | 4 → 2 → 1 columns |

Properties used: `display:grid`, `grid-template-columns: repeat(n, 1fr)`, `gap`.

## Responsive design

Breakpoints are in `css/responsive.css`:

- **Tablet (`max-width: 900px`):** 3- and 4-column grids become 2 columns.
- **Phone (`max-width: 640px`):** all grids become 1 column, flex rows stack vertically, spacing and heading sizes are reduced, and the navigation turns into a hamburger menu.

**Mobile menu without JavaScript:** a visually hidden `<input type="checkbox">` is paired with a `<label>` (the hamburger icon). The CSS `:checked` selector shows the menu and turns the icon into an X. The checkbox stays keyboard-focusable and can be toggled with Space.

## Testing checklist

- [x] All navigation links work on every page
- [x] All images, fonts and styles load on the deployed site
- [x] Checked at 375px (phone), 768px (tablet) and 1280px (desktop)
- [x] No horizontal scrolling or overlapping content
- [x] Mobile menu opens and closes, also with the keyboard
- [x] Keyboard focus is visible on links, buttons and form fields
- [x] Form labels are connected to inputs
- [x] Browser console has no errors

**Problem found and fixed:** after the first upload the deployed site had no styles because the `css/` and `images/` folders were not uploaded to GitHub (only the HTML files were). We re-uploaded the folders with their structure and the site displayed correctly.

## Run locally

1. Download or clone the repository:
   ```bash
   git clone https://github.com/aikonzhenisovvova-ops/bellure_clinic.git
   ```
2. Open `index.html` in any browser. No build step or server is needed.

## Deployment

The site is deployed with **GitHub Pages** from the `main` branch (root folder):
https://aikonzhenisovvova-ops.github.io/bellure_clinic/

## Git contributions

| Member | GitHub | Contribution |
|---|---|---|
| Nurakysheva Ayaulym | `aikonzhenisovvova-ops` | Created the shared repository, added `index.html`, set up GitHub Pages |
| Bekbolat Adina | `adinabek` | Added `services.html` |
| Nazymkyzy Aizada | `Aizzadamsn` | Added `about.html` |
| Khabibullina Aigerim | `aigerim-kh` | Uploaded shared `css/` and `images/` folders and README, added `contact.html` |

Full history: [commits on main](https://github.com/aikonzhenisovvova-ops/bellure_clinic/commits/main)

---

© 2026 Bellure Clinic — student project, Astana IT University.
