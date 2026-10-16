# RIN-framework

Download [Protein_Network_Analysis_AAV8.ipynb](tutorial/Protein_Network_Analysis_AAV8.ipynb)
using GitHub's **Download raw file** button, then open it in Jupyter.
Only the notebook needs to be downloaded manually. Run the setup cell, then the
lysozyme example or the AAV8 section. Input data are fetched automatically and
cached in `.rin_tutorial_data/`; verified local files are reused.

The data repository is public, so no login, token or Git installation is needed.
Data are pinned to a specific commit and checked with SHA256 before use.

Use an environment with NumPy, SciPy, NetworkX, MDAnalysis, Matplotlib, Plotly,
ipywidgets and py3Dmol. The notebook does not install packages. Interactive 3D
views also need internet access for 3Dmol.js and Plotly.js.

The tutorial includes [Jonathan Zajac's examples](https://github.com/Jonathan-Zajac/Tutorial-RIN)
and an AAV8 MD snapshot: single-VP structure, centrality-colored RIN views,
and the complete capsid. File provenance is recorded in
[tutorial/manifest.json](tutorial/manifest.json).

This repository upload contains the tutorial and its data. The full MD workflow
and production analysis outputs are not part of this upload.
