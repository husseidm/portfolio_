# Siwa Oasis case study: publishing guide

## 1. Files and where they go

Replace / add these in the root of your `portfolio_` repository:

```
portfolio_/
├── index.html                      REPLACE with the updated one (adds one card, nothing else changes)
├── siwa-change-detection.html      NEW case study page
└── images/
    └── siwa/                       NEW folder (8 files)
        ├── ndvi-layout.png         full-resolution original (4250 x 5500), used by the zoom viewer
        ├── ndvi-layout-web.png     2000 px inline version, same aspect ratio
        ├── mndwi-layout.png / mndwi-layout-web.png
        ├── ndti-layout.png  / ndti-layout-web.png
        └── sst-layout.png   / sst-layout-web.png
```

## 2. What changed in index.html

Only two additions, both marked in the file:
- a CSS block starting with `/* ── Siwa teaser card (added) ── */` (just before `</style>`)
- a card with the comment `NEW: Siwa Oasis environmental change detection` at the end of the
  Remote Sensing Projects section, after the Dead Sea project. It shows the four layouts as
  thumbnails and a "View Full Case Study" button linking to `siwa-change-detection.html`.

To show it before the Dead Sea project instead, cut that card and paste it above the
`<div class="rs-project reveal">` of the Dead Sea.

## 3. Styling

The case study page uses the same colour tokens, fonts (Space Grotesk, JetBrains Mono),
navigation bar, light/dark toggle and footer as index.html. Its nav links go back to the
matching sections of `index.html`.

## 4. Publish through GitHub

Website: open the repository, Add file > Upload files, drag in `index.html`,
`siwa-change-detection.html` and the `images` folder, then Commit changes.

Command line:

```
git add index.html siwa-change-detection.html images/siwa
git commit -m "Add Siwa Oasis change detection case study"
git push
```

GitHub Pages rebuilds in about a minute. Then open
`https://husseidm.github.io/portfolio_/siwa-change-detection.html` and check the images,
the zoom viewer, and the Back to Portfolio links.

## 5. Information still needed (yellow highlights on the page)

- Country / region of Siwa Oasis, coordinates, projection
- Satellite sensor(s), processing level, spatial resolution
- Acquisition dates for 2014, 2018, 2021, 2024
- Band numbers for NDVI, MNDWI and NDTI
- Temperature product, thermal band, conversion method, and whether the unit is °C
- Subtraction order for the difference maps, and the class thresholds
- How the area values in the NDVI and MNDWI charts were derived
- Whether any field turbidity data was used to check NDTI
- Any extra tools used (Raster Calculator, Spatial Analyst, GEE, Python)

## 6. Corrections to consider in the layouts before publishing

- The MNDWI and NDTI layouts carry the footer caption "Change in vegetation cover of Siwa Oasis over four years" (copied from the NDVI layout).
- The temperature layout's Arabic chart subtitle says "sea temperature"; the study area is inland.
- The NDVI, MNDWI and NDTI scale bars say "Depth Units = KM"; the temperature layout says "Data Unit = Kilometers". A scale bar measures distance, so "Map distance" is the usual wording.
- The temperature colour ramp puts red-orange at the lowest value and blue at the highest, the reverse of the usual warm-red convention.
- The NDVI explanatory text mixes index values with change values (negative / positive / near zero).
- The NDTI legend title reads "Map Change 2018 & 2014" while the map titles read "2014 & 2018".
- The temperature layout has no difference map.
