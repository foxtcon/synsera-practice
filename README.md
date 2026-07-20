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
- **Primary CTA:** Book Health Check Meeting (mailto VJ). Discovery is a paid
  stage name, not a booking label.
- **Pipeline framing:** Project A (governance / Copilot readiness; Foxtcon can
  run Health Check through Implementation under Synsera) and Project B
  (Purview catalog foundations Foxtcon can extend into DLP / Insider Risk).
  Synsera owns the clients; Foxtcon is the white-label delivery engine.
- **Start here path:** Welcome → Fit → Project A → Project B → Get started
  (Health Check Meeting). Sample client journey lives under The program.
- **Beyond Security:** `beyond-security.html` lists 36 digital services
  (Digital Growth, Enterprise IT, App Studio, AI Studio) under the same
  commercial model, powered by Suvysoft.
- **Client lift page:** Synsera-branded section ready to place on synsera.co.uk
  (keep demoted until Synsera brand-approves public copy).

## Files
- `index.html` - the practice hub (hash routes, e.g. `#welcome`, `#first`, `#site`)
- `beyond-security.html` - digital services catalogue (36 services)
- `practice-presenter.html` - optional live Health Check presenter tool
- `assets/foxtcon-logo.png` - local Foxtcon logo (do not depend on the live website)
- `Synsera_Stage0_Readiness_Profile_Template.html` - Pre-Health Check sample
- `Synsera_Deliverable_1_HealthCheck.html` … `_6_Managed.html` - sample deliverables
- `Synsera_Deliverable_Discovery.html` - Discovery sample
- `Synsera_Sample_BeyondSecurity_AI_Setup.html` - AI Studio SOW-shaped sample
- Sample URLs support `?client=1` for Synsera-only client export (hides Foxtcon mark)
- `404.html` - redirects stray URLs back to the hub
- `robots.txt` - Disallow all (partner-confidential)
- `_headers` - Cloudflare Pages security headers (noindex, frame deny, etc.)
- `CNAME` - synsera.foxtconsecurity.com

Everything uses relative paths. Keep files in this folder layout.

`index.html` and `beyond-security.html` intentionally duplicate the Synsera /
Foxtcon chrome CSS tokens so each page stays a single static file. When you
change brand colours or sidebar behaviour, update both.

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

### 3. Required before sharing (Cloudflare Access)

This hub is partner-confidential commercial material. `noindex` / `robots.txt` /
`_headers` reduce indexing and clickjacking risk, but they are **not**
authentication. Do not treat a JavaScript password prompt as security.

**Turn on Cloudflare Access before forwarding the live URL to Synsera:**

1. Cloudflare Zero Trust → Access → Applications → Add an application → Self-hosted
2. Application domain: `synsera.foxtconsecurity.com`
   - Also protect any `*.pages.dev` preview host if you share it
3. Policy name example: `Synsera Foxtcon partner hub`
4. Action: Allow
5. Include (policy owners / who may open the hub):
   - Emails ending in Synsera's domain(s) (confirm with Shehbaz / Juber)
   - Emails ending in `@foxtcon.com` (and any other Foxtcon domains in use)
   - Named individual emails for the pitch room if domains differ
6. Prefer **One-time PIN (email OTP)** over a shared password
7. Session duration: short enough for a partner hub (for example 24 hours)

Also:
- Keep the GitHub repo **private**
- Pages already ship with `noindex` meta, `robots.txt` (`Disallow: /`), and
  `_headers` (X-Frame-Options, Referrer-Policy, Permissions-Policy, X-Robots-Tag)
- Optional later: add a Content-Security-Policy in `_headers` once Access is live.
  Current pages use inline CSS/JS, so any CSP must allow `'unsafe-inline'` for
  `script-src` and `style-src` or the hub will break. A commented template sits
  in `_headers`.

### 4. Make changes
```
git add .
git commit -m "what changed"
git push
```

------------------------------------------------------------------------

## Editing notes
- House style: no em dashes and no en dashes.
- Primary booking CTA label: **Book Health Check Meeting** (not discovery call,
  not mock session). Mailto: `vj@foxtcon.com`.
- Delivery story: senior-led by VJ; certified specialists across the USA and
  India; white-label behind Synsera; Foxtcon can own Assessment→Implementation;
  day rate or fixed price under SOW. Only Pre-Health Check and Health Check are
  complimentary; do not imply the whole practice or later stages are free.
- Do not invent Synsera client prices, net rates, win counts, or delivery SLAs
  without SOW evidence.
- Microsoft claims: Entra Agent ID GA **April 2026**; unified Purview DSPM
  **May 2026**; Sentinel in Defender portal GA; Azure-portal Sentinel retires
  31 March 2027.
- Illustrative sample client in deliverables is Northbridge Insurance (clearly
  SAMPLE). Live pipeline framing in the hub uses anonymised labels only:
  Project A and Project B. Do not put real client names or identifying estate
  maths on forwardable pages.
- Before any end-client sees numbers or claims, sanity-check they are defensible.
- For client-forwardable samples, open with `?client=1` or use the Synsera-only
  export link on each stage page.

## Useful hash links for Synsera
- `#welcome` - partnership welcome
- `#synfit` - fit with Synsera's AI / Purview / agents offer
- `#first` - Project A (governance / Copilot readiness)
- `#utilities` - Project B (catalog foundations → DLP / IRM)
- `#contact` - Get started / Book Health Check Meeting
- `#site` - client-facing page lift
- `#lifecycle` - eight-stage program
- `#commercial` - billing and pipeline (day rate or fixed)
- `#wl` - white-label engagement model
- `#breadth` - capability breadth (links to Beyond Security)
