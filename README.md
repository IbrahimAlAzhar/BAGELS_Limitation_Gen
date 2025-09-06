# 📘 Limitation Generation from Scientific Articles

This repository contains code and experiments for **automatic limitation generation** from scientific research papers. We explore multiple large language models (LLMs) and sequence-to-sequence models (BART, Pegasus, T5) alongside GPT-based models (GPT-3.5, GPT-4o, Mistral) to generate limitations.  
The repo also provides tools for **ground truth preparation, evaluation (coverage and performance), and Retrieval-Augmented Generation (RAG) using citation networks**.

---

## 🚀 Features
- **limitation generation**: Experiments with BART, Pegasus, T5, GPT-3.5, GPT-4o, and Mistral.  
- **Ground truth construction**: Extract author-mentioned limitations and OpenReview peer feedback.  
- **Evaluation pipeline**: Measure coverage (Ground Truth Coverage, LLM-generated limitation coverage) and performance (precision, recall, F1, semantic similarity).  
- **Citation-aware RAG**: Use *cited-in* and *cited-by* papers to enrich context.  
- **Reproducible notebooks**: All experiments are structured as Jupyter notebooks.  

---

```bash
## 📂 Repository Structure

├── models/
│   ├── BAGELS_BART_(Limitation_Generation).ipynb
│   ├── BAGELS_Pegasus_(Limitation_Generation).ipynb
│   ├── BAGELS_T5_(Limitation_Generation).ipynb
│   ├── BAGELS_GPT_3_5_+_RAG_(Limitation_Generation)_ipynb.ipynb
│   ├── BAGELS_GPT_4o_(Limitation_Generation).ipynb
│   └── BAGELS_Mistral_(Limitation_Generation).ipynb
|   └── BAGELS_Llama_(Limitation_Generation).ipynb
│
├── ground_truth/
│   ├── BAGELS_Ground_Truth_Limitation_extraction.ipynb
│   └── BAGELS_OpenReview_Extraction.ipynb
│
├── evaluation/
│   ├── Evaluation_(Coverage)_LLM_as_a_Judge.ipynb
│   └── Evaluation_(Performance).ipynb
│
├── rag/
│   └── BAGELS_Cited_In_and_Cited_by.ipynb
│
└── README.md 
```



---

## 📑 Components

### 🔹 Models (`/models`)
Each notebook generates limitations using a specific model:  
- **BART** → `BAGELS_BART_(Limitation_Generation).ipynb`  
- **Pegasus** → `BAGELS_Pegasus_(Limitation_Generation).ipynb`  
- **T5** → `BAGELS_T5_(Limitation_Generation).ipynb`  
- **GPT-3.5** → `BAGELS_GPT_3_5_+_RAG_(Limitation_Generation)_ipynb.ipynb`  
- **GPT-4o** → `BAGELS_GPT_4o_(Limitation_Generation).ipynb`  
- **Mistral** → `BAGELS_Mistral_(Limitation_Generation).ipynb`
- **Llama** → `BAGELS_Llama_(Limitation_Generation).ipynb`  
 
---

### 🔹 Ground Truth (`/ground_truth`)
- `BAGELS_Ground_Truth_Limitation_extraction.ipynb` → Extracts explicit limitations from paper sections (e.g., *Limitations*, *Discussion*).  
- `BAGELS_OpenReview_Extraction.ipynb` → Collects implicit limitations from OpenReview peer reviews.  

These files build the **gold standard dataset** for evaluation.  

---

### 🔹 Evaluation (`/evaluation`)
- `Evaluation_(Coverage)_LLM_as_a_Judge.ipynb` → Measures how well generated limitations cover ground truth.  
- `Evaluation_(Performance).ipynb` → Computes metrics such as Precision, Recall, F1, and novelty.  

---

### 🔹 RAG (`/rag`)
- `BAGELS_Cited_In_and_Cited_by.ipynb` → Uses *cited-in* and *cited-by* papers as external knowledge to improve limitation generation.  

---

## 📊 Evaluation Metrics
- **Coverage**: % of ground truth limitations captured by generated ones.  
- **Performance**: Precision, Recall, F1, semantic similarity.  
- **Citation-aware gains**: Improvement from RAG with citation context.  

---

```bash
## ⚙️ Installation

Clone the repo:

git clone https://github.com/your-username/limitation-generation.git
cd limitation-generation

Install dependencies:
pip install -r requirements.txt

Notes:
GPT-3.5 and GPT-4o mini notebooks require an OpenAI API key.
Other models (BART, Pegasus, T5, Mistral) use Hugging Face Transformers. 

Example: Run BART limitation generation
jupyter notebook bart_limitation_generation.ipynb

Example: Evaluate coverage
jupyter notebook coverage_evaluation.ipynb

 Example: Run citation-aware RAG
jupyter notebook cited_in_cited_by_rag.ipynb
```

```bash
flowchart LR
    A[Research Paper] --> B[Ground Truth Construction]
    A --> C[Model (BART / GPT-4o / T5 / etc.)]
    C --> D[Generated Limitations]
    B --> E[Evaluation (Coverage & Performance)]
    D --> E
    A --> F[Cited-in / Cited-by Papers]
    F --> G[RAG Pipeline]
    G --> D

```

Acknowledgments

This repository is part of ongoing research at Northern Illinois University (NIU).
We thank all contributors, reviewers, and open-source communities (Hugging Face, LangChain, OpenAI) for tools and datasets that made this work possible.

## Citation
This code is related to work below

```bash
Azher, Ibrahim Al; Mokarrama, Miftahul Jannat; Guo, Zhishuai; Choudhury, Sagnik Ray; Alhoori, Hamed (2025). *BAGELS: Benchmarking the Automated Generation and Extraction of Limitations from Scholarly Text*. arXiv preprint arXiv:2505.18207.
```

This work has been **accepted at EMNLP 2025 (Findings)**.

```bash
@article{azher2025bagels,
  title={BAGELS: Benchmarking the Automated Generation and Extraction of Limitations from Scholarly Text},
  author={Azher, Ibrahim Al and Mokarrama, Miftahul Jannat and Guo, Zhishuai and Choudhury, Sagnik Ray and Alhoori, Hamed},
  journal={arXiv preprint arXiv:2505.18207},
  year={2025}
}
```

