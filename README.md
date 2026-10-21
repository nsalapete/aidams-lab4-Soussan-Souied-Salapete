# AIDAMS Lab 4: An LLM extraction you can trust

Group: Josh Soussan, Edouard Souied, Nicolas Salapete.

We treat an LLM that turns sustainability-report text into a table as a measurement instrument. We parse and validate its answers (Part A), measure its accuracy with an interval and look at what its errors do to a sector total (Part B), test whether asking it five times reveals its mistakes (Part C), check how well a simple retrieval step finds the right paragraph (Part D), and write a recommendation for a bank (Part E).

## Files

| File | Content |
|---|---|
| `lab4.ipynb` | The completed notebook, with all outputs |
| `data/excerpts.json` | 20 report excerpts from fictional steel companies |
| `data/gold_labels.json` | The hand-made "true" values for each excerpt |
| `data/recorded_responses.json` | 120 LLM answers recorded in advance (1 at temperature 0 and 5 at temperature 0.7 per excerpt) |
| `data/aurelia_report_chunks.json` | A fictional report cut into 16 chunks, with 6 test questions (Part D) |
| `requirements.txt` | Python packages |

## How to run

1. Install Python 3.10 or later. We tested with Python 3.12, pandas 3.0, numpy 2.4, scipy 1.17, pydantic 2.11 and scikit-learn 1.9.
2. Install the packages: `pip install -r requirements.txt`
3. Keep the `data` folder next to the notebook.
4. Open `lab4.ipynb` in Jupyter or VS Code and run **Kernel > Restart & Run All**. Without the optional D2 cell the run takes a few seconds.

No API key is needed: the whole lab works on the recorded answers.

## Optional parts

- **A2 (run your own model):** we had no API key or local model, so the cell prints that it is skipped. To use it, set `BACKEND` and `MODEL` in the `ask_llm` cell.
- **D2 (dense embeddings):** needs `pip install sentence-transformers` (we used 6.1.0, which also installs PyTorch). The first run downloads the `all-MiniLM-L6-v2` model (about 90 MB) and the cell takes a few minutes on a laptop. Without the package the cell just prints that D2 is skipped.
