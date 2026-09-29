# Semantic Course Finder

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sumaiya-sultan-0008/LLM-Assigment/blob/education-dataset/semantic_retrieval.ipynb)

Part A Mini Project, **Question 1 (Creative Semantic Retrieval)**. This is the `education-dataset` branch; the `main` branch has the earlier "Midnight Museum" version.

A student describes what they want to learn in their own words, for example *"teach a computer to learn from examples"* or *"I want to become a doctor"*. The system suggests the 5 best-matching courses from a self-created catalogue of 137 courses in 14 subjects.

It works in four steps:

1. Embed the requests and the course descriptions.
2. Compare them with cosine similarity.
3. Rank the courses.
4. Return the top 5.

The notebook then analyses where this works and where it fails: words with two meanings (Python, cells, viruses, stars), negation ("no maths"), an idiom ("isn't rocket science") and a request in Arabic.

## Run it in Google Colab

Click the **Open in Colab** badge above, then choose *Runtime → Run all*.

The notebook installs what it needs and downloads the data from this branch by itself. The first run downloads about 0.8 GB of model weights. A GPU is optional.

## Files

| File | Contents |
|---|---|
| `semantic_retrieval.ipynb` | **Main submission**: code, results for all requests, evaluation, analysis and discussion (saved with outputs) |
| `semantic_retrieval.html` | The same notebook as a web page |
| `data/courses.json` | Self-created dataset: 137 courses (`id`, `title`, `subject`, `level`, `description`) |
| `data/queries.json` | 15 student requests with the matching courses and decoys, written before running any model |
| `requirements.txt` | Python packages for running locally |

## Resources used

* **Dataset:** self-created for this project (no external data).
* **Pretrained models** (Hugging Face, used as-is, no training):
  * `thenlper/gte-large`: large model
  * `sentence-transformers/all-MiniLM-L6-v2`: small model
* **Baseline:** TF-IDF (scikit-learn).
* **Libraries:** sentence-transformers, PyTorch, scikit-learn, NumPy, pandas, matplotlib.

## Running locally instead

```bash
pip install -r requirements.txt
jupyter notebook semantic_retrieval.ipynb
```
