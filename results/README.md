# Results

Generated outputs are intentionally not committed to the repository by default.

Running `notebooks/01_main_analysis.ipynb` creates:

- CSV tables for the structural analyses
- PNG figures
- `FINAL_REPORT.md`
- `final_results.zip`

The Bayesian follow-up notebook reads selected CSV files from `final_results.zip`.

Large generated files, cached embeddings, and source datasets should normally remain outside Git.
