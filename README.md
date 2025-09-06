# 📘 Limitation Generation from Scientific Articles

This repository contains code and experiments for **automatic limitation generation** from scientific research papers. We explore multiple large language models (LLMs) and sequence-to-sequence models (BART, Pegasus, T5) alongside GPT-based models (GPT-3.5, GPT-4o, Mistral) to generate limitations.  
The repo also provides tools for **ground truth preparation, evaluation (coverage and performance), and Retrieval-Augmented Generation (RAG) using citation networks**.

---

## 🚀 Features
- **Multi-model limitation generation**: Experiments with BART, Pegasus, T5, GPT-3.5, GPT-4o, and Mistral.  
- **Ground truth construction**: Extract author-mentioned limitations and OpenReview peer feedback.  
- **Evaluation pipeline**: Measure coverage and performance (precision, recall, F1, semantic similarity).  
- **Citation-aware RAG**: Use *cited-in* and *cited-by* papers to enrich context.  
- **Reproducible notebooks**: All experiments are structured as Jupyter notebooks.  

---

## 📂 Repository Structure

├── models/
│   ├── bart_limitation_generation.ipynb
│   ├── pegasus_limitation_generation.ipynb
│   ├── t5_limitation_generation.ipynb
│   ├── gpt35_limitation_generation.ipynb
│   ├── gpt4o_limitation_generation.ipynb
│   └── mistral_limitation_generation.ipynb
│
├── ground_truth/
│   ├── author_mentioned_limitations.ipynb
│   └── openreview_limitations.ipynb
│
├── evaluation/
│   ├── coverage_evaluation.ipynb
│   └── performance_evaluation.ipynb
│
├── rag/
│   └── cited_in_cited_by_rag.ipynb
│
└── README.md 




---

## 📑 Components

### 🔹 Models (`/models`)
Each notebook generates limitations using a specific model:  
- **BART** → `bart_limitation_generation.ipynb`  
- **Pegasus** → `pegasus_limitation_generation.ipynb`  
- **T5** → `t5_limitation_generation.ipynb`  
- **GPT-3.5** → `gpt35_limitation_generation.ipynb`  
- **GPT-4o** → `gpt4o_limitation_generation.ipynb`  
- **Mistral** → `mistral_limitation_generation.ipynb`  

---

### 🔹 Ground Truth (`/ground_truth`)
- `author_mentioned_limitations.ipynb` → Extracts explicit limitations from paper sections (e.g., *Limitations*, *Discussion*).  
- `openreview_limitations.ipynb` → Collects implicit limitations from OpenReview peer reviews.  

These files build the **gold standard dataset** for evaluation.  

---

### 🔹 Evaluation (`/evaluation`)
- `coverage_evaluation.ipynb` → Measures how well generated limitations cover ground truth.  
- `performance_evaluation.ipynb` → Computes metrics such as Precision, Recall, F1, and novelty.  

---

### 🔹 RAG (`/rag`)
- `cited_in_cited_by_rag.ipynb` → Uses *cited-in* and *cited-by* papers as external knowledge to improve limitation generation.  

---

## 📊 Evaluation Metrics
- **Coverage**: % of ground truth limitations captured by generated ones.  
- **Performance**: Precision, Recall, F1, semantic similarity.  
- **Citation-aware gains**: Improvement from RAG with citation context.  

---

## ⚙️ Installation

Clone the repo:

git clone https://github.com/your-username/limitation-generation.git
cd limitation-generation

Install dependencies:
pip install -r requirements.txt

Notes:
GPT-3.5 and GPT-4o notebooks require an OpenAI API key.
Other models (BART, Pegasus, T5, Mistral) use Hugging Face Transformers. 

Example: Run BART limitation generation
jupyter notebook models/bart_limitation_generation.ipynb

Example: Evaluate coverage
jupyter notebook evaluation/coverage_evaluation.ipynb

 Example: Run citation-aware RAG
jupyter notebook rag/cited_in_cited_by_rag.ipynb

flowchart LR
    A[Research Paper] --> B[Ground Truth Construction]
    A --> C[Model (BART / GPT-4o / T5 / etc.)]
    C --> D[Generated Limitations]
    B --> E[Evaluation (Coverage & Performance)]
    D --> E
    A --> F[Cited-in / Cited-by Papers]
    F --> G[RAG Pipeline]
    G --> D

Acknowledgments

This repository is part of ongoing research at Northern Illinois University (NIU).
We thank all contributors, reviewers, and open-source communities (Hugging Face, LangChain, OpenAI) for tools and datasets that made this work possible.


