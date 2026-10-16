# Protein network tutorial + AAV8

Open [Protein_Network_Analysis_AAV8.ipynb](Protein_Network_Analysis_AAV8.ipynb).
Keep this folder intact: the notebook reads `conf/` and `aav8/` directly.
Download the full repository with **Code → Download ZIP**, or clone it:

```bash
git clone git@github.com:SAMPEL-Group/RIN-framework.git
cd RIN-framework/tutorial
jupyter lab Protein_Network_Analysis_AAV8.ipynb
```

If you need a new environment, run these commands yourself in a terminal:

```bash
conda create -n rin-tutorial -c conda-forge python=3.11 numpy scipy networkx matplotlib mdanalysis ipywidgets plotly py3dmol jupyterlab ipykernel
conda activate rin-tutorial
python -m ipykernel install --user --name rin-tutorial --display-name "Python (RIN tutorial)"
```

Select that kernel. Existing compatible environments can also be used; the
notebook does not install packages or clone another repository.

The original example uses lysozyme; `prot` can also be `thaumatin` or `apoferritin`.
The AAV8 section runs independently from its first, collapsed display-functions
cell: single VP0 → degree/closeness/betweenness RIN → complete capsid.
Display functions are inside the notebook; no separate Python helper is needed.
Run the cells to display interactive outputs; the browser needs internet access
for 3Dmol.js and Plotly.js. GitHub itself shows notebook code, not interactive 3D.

## AAV8 files

- `aav8_frame_334_backbone.npz`: exact single-frame backbone coordinates and original MD identities; used by the notebook.
- `vp0_frame334_backbone.pdb`: VP0 backbone, chain A; open in PyMOL.
- `capsid_frame334_backbone.cif.gz`: all 60 VP backbones, chains VP0–VP59; decompress if your viewer requires `.cif`.
- `aav8_vp0_edges.csv` and `aav8_vp0_centrality.csv`: reference results for the default VP0 settings.
- `metadata.json`: provenance, frame, atom/residue counts and graph definitions.

One frame at 400.8 ns; full-vp3 residues 204–738. VP0 has 535 CA nodes and
1,109 intra-VP contacts at CA ≤8 Å, excluding residue-number separation ≤3.
Centralities are exact and unweighted; full-capsid centralities are not computed.
The full structure contains 32,100 residues and 128,400 backbone atoms.
These are backbone exports, not all-atom structures. Changing notebook parameters
updates the display, not the bundled reference CSVs. The lysozyme example retains
its original minimum-heavy-atom <6 Å definition.

See [SOURCES.md](SOURCES.md) for Jonathan Zajac's data and provenance.
