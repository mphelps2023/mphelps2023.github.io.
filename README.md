# Madison (Sluter) Phelps, Ph.D. | CV

Personal CV site for Madison (Sluter) Phelps, Ph.D., Senior Scientific Writer at the Office of Data Science, St. Jude Children's Research Hospital.

Live site (after deployment): `https://<your-github-username>.github.io/<repo-name>/`

## What is in this repository

| File | Purpose |
|---|---|
| `index.html` | The full CV. Self-contained: all CSS, JavaScript, animations, and the headshot are embedded. No external dependencies. |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is and skip Jekyll processing. Keep this file. |
| `README.md` | This file. Not published to visitors. |

The site is one HTML file. There are no build steps, no `node_modules`, no package manager. Edit and push.

## Deploy to GitHub Pages

### Option A: personal site (recommended for a CV)
Your CV will live at `https://<username>.github.io/`.

1. On GitHub, create a new **public** repository named exactly `<your-github-username>.github.io` (for example, `madison-sluter-phelps.github.io`).
2. Upload `index.html`, `.nojekyll`, and `README.md` to the repository root. You can drag and drop them in the GitHub web UI via **Add file > Upload files**.
3. Go to **Settings > Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**, then **Branch** to `main` and folder to `/ (root)`. Save.
5. Wait about a minute. Your site will be live at `https://<username>.github.io/`.

### Option B: project site
Your CV will live at `https://<username>.github.io/<repo-name>/`.

1. Create any public repository (for example, `cv`).
2. Upload the three files.
3. **Settings > Pages > Source = Deploy from a branch**, **Branch = main**, folder `/ (root)`. Save.
4. Site publishes at `https://<username>.github.io/cv/`.

### Optional: custom domain
1. Buy a domain (for example, `madisonphelps.com`).
2. Add a file named `CNAME` in the repo root containing just your domain, no protocol: `madisonphelps.com`
3. In your domain registrar, add these DNS records:
   - `A` records for the apex domain pointing to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` record for `www` pointing to `<username>.github.io`
4. In **Settings > Pages**, enter your custom domain and check **Enforce HTTPS** once the certificate provisions.

## Updating the CV

The whole CV is `index.html`. Two low-effort ways to keep it current:

**A. Content edits.** Section text (jobs, publications, awards, talks, etc.) lives directly in the HTML markup under each `<details class="sec">` block. Search for the section heading and edit the surrounding markup.

**B. Visuals and data.** Numbers and lists that drive the animated widgets live in a single JSON block near the bottom of the file:

```html
<script id="cvConfig" type="application/json"> ... </script>
```

This block controls:

- `skills` - sidebar Core Strengths meters (label and percent).
- `chips` - Tools & Software chip list.
- `deliverables` - Signature Deliverables bar chart in "At a Glance" (label, count, and bar `weight` from 0 to 100).
- `topics` - Focus Areas donut (label, percent, color).
- `reveal` and `counters` - animation timings.

Change a value, save, push. No JavaScript editing required.

## Local preview

Just double-click `index.html` in a file browser. It runs entirely in the browser with no server required. To preview with a local server (recommended, since some browsers restrict `file://` behavior for observers):

```bash
# Python 3
python3 -m http.server 8080
# then open http://localhost:8080/
```

## Export as PDF

Open the site, press `Ctrl/Cmd + P`, choose **Save as PDF**. The stylesheet includes a `@media print` block that:

- Expands every collapsible section automatically.
- Removes the animated backdrop glows.
- Preserves the navy sidebar and pink accents.
- Prevents section breaks mid-role.

## Accessibility and browser support

- Semantic HTML (`<main>`, `<aside>`, `<details>`, `<summary>`, `<section>`).
- Keyboard navigable: section headings are `<summary>` elements, focusable and toggleable with Enter or Space.
- All animations respect the browser's reduced-motion preferences when the OS setting is enabled (via the underlying transition properties).
- Tested layouts: modern Chrome, Edge, Firefox, and Safari on desktop and mobile.
- No external network requests. The site works offline once loaded.

## Privacy

- No analytics scripts.
- No third-party fonts, CSS, or JS.
- No cookies.
- The only outbound links are the ones you added (LinkedIn, Google Scholar, DOIs, stjude.org/ods, cell.com).

## Credits

- Design and content: Madison (Sluter) Phelps, Ph.D.
- Typefaces used are system stacks (Inter, Merriweather, Georgia, Helvetica, Arial) so nothing needs to be loaded from a font CDN.

## License

Personal CV content. All rights reserved. If you would like to reuse the layout as a template for your own CV, please contact me.
