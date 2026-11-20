# DataScope · Four Screens

Prototype that tells the data-center story on four screens (three walls and a table), alongside the MIT City Science [DataScope](https://cityscope.media.mit.edu/DataScope/) tool.

Live: https://leticiaig.github.io/datascope-four-screens/

| Screen | Link | Shows |
| --- | --- | --- |
| Left wall | `#sentiment` | Sentiment map (capture of the original tool) |
| Center wall | `#view` | Site layout of the original Scenario Editor (a photo, as a placeholder) |
| Right wall | `#analysis` | The chosen scenario painted, its alternatives as small scenarios with their radars, and the measures: Impacts radar, key figures and Community benefits. Chapters, scenarios and benefits can be clicked |
| Table | `#editor` | Scenario Editor: a map of the real site (street map or satellite, zoom and pan like any web map) with the intervention drawn on it and the control panel (chapters 1–4 and alternatives D1–D4, T1–T4, E1–E4, B1–B4). The building can be dragged and turned inside the study parcel |
| Extra | `#metrics` | Only the measures: radar, one small radar per alternative, key figures and the offer |
| All | `#all` | The four screens laid out like the room |

Screens opened in the same browser stay in step.

## Run

Static page, no build. Open `index.html`, or serve the folder:

```
python3 -m http.server
```

## Status

Prototype. The table map uses the site center, approximate study parcel, river bends and landmark points of the original DataScope (`dist/geography.js` in CityScope/DataScope, which lists their sources); tiles come from OpenStreetMap and Esri World Imagery. The painted view is a hypothetical model of the site, not its surveyed geometry; where map tiles cannot load, a drawn plan of that model is shown instead. The left and center walls are static images of the original DataScope. Costs for the Design and Technology options, the design figures, the benefit amounts and the radar weights are placeholders.
