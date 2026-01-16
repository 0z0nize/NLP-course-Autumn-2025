# NLP-course-Autumn-2025: Unsupervised Discovery of Thematic Structure in Russian-Mansi Bilingual Texts

## 🎯 Project Overview

This repository implements a comprehensive comparative study of **unsupervised topic modeling techniques** applied to a **parallel Russian-Mansi corpus** containing **81,146 sentence pairs**. The primary objective is to create **thematically structured corpora** that support **Mansi language learning** and **linguistic analysis** for this critically endangered Uralic language spoken by only **~1,000–1,500 native speakers** primarily in Western Siberia.

## 🔬 Research Methods

We systematically evaluate three distinct topic modeling approaches:

1. **Sentence Embedding Clustering** (Text2Vec multilingual transformer → 384D embeddings → k-means/Fuzzy c-means)
2. **Latent Dirichlet Allocation (LDA)** (traditional probabilistic generative model)
3. **BERTopic** (transformer embeddings → UMAP → HDBSCAN → class-based TF-IDF)

## 📊 Key Results & Performance

**Sentence embedding clustering** significantly outperformed baselines:

**Russian-Mansi Corpus:**
| Method | Optimal Configuration | Coherence Score | Topics |
|--------|----------------------|-----------------|--------|
| **Clustering** | k=30 | **0.8054** | Highly interpretable |
| LDA | k=50 | 0.5788 | Fragmented |
| BERTopic | Auto (763 topics) | 0.2770 | Low quality |

**20 Newsgroups Benchmark:**
| Method | Configuration | Coherence Score |
|--------|---------------|-----------------|
| **Clustering** | k=100 | **0.6227** |
| BERTopic | Auto (381 topics) | 0.4441 |

**Example interpretable topics from Russian-Mansi clustering:**
- Topic 0: Women, family relationships (`женщина`, `мать`, `дочь`)
- Topic 5: Wildlife, nature (`лес`, `река`, `рыба`, `птица`)
- Topic 8: Work, labor (`работа`, `делать`, `идти`)

## 🛠️ Quick Start

```bash
# 1. Clone repository
git clone https://github.com/0z0nize/NLP-course-Autumn-2025.git
cd NLP-course-Autumn-2025

# 2. Setup environment (Python 3.10+)

# 3. Download Russian-Mansi parallel corpus
# [Public dataset link provided in paper]

# 4. Run analysis notebooks
jupyter notebook notebooks/
```

**Core dependencies:**
```
sentence-transformers  # Text2Vec embeddings
bertopic               # BERTopic implementation
gensim                 # LDA
scikit-learn           # Clustering
umap-learn             # Dimensionality reduction
hdbscan                # Density clustering
```

## 👥 Research Team

| Name | Contributions |
|------|---------------|
| **Sofia Baranetskaya** | Exploratory Data Analysis, data preprocessing & cleaning, model training |
| **Vadim Korobkovskii** | Literature review, sentence embedding clustering, BERTopic implementation, 20NG benchmark |
| **Vladislav Shkarovskii** | Experimental design, LDA implementation, 20NG analysis |

## 📚 Dataset Preprocessing Highlights

**Raw corpus challenges addressed:**
- 267 duplicate sentence pairs removed
- Sentence misalignment fixed (Russian ≠ Mansi lengths)
- 463 long texts without sentence breaks split
- Words with spaces corrected (847 Mansi cases)
- Outliers with length differences >25 tokens resolved

**Final cleaned dataset:** Ready for topic modeling with exponential sentence length distribution.

## 📈 Evaluation Metrics

- **Coherence Score** (0-1): Semantic similarity of top words per topic [higher = better]
- **Perplexity**: Model fit to data [lower = better, but doesn't guarantee interpretability]

## 📄 Full Paper

[Unsupervised_Discovery_of_Thematic_Structure_in_Russian_Mansi_Bilingual_Texts.pdf](https://github.com/0z0nize/NLP-course-Autumn-2025/blob/main/report/Unsupervised_Discovery_of_Thematic_Structure_in_Russian_Mansi_Bilingual_Texts.pdf)

**Key findings:** Sentence embedding clustering establishes new state-of-the-art results for topic modeling in low-resource language settings.

## ⚖️ License

MIT License - free for academic and commercial use.

## 🔗 Related Resources

- **Raw Russian-Mansi parallel corpus**: Publicly available
- **Code reproducibility**: All notebooks, data preprocessing, and models included
- **Interactive visualizations**: Coherence plots vs. number of topics

---

**Questions or feedback?** Open an issue or contact the research team.
```
