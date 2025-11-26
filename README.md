# UMAP Visualization of GPT-5 Reddit Discussion Clusters

A comprehensive quantitative analysis of user sentiment and pain points following the GPT-5 launch, using advanced NLP techniques on Reddit discussion data.

## Overview

This project systematically analyzes 1,972 unique Reddit posts and comments from the official OpenAI GPT-5 AMA thread to identify and categorize user concerns during this major LLM transition. Using state-of-the-art embedding models and clustering techniques, the study reveals critical insights into user experience challenges that emerged with GPT-5's release.

## Key Features

- **Advanced Text Clustering**: Implements UMAP dimensionality reduction combined with HDBSCAN clustering
- **Multiple Embedding Models**: Evaluates BAAI/bge-base-en-v1.5 and nomic-ai/nomic-embed-text-v1.5
- **Topic Modeling**: Utilizes BERTopic with Maximal Marginal Relevance (MMR) for interpretability
- **Comprehensive Evaluation**: Tests 12 different combinations of embeddings, dimensionality reduction, and clustering algorithms

## Methodology

### Data Processing Pipeline

1. **Data Collection**: Reddit posts extracted using AsyncPRAW library
2. **Preprocessing**: Removal of URLs, user mentions, markdown formatting, and noise reduction
3. **Embedding Generation**: 768-dimensional dense vectors using state-of-the-art models
4. **Dimensionality Reduction**: PCA and UMAP techniques (reduced to 50 dimensions)
5. **Clustering**: KMeans, DBSCAN, and HDBSCAN algorithms
6. **Topic Modeling**: BERTopic with MMR re-ranking and Flan-T5 generative labeling

### Optimal Configuration

The study identified **UMAP (nomic-embed-text-v1.5) + HDBSCAN** as the optimal configuration:
- **Silhouette Score**: 0.603 (highest across all experiments)
- **Clusters Identified**: 21 distinct semantic groups
- **Noise Points**: 759 outliers

## Key Findings

The analysis revealed four major user pain points:

### 1. Removal of Legacy Models
Strong dissatisfaction with the deprecation of GPT-4o, with widespread demand for model selector options.

### 2. Creative Writing Quality Degradation
Users reported GPT-5 outputs as less imaginative, emotionally flat, and inferior for creative tasks compared to GPT-4o.

### 3. Usage Limitations and Pricing Concerns
Frustration over restrictive message caps and reduced perceived value for Plus subscription holders.

### 4. Personality and Communication Style Changes
Emotional dissatisfaction with GPT-5's altered personality, described as colder and less expressive.

## Technologies Used

- **Embeddings**: BAAI/bge-base-en-v1.5, nomic-ai/nomic-embed-text-v1.5
- **Dimensionality Reduction**: PCA, UMAP
- **Clustering**: KMeans, DBSCAN, HDBSCAN
- **Topic Modeling**: BERTopic with c-TF-IDF
- **Representation Re-ranking**: Maximal Marginal Relevance (MMR)
- **Generative Labeling**: google/flan-t5-small
- **Data Collection**: AsyncPRAW

## Results Summary

| Configuration | Silhouette Score | Clusters | Noise Points |
|--------------|------------------|----------|--------------|
| UMAP–Nomic + HDBSCAN | **0.603** | 21 | 759 |
| UMAP–Nomic + KMeans | 0.427 | 8 | 0 |
| UMAP–BGE + HDBSCAN | 0.369 | 2 | 6 |
| UMAP–BGE + KMeans | 0.368 | 8 | 0 |

## Research Contributions

1. **Empirical Validation**: Provides concrete evidence of user friction during LLM transitions
2. **Methodological Framework**: Establishes a robust NLP pipeline for analyzing noisy user-generated content
3. **Actionable Insights**: Offers data-driven recommendations for future LLM deployment strategies

## Author

**Veer Shah**  
Department of Computer Engineering  
Sardar Patel Institute of Technology  
Mumbai, India  
veer.shah22@spit.ac.in
