# Creative Semantic Retrieval: *The Midnight Museum*

Part A Mini Project, **Question 1 (Creative Semantic Retrieval)**.

Given an abstract, emotional query such as *"the loneliness of an empty train station at 3 AM"*, the system retrieves the 5 most semantically similar works from a self-created collection of 125 poems, paintings, photographs, sound clips, sculptures and film scenes, all described in text. It embeds items and queries, compares them with cosine similarity, ranks the items and returns the top 5. It also analyses where this succeeds and where it fails.

## Files

| File | Contents |
|---|---|
| `semantic_retrieval.ipynb` | **Main submission**: implementation, results for all queries, evaluation, analysis and discussion (executed, with outputs) |
| `semantic_retrieval.html` | The same executed notebook as a web page, for reading without Jupyter |
| `data/artifacts.json` | Self-created dataset: 125 items (`id`, `type`, `title`, `description`, hidden `theme` label used only for analysis) |
| `data/queries.json` | 14 evaluation queries with graded relevance labels and decoy lists, fixed before running any model |
| `requirements.txt` | Python packages |

## Resources used

* **Dataset:** self-created for this project (no external data).
* **Pretrained models** (Hugging Face, used as-is, no training):
  * `thenlper/gte-large`: final retriever
  * `sentence-transformers/all-MiniLM-L6-v2`: lightweight comparison
  * `bert-base-uncased`: ablation, a model not trained for sentence similarity
* **Baseline:** TF-IDF (scikit-learn).
* **Libraries:** PyTorch, transformers, scikit-learn, NumPy, pandas, matplotlib.

## Running

```bash
pip install -r requirements.txt
jupyter notebook semantic_retrieval.ipynb
```

Run all cells from this folder, so that `data/` is found. The three models (about 1.2 GB of weights in total) are downloaded from Hugging Face on first run if they are not already cached. A full run takes about 2–3 minutes on a laptop CPU; no GPU is needed.
