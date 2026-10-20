# The figures, videos and pages of the landing, the files they copy, and the notebook cells that write those files

Each SVG here, each file of `assets/videos/` whose name starts with `rocket-requirements-` and each file of `assets/plots/` is an unchanged copy of the file of the same name in `PosetalOptProj/posetal-opt/figures/slides/` of the ai-workspace.
The notebook `PosetalOptProj/posetal-opt/notebooks/rocket-landing-with-requirements-that-hold-together-or-conflict.ipynb` writes each of those files when it runs.
Its cells are counted from 0, as the notebook stores them, and each cell is named as well by the heading of its part.
The slides of every section hold each file that they show as data in the cell of its picture, and name the file in the style key `assetSource=assets/<folder>/<file>`.
The cells hold the data because the draw.io editor of VS Code finds no picture by a relative path.

| file | slide of the design | cell of the notebook that writes the file |
|---|---|---|
| `rocket-requirements-decision-thrusts.svg` | `decisions-1` | 28, under "The optimal landings form a front from the least fuel to the least control energy" |
| `rocket-requirements-upright-violation.svg` | `decisions-metrics-1` | 55, under "Upright as a violation, and the least upright over bounds on on target and soft touchdown" |
| `rocket-requirements-limit-of-one-extension.svg` | `scalarization-with-sequences-of-weights-guarantees-*` | 47, under "The landings of the case study, named by the physical sense of each violation" |
| `rocket-requirements-tilt-front.svg` | `reset-metrics-to-explore-pointwise-layer-*` | 40, under "The front of $p$ against $a$, and the least $e$ among the landings no worse on both" |
| `rocket-requirements-minimal-extensions.svg` | `minimal-layered-extensions-*` | 13, under "The slides name the metrics in words, and take the order $e$ lowest as the example of the algorithms" |
| `rocket-requirements-three-orders.svg` | `case-study-orders-1` | 15, under the same heading |
| `rocket-requirements-three-landing-values.svg` | `case-study-violated-requirements-1` | 49, under "The landings of the case study, named by the physical sense of each violation" |
| `rocket-requirements-trade-off.svg` | `case-study-first-case-1` | 25, the code cell after the markdown cell that ends "and then the front alone for the slides." |

The videos in `assets/videos/` and their stills, the last frame of each video, come from cell 60, under "The videos and the interactive pages of the slides".
`rocket-requirements-upright-for-the-last-2-s-and-5-s.mp4` goes to `case-study-first-case-1`, and `rocket-requirements-lowest-requirement-gives-way.mp4` to `case-study-second-case-1`.
The pages in `assets/plots/` come from cell 62, under the same heading.
The still of each page, `<page>-still.png` beside it, is the picture of the page that the build takes in `build/page-snapshots/`, so it shows the page as it first draws in its cell.
Only the editor without the media plugin shows a still, because every build draws the cell of a page as that picture.
`rocket-requirements-conflict-surface.html` goes to `case-study-trade-off-1`, and `rocket-requirements-trajectories.html` to `running-example-landing-1`.
The cell 5, under the heading of the cell 3, prints the limits of the requirements and the start that `running-example-landing-1` quotes.
The cell 11, under the heading of the cell 13, prints the numbers of the slides on the chain family and on the layered extensions, and the cell 38 prints the front and the reset of the slides `reset-metrics-to-explore-pointwise-layer-*`.

The slides `case-study-first-case-1` and `case-study-violated-requirements-1` of the commit `152e0ed` draw the four orders in draw.io, from the orders that the notebook defines under the heading "Four orders put the requirements above the objectives".
The slide `case-study-second-case-1` of the same commit draws in draw.io a table of the requirements that each optimal landing meets, from the outputs of the notebook under the heading "The tilt, the touchdown speed and the point of touchdown show which requirements each limit violates" and from the weighted sums of the first order under "With the tilt over the last 5 s, the optimal landings of the four orders violate different requirements".

## Refresh the files after the notebook runs again

Copy the files of the notebook again, from the workspace root:

```sh
source=PosetalOptProj/posetal-opt/figures/slides
assets=Presentations/posetal-optimization/assets
for f in decision-thrusts upright-violation limit-of-one-extension tilt-front minimal-extensions three-orders three-landing-values trade-off; do
    cp "$source/rocket-requirements-$f.svg" "$assets/figures/"
done
for f in upright-for-the-last-2-s-and-5-s lowest-requirement-gives-way; do
    cp "$source/rocket-requirements-$f.mp4" "$source/rocket-requirements-$f-still.png" "$assets/videos/"
done
for f in conflict-surface trajectories; do
    cp "$source/rocket-requirements-$f.html" "$assets/plots/"
done
```

After the pages change, run `npm run html` in the deck, and copy the picture of each page from `build/page-snapshots/` to `assets/plots/<page>-still.png`.

Then write the pictures into the cells of each section that shows them again with the function `embed_style` of `tools/draw-io/embed-pictures.py`, applied to that section file alone.
Then compare the numbers on the slides with the markdown cells and the printed outputs of the notebook, because the slides quote them.
