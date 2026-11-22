# DataScope · Four Screens

Prototype that tells the data-center story on four screens (three walls and a table), alongside the MIT City Science [DataScope](https://cityscope.media.mit.edu/DataScope/) tool.

Live: https://leticiaig.github.io/datascope-four-screens/

| Screen | Link | Shows |
| --- | --- | --- |
| Left wall | `#sentiment` | The original DataScope, running live inside the page (choose Sentiment map in its bar). A capture is shown where the original cannot be reached |
| Center wall | `#view` | The original DataScope Scenario Editor (Site layout), running live inside the page. A capture is shown where the original cannot be reached |
| Right wall | `#analysis` | The chosen scenario painted, its alternatives as small scenarios with their radars, and the measures: Impacts radar, key figures and Community benefits. Chapters, scenarios and benefits can be clicked |
| Table | `#editor` | Scenario Editor: a map of the real site (street map or satellite, zoom and pan like any web map) with the intervention drawn on it and the control panel (chapters 1–4 and alternatives D1–D4, T1–T4, E1–E4, B1–B4). The building can be dragged and turned inside the study parcel |
| Extra | `#metrics` | Only the measures: radar, one small radar per alternative, key figures and the offer |
| All | `#all` | The four screens laid out like the room. The right wall can switch between Live analysis with images and metrics only |

Screens opened in the same browser stay in step.

## Case studies

The switch in the header (or `?site=texas` / `?site=michigan` in the address) changes the case study on every screen.

- **Michigan** — Allen Park, the site of the original DataScope.
- **Texas** — College Station: about 200 acres of city land in the Midtown Business Park, at Midtown Drive and Corporate Parkway, which the city council declined to sell for a 600 MW data center on 11 September 2025 (reported by KBTX and KXXV). The tract's outline is not drawn; the map shows the crossing the press reports and a circle of the same area, set on the undeveloped land beside it, to give its size. Landmark positions come from Google Maps. With no original tool for this site, the center wall shows the aerial photo and the left wall a sentiment map of its own: positions reported in the press about the proposal (KBTX, KXXV, Chron, BCS Chronicle, TexAgs), each with its source and set around the site, not at anyone's home; and a window left open where the people in the room add their position, one sentence, a picture and a pin. What visitors add is kept in that browser only (Export downloads it as a file; Clear removes it). The figures on the right wall are still those of the Michigan reference building (26 MW), not of the 600 MW proposal.

## Run

Static page, no build. Open `index.html`, or serve the folder:

```
python3 -m http.server
```

## Status

Prototype. The table map follows the original DataScope's Map overview: its site center, approximate study parcel, river bends, landmark points and generalized road, rail, park and building outlines (`dist/geography.js`, `dist/studio/constraints.js` and `dist/studio/model-data.js` in CityScope/DataScope, which list their sources), the same light basemap (OpenFreeMap positron, with OpenStreetMap tiles in grey as a fallback and Esri World Imagery for the satellite view), and wetlands, parks and flood areas read live from the USFWS, USGS PAD-US and FEMA services. MapLibre GL JS and its Leaflet adapter are in `vendor/` with their licenses. The painted view is a hypothetical model of the site, not its surveyed geometry; where map tiles cannot load, a drawn plan of that model is shown instead.
