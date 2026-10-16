# Sources

## Jonathan Zajac tutorial data

- Repository: https://github.com/Jonathan-Zajac/Tutorial-RIN
- Commit checked: `74135b18cbb622009fcfe34553dae34edf619b69`.
- Supplied archive: `Tutorial-RIN-main.zip`; SHA256 `1e5bc692af6e77da61d7bbe53e661db5e6d425d5a2c0f7b8223dfcbb495f026d`.
- `conf/` contains the six original GRO/XTC files, copied byte-for-byte.
- The upstream README is preserved as `upstream/README.md`.
- Neither the supplied archive nor the checked upstream repository includes a LICENSE file. No new license is assigned to these third-party files.

The tutorial notebook was supplied separately by the user. Its lysozyme material
is attributed to Jonathan Zajac. Local changes make data paths portable, define
the protein selection before use, render the animation without deleting a local
file, adapt residue-plot limits to the selected protein, seed the synthetic
weights with 42, and append the AAV8 single-frame example.

## AAV8 example

Prepared from the existing SAMPEL Group MD analysis, full-vp3 branch, frame 334
(400.8 ns). This is the same frame used for the previously checked PyMOL view.
The original trajectory and topology are not included. Original numeric VP IDs
are retained; they do not come from the unrelated 9J7K receptor-complex PDB.
Only the backbone subset needed for structural display is provided. Residue
contacts use unrounded CA coordinates in the NPZ. The PDB rounds coordinates to
0.001 Å and labels terminal OT1 as O for display; the mmCIF preserves original
atom names and float32 coordinate precision. The included files support a
single-conformation tutorial, not a trajectory-occupancy or convergence result.

`manifest.json` records the distributed file hashes and original data provenance.
