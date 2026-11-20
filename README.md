# DataScope · Four Screens

Prototype that tells the data-center story on four screens (three walls and a table), alongside the MIT City Science [DataScope](https://cityscope.media.mit.edu/DataScope/) tool.

| Screen | Shows |
| --- | --- |
| Left wall | Sentiment map (capture of the original tool) |
| Table | Scenario Editor, Neighborhood view (capture of the original) with the control panel: chapters 1–4 and their alternatives (D1–D4, T1–T4, E1–E4, B1–B4) |
| Center wall | Neighborhood view (painted 3D) |
| Right wall | Live analysis (radar plots) |
| All | The four screens laid out like the room |

## Run

Static page, no build. Open `index.html`, or serve the folder:

```
python3 -m http.server
```

Views by hash: `#editor`, `#sentiment`, `#view`, `#analysis`, `#all`.

## Status

Prototype. The table and left-wall screens are static captures of the original DataScope. Costs for the Design and Technology options, the design figures and the radar weights are placeholders.
