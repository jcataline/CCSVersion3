# Convenient Care Solutions — Single-Page Site + Ad Variants

A complete, self-contained website in three HTML files. No build step, no dependencies.
The entire booking funnel is call/text (tel:/sms: to 330-862-9127) — no form, no email,
so the pages collect no patient information and raise no PHI/HIPAA concerns.

## Files
- **index.html** — your main page. This is what loads at your domain. Targets Ohio + Illinois.
- **ohio.html** — ad variant for Ohio campaigns. Headline + SEO emphasize "insurance accepted,
  evenings & weekends." Point your Ohio Google/Meta ads here.
- **chicago.html** — ad variant for Chicago/suburbs campaigns. Headline + SEO emphasize
  "private, concierge-level, self-pay, no insurance hassle." Point your Chicago ads here.

All three share the same design; only the headline, page title, meta description, and
LocalBusiness schema differ. That "message match" (ad text = landing headline) raises Google
Ads Quality Score, which lowers your cost-per-click.

This is final and ready to deploy: prices are set ($99 / $159 / $249 per-visit, $199/mo concierge),
the physician photo is embedded, and there are no testimonials. To change a price later, edit the
three spots per file marked `PRICE:` (hero card, visit tiers, concierge box).

---

## Hosting: single page on Vercel, with your domain pointed to it (recommended)

Because this is now your whole site, you can point your real domain straight at Vercel.

### 1. Deploy
- **Vercel CLI:** install once (`npm i -g vercel`), run `vercel` in this folder, then `vercel --prod`.
- **Or GitHub:** push this folder to a repo, then import it at vercel.com (framework preset: Other).
- Test the `*.vercel.app` URL. You'll see:
  - `…vercel.app/`        → index.html
  - `…vercel.app/ohio`    → Ohio variant
  - `…vercel.app/chicago` → Chicago variant

### 2. Point your domain (apex)
1. Vercel project → **Settings → Domains → Add** → enter `convenientcaresolutions.com`
   (and `www.convenientcaresolutions.com`).
2. Vercel shows the DNS records to set — typically an **A record** for the apex
   (e.g. `76.76.21.21`) and a **CNAME** for `www` → `cname.vercel-dns.com`.
   Use exactly what Vercel displays.
3. In Squarespace (where your domain currently lives): **Settings → Domains →**
   (your domain) **→ DNS Settings → Custom Records**, and set the records Vercel gave you.
   Remove the old Squarespace A/CNAME records that pointed the domain at Squarespace.
4. SSL is issued automatically once Vercel sees the records. Propagation: minutes to a few hours.

> Once the domain points to Vercel, your old Squarespace site no longer serves your domain.
> You can keep the domain registered at Squarespace (registration ≠ hosting) and, if you want,
> drop the Squarespace website plan to save money — confirm domain/registration terms first.
> The Squarespace plan question (which gates code blocks) becomes irrelevant on this route.

### 3. Ads
- Ohio campaigns → `convenientcaresolutions.com/ohio`
- Chicago campaigns → `convenientcaresolutions.com/chicago`
- Everyone else / typed-in domain → `convenientcaresolutions.com` (index)

---

## Local SEO (the organic lever)
On-page text on one site won't out-rank dedicated local pages, so your real organic
local-search tool is a **Google Business Profile** — ideally one positioned for each market
you serve. Keep name/phone/website identical to this site, gather reviews, and list your
services. That moves the needle on "telehealth near me" far more than the page copy does.

The schema (structured data) already baked into each file tells Google your business type,
phone, price range, and which areas you serve (Ohio / Illinois / Chicago) — it helps Google
understand the pages but does not replace a Business Profile.

---

## Alternative: keep it in Squarespace
If you'd rather not move hosting: make index.html a new Squarespace page set as your homepage,
delete the other pages, and paste the inner content into a code block (requires Core plan or
higher for the JavaScript). This is more fiddly and makes the ad variants harder to manage,
which is why Vercel is recommended for a single-page, ad-driven site. Ask and I'll generate a
pre-stripped Squarespace version.


## Legal / compliance pages (added for LegitScript + patient transparency)
- `privacy.html`  -> /privacy  (HIPAA Notice of Privacy Practices — verbatim from attorney draft)
- `terms.html`    -> /terms    (Patient Service Agreement, Controlled Substance & Prescription History consents; membership pricing set to single $199/mo concierge + $99/$159/$249 visits)
- `telehealth-consent.html` -> /telehealth-consent  (Telehealth, AI & Remote Monitoring consent — verbatim)
All three are linked in the site footer. Public practice address (Canfield) is in the footer;
the Selkirk/Youngstown address remains the official + Privacy Contact address per the attorney draft.
