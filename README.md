# From Fondue to Flexitarian

An interactive data story about how Swiss eating habits are changing, compared with nine other food cultures. Bilingual (English / French).

The site is plain HTML, CSS and JavaScript. It has no framework and no build step.

## Project structure

```
fondue-to-flexitarian/
├── index.html                  Page markup (cover, prologue, chapters 1–5)
├── css/styles.css              All styles
├── js/app.js                   All interactive modules and the embedded data
├── assets/
│   ├── favicon.svg
│   └── fonts/                  Self-hosted Inter (fallback) + OFL licence
├── data/                       Source data used to build the country plates (reference only)
│   ├── country-plates.json
│   └── country-plates-by-year.json
├── package.json                Local preview scripts
├── vercel.json                 Vercel settings (static output, caching)
└── README.md
```

All the data the page needs is already inside `js/app.js`. The page does not read the `data/` folder at runtime; it is there so you can check or reuse the numbers.

## Run it locally

You need Node.js 18 or newer.

```bash
npm run dev
```

Then open http://localhost:3000.

You can also open `index.html` directly in a browser. Everything works except a few browser features that need a server.

## Deploy with GitHub and Vercel

1. Create a new, empty repository on GitHub, for example `fondue-to-flexitarian`.
2. In this folder, run:
   ```bash
   git init
   git add .
   git commit -m "From Fondue to Flexitarian"
   git branch -M main
   git remote add origin https://github.com/<your-username>/fondue-to-flexitarian.git
   git push -u origin main
   ```
3. On vercel.com, choose **Add New → Project** and import the repository.
4. Leave **Framework Preset** on **Other**. The `vercel.json` file already sets everything: there is no build command and the output directory is the project root.
5. Click **Deploy**. Every later `git push` to `main` redeploys the site automatically.

## External resources (loaded from the internet)

- **Fonts:** Inter Tight and Inter come from Google Fonts. If Google Fonts cannot load, the page falls back to the self-hosted Inter in `assets/fonts/`.
- **World map shapes:** `plotly-geo-assets.js` (world country outlines) is loaded from the jsDelivr CDN. If it cannot load, the map in Chapter 4 falls back to simplified, stylised continents.

## Data sources

Our World in Data / FAO (dietary composition by country), Proviande, Swissveg / MACH Consumer, Nutrition Atlas and IRM-HSG St. Gallen, menuCH, BLV and SGE (Swiss food pyramid), Coop / LINK, Poore & Nemecek (2018), ProVeg, Good Growth, the Japanese fisheries white paper and the Korea Rural Economic Institute. The full list with links is in the "Sources" section at the bottom of the page.

The dish compositions in the week planner are estimates of typical recipes, not measured data.

## Licences

- Inter font: SIL Open Font License 1.1 (see `assets/fonts/OFL.txt`).
- Project code and text: © the author. All rights reserved unless you choose a licence.
