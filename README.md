<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:18181b,50:27272a,100:3f3f46&height=180&section=header&text=Information%20Retrieval%20Evaluation&fontSize=34&fontColor=ffffff&fontAlignY=38&desc=TF-IDF%20%7C%20Cosine%20Similarity%20%7C%20Semantic%20Search%20Benchmarking&descAlignY=58&descSize=14&animation=fadeIn" width="100%"/>

<br/>

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![SpaCy](https://img.shields.io/badge/SpaCy-09A3D5?style=flat-square)
![Vocab](https://img.shields.io/badge/Vocabulary-21%2C359%20terms-3f3f46?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

</div>

<br/>

## 📋 Overview

A benchmarking pipeline for classical **information retrieval (IR)** techniques. The project implements and compares three document representation strategies — Binary BoW, Frequency BoW, and TF-IDF — and evaluates their effectiveness at semantic document retrieval using cosine similarity and Euclidean distance.

Intended as a rigorous baseline before introducing neural retrieval methods (BERT, BM25, dense retrieval).

<br/>

## 🔍 What's Evaluated

| Technique | Type | Description |
|-----------|------|-------------|
| Binary Bag-of-Words | Sparse | Presence/absence of each term |
| Frequency Bag-of-Words | Sparse | Raw term counts |
| TF-IDF | Sparse | Term frequency weighted by inverse document frequency |
| Cosine Similarity | Metric | Angle between document vectors (length-invariant) |
| Euclidean Distance | Metric | L2 distance in vector space |

<br/>

## 🏗️ Pipeline

```
Raw Text Corpus (NLP_2.csv — academic abstracts)
      │
      ▼
┌─────────────────────────┐
│     Preprocessing       │
│  Tokenisation           │
│  Lemmatisation (SpaCy)  │
│  Stop word removal      │
│  Punctuation cleaning   │
└──────────┬──────────────┘
           │
           ▼
┌─────────────────────────┐
│  Feature Extraction     │
│  Binary BoW             │
│  Frequency BoW          │
│  TF-IDF Vectoriser      │
│  Vocab: 21,359 terms    │
└──────────┬──────────────┘
           │
           ▼
┌─────────────────────────┐
│  Similarity Computation │
│  Cosine similarity      │
│  Euclidean distance     │
└──────────┬──────────────┘
           │
           ▼
  Document Retrieval
  (nearest-neighbour cosine search)
```

<br/>

## 📊 Key Results

| Property | Value |
|----------|-------|
| Vocabulary size | 21,359 unique terms |
| Representation | Sparse TF-IDF matrix |
| Similarity metrics | Cosine + Euclidean |
| Preprocessing | Lemmatisation via SpaCy `en_core_web_sm` |
| Dataset | Academic abstracts (`NLP_2.csv`) |

<br/>

## 🚀 Quick Start

> ⚠️ This notebook runs on **Google Colab** — it uses `files.upload()` to load the dataset.

```bash
git clone https://github.com/itomarbahaaeldin/information-retrieval-evaluation.git
cd information-retrieval-evaluation
```

1. Open `information_retrieval_evaluation.ipynb.ipynb` in **Google Colab**
2. When prompted, upload `NLP_2.csv` — a dataset of academic abstracts with `id` and `ABSTRACT` columns
3. Run all cells top to bottom

```python
# Install dependencies if needed
pip install spacy scikit-learn pandas
python -m spacy download en_core_web_sm
```

<br/>

## 📁 Project Structure

```
information-retrieval-evaluation/
├── information_retrieval_evaluation.ipynb.ipynb   # Full pipeline notebook
└── README.md
```

> Dataset (`NLP_2.csv`) is not included in the repo — upload it manually when running in Colab.

<br/>

## 💡 Key Insights

1. **TF-IDF outperforms raw counts** — down-weighting common terms dramatically improves retrieval relevance
2. **Cosine similarity beats Euclidean** — length-normalisation makes cosine robust to document length variation
3. **Lemmatisation reduces vocab by ~30%** — collapsing inflected forms improves both precision and recall
4. **Sparse methods are fast baselines** — sub-second retrieval on this corpus; scalable to millions of docs with sparse matrix ops

<br/>

## 🔮 Future Work

- [ ] BM25 as a stronger classical baseline (Okapi BM25)
- [ ] BERT/SBERT dense embeddings for semantic retrieval
- [ ] Evaluation with MAP@K and nDCG@10 metrics
- [ ] Comparison on a labelled benchmark (MS-MARCO, BEIR)

<br/>

## 👨‍💻 Author

**Omar Bahaa Eldin**

[![Portfolio](https://img.shields.io/badge/Portfolio-000?style=flat-square&logo=vercel&logoColor=white)](https://itomarbahaaeldin.github.io/omar-bahaa-portfolio/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/omar-bahaaeldin10)
[![Gmail](https://img.shields.io/badge/Gmail-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:itomarbahaaeldin@gmail.com)

<br/>

## 📄 License

MIT © [Omar Bahaa Eldin](https://github.com/itomarbahaaeldin)

<div align="center">
<br/>
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:3f3f46,50:27272a,100:18181b&height=100&section=footer" width="100%"/>
</div>
