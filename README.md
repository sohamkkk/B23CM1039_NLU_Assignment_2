# B23CM1039 — NLU Assignment 2

**Name:** Soham Khairnar  
**Roll No:** B23CM1039  
**Course:** Natural Language Understanding (NLU)

---

## Overview

This repository contains solutions for **NLU Assignment 2**, which covers two problems:

1. **Problem 1:** Learning Word Embeddings (Word2Vec) from IIT Jodhpur domain-specific data
2. **Problem 2:** Character-Level Indian Name Generation using RNN variants

A detailed report with analysis and visualizations is included in the `Report/` directory.

---

## Repository Structure

```
B23CM1039_NLU_Assignment_2/
│
├── Problem-1/
│   ├── B23CM1039_A2_Problem_1.ipynb   # Main notebook for Problem 1
│   └── corpus.txt                     # Processed text corpus from IIT Jodhpur sources
│
├── Problem-2/
│   ├── B23CM1039_A2_Problem_2.ipynb   # Main notebook for Problem 2
│   └── TrainingNames.txt              # Dataset of 1000 Indian names (one per line)
│
├── Report/
│   ├── main.tex                       # LaTeX source for the report
│   ├── figures/                       # All figures used in the report
│   └── report.pdf                     # Compiled PDF report
│
└── README.md
```

---

## Problem 1 — Word2Vec on IIT Jodhpur Data

### Description

Train Word2Vec models (CBOW and Skip-gram with Negative Sampling) on textual data collected from IIT Jodhpur sources and analyze the semantic structure captured by the learned embeddings.

**Data Sources:**
- IIT Jodhpur official website (departments, academics, research pages)
- Academic regulation documents (PDFs)
- Faculty profile pages

**Key Tasks:**
- Web scraping and PDF text extraction to build the corpus
- Text preprocessing (cleaning, tokenization, sentence splitting)
- Word2Vec implementation **from scratch** using PyTorch (CBOW & Skip-gram)
- Comparison with Gensim's reference Word2Vec implementation
- Embedding visualization (t-SNE, PCA, word clouds)
- Semantic similarity and analogy evaluation

### How to Run

1. **Install dependencies:**
   ```bash
   pip install requests beautifulsoup4 pdfplumber gensim wordcloud matplotlib scikit-learn numpy torch tqdm
   ```

2. **Run the notebook:**
   ```bash
   cd Problem-1/
   jupyter notebook B23CM1039_A2_Problem_1.ipynb
   ```

3. **Run all cells sequentially.** The notebook will:
   - Scrape IIT Jodhpur web pages and extract PDF text
   - Build and save the corpus (`corpus.txt`)
   - Train Word2Vec models (CBOW & Skip-gram) from scratch
   - Train Gensim Word2Vec models for comparison
   - Generate all visualizations and evaluations

> **Note:** The web scraping cells require an active internet connection. The corpus is also pre-saved in `corpus.txt` for convenience.

---

## Problem 2 — Character-Level Name Generation

### Description

Implement and compare three recurrent neural network architectures for **character-level Indian name generation**. All recurrent cells (RNN, LSTM) are implemented **from scratch** using raw weight matrices.

**Models:**
1. **Vanilla RNN** — 2-layer RNN with hand-coded `tanh` cells
2. **Bidirectional LSTM (BLSTM)** — 2-layer BLSTM with hand-coded LSTM cells
3. **RNN + Bahdanau Attention** — LSTM encoder with additive attention mechanism

**Key Tasks:**
- Dataset loading and exploration
- Model architecture implementation from scratch
- Training and loss curve analysis
- Quantitative evaluation (novelty rate, diversity metrics)
- Qualitative analysis (realism, failure modes, temperature effects)

### How to Run

1. **Install dependencies:**
   ```bash
   pip install torch matplotlib numpy
   ```

2. **Ensure the dataset is in place:**  
   The file `TrainingNames.txt` (1000 Indian names, one per line) should be in the `Problem-2/` directory.

3. **Run the notebook:**
   ```bash
   cd Problem-2/
   jupyter notebook B23CM1039_A2_Problem_2.ipynb
   ```

4. **Run all cells sequentially.** Training takes approximately 10–20 minutes per model on CPU.

---

## Report

The detailed report covering both problems is available at:
- **PDF:** [`Report/report.pdf`](Report/report.pdf)
- **LaTeX source:** [`Report/main.tex`](Report/main.tex)

---

## Requirements

- Python 3.9+
- PyTorch >= 2.0
- NumPy, Matplotlib
- scikit-learn (for t-SNE, PCA)
- Gensim (for reference Word2Vec in Problem 1)
- BeautifulSoup4, requests, pdfplumber (for web scraping in Problem 1)
- wordcloud (for visualization in Problem 1)
- Jupyter Notebook
