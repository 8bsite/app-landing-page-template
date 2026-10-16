# Free HTML app landing page template with GSAP scroll animations — Linea

**Landing page for a mobile app or SaaS (demo: a live-captioning app for phone calls): a free HTML template in one file, with GSAP scroll animations, no build step, MIT license. Made by [8B](https://8b.com/), the AI website builder.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) ![one HTML file: no build](https://img.shields.io/badge/one%20HTML%20file-no%20build-orange) ![GSAP: ScrollTrigger](https://img.shields.io/badge/GSAP-ScrollTrigger-88ce02)

**[Live demo](https://8bsite.github.io/app-landing-page-template/)** · **[Use this template](https://github.com/new?template_name=app-landing-page-template&template_owner=8bsite)** · **[Download ZIP](https://github.com/8bsite/app-landing-page-template/archive/refs/heads/main.zip)**

<a href="https://8bsite.github.io/app-landing-page-template/"><img src="previews/desktop.png" alt="Linea, a free HTML template: first screen on a desktop" width="76.1%"></a> <a href="https://8bsite.github.io/app-landing-page-template/"><img src="previews/phone.png" alt="Linea, a free HTML template: first screen on a phone" width="21.9%"></a>

<p align="center"><a href="https://8bsite.github.io/app-landing-page-template/"><img src="previews/scroll.gif" alt="Linea, a free HTML template: scrolling through the first sections on a desktop" width="40%"></a><br><sub>Scroll animation</sub></p>

A one-page site for a free app that turns phone calls and the conversations around you into live captions. Warm paper and espresso bands with one green accent stack over each other as you scroll; spoken words cross from a waveform into readable caption bubbles, a phone builds its transcript feature by feature, and a row of places slides sideways along two curved voice lines.

Good for: SaaS or mobile app landing page; app with a free plan or a sign-up; communication, messaging or accessibility product; any product whose features can be shown on a phone screen one by one.

## Use it with an AI coding agent

Download the files into your project (in Windows PowerShell type `curl.exe`):

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

Give the agent the downloaded file, not a link: from a link it would rebuild a different page. No agent? Click **[Use this template](https://github.com/new?template_name=app-landing-page-template&template_owner=8bsite)**, edit `index.html` and turn on **Settings → Pages**.

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

## Design

Palette: ![#1b1411](https://img.shields.io/badge/-%231b1411-1b1411?style=flat-square) ![#faf5f0](https://img.shields.io/badge/-%23faf5f0-faf5f0?style=flat-square) ![#eee5dc](https://img.shields.io/badge/-%23eee5dc-eee5dc?style=flat-square) ![#33cc7a](https://img.shields.io/badge/-%2333cc7a-33cc7a?style=flat-square) ![#66574f](https://img.shields.io/badge/-%2366574f-66574f?style=flat-square) ![#1f3954](https://img.shields.io/badge/-%231f3954-1f3954?style=flat-square) ![#bacde0](https://img.shields.io/badge/-%23bacde0-bacde0?style=flat-square) ![#2e241f](https://img.shields.io/badge/-%232e241f-2e241f?style=flat-square) ![#b8aba3](https://img.shields.io/badge/-%23b8aba3-b8aba3?style=flat-square)  
Fonts: Host Grotesk (Google Fonts). Change both through the CSS variables in the `:root` block at the top of `<head>`. A big display line with `style="--len:N"` fills its width: set N to its new number of characters.

- The phone, the waveform, the settings controls and the step cards are HTML and CSS, not images: change their text in place and recolour them through the CSS variables.
- The contact form's thank-you and error texts are in data-msg-ok and data-msg-error on the <form>.
- The text-message link uses sms: (not tel:); replace the number in both the href and the visible text.

## Before you publish

- Replace everything marked `data-8b-placeholder` (social preview image, favicon, phone, email, form) and the invented demo facts: prices, dates, address. [AGENTS.md](AGENTS.md) lists them.
- The form sends nothing yet: connect it to Formspree or Netlify Forms, or remove it.

## Tech

GSAP 3.13.0, ScrollTrigger, SplitText, Lenis 1.3.27 from jsDelivr, 134 KB, no build step. Chrome and Edge 111+, Safari 16.2+, Firefox 113+ (it uses color-mix(), container query units, cascade layers, small/dynamic viewport units). With "reduce motion" on, the page is complete and still.

## License

MIT, see [LICENSE](LICENSE); the "Design: 8B" footer link is welcome, not required. Photos, fonts and libraries keep their own licences: [CREDITS.md](CREDITS.md). More free templates: [github.com/8bsite](https://github.com/8bsite).
