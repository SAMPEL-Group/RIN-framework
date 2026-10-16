# Protein network tutorial + AAV8

Download the whole repository, then open
[Protein_Network_Analysis_AAV8.ipynb](Protein_Network_Analysis_AAV8.ipynb).
Keep `conf/` and `aav8/` beside the notebook.

If you need a new environment, run these commands in a terminal:

```bash
conda create -n rin-tutorial -c conda-forge python=3.11 numpy scipy networkx matplotlib mdanalysis ipywidgets plotly py3dmol jupyterlab ipykernel
conda activate rin-tutorial
python -m ipykernel install --user --name rin-tutorial --display-name "Python (RIN tutorial)"
jupyter lab Protein_Network_Analysis_AAV8.ipynb
```

Select that kernel and run the setup cell. Then follow the original lysozyme
example, or jump to **AAV8 capsid**. The AAV8 order is single VP structure →
degree, closeness and betweenness RINs → complete capsid structure.
All calculations and display helpers are in the notebook. Interactive views
need a browser connection to 3Dmol.js and Plotly.js; rerun the cells locally
to view them. No packages are installed by the notebook.

## AAV8 structures

Both GRO files contain complete protein atoms, including sidechains and
hydrogens, from MD frame 334 (400.8 ns):

| File in `aav8/` | Atoms | Residues |
|---|---:|---:|
| `aav8_vp0_frame334.gro` | 8,213 | 535 |
| `aav8_capsid_frame334.gro` | 492,780 | 32,100 across 60 VPs |

The notebook reads the VP0 GRO and computes contacts using the same definition
as lysozyme: **minimum heavy-atom distance <6 Å**, excluding sequence neighbors
≤3. The default VP0 graph has 535 nodes and 1,795 edges. All three centralities
are exact and unweighted; CA coordinates only position nodes in the view.
The complete capsid GRO is used for the final structural view. Cartoon display
uses backbone atoms; the input structures and contact calculation include sidechains.

These are single-frame snapshots, not trajectories or occupancy results.
Coordinates are unwrapped/fitted, and distances use no periodic wrapping.
GRO atom serials wrap at 100,000; physical VP identity follows the contiguous
atom blocks recorded in `aav8/metadata.json`, not serial numbers.
The main MD workflow keeps its existing contact definitions.

See [SOURCES.md](SOURCES.md) for attribution and provenance.
