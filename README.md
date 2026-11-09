# [Intelligence Artificielle et Biotechnologie](https://nevermind78.github.io/IA_Biotech/)

Module pratique de **10 heures** (5 ateliers de 2h) pour élèves ingénieurs non spécialistes en
informatique : *learn by doing* sur **Google Colab**, avec des données biologiques réelles.

| Séance | Thème | Notebook |
|:---:|---|:---:|
| 0 | Prise en main de Colab et Python (auto-formation) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nevermind78/IA_Biotech/blob/main/notebooks/S0_prise_en_main_colab.ipynb) |
| 1 | Toxicité des molécules (Tox21) — Random Forest | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nevermind78/IA_Biotech/blob/main/notebooks/S1_toxicite_random_forest.ipynb) |
| 2 | RNA-seq single-cell (PBMC 3k) — ACP, UMAP, K-Means | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nevermind78/IA_Biotech/blob/main/notebooks/S2_transcriptomique_clustering.ipynb) |
| 3 | Localisation des protéines — k-mers vs ESM-2 | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nevermind78/IA_Biotech/blob/main/notebooks/S3_sequences_esm2.ipynb) |
| 4 | Imagerie cellulaire — Otsu, Cellpose, transfer learning | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nevermind78/IA_Biotech/blob/main/notebooks/S4_imagerie_cellpose.ipynb) |
| 5 | Structure 3D et mutations — ColabFold, ESM-2, mini-projet | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nevermind78/IA_Biotech/blob/main/notebooks/S5_alphafold_mutations.ipynb) |

## Structure du dépôt

```
├── _quarto.yml          # configuration du livre Quarto
├── index.qmd            # présentation du module
├── seance1.qmd … seance5.qmd   # cours résumé + notions théoriques + déroulé de chaque atelier
├── annexe-colab.qmd, notebooks.qmd, evaluation.qmd, glossaire.qmd, depannage.qmd
├── notebooks/           # notebooks Google Colab (S0 à S5)
├── data/                # copies de secours des petits jeux de données
├── styles.css
└── .github/workflows/deploy.yml   # rendu + publication sur GitHub Pages
```

## Construire le site en local

```bash
pip install -r requirements.txt
quarto preview        # ou : quarto render  (sortie dans _site/)
```

## Site du cours

Le site est en ligne sur **<https://nevermind78.github.io/IA_Biotech/>** 