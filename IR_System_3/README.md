# Document Ranking Models – Advanced IR

This project was done for the **Advanced Information Retrieval** course at the University of Tehran. The goal was to try out different ranking models on the **MS MARCO dataset** and see how they compare.

### Implemented Models
1. **BM25 (Probabilistic Model)**  
   - Used default parameters (`k1 = 1.2`, `b = 0.75`) which work well for short queries and variable document lengths.  

2. **Language Model**  
   - Implemented with **Jelinek-Mercer smoothing (λ = 0.5)** to avoid zero probabilities and handle queries of different sizes.  

3. **Hybrid Model**  
   - Combines **BM25**, **Vector Space Model (VSM)**, and the **Language Model**.  
   - Scores from each model were normalized and weighted before combining.  

### Results
- BM25 and the Language Model gave similar results for the top documents.  
- The **Hybrid Model** performed better overall, especially after the first few ranked results.  
- Since the dataset didn’t have full relevance judgments, a precise evaluation wasn’t possible, but manual checks showed the hybrid approach worked best.  
