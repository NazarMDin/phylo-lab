# Lab – Phylogenetics with Bio.Phylo & Nextstrain/Auspice

> **Course Assignment**  
> This repository covers Lab 03 on phylogenetic analysis using Biopython's `Bio.Phylo` module, and connects the concepts to interactive visualisation via Nextstrain/Auspice.

---

## Reference Materials

| Resource | Link |
|---|---|
| Neherlab Auspice Tutorial | https://neherlab.org/201901_krisp_auspice.html |
| Lab Notebook (Colab) | https://colab.research.google.com/gist/tahashmi/f6bf9c8b3dc9f719289c9ddc0b4f25e3/lab03_phylo.ipynb |
| Nextstrain Zika Tutorial | https://nextstrain.org/community/neherlab/krisp/zika-tutorial |
| Biopython Phylo Docs | https://biopython.org/wiki/Phylo |

---

## Repository Structure

```
phylo-lab/
├── lab03_phylo.ipynb       ← Main notebook (run this)
├── requirements.txt        ← Python dependencies
├── data/
│   ├── simple.dnd          ← Example Newick tree
│   └── example.xml         ← Example PhyloXML tree
├── outputs/                ← Generated figures & output files (auto-created)
└── README.md
```

---

## How to Run

### Option A – Google Colab (recommended, no installation needed)

1. Go to [Google Colab](https://colab.research.google.com/)
2. Click **File → Open notebook → GitHub**
3. Paste your repo URL and open `lab03_phylo.ipynb`
4. Run the first cell to install Biopython, then run all cells top-to-bottom

### Option B – Local (Jupyter)

```bash
# 1. Clone the repo
git clone https://github.com/<your-username>/phylo-lab.git
cd phylo-lab

# 2. Install dependencies
pip install -r requirements.txt

# 3. Create the outputs directory
mkdir -p outputs

# 4. Launch Jupyter
jupyter notebook lab03_phylo.ipynb
```

---

## What the Notebook Covers

| Section | Topic |
|---|---|
| 1 | Reading a Newick tree & ASCII display |
| 2 | Tree traversal – terminals, internal nodes |
| 3 | Searching – `find_any`, `common_ancestor`, `distance` |
| 4 | Modifying – `root_at_midpoint`, `prune` |
| 5 | Colour & width annotations (PhyloXML) |
| 6 | Matplotlib visualisation with `Phylo.draw` |
| 7 | I/O – write & convert between formats |
| 8 | Building trees from distance matrices (UPGMA, NJ) |
| 9 | Building trees from sequence alignments |
| 10 | Connection to Nextstrain / Auspice concepts |
| 11 | Summary |

---

## Auspice / Nextstrain – Key Concepts

The [Neherlab tutorial](https://neherlab.org/201901_krisp_auspice.html) uses Nextstrain's **Auspice** viewer to demonstrate concepts that go beyond basic `Bio.Phylo`:

- **Time-resolved tree** — branches scaled by calendar time via a molecular clock model (TreeTime)
- **Clock view** — divergence vs. sampling date; slope = evolutionary rate
- **Colour-by** — recolour leaves/branches by metadata (country, genotype, date, author)
- **Diversity panel** — per-site entropy or event counts along the genome; click a site to colour the tree by genotype
- **Geographic animation** — ancestral location reconstruction animated over time

### Comparison

| Feature | Bio.Phylo | Nextstrain / Auspice |
|---|---|---|
| Tree construction | Newick, NJ, UPGMA | IQ-TREE / FastTree + temporal signal |
| Visualisation | Static matplotlib | Interactive browser |
| Time-resolved | Manual | ✅ ==Automatic (molecular clock) |
| Geographic map | ❌ | ✅ Animated spread |
| Ancestral states | ❌ | ✅ Location + genotype |
| Diversity panel | ❌ | ✅ Per-site entropy |

---

## Dependencies

See `requirements.txt`. Core packages:

- `biopython >= 1.79`
- `matplotlib >= 3.5`
- `numpy`

---

## License

Educational use only. Notebook content adapted from the [Biopython Tutorial and Cookbook](https://biopython.org/DIST/docs/tutorial/Tutorial.html) and the [Neherlab Auspice tutorial](https://neherlab.org/201901_krisp_auspice.html).
