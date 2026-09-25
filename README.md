# Bellure Clinic — team website

**Topic:** Medical cosmetology clinic
**Team:** 4 members
**Pages:** Home, Services, About, Contact

## Page ownership

| Member | Page | Focus |
|---|---|---|
| Student 1 | index.html | Hero, trust cards, popular treatments preview, testimonials |
| Student 2 | services.html | Full treatment catalogue (Grid), category nav, pricing table |
| Student 3 | about.html | Team (Grid), process timeline, values |
| Student 4 | contact.html | Booking form, gallery (Grid), FAQ, map |

## Structure

```
bellure-clinic/
├── index.html
├── services.html
├── about.html
├── contact.html
├── css/
│   ├── style.css        (shared design tokens, layout, components)
│   └── responsive.css   (tablet + phone breakpoints, incl. mobile nav)
└── images/                (logo mark, hero illustration, team + gallery SVGs)
```

## Mobile navigation

No JavaScript. The hamburger menu on phones is a hidden `<input type="checkbox">` paired with a `<label>`; CSS `:checked` shows the menu and animates the icon into an X. The checkbox stays keyboard-focusable and toggles with Space/Enter.

## Flexbox used in

- Main navigation (`.bar`)
- Trust / value card rows (`.flex-row`)
- Footer columns (`.footer-cols`)
- Contact form actions (`.form-actions`)

## CSS Grid used in

- Services catalogue, 3-column → 1-column (`.grid-3`)
- Team grid, 4-column → 1-column (`.grid-4`)
- Contact page: form + info card (`.grid-2`), results gallery (`.grid-4`, 4 items)

## Deploy

Push this folder to a GitHub repository and enable **GitHub Pages** (Settings → Pages → deploy from `main`), or drag the folder into **Netlify**. Update this README with the live URL and each member's commit history before submission.

## Deployed URL

_TBD — add after deployment._

## Repository

_TBD — add after pushing to GitHub._
