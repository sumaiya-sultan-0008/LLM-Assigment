# Creative Semantic Retrieval: *The Midnight Museum*

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sumaiya-sultan-0008/LLM-Assigment/blob/main/semantic_retrieval.ipynb)

Part A Mini Project, **Question 1 (Creative Semantic Retrieval)**.

Given an abstract, emotional query such as *"the loneliness of an empty train station at 3 AM"*, the system finds the 5 most similar works in a self-created collection of 125 poems, paintings, photographs, sound clips, sculptures and film scenes, each described in text.

It works in four steps:

1. Embed the items and the query.
2. Compare them with cosine similarity.
3. Rank the items.
4. Return the top 5.

The notebook also analyses where this works and where it fails.

## Run it in Google Colab

Click the **Open in Colab** badge above, then choose *Runtime → Run all*.

The notebook installs what it needs and downloads the data from this repository by itself. The first run also downloads about 1.2 GB of model weights. A GPU is optional; on CPU the notebook takes a few minutes.

## Files

| File | Contents |
|---|---|
| `semantic_retrieval.ipynb` | **Main submission**: code, results for all queries, evaluation, analysis and discussion (saved with outputs) |
| `semantic_retrieval.html` | The same notebook as a web page, for reading without Jupyter |
| `data/artifacts.json` | Self-created dataset: 125 items (`id`, `type`, `title`, `description`, and a hidden `theme` label used only for analysis) |
| `data/queries.json` | 14 test queries with relevance labels and decoy lists, written before running any model |
| `requirements.txt` | Python packages for running locally |

## Resources used

* **Dataset:** self-created for this project (no external data).
* **Pretrained models** (Hugging Face, used as-is, no training):
  * `thenlper/gte-large`: final system
  * `sentence-transformers/all-MiniLM-L6-v2`: small comparison model
  * `bert-base-uncased`: comparison model, not trained for sentence similarity
* **Baseline:** TF-IDF (scikit-learn).
* **Libraries:** sentence-transformers, PyTorch, scikit-learn, NumPy, pandas, matplotlib.

## Running locally instead

```bash
pip install -r requirements.txt
jupyter notebook semantic_retrieval.ipynb
```
