# RAG Assistant — Retrieval-Augmented Generation for Customer Support

RAG Assistant is an interactive, tutorial-style project demonstrating how to build a retrieval-augmented generation (RAG) system for customer support. It combines semantic search (embeddings + vector retrieval) with LLM generation to return accurate, context-aware answers while keeping a reproducible and testable pipeline.

What you'll find in this repo
- `notebook.ipynb` — Original notebook (reference).
- `tutorial_notebook.ipynb` — Clean, step-by-step tutorial notebook (English/Spanish-ready) that explains each stage and includes a mock mode for offline testing.
- Example data files (if present): `knowledge_base.csv`, `predefined_responses.json`, `chatbot_responses.json`.
- `requirements.txt` — Minimal dependencies.

Why this project matters
- Improves response accuracy and consistency by prioritizing retrieved answers from a knowledge base.
- Falls back to LLM generation when retrieval confidence is low, ensuring coverage for unexpected queries.
- Provides structured logging (query, response, timestamp, confidence) for auditing and continuous improvement.

Technical highlights
- 3-stage pipeline: ingestion & chunking → batch embedding generation & caching → vector retrieval + LLM fallback.
- Robust engineering practices: batching, retry wrappers, vector normalization, and persisted indexes (demo JSON; extensible to FAISS/Annoy/Pinecone).
- Development-friendly: offline/mock mode, unit-testable utilities, and an interactive tutorial notebook.

Quick start (PowerShell)

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Open the tutorial notebook in Jupyter or VS Code:

```powershell
jupyter notebook tutorial_notebook.ipynb
# or execute the entire notebook headlessly
jupyter nbconvert --to notebook --execute tutorial_notebook.ipynb --inplace
```

Notes
- The notebook includes a `USE_MOCK` mode that avoids calling external APIs, making it easy to run and test locally without an OpenAI key.
- To run with real OpenAI calls, set the `OPENAI_API_KEY` environment variable in your OS (and restart your shell/IDE):

```powershell
setx OPENAI_API_KEY "your_api_key_here"
# restart your terminal/IDE to pick up the environment variable
```

Suggested next steps
- Tune similarity thresholds, chunk sizes, and top-k to fit your KB and latency/cost constraints.
- Swap the demo JSON vector store for FAISS or Pinecone for production-scale retrieval.
- Add pytest-based unit tests and export the core utilities to a Python package for reuse.

License & contribution
- Feel free to adapt this tutorial for demos, interviews, or prototypes. If you want, I can add a CONTRIBUTING guide and a permissive license file (MIT).
