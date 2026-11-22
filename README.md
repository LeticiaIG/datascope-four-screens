# DataScope · Four Screens

Prototype that tells the data-center story on four screens (three walls and a table), alongside the MIT City Science [DataScope](https://cityscope.media.mit.edu/DataScope/) tool.

Live: https://leticiaig.github.io/datascope-four-screens/

| Screen | Link | Shows |
| --- | --- | --- |
| Left wall | `#sentiment` | The original DataScope, running live inside the page (choose Sentiment map in its bar). A capture is shown where the original cannot be reached |
| Center wall | `#view` | The original DataScope Scenario Editor (Site layout), running live inside the page. A capture is shown where the original cannot be reached |
| Right wall | `#analysis` | The chosen scenario painted and its alternatives, each with its own wheel. Beside them, in words: what the scenario **gains**, what it **gives up** and what is **not known yet**. Tap a result to trace it back: result ← because ← the choice it comes from, with the number behind it and its source. Ask about a result by typing or speaking; what cannot be traced is kept as a question for the developer |
| Table | `#editor` | Scenario Editor: a map of the real site (street map or aerial photo, zoom and pan like any web map) with the intervention drawn on it and the control panel (chapters 1–4 and alternatives D1–D4, T1–T4, E1–E4, B1–B4). The building can be dragged and turned, or put somewhere by tapping it and then tapping the place. The microphone takes commands ("put that there", "use dry cooling", "add jobs", "turn it left") |
| Extra | `#metrics` | The same reading without the picture: the wheel large, the three lists, the trace and the offer |
| All | `#all` | The four screens laid out like the room. The right wall can switch between Live analysis with images and metrics only |

For a case study that has no original DataScope (Texas), the left wall is a sentiment map of reported positions that stays open for the room, and the center wall is the real place in axonometric: aerial photo, OpenStreetMap buildings and the data center from the table, repainted with a brush once the view is still. Residents (2020 Census blocks, one dot for a fixed number of people) move as dots colored by what they would hear, and can be switched off. Sound can be switched on: it gets louder as you come closer and changes with the cooling package.

Screens opened in the same browser stay in step.

## Case studies

The switch in the header (or `?site=texas` / `?site=michigan` in the address) changes the case study on every screen.

- **Michigan** — Allen Park, the site of the original DataScope.
- **Texas** — College Station: about 200 acres of city land in the Midtown Business Park, at Midtown Drive and Corporate Parkway, which the city council declined to sell for a 600 MW data center on 11 September 2025 (reported by KBTX and KXXV). The tract's outline is not drawn; the map shows the crossing the press reports and a circle of the same area, set on the undeveloped land beside it, to give its size. Landmark positions come from Google Maps. With no original tool for this site, the center wall shows the aerial photo and the left wall a sentiment map of its own: positions reported in the press about the proposal (KBTX, KXXV, Chron, BCS Chronicle, TexAgs), each with its source and set around the site, not at anyone's home; and a window left open where the people in the room add their voice: a position, one sentence, and marks tapped on the map (one place, several places linked, or none for the list only). They can have a picture drawn from the sentence; for that the sentence alone is sent to an open image service (Pollinations). Everything else visitors add is kept in that browser only (Export downloads it as a file; Clear removes it). The figures on the right wall are still those of the Michigan reference building (26 MW), not of the 600 MW proposal.

## Where the figures come from

Only figures with a source are shown.

- **Cooling packages** (electricity, peak demand, cooling water, sound): the three designs of the original DataScope Scenario Editor (`dist/studio/analysis.js`: Reference, Dry cooling, Higher efficiency), for 17.3 MW of computing in Southeast Michigan. T2 uses Dry cooling, T3 uses Higher efficiency.
- **Energy**: the cost and land to match all the power, from the project notes ($275M solar, $150M wind, about $1B for six microreactors).
- **The offer**: $10M upfront and $0.5M a year, or 20% of the profits, from the brief.
- **Designs and benefits**: the brief describes them without measurements, so their direction is shown and their size is listed under "Not known yet". No costs are charged for designs or technologies.
- **Words for sizes** use the same steps every time: a little (under 10%), clearly (10 to 30%), much (over 30%); for sound, under 3 dB, 3 to 8 dB, over 8 dB.
- **Sound at a distance** (Texas rings, residents, listening): in the open, from the original's reference plant: 72.5 dBA at 15 m, 6 dB less for each doubling of distance, 0.0035 dB per metre to the air. Walls and buildings in between are not counted. The 600 MW switch is a what-if: 23 reference plants heard as one source (+14 dB).
- **Residents**: 2020 Census blocks (TIGERweb, field POP100).
- The sound you hear is made in the browser. Its loudness follows the model; its color is an impression, not a recording.

## Run

Static page, no build. Open `index.html`, or serve the folder:

```
python3 -m http.server
```

## Status

Prototype. The table map follows the original DataScope's Map overview: its site center, approximate study parcel, river bends, landmark points and generalized road, rail, park and building outlines (`dist/geography.js`, `dist/studio/constraints.js` and `dist/studio/model-data.js` in CityScope/DataScope, which list their sources), the same light basemap (OpenFreeMap positron, with OpenStreetMap tiles in grey as a fallback and Esri World Imagery for the satellite view), and wetlands, parks and flood areas read live from the USFWS, USGS PAD-US and FEMA services. MapLibre GL JS and its Leaflet adapter are in `vendor/` with their licenses. The painted view is a hypothetical model of the site, not its surveyed geometry; where map tiles cannot load, a drawn plan of that model is shown instead.
