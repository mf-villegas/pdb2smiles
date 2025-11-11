# PDB → SMILES Extractor

A lightweight notebook that retrieves ligand SMILES strings for a list of PDB entry codes.

The workflow:
1) Provide PDB IDs (typed or via CSV/XLS upload).
2) Ligands are fetched from PDBe.
3) Undesired components (solvents/buffers/ions, inorganic, etc.) are filtered.
4) SMILES are retrieved from:
   - RCSB (primary)
   - PDBe (fallback)
5) Results are exported to Excel.

---

## Features
- Works with any public PDB entries  
- Removes common crystallography artifacts  
- Supports bulk upload of IDs  
- SMILES caching reduces repeated lookups  
- Outputs Excel with `pdb_id`, `title`, `chem_comp_id`, `smiles`  

---

## Input
- PDB IDs by text field
- OR CSV / Excel upload containing PDB IDs anywhere in the sheet

---

## Output
- Excel file (`.xlsx`) with:
  - `pdb_id`
  - `title`
  - `chem_comp_id`
  - `smiles`

If no ligands survive filtering for a given PDB, a placeholder row is included.

---

## Dependencies
See `requirements.txt`.

---

## Data sources
- **PDBe**  
  API docs: https://www.ebi.ac.uk/pdbe/

- **RCSB PDB**  
  API docs: https://data.rcsb.org/

These services may apply rate limits.  
Please use responsibly.

---

## How to use
1) Open the notebook (`notebook/pdb_smiles_extractor.ipynb`) in Google Colab.
2) Paste or upload your PDB IDs.
3) Run all cells.
4) Download the Excel output.

---

## License
MIT — see `LICENSE`.

---

## Notes
- Best effort extraction; not all ligands have SMILES.
- Ligand name/formula retrieval is available but not included in the final sheet by default.
