# Fairy Tales – Interior Design Landing Page (Google Ads)

A static page with no build step and no framework: `index.html` plus an `images/` folder.
Upload the whole folder to any host (cPanel/WordPress server, Netlify, Vercel, Hostinger, S3 and so on).

Suggested URL: `https://www.fairytalesfurniture.in/interior-designers-trivandrum/`
(this is already set as the canonical URL in `index.html`. If you use a different URL, update that line.)

---

## 1. Add the photos

Put these files in `images/`, using exactly these names. Use JPG, compress each to under 200 KB, and use real project photos only.
Until a photo is added, its slot shows as a beige box with its alt text.

| File | Where it shows | Size (px) |
|---|---|---|
| `logo.png` | Header (already added) | — |
| `hero-1.jpg` | Strip under the hero: living room | 800 × 500 |
| `hero-2.jpg` | Strip under the hero: kitchen | 800 × 500 |
| `hero-3.jpg` | Strip under the hero: bedroom | 800 × 500 |
| `service-kitchen.jpg` | Services: Modular Kitchen | 800 × 500 |
| `service-bedroom.jpg` | Services: Bedroom & Wardrobes | 800 × 500 |
| `service-living.jpg` | Services: Living Room & TV Units | 800 × 500 |
| `service-dining-pooja.jpg` | Services: Dining, Study & Pooja | 800 × 500 |
| `service-false-ceiling.jpg` | Services: False Ceiling | 800 × 500 |
| `service-villa.jpg` | Services: Flat & Villa | 800 × 500 |
| `service-turnkey.jpg` | Services: Turnkey & Renovation | 800 × 500 |
| `service-office.jpg` | Services: Office & Commercial | 800 × 500 |
| `project-1.jpg` … `project-6.jpg` | Recent projects gallery | 800 × 600 |

Photos already on fairytalesfurniture.in that fit: `home-page-interior`, `Projects-1/2/3`, `project22-8`,
`why-choos-1…4`, `trunkey-banner-1`, `architech-banner-1`, `about-sub-1` (all in `/wp-content/uploads/`).

## 2. Fill in the text placeholders

Search `index.html` for `[` to find these:
- `₹[PRICE]` – starting prices (2 BHK, 3 BHK, villa, modular kitchen), 5 places
- `[X–Y weeks]` – typical project timeline
- `[Project name, area]` – captions for the 6 project photos
- `[Paste … review]` – the 3 real client reviews from the website or Google
- `[Confirm list]` – areas served, and the warranty coverage line

## 3. Google Ads tracking

1. In `<head>`, replace `AW-XXXXXXXXX` (2 places) with the Google Ads conversion ID.
2. At the bottom of `index.html`, set the 3 conversion labels:
   - `CONV_FORM` – lead form submitted (primary conversion)
   - `CONV_CALL` – tap on any phone number
   - `CONV_WHATSAPP` – tap on the WhatsApp button
3. Check them with Google Tag Assistant before the ads go live.

If you use Google Tag Manager instead, remove the gtag block and fire tags on the same events.

## 4. Where leads go

At the bottom of `index.html`, set `LEAD_ENDPOINT` to a URL that accepts a JSON POST (CRM webhook,
Google Apps Script to Google Sheet, PHP mailer, Zapier/Make and so on). Each lead includes:

`name, phone, property, scope, location, timeline, gclid, utm_source, utm_medium, utm_campaign, utm_term, utm_content, page`

**Important:** while `LEAD_ENDPOINT` is empty, the form shows "Thank you" but the lead is not saved anywhere.
Connect it and send a test lead before the ads go live.

## 5. Before launch checklist
- [ ] Confirm +91 95674 47700 is active on WhatsApp (the mobile bar links to it)
- [ ] All photos added and compressed (aim for a PageSpeed mobile score of 80+)
- [ ] HTTPS on the final URL
- [ ] Test lead received and the conversion shows in Google Ads
- [ ] Add `noindex` if this page should not show up in organic search alongside the main site
