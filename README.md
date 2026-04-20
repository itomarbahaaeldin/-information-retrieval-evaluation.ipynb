# Information Retrieval Evaluation

Benchmarking pipeline comparing NLP models for semantic search and question-answering. This project demonstrates traditional information retrieval methods using TF-IDF vectorization and similarity measures.

##  Project Overview

This project evaluates information retrieval techniques by:
- Implementing TF-IDF vectorization for document representation
- Calculating similarity metrics (Cosine similarity, Euclidean distance)
- Performing semantic search to find relevant documents
- Benchmarking traditional IR methods as baselines

##  Technologies Used

- **Python** - Core programming language
- **Scikit-learn** - TF-IDF vectorization and similarity metrics
- **SpaCy** - Text preprocessing and NLP
- **Pandas** - Data manipulation and analysis

##  Key Features

- **Text Preprocessing**: Lemmatization, stop word removal, punctuation cleaning
- **Feature Extraction**: Binary BoW, Frequency BoW, TF-IDF
- **Similarity Calculation**: Cosine similarity and Euclidean distance
- **Document Retrieval**: Finding nearest abstracts using similarity measures

##  Results

- Vocabulary size: 21,359 unique terms
- Successfully computed document similarities
- Implemented semantic search functionality
- Demonstrated baseline performance for comparison with advanced models

##  Usage

1. Clone the repository
2. Install required dependencies
3. Run the Jupyter notebook: `information_retrieval_evaluation.ipynb`

##  Future Work

- Implement BERT-based embeddings for comparison
- Add MAP and nDCG@10 evaluation metrics
- Compare performance with BM25 baselines
