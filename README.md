# Synsera x Foxtcon One - Microsoft Security Practice (partner hub)

Static partner hub for the Synsera × Foxtcon One Microsoft Security practice and
program. No build step, no framework. HTML, CSS, and a little vanilla JS.

**Audience:** Synsera leadership (Shehbaz, Juber, and team). Partner-review and
sales enablement. Not a public marketing site.

Target URL: https://synsera.foxtconsecurity.com

## What this is
- **White-label delivery:** Synsera owns the client relationship and brand.
  Foxtcon One is the Microsoft Security delivery engine behind it.
- **Program:** Pre-Health Check (~60 min) → interview-based Health Check
  (45–60 min) → Discovery → Envisioning → White Glove Assessment →
  Architecture → Implementation → optional Manage.
- **First client framing:** Cole Technologies (fine-tune before scale), plus a
  recommended mock delivery session with Synsera’s internal team.
- **Client lift page:** Synsera-branded section ready to place on synsera.co.uk.

## Files
- `index.html` - the practice hub (hash routes, e.g. `#welcome`, `#first`, `#site`)
- `assets/foxtcon-logo.png` - local Foxtcon logo (do not depend on the live website)
- `Synsera_Stage0_Readiness_Profile_Template.html` - Pre-Health Check sample
- `Synsera_Deliverable_1_HealthCheck.html` … `_6_Managed.html` - sample deliverables
- `Synsera_Deliverable_Discovery.html` - Discovery sample
- `404.html` - redirects stray URLs back to the hub
- `robots.txt` - Disallow all (partner-confidential)
- `CNAME` - synsera.foxtconsecurity.com

Everything uses relative paths. Keep files in this folder layout.

------------------------------------------------------------------------

## Recommended setup: GitHub + Cloudflare Pages

Why this stack: free, automatic HTTPS, global CDN, and every push updates the
live site in about 30 seconds.

### 1. Deploy on Cloudflare Pages
1. Sign in at https://dash.cloudflare.com
2. Workers and Pages > Create > Pages > Connect to Git > pick this repo
3. Build settings: Framework preset = None. Build command blank. Output directory = `/`
4. Deploy, then add custom domain `synsera.foxtconsecurity.com`

### 2. DNS at IONOS
- CNAME host `synsera` → your `*.pages.dev` hostname from Cloudflare

### 3. Strongly recommended before sharing
- Keep the repo **private**
- Add Cloudflare Access (email allow-list for Synsera and Foxtcon) so the hub
  is not open to the public web
- Pages already ship with `noindex` meta and `robots.txt`

### 4. Make changes
```
git add .
git commit -m "what changed"
git push
```

------------------------------------------------------------------------

## Editing notes
- House style: no em dashes.
- Delivery story: senior-led by VJ; certified specialists across the USA and
  India; white-label to Synsera’s clients; day rate or fixed price under SOW.
- Microsoft claims: Entra Agent ID GA **April 2026**; unified Purview DSPM
  **May 2026**; Sentinel in Defender portal GA; Azure-portal Sentinel retires
  31 March 2027.
- Illustrative sample client in deliverables is Northbridge Insurance. Live
  first-client framing in the hub is Cole Technologies.
- Before any end-client sees numbers or claims, sanity-check they are defensible.

## Useful hash links for Synsera
- `#welcome` - partnership welcome
- `#synfit` - fit with Synsera’s AI / Purview / agents offer
- `#first` - Cole Technologies
- `#site` - client-facing page lift
- `#lifecycle` - eight-stage program
- `#commercial` - billing and pipeline (day rate or fixed)
- `#wl` - white-label engagement model
