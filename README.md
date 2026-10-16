# Free HTML app landing page template with GSAP scroll animations — Linea

**Landing page for a mobile app or SaaS (demo: a live-captioning app for phone calls): a free HTML template in one file, with GSAP scroll animations, no build step, MIT license. Made by [8B](https://8b.com/), the AI website builder.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) ![one HTML file: no build](https://img.shields.io/badge/one%20HTML%20file-no%20build-orange) ![GSAP: ScrollTrigger](https://img.shields.io/badge/GSAP-ScrollTrigger-88ce02)

**[Live demo](https://8bsite.github.io/app-landing-page-template/)** · **[Use this template](https://github.com/new?template_name=app-landing-page-template&template_owner=8bsite)** · **[Download ZIP](https://github.com/8bsite/app-landing-page-template/archive/refs/heads/main.zip)**

<a href="https://8bsite.github.io/app-landing-page-template/"><img src="previews/desktop.png" alt="Linea, a free HTML template: first screen on a desktop" width="76.1%"></a> <a href="https://8bsite.github.io/app-landing-page-template/"><img src="previews/phone.png" alt="Linea, a free HTML template: first screen on a phone" width="21.9%"></a>

<p align="center"><a href="https://8bsite.github.io/app-landing-page-template/"><img src="previews/scroll.gif" alt="Linea, a free HTML template: scrolling through the first sections on a desktop" width="40%"></a><br><sub>Scroll animation</sub></p>

A one-page site for a free app that turns phone calls and the conversations around you into live captions. Warm paper and espresso bands with one green accent stack over each other as you scroll; spoken words cross from a waveform into readable caption bubbles, a phone builds its transcript feature by feature, and a row of places slides sideways along two curved voice lines.

Good for: SaaS or mobile app landing page; app with a free plan or a sign-up; communication, messaging or accessibility product; any product whose features can be shown on a phone screen one by one. Free for personal and commercial use (MIT), made by [8B](https://8b.com/).

## Quick start

Pick one:

- **With an AI coding agent** (Claude Code, Codex, Cursor, Windsurf…). Download the files into your project (in Windows PowerShell type `curl.exe`):
  ```bash
  curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/index.html
  curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/AGENTS.md
  curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/LICENSE
  curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/CREDITS.md
  ```
  Then give your agent this prompt:
  ```text
  Read AGENTS.md, then edit index.html. Use this template as the base for a landing page for <your app or SaaS product: what it does, who it is for, pricing or free plan, where to sign up or download>. Keep the layout, the motion and the single-file format; replace the brand name, copy, photos, the phone screen, reviews, links and contacts, and recolour it through the CSS variables if needed.
  ```
  Give the agent the downloaded file, not a link: an agent reads a link as a summary and would rebuild a different page.
- **No code.** Download the ZIP, unzip it, replace the contacts and texts in `index.html`, put `index.html` into an empty folder and drag that folder onto [Netlify Drop](https://app.netlify.com/drop). The page is online in a minute.
- **On GitHub.** Click **[Use this template](https://github.com/new?template_name=app-landing-page-template&template_owner=8bsite)** to get your own copy, then **Settings → Pages → Deploy from a branch → main**. Your site appears at `https://<you>.github.io/<repo>/`.

## What's on the page

- **Navigation** — top bar: logo, section links, Get-the-app button; phone menu overlay
- **Every call, written as it’s spoken.** — first screen: headline over a full-bleed photo, lead, proof line, button; caption chips ride curved lines across the photo
- **Nothing lost between a voice and a word.** — two-panel stage: speech on one side, readable captions on the other (demo: They speak / You read)
- **Calls that feel easy again.** — feature list beside a sticky phone whose screen builds one step per feature
- **Captions, set your way.** — a wall-sized sample sentence over a list of eight settings with drawn controls
- **Captions for the room, too.** — horizontal track of five places with photos and caption pairs, two curved lines run through all of them
- **Recommended by clinicians. Loved by the people who use it.** — expert quote with portrait beside two columns of short reviews
- **Three steps, then just talk.** — three numbered step cards that stack on top of each other
- **Questions, answered plainly.** — questions and answers (native &lt;details&gt;)
- **Your next call can be the easy one.** — closing call to action over a photo that opens from a small window to the full band
- **Talk to a person, any way you like.** — support hours, a photo, three ways to reach the team and a contact form (placeholders)
- **Footer** — tagline, link columns, giant wordmark, copyright with the Design: 8B credit and a legal note

## Before you publish

- Replace everything marked `data-8b-placeholder` (social preview image, favicon, phone, email, form) and the invented demo facts — prices, dates, address. [AGENTS.md](AGENTS.md) lists them.
- The contact form does not send anything yet: connect it to a form service (Formspree, Netlify Forms) or remove it; [AGENTS.md](AGENTS.md) shows both.

## Customize

- **Colours and fonts**: CSS variables in the `:root` block at the top of `<head>`.
- **Text**: edit it in place. A big display line with `style="--len:N"` fills its width: set N to its new number of characters.
- **Photos**: replace `src`, delete `srcset` and `sizes` (they list Unsplash sizes) and update the `alt` texts.
- **Animations**: each section's animation is one `<script data-8b-part="scene:<id>">` block at the end of the file. For native scroll, delete the Lenis block in `page-init`.

## For developers

- **Stack.** HTML and CSS (custom properties, cascade layers) with GSAP 3.13.0, ScrollTrigger, SplitText, Lenis 1.3.27 from jsDelivr. No build step, no framework, no npm. 134 KB.
- **Layout of the file.** `<head>`: CSS variables, shared classes, then one style block per section. Then the markup, one element per section with a one-line comment above it. End of `<body>`: small behaviour scripts, the libraries, smooth scroll (`page-init`), the effects, one animation script per section.
- **Browsers.** Chrome and Edge 111+, Safari 16.2+, Firefox 113+ (it uses color-mix(), container query units, cascade layers, small/dynamic viewport units).
- **Accessibility.** Motion runs only when the visitor's system allows it; with "reduce motion" the page is complete and still. FAQ answers use native `<details>` and open without JavaScript. Every photo has alt text.
- **External requests.** fonts.gstatic.com, images.unsplash.com, cdn.jsdelivr.net. No analytics, no cookies. To self-host everything (offline use, or Google Fonts and GDPR in the EU), download those files and change the URLs.
- **Licences of the parts.** GSAP is free, commercial use included, under its own standard licence (not MIT); Lenis is MIT; fonts are SIL OFL; photos are under the Unsplash License. See [CREDITS.md](CREDITS.md).

## FAQ

**Can I use it for a client or a commercial site?** Yes. The code is MIT: use it, change it, sell the site you build with it.

**Do I have to keep the "Design: 8B" link?** No. It is welcome, not required.

**Can I use it in React, Next.js, Astro or Vue?** Yes. Move each section's markup and style block into a component and run its animation script in `useGSAP()` (React) or `onMounted` (Vue); start Lenis once. Or keep it as a separate static landing page next to your app (`example.com` for the landing, `app.example.com` for the app).

**Why doesn't the contact form send?** It is a demo. Connect it to Formspree, Netlify Forms or your backend; AGENTS.md has the steps.

**Where are the photos from?** Unsplash; they load from Unsplash's servers. Replace them with your own when you can.

## More free templates

[More 8B templates on GitHub](https://github.com/8bsite) · [8b.com](https://8b.com/)

## License

The template code is MIT licensed — see [LICENSE](LICENSE). Photos, fonts and libraries keep their own licences — see [CREDITS.md](CREDITS.md).
