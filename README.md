# Synsera x Foxtcon One - Microsoft Security Practice (partner hub)

Static partner hub for the Synsera × Foxtcon One Microsoft Security practice and
program. No build step, no framework. HTML, CSS, and a little vanilla JS.

**Audience:** Synsera leadership (Shehbaz, Juber, and team). Partner-review and
sales enablement. Not a public marketing site.

Target URL: https://synsera.foxtconsecurity.com

## What this is
- **White-label delivery:** Synsera owns the client relationship and brand.
  Foxtcon One is the Microsoft Security delivery engine behind it.
- **Program:** Pre-Health Check (~30 min) and Health Check (45-60 min)
  are complimentary; Discovery onward is scoped and paid under SOW through
  Envisioning → White Glove Assessment → Architecture → Implementation →
  optional Manage.
- **Pipeline framing:** Project A (governance / Copilot readiness; Foxtcon can
  run Health Check through Implementation under Synsera) and Project B
  (Purview catalog foundations Foxtcon can extend into DLP / Insider Risk).
  Synsera owns the clients; Foxtcon is the white-label delivery engine.
  Optional mock session with Synsera’s internal team before live delivery.
- **Start here path:** Welcome → Fit → Project A → Project B → Get started
  (mock agenda). Sample client journey lives under The program.
- **Client lift page:** Synsera-branded section ready to place on synsera.co.uk.

## Files
- `index.html` - the practice hub (hash routes, e.g. `#welcome`, `#first`, `#site`)
- `assets/foxtcon-logo.png` - local Foxtcon logo (do not depend on the live website)
- `Synsera_Stage0_Readiness_Profile_Template.html` - Pre-Health Check sample
- `Synsera_Deliverable_1_HealthCheck.html` … `_6_Managed.html` - sample deliverables
- `Synsera_Deliverable_Discovery.html` - Discovery sample
- `404.html` - redirects stray URLs back to the hub
- `robots.txt` - Disallow all (partner-confidential)
- `_headers` - Cloudflare Pages security headers (noindex, frame deny, etc.)
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

### 3. Strongly recommended before sharing (access control)

This hub is partner-confidential. `noindex` / `robots.txt` / `_headers`
reduce indexing and clickjacking risk, but they are **not** authentication.
Do not treat a JavaScript password prompt as security.

**Cloudflare Access (recommended):**
1. Cloudflare Zero Trust → Access → Applications → Add an application → Self-hosted
2. Application domain: `synsera.foxtconsecurity.com` (or your `*.pages.dev` host)
3. Policy: Allow → include emails / email domains for Synsera and Foxtcon only
4. Optional: require one-time PIN (email OTP) so no shared password is needed

Also:
- Keep the repo **private**
- Pages already ship with `noindex` meta, `robots.txt` (`Disallow: /`), and
  `_headers` (X-Frame-Options, Referrer-Policy, Permissions-Policy, X-Robots-Tag)

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
  India; white-label behind Synsera; Foxtcon can own Assessment→Implementation;
  day rate or fixed price under SOW. Only Pre-Health Check and Health Check are
  complimentary; do not imply the whole practice or later stages are free.
- Microsoft claims: Entra Agent ID GA **April 2026**; unified Purview DSPM
  **May 2026**; Sentinel in Defender portal GA; Azure-portal Sentinel retires
  31 March 2027.
- Illustrative sample client in deliverables is Northbridge Insurance (clearly
  SAMPLE). Live pipeline framing in the hub uses anonymised labels only:
  Project A and Project B. Do not put real client names or identifying estate
  maths on forwardable pages.
- Before any end-client sees numbers or claims, sanity-check they are defensible.

## Useful hash links for Synsera
- `#welcome` - partnership welcome
- `#synfit` - fit with Synsera’s AI / Purview / agents offer
- `#first` - Project A (governance / Copilot readiness)
- `#utilities` - Project B (catalog foundations → DLP / IRM)
- `#site` - client-facing page lift
- `#lifecycle` - eight-stage program
- `#commercial` - billing and pipeline (day rate or fixed)
- `#wl` - white-label engagement model
