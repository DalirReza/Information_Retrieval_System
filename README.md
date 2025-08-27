# Advanced Information Retrieval

This collection contains three related course projects from Advanced Information Retrieval that together cover indexing, compression, classical vector-space retrieval, term-at-a-time scoring, and probabilistic & language-model ranking.

## Projects (concise)
- **Indexing & Compression (Dictionary + Postings)**  
  Build a full pipeline: preprocessing (lowercase, punctuation removal, stopwords), unique-term dictionaries, postings lists, **front-coding** for dictionary compression, and **delta + Elias-gamma** encoding for postings. Includes a Boolean query engine that works on the compressed index.

- **TF-IDF, VSM & Term-At-A-Time Retrieval**  
  Compute TF-IDF (log tf × idf), build document vectors, implement cosine retrieval with and without normalization, visualize similarities, apply **pivot normalization**, and implement **term-at-a-time** scoring using a min-heap to retrieve top-k documents efficiently.

- **Document Ranking Models (BM25, Language Model, Hybrid)**  
  Implement Okapi **BM25** (k1=1.2, b=0.75), a **Jelinek-Mercer language model** (λ=0.5), and a **hybrid** that normalizes & weights VSM/BM25/LM scores. Compare outputs, discuss normalization effects, and show that the hybrid approach typically improves relevance beyond the top-1 results.

## Key takeaways
- Compression (front-coding, gamma) reduces index size while supporting fast boolean queries.  
- Normalizing document vectors prevents long documents from dominating retrieval; pivot normalization further stabilizes TF effects.  
- Hybrid scoring combining complementary models (VSM + BM25 + LM) gives the most robust ranked lists in manual evaluations when full relevance judgments are not available.

## Run / files
- Notebooks (.ipynb) demonstrate preprocessing, indexing, and experiments.  
- Core functions are split into `.py` modules (indexing, tfidf/vsm, bm25, lm, hybrid).  
- To reproduce: create venv → `pip install -r requirements.txt` → open the notebooks and run cells in order.

