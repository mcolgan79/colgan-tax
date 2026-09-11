# Colgan Tax — Website

Plain static HTML/CSS site — no build step, no framework, no dependencies.

## Structure

- `index.html` — Home
- `services.html` — Individual tax, business tax, bookkeeping
- `short-term-rentals.html` — STR / vacation rental niche page
- `about.html` — About / bio
- `contact.html` — Contact form (Netlify Forms) + client portal link
- `css/styles.css` — all styling, colors/fonts defined as CSS variables at the top for easy re-theming
- `js/main.js` — mobile nav toggle, footer year
- `netlify.toml` — Netlify config (publish dir, security headers)

## Deploying to Netlify

**Fastest option — drag and drop (no account setup beyond Netlify itself):**

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag the whole `Colgan Tax Site` folder onto the page
3. Netlify gives you a live `*.netlify.app` URL immediately

**Better long-term option — connect to Git (auto-deploys on every change):**

1. Push this folder to a GitHub repo
2. In Netlify: **Add new site → Import an existing project → GitHub**
3. Select the repo — build command: none, publish directory: `.`
4. Every push to `main` auto-deploys

## Connecting your existing domain

In Netlify: **Site settings → Domain management → Add a domain**, then update your domain's DNS (at whichever registrar holds it) to point to Netlify — either an `A` record to Netlify's load balancer IP, or (preferred) delegate DNS to Netlify's nameservers. Netlify issues a free HTTPS certificate automatically once DNS is pointed at them.

## The contact form

Uses [Netlify Forms](https://docs.netlify.com/forms/setup/) — detected automatically at deploy time via `data-netlify="true"` on the `<form>` tag. No backend, no API keys. Submissions appear in **Site → Forms** in the Netlify dashboard, and you can set up email notifications there (Site settings → Forms → Form notifications).

## Design system

Styled per the **Colgan Tax Design System v1 (July 2026)**: Ledger Green + Cent Gold on a warm Paper background, Lora (display) + Work Sans (body), and the "Grand Total" double-rule wordmark. All tokens live at the top of `css/styles.css` as CSS custom properties (using `oklch()` colors) — edit there to adjust the palette or type scale. Fonts load from Google Fonts via the `@import` at the top of that file.

Real business info (phone, email, Winter Park FL address, "It just makes cents" tagline) is already wired into the footer and contact page.

## Still placeholder — needs real content before launch

- Headshot / photo (about.html, and the "photo — ..." placeholder blocks on index.html / short-term-rentals.html — swap `.photo-block` divs for real `<img>` tags)
- Credentials / PTIN / years of experience (about.html)
- Business hours (contact.html)
- Real testimonial + client name/attribution (index.html)
- Client portal link — pick a provider (Liscio, SafeSend, TaxDome, Canopy) and link it from contact.html
- Privacy Policy page (footer links to "#" currently)
