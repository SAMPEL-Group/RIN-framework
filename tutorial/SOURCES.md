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
weights with 42, and append the AAV8 single-frame example. Both examples use
the same spatial-neighbor implementation of the original strict heavy-atom
cutoff and sequence-order exclusion; the contact definition is unchanged for
lysozyme.

## AAV8 example

Prepared from the existing SAMPEL Group MD analysis, full-vp3 branch, frame 334
(400.8 ns). The source has 801 frames at 1.2 ns spacing and 499,164 atoms.
The two complete protein GRO snapshots retain the original atom names, order,
residue IDs (204–738) and coordinates; source ions are excluded. The original
MD topology and trajectory are not distributed. These VP IDs do not come from
the unrelated 9J7K receptor-complex PDB.

GRO coordinates use six decimal places in nm. The box is zero: these fitted,
unwrapped coordinates are used without periodic wrapping. MDAnalysis loads
coordinates in angstrom. The notebook derives contacts and centralities from
the GRO directly; it does not load precomputed network arrays. See
`aav8/metadata.json` for source fingerprints, VP boundaries and exact definitions.

On 2026-10-16 the user selected the original lysozyme contact method for AAV8:
minimum heavy-atom distance strictly <6 Å, sequence-order separation >3 within
VP0. This supersedes the earlier tutorial CA ≤8 Å graph, not the main MD
analysis. The default graph has 535 nodes and 1,795 edges; degree, closeness
and betweenness are exact and unweighted. The full capsid is displayed only.
This single conformation does not establish trajectory occupancy or convergence.

`manifest.json` records distributed file hashes and original data provenance.
