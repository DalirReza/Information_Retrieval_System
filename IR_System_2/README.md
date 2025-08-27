# Document Ranking Models

This project was developed as part of the **Advanced Information Retrieval** course at the University of Tehran. The goal was to enhance an IR system by implementing and comparing multiple document ranking models using the MS MARCO dataset.

The project includes the following components:

1. **Data Preprocessing**  
   - Cleaned documents by removing punctuation, lowercasing, and removing stopwords.  
   - Built an inverted index and posting lists to calculate term and document frequencies.  
   - Organized queries for easier access.

2. **Probabilistic Model (Okapi BM25)**  
   - Implemented BM25 with basic weighting.  
   - Used default parameters `k1=1.2` and `b=0.75` to handle short queries and variable document lengths effectively.  
   - Calculated relevance scores for all documents and returned top-k results per query.

3. **Language Model**  
   - Implemented a language model using **Jelinek-Mercer smoothing** (`λ=0.5`) to handle zero probabilities and varying query lengths.  
   - Calculated document scores for each query and retrieved top-k documents.

4. **Hybrid Model**  
   - Combined the Vector Space Model, BM25, and Language Model into a single scoring function.  
   - Normalized scores across models to account for differing scales and variances.  
   - Weighted the language model more to capture small differences in scores.  
   - Observational comparison suggests the hybrid model retrieves more relevant documents, especially for the third and fourth ranked results.

Due to the lack of complete relevance judgments in the dataset, precise evaluation metrics (e.g., 11-point interpolated average precision) could not be computed. However, manual inspection indicates that the hybrid model provides better ranking than individual models in most cases.

