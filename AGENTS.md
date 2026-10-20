# AGENTS.md: app landing page template

Landing page for a mobile app or SaaS (demo: a live-captioning app for phone calls). One file, `index.html`, with inline CSS and scripts (GSAP, ScrollTrigger, Lenis from jsDelivr); no build step, and none is needed for copy, colour or photo edits.

## Files
Edit these files, not a page fetched by URL (that arrives as a summary).
```bash
curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/CREDITS.md
```
Upload `index.html`, LICENSE and CREDITS.md; not this file, README.md or `previews/`.

## Keep
- Every `id`, `data-8b-section`, `data-8b-motion` and `data-8b-part` (`section:<id>` styles, `scene:<id>` animation).
- Selectors the scripts use:
  - `section-script:nav`: `.nav__bar` `.nav__toggle` `.menu` `.menu__close`
  - `section-script:contact`: `.contact__status` `data-msg-ok` `data-msg-error`
  - `scene:hero`: `.hero__copy` `.hero__talk` `.hero__media`
  - `scene:listen`: `.listen__sheet` `.listen__title` `.listen__hold` `.listen__panel--voice` `.listen__panel--read` `.listen__track--voice` `.listen__track--read` `.listen__row` `.listen__wave` `.m-caption__text`
  - `scene:calls`: `.calls__list` `.calls__device` `.phone` `data-step`
  - `scene:tune`: `.tune__stage` `.tune__line` `data-ctl` `.tune__fill` `.tune__thumb` `.tune__pill` `.calls__aside` `.calls__sticky` `.phone__screen`
  - `scene:rooms`: `.rooms__hold` `.rooms__track` `.rooms__place` `.rooms__line` `.rooms__talk`
  - `scene:voices`: `.voices__cols` `.voices__col` `.voices__photo`
  - `scene:setup`: `.setup__steps`
  - `scene:start`: `.start__window` `.start__copy`
  - `scene:footer`: `.footer__brand` `.footer__word` `.footer__logo`
- `hero` directly above `listen`, `calls` directly above `tune`: the animation crosses that border and stops if they are split.
- `style="--len:N"` = characters in that display line, spaces included: `Friday at ten` is 13, `works for me.` is 13, `Linea` is 5.
- The phone, the waveform, the settings controls and the step cards are HTML and CSS, not images: change their text in place and recolour them through the CSS variables.
- The contact form's thank-you and error texts are in data-msg-ok and data-msg-error on the <form>.
- The text-message link uses sms: (not tel:); replace the number in both the href and the visible text.
- Colours and fonts are variables in `:root` (`data-8b-part="tokens"`): `--color-1` #1b1411 (espresso text and dark bands), `--color-2` #faf5f0 (warm paper background), `--color-3` #eee5dc (deeper paper bands and review cards), `--color-4` #33cc7a (green buttons, your captions, curved lines), `--color-5` #66574f (muted body text), `--color-6` #1f3954 (navy hero and calls band), `--color-7` #bacde0 (pale blue text on navy), `--color-8` #2e241f (dark brown fill behind the place photos, the closing photo and the Room mode pill), `--color-9` #b8aba3 (muted text on espresso); body text needs 4.5:1 contrast.
- With reduced motion the page must read in full.
- Keep the header comment and `<meta name="generator">`. Keep the "Design: 8B" footer link unless the site owner asks to remove it.

## Replace
- `data-8b-placeholder` (og-image, favicon, phone, email, form): real value in, attribute out; no value, remove the row (no image: drop `og:image`, set `twitter:card` to `summary`).
- "Get Linea free" buttons in the nav, the phone menu and the hero: now #start; owner's target: your sign-up page or app store URL.
- "Download the app" in calls and "Get the app" in the footer: now #start; owner's target: your App Store / Google Play or download URL.
- "Get Linea free" in call-to-action: now #hero (back to the top); owner's target: your sign-up page or app store URL.
- "Book a captioned call" in contact: now #contact-form; owner's target: your booking or calendar URL, or keep it pointing at the form.
- Privacy, Terms and Emergency calling in the footer: now #hero; owner's target: your own legal pages.
- The form in `#contact` (fields `name`, `email`, `message`) sends nothing; `section-script:contact` validates it and shows the thank-you text. Formspree: `action="https://formspree.io/f/<id>"` and `fetch` POST `new FormData(form)` first. Netlify: `data-netlify="true"` and a hidden `form-name`. Or delete it and the script.
- The name Linea (any letter case); the favicon letter and colours in `<link rel="icon">`.
- Photos (9, Unsplash: hero 1, in-person 5, testimonials 1, call-to-action 1, contact 1): `src`, no `srcset`/`sizes`, `width`/`height` to the ratio, `alt`, CREDITS.md.
- `<title>`, meta description, og tags.

## Ask the owner for
All demo text, never to be invented:
- Rating and reviews: "4.8 from 9,400 reviews" (hero), eight five-star reviews with names Marguerite L., Tomás R., Daniel K., Hannah W., Evelyn C., Ruth A., Samuel O., Priya N. and their claims ("Set up in five minutes", "Forty years with hearing aids") (testimonials).
- Endorsement: "Recommended by clinicians" and the expert Dr. Amara Osei, Audiologist, with her quote (testimonials).
- Pricing and eligibility: free for people with hearing loss, "Free if you qualify", confirm your hearing loss once, "covered by a public accessibility fund", no subscription, a free new number (hero, how-it-works, faq, call-to-action, setup card "Free plan active").
- Setup time: "Ready in five minutes" (call-to-action) and "No installer visit and no special handset" (how-it-works).
- Feature and accuracy claims: captions "within a beat", accurate for fast talkers and bad lines, corrections as each sentence completes, keep your existing number, typed replies read aloud, speaker names, pauses and laughter, Room mode labels each voice (calls, in-person, faq).
- Languages: "Forty-plus languages", "More than forty, including Spanish, French, Mandarin, Arabic and Hindi", automatic language switching (caption-styles, faq).
- Compatibility: pairs with Bluetooth hearing aids, cochlear implant processors and headsets; spam and robocall screening; needs mobile data or Wi-Fi, transcripts readable offline (caption-styles, faq).
- Privacy: transcripts stored on the phone, not on servers; audio processed only for the length of the call and never used for advertising; "Private on your phone" (hero, calls, faq).
- Support: answers by text, email or captioned video call "every day from 7 am to 11 pm Eastern", "we reply within a day" (contact, faq, the form's data-msg-ok message).
- Contacts replaced with placeholders: help@linea.example and the text number (415) 000-0000 (contact, footer); the same number is the demo "Your number" in the phone (calls) and in step 2 (how-it-works).
- Demo call on the phone: "Dr. Park's office", "Captioning live · 02:14", the Thursday/Friday-at-ten appointment, "Voice 2" (calls, caption-styles sample and preview label "Size L · Weight 600 · Dark").
- Company and legal: "© 2026 Linea Inc.", "Made for people with hearing loss, by people who live with it." and the emergency-calling note (footer).

## Known limits
- The second hero caption chip shows only from 1440 px wide; below that there is no free area of the photo for it.
- On phones the docked phone in calls is compact (no controls row, small caption text); the same sentence is shown large in caption-styles.
- The voice-to-text and in-person stages and the stacked steps need JavaScript and motion allowed; with reduced motion or no scripts they fall back to plain layouts (joined panels, a grid of places, a column of steps).
- Without JavaScript the phone menu button cannot open the overlay; the links stay reachable in the footer.

## Check
375 and 1440 px, reduced motion on, console clean; `data-8b-placeholder` and Linea left only in class names.
