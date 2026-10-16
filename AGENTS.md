# Linea — notes for AI coding agents

One HTML file: markup, inline CSS and inline scripts; GSAP with ScrollTrigger and SplitText, Lenis smooth scroll, all from jsDelivr. No build step, no framework.

## Files
Work from the files: a page read through a link comes back as a summary, and a page rebuilt from it would differ.
```bash
curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/app-landing-page-template/main/CREDITS.md
```
In Windows PowerShell type `curl.exe`. Publish `index.html` with LICENSE and CREDITS.md; this file, README.md and `previews/` are not part of the site.

## Do not break
- Keep it one file unless the user asks otherwise; no framework or bundler for copy, colour or photo changes.
- Keep the ids and the `data-8b-section` / `data-8b-motion` attributes. Each section has its styles in `<style data-8b-part="section:<id>">` and its animation, if any, in `<script data-8b-part="scene:<id>">`.
- The scripts find these classes and attributes; when you change a section's markup, keep them or update the script:
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
- Colours, fonts, radii and shadows are CSS variables in the `:root` block (`data-8b-part="tokens"`); change them there and keep body text at 4.5:1 contrast or more.
- Animations run only when the visitor allows motion (`prefers-reduced-motion: no-preference`); the page must stay readable without them.
- A display line with `style="--len:N"` is sized to fill its width: N is its number of characters, spaces included (`Friday at ten` → 13, `works for me.` → 13).
- These neighbouring sections animate across their border: hero → listen, calls → tune. Keep each pair next to each other, or that transition switches off.
- Keep the header comment and `<meta name="generator">`; the "Design: 8B" footer link is optional.

## Replace before publishing
- Everything marked `data-8b-placeholder` (og-image, favicon, phone, email, form); remove the attribute once the real value is in. With no real value: no preview image — delete the `og:image` tag and set `twitter:card` to `summary`; no phone, email or address — remove that link or row.
- "Get Linea free" buttons in the nav, the phone menu and the hero: link to #start now; point them to your sign-up page or app store URL.
- "Download the app" in calls and "Get the app" in the footer: link to #start now; point them to your App Store / Google Play or download URL.
- "Get Linea free" in call-to-action: link to #hero (back to the top) now; point them to your sign-up page or app store URL.
- "Book a captioned call" in contact: link to #contact-form now; point them to your booking or calendar URL, or keep it pointing at the form.
- Privacy, Terms and Emergency calling in the footer: link to #hero now; point them to your own legal pages.
- **The form sends nothing.** `section-script:contact` checks the fields and shows a thank-you message without sending. Pick one:
  - Formspree: set `action="https://formspree.io/f/<id>"` on the form; in the script, before the thank-you message, `await fetch(form.action, { method: 'POST', body: new FormData(form), headers: { Accept: 'application/json' } })` and show it only if the response is ok.
  - Netlify Forms (site on Netlify): add `name="contact" data-netlify="true"` and `<input type="hidden" name="form-name" value="contact">`; send with `fetch('/', { method: 'POST', headers: { 'Content-Type': 'application/x-www-form-urlencoded' }, body: new URLSearchParams(new FormData(form)) })`.
  - No form service: remove the `<form>` together with the script that handles it (it would fail without the form) and keep the email link.
- Invented demo facts (ask the user for the real ones; do not make up prices, dates or addresses):
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
- `<title>`, the meta description and the og tags; photos (Unsplash, see CREDITS.md) when the user has their own.

## Notes
- The phone, the waveform, the settings controls and the step cards are HTML and CSS, not images: change their text in place and recolour them through the CSS variables.
- The contact form's thank-you and error texts are in data-msg-ok and data-msg-error on the <form>.
- The text-message link uses sms: (not tel:); replace the number in both the href and the visible text.
- The third hero caption chip shows only from 1440 px wide; below that there is no free area of the photo for it.
- On phones the docked phone in calls is compact (no controls row, small caption text); the same sentence is shown large in caption-styles.
- The voice-to-text and in-person stages and the stacked steps need JavaScript and motion allowed; with reduced motion or no scripts they fall back to plain layouts (joined panels, a grid of places, a column of steps).
- Without JavaScript the phone menu button cannot open the overlay; the links stay reachable in the footer.

## Common edits
- Rebrand: search the old name (`Linea`) in any letter case and replace every match; change the favicon letter and colours in `<link rel="icon">`.
- Photos: replace `src` and delete `srcset` and `sizes` (they list Unsplash sizes), keep `width`/`height` to the new photo's ratio, update `alt` and CREDITS.md.
- Remove a section: delete its markup, its `section:<id>` and `scene-style:<id>` styles, its `scene:<id>` and `section-script:<id>` scripts, and links to `#<id>`.
- Native scroll instead of smooth scroll: delete the Lenis block in `page-init` and the Lenis `<script>` tag.

## Check and publish
- Open the page at 375 and 1440 px, with reduced motion on, with the console open.
- Search `data-8b-placeholder` and the old name: nothing should be left but class names.
