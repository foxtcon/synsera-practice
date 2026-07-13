# Synsera x Foxtcon One - Microsoft Security Practice (live site)

A single, static website that showcases the practice, the eight-stage program, the
nine MCRA pillars, the commercial and pipeline model, sample client deliverables, and
the Fox AI assistant. No build step, no framework. Just HTML and CSS, so it is fast,
cheap to host, and easy to edit in Cursor.

Target URL: https://synsera.foxtconsecurity.com

## Files
- `index.html` - the practice hub (the whole experience lives here)
- `Synsera_Deliverable_1_HealthCheck.html` ... `_6_Managed.html` - sample client deliverables (open in-window from the stage pages)
- `Synsera_Stage0_Readiness_Profile_Template.html` - Pre-Health Check sample
- `404.html` - redirects stray URLs back to the hub

Everything is linked with relative paths, so keep all files in the same folder.

------------------------------------------------------------------------

## Recommended setup: GitHub + Cloudflare Pages

Why this stack: free, automatic HTTPS, global CDN, and every time you push a change
from Cursor the live site updates in about 30 seconds. Cloudflare also fits the
security brand and gives you DNS, caching, and protection in one place.

### 1. Put the site in a GitHub repo (from Cursor)
1. Open this folder in Cursor (File > Open Folder).
2. Terminal (Ctrl+`) and run:
   ```
   git init
   git add .
   git commit -m "Initial Synsera x Foxtcon One practice site"
   ```
3. Create a new EMPTY repo on github.com (name it e.g. `synsera-practice`). Do not add a README there.
4. Back in Cursor terminal, connect and push (use the commands GitHub shows you):
   ```
   git remote add origin https://github.com/<your-user>/synsera-practice.git
   git branch -M main
   git push -u origin main
   ```

### 2. Deploy on Cloudflare Pages
1. Sign in at https://dash.cloudflare.com (create a free account if needed).
2. Workers and Pages > Create > Pages > Connect to Git > pick the repo.
3. Build settings: Framework preset = None. Build command = blank. Output directory = `/` (root).
4. Save and Deploy. You get a live URL like `synsera-practice.pages.dev` in under a minute.

### 3. Point synsera.foxtconsecurity.com at it
In Cloudflare Pages > your project > Custom domains > Set up a custom domain, enter
`synsera.foxtconsecurity.com`. Cloudflare shows you the DNS record to add.

Then in IONOS (Domains > foxtconsecurity.com > DNS):
- Add a `CNAME` record:
  - Host / Name: `synsera`
  - Points to / Value: `synsera-practice.pages.dev` (the value Cloudflare gives you)
  - TTL: default (1 hour is fine)
- Save. Propagation is usually minutes, up to an hour.

HTTPS is issued automatically. Done.

### 4. Make changes later (the whole point)
Edit any file in Cursor, then:
```
git add .
git commit -m "what changed"
git push
```
The live site updates itself. No re-uploading, no rebuilding.

------------------------------------------------------------------------

## Alternatives (if you prefer)
- Netlify: same idea, arguably the simplest. Connect the GitHub repo at app.netlify.com,
  deploy, then Domain settings > Add custom domain > `synsera.foxtconsecurity.com`, and add
  the CNAME it gives you at IONOS.
- GitHub Pages: free and built in. Repo > Settings > Pages > deploy from `main` branch, then
  add a custom domain and a CNAME at IONOS. Slightly slower cache invalidation than Cloudflare.

------------------------------------------------------------------------

## Notes
- The Foxtcon One logo loads from foxtcon1.com. Keep that image reachable, or drop a local
  copy into this folder and update the `<img src>` in `index.html`.
- No em dashes anywhere, per house style. Keep it that way when editing.
- This is a partner-review and sales tool. Before pointing real clients at it, sanity check
  any illustrative figures (deployment counts, savings) so they are defensible.
- To keep the internal build off the public web, you can keep the repo private and still
  deploy from it. Cloudflare Pages and Netlify both deploy private repos.
