# The figures of the case study, the files they copy, and the notebook that writes those files

Each SVG here is an unchanged copy of the file of the same name in `PosetalOptProj/posetal-opt/figures/slides/` of the ai-workspace.
The notebook `PosetalOptProj/posetal-opt/notebooks/rocket-landing-with-requirements-that-hold-together-or-conflict.ipynb` writes each of those files when it runs.
The slides of `sections/5-case-study.drawio.xml` hold each file that they show as data in the cell of its picture, and name the file in the style key `assetSource=assets/figures/<file>`.
The cells hold the data because the draw.io editor of VS Code finds no picture by a relative path.

| file | slide | cell of the notebook that draws the file |
|---|---|---|
| `rocket-requirements-trade-off.svg` | `case-study-front-1` | the code cell after the markdown cell that ends "and then the front alone for the slides." |

The slides `case-study-first-case-1` and `case-study-violated-requirements-1` draw the four orders in draw.io, from the orders that the notebook defines under the heading "Four orders put the requirements above the objectives".
The slide `case-study-second-case-1` draws in draw.io a table of the requirements that each optimal landing meets, from the outputs of the notebook under the heading "The tilt, the touchdown speed and the point of touchdown show which requirements each limit violates" and from the weighted sums of the first order under "With the tilt over the last 5 s, the optimal landings of the four orders violate different requirements".

## Refresh the files after the notebook runs again

Copy the files of the notebook again, from the workspace root:

```sh
for f in trade-off; do
    cp "PosetalOptProj/posetal-opt/figures/slides/rocket-requirements-$f.svg" Presentations/posetal-optimization/assets/figures/
done
```

Then write the files into the cells of section 5 again with the function `embed_style` of `tools/draw-io/embed-pictures.py`, applied to that section file alone.
Then compare the numbers on the slides with the markdown cells and the printed outputs of the notebook, because the slides quote them.
