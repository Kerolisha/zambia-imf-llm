# zambia-imf-llm

A Google Colab notebook that reads one IMF programme review with Gemini models and tests the results against the report.

**Source:** IMF Country Report No. 26/21, *Zambia: Sixth Review Under the Extended Credit Facility Arrangement* (February 2026, 140 pages), in `data/`.

Open `Zambia_ECF_Review_Pipeline.ipynb` in Colab with `data/` and `cache/` in `/content`, then choose *Runtime > Run all*. All 176 model requests are answered from `cache/replies.json`, so no API key is needed. To call the models again, add a Gemini key as the Colab secret `GEMINI_FREE_KEY` and delete that file.

Stages are ordinary functions chained with the `|` operator and sharing one dictionary. Settings are in a `.env`-style block. Writer: `gemini-3.8-flash`. Judge: `gemini-3.7-flash`. Embeddings: `BAAI/bge-base-en-v1.5` with a FAISS `IndexFlatL2`. Results and the two 300 dpi figures are in `results/`.

MIT licence, see `LICENSE`. The IMF report remains the property of the International Monetary Fund and is included only so the notebook can run.
