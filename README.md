# Redox Agency — Website Replica

A pixel-close, front-end-only replica of the Redox Agency landing page + contact
page, built with plain HTML, CSS and vanilla JavaScript (no build step, no
frameworks, no dependencies to install).

## What's inside

```
redox-agency/
├── index.html      → Home page (hero, work, activity stats, clients, footer)
├── contact.html     → Contact page (opens when you click "Let's Talk")
├── css/
│   └── style.css    → All styling
└── js/
    └── script.js     → All scroll animations & interactions
```

## How to view it

No installation needed. Just double-click **index.html** (or `contact.html`)
and it opens in your default browser.

If you'd rather serve it locally (recommended for the smoothest experience,
some browsers restrict autoplaying video / fonts on `file://` pages):

```bash
cd redox-agency
python3 -m http.server 8000
# then open http://localhost:8000 in your browser
```

or with Node:

```bash
npx serve redox-agency
```

**An internet connection is required** — the stock photos, the hero video,
and the two Google Fonts (Anton + Sora + Inter) are all loaded from external
CDNs rather than bundled locally, to keep the download small.

## Features replicated

- Sticky pill-shaped nav bar with hover dropdowns (Home / Service / Pages / Blog)
  and an arrow that rotates on hover
- Rotating "AWARD WINNING AGENCY · SINCE 2010" circular badge
- Peach hero section with stat counters (98% / 120+)
- Giant scroll-scrubbed "REDOX" text that scales up and fades the background
  from peach to white as you scroll past it
- Autoplaying background video with a "FEATURED WORK" marquee strip
  underneath it (with an animated Ken-Burns fallback if the video can't load
  on your network)
- Featured Work grid — cards fade/slide in as they scroll into view
- Dark "Perfect—activity" section: a sticky title on the left while five
  stat blocks (1.8M / 260+ / 12+ / 80+ / 99%) scroll past normally on the right
- "Client:" section with logo pills that drop in from above when scrolled
  into view
- Full-screen black "LET'S WORK" pinned curtain that scales in and out
- Testimonial line that lights up word-by-word as you scroll through it,
  followed by a full (uncropped) photo
- Full footer: subscribe form, Company / Social / Office link columns,
  back-to-top button
- Separate **Contact** page: big "CONTACT" headline, intro copy, contact
  form with floating labels, social links sidebar

## Known limitations / things to swap out

- **Stock imagery & video** are pulled from Unsplash / third-party CDNs.
  If any image or the hero video doesn't load on your network, replace the
  URLs in `index.html` with your own files (e.g. drop them in an `assets/`
  folder and update the `src`/`poster` attributes).
- **Fonts** (Anton, Sora, Inter) are loaded from Google Fonts via `@import`
  in `style.css`. For an offline-capable version, self-host the font files
  and update the `@font-face`/`@import` rule.
- This is a static front-end only — the contact form doesn't actually send
  email (it just shows a "Message sent ✓" confirmation on submit). Wire it
  up to your own backend or a form service (e.g. Formspree) if you need real
  submissions.
- Copy, company details (email, offices, social links) are placeholders
  matching the original design — update them to your real business info.

## Customizing

- **Colors / fonts**: all defined as CSS variables at the top of
  `css/style.css` under `:root` — change `--peach`, `--orange`, `--black`,
  etc. in one place to re-theme the whole site.
- **Scroll animations**: all handled in `js/script.js`, each effect is in
  its own clearly-commented block (giant text scrub, activity stats reveal,
  logo drop-in, curtain scale, word-by-word testimonial, video fallback).
