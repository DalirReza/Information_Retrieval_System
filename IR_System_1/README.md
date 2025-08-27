# Information Retrieval System

This project was developed as part of the **Advanced Information Retrieval** course at the University of Tehran. The goal was to design a small-scale search engine capable of efficient storage, compression, and retrieval of documents, as well as ranking them using vector-space models.

The system was built in three main parts:

1. **Dictionary and Postings Compression**  
   - Preprocessed documents (lowercasing, punctuation removal, stopword removal).  
   - Built dictionary and postings lists for all terms.  
   - Applied **front-coding** for dictionary compression and **gamma encoding** with delta encoding for postings compression.  
   - Implemented a Boolean query processor on top of the compressed index.

2. **Vector-Space Model**  
   - Constructed a **TF-IDF matrix** and represented documents as vectors.  
   - Implemented cosine similarity retrieval with and without normalization, showing how normalization prevents long documents from dominating results.  
   - Visualized query and document vectors to better understand their distribution.

3. **Term-At-A-Time Processing**  
   - Applied **pivot normalization** to refine TF-IDF scores.  
   - Implemented term-at-a-time retrieval using a **min-heap** to efficiently rank and return the top-k documents.  
   - Compared performance and discussed differences with document-at-a-time processing.

Overall, the project demonstrates how compression, vector models, and different retrieval strategies impact both efficiency and accuracy in information retrieval. The experiments showed that **normalization and GRU-style indexing tricks like pivot normalization** improve fairness in ranking, and that min-heaps are a practical solution for efficient top-k retrieval.
