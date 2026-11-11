# needmorespace.studio website

Website of Need More Space Studio, an interior design studio in Bangkok.
Live at https://www.needmorespacestudio.com (GitHub Pages, custom domain in `CNAME`).
Pushing to `main` publishes the live site within 1–2 minutes. There is no build step and no staging.

The owner (Panupong) writes in Thai and often works from his phone. Reply in Thai.

## How to work on this site

- **No preview on mobile.** Before pushing, explain in Thai, briefly, what changed on which page,
  so the owner can approve. Small copy/image edits: push to `main` after he approves.
  Big layout or design changes: say so and suggest checking on desktop first.
- After pushing, give the live URL of the changed page so he can check it.
- Commit messages in English, describing what changed and why.
- Never upload or replace HTML pages via GitHub's web "Add files via upload". On 5 Nov 2026 an
  upload overwrote 6 pages with old versions and dropped GA4, Pixel, canonical/OG, owner mode and
  optimized images (fixed in "Restore pages overwritten by upload"). If an uploaded file shows up,
  diff it against the previous commit before keeping it.
- Do not leave backup copies (e.g. `index (1).html`) in the repo: every file here is public.
- Change all pages consistently. There are ~14 pages that share nav, footer, tracking and CTAs
  as copy-pasted code (no templates), so a change to one shared part usually needs every page.

## Pages

- `index.html` homepage, `projects.html` portfolio, `contact.html`, `budget-guide.html`
  (free budget checklist landing page; PDF `needmorespace-budget-checklist.pdf` hosted here).
- Project pages: `chun-residence`, `cozy-retreat-kpei`, `grand-britania`, `harmony-curve`
  (Millennium IVF Clinic), `ivory-grace`, `kao-vow`, `private-resident-kmax`, `the-five`,
  `the-refined-core`, `venue-flow`.
- Tiny redirect pages (`grand-britania-rama-5.html`, `harmony-curve-clinic.html`,
  `the-crest-residence.html`) and folders like `home/`, `kpei/`, `services-6-1-1/` keep old
  Squarespace URLs working for SEO. Do not delete them.
- `sitemap.xml`: update it (and `lastmod`) when adding or renaming pages.

## Adding a new project page

Copy the newest project page (`the-refined-core.html`) as the template, then:
1. Images: resize to max 1920px, save as `.webp` in `img/` named `<project>-<room>.webp`,
   plus one `<project>-og.jpg` for social sharing. Lazy-load gallery images.
2. Title: Thai keyword first, e.g. `ออกแบบ... <ขนาด> <ทำเล> | Need More Space Studio`.
   Keep the meta description short.
3. Keep canonical, Open Graph, twitter:card, schema, GA4, Meta Pixel, owner mode and the
   More Projects strip.
4. Add it to the homepage carousel, `projects.html`, the footer nav, other pages' More Projects
   strips where relevant, and `sitemap.xml`.
5. Double-check room labels against the photos (labels have been wrong before).

## Design system

- Colours (CSS variables in each page): `--white #FDFAF6`, `--off #F2EDE4`, `--sand #E5DDD1`,
  `--muted #9A9080`, `--dark #1C1A16`, `--ink #2A2620`, `--gold #B89860`. Light theme, no dark
  section backgrounds.
- Fonts: Marcellus (English headings), Noto Serif Thai (Thai headings), DM Sans (body).
  Only weights 300/400/600 are loaded; do not use other weights.
- On desktop, emphasise with colour, not bold.
- Thai text: no line breaks in the middle of a Thai word; avoid orphan words.
- Breakpoints in use: 768, 900, 1100, 1366px. Check desktop, tablet (iPad) and mobile.
- LINE buttons use the gold palette.
- Right-click is disabled on pages (image protection); keep it on new pages.

## Contact and tracking (keep on every page)

- All consult / contact buttons go to LINE OA `https://line.me/R/ti/p/%40299qrytx`.
  Mobile has a LINE bar; index and contact show `line-qr.png`. The old contact form was removed.
- Phone 090-545-6166, email needmorespacestudio@gmail.com.
- GA4 `G-R0CKBW47ZQ`. Events: `line_click` for LINE, `contact_click` for other contact
  (not LINE), `guide_download` / `generate_lead` on the budget guide.
- Meta Pixel `966270802855166`, with a `Contact` event on LINE clicks.
- Owner mode: visiting any page with `?owner=1` stops counting that device in GA4 and Pixel
  (`?owner=0` turns it off). Every page must include the owner-mode snippet before GA4/Pixel.

## Copy rules

- Budget language: "plan and control" the budget. Do not promise a locked price or
  claim "no hidden costs".
- Do not state a number of projects per year (matches the LINE bot's rules).
- Positioning: premium, curated, limited queue; calm and transparent tone.
