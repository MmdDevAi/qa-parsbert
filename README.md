---
language:
- en
# اگر روی متون فارسی کار کرده‌اید:
# - fa
tags:
- question-answering
- rag
- langchain
- distilbert
- roberta
datasets:
- squad
# یا نام دیتاست مورد استفاده شما
pipeline_tag: question-answering
license: mit
---
## 🔗 Links & Resources

- GitHub Repository: [https://github.com/MmdDevAi/qa-parsbert](https://github.com/MmdDevAi/qa-parsbert)
- Hugging Face Model Card: [https://huggingface.co/Msoldier-ai/parsbert-qa](https://huggingface.co/Msoldier-ai/parsbert-qa)
- Interactive Web Demo (Hugging Face Spaces): [https://huggingface.co/spaces/Msoldier-ai/parsbert-qa-and-samsum](https://huggingface.co/spaces/Msoldier-ai/parsbert-qa)

# 📚 Intelligent Document Question Answering & RAG System

An end-to-end Question Answering (QA) and Retrieval-Augmented Generation (RAG) system designed for accurate, context-aware information extraction from complex documents. This repository covers both extractive QA architectures (DistilBERT, RoBERTa) and modern RAG pipelines using LangChain.

---

## 🌟 Highlights & Key Features

- Extractive QA Baseline: Fast inference and high token-level precision using fine-tuned DistilBERT and RoBERTa models.
- Retrieval-Augmented Generation (RAG): Integrated retrieval pipeline powered by LangChain for contextual grounding and hallucination reduction.
- Document Ingestion & Chunking: Efficient parsing and semantic chunking for dense text and technical documentation.
- Evaluation Framework: Benchmarked against standard QA metrics (Exact Match and F1-Score).

---

## 🏗️ Architecture & Model Progression

1. Extractive Pipeline (DistilBERT / RoBERTa):
   - Identifies the start and end logits directly from the source passage.
   - Ideal for low-latency, strictly factual question answering where answers are verbatim in the context.

2. RAG Pipeline (LangChain Integration):
   - Uses vector embeddings and similarity search to retrieve relevant document chunks dynamically.
   - Synthesizes answers over large multi-page documents without exceeding model context limits.

---
## 📊 Quantitative Evaluation & Results

The system was evaluated on the PQuAD (Persian Question Answering Dataset) benchmark using standard reading comprehension metrics (Exact Match and F1-Score).

### Benchmark Performance

| Model Architecture | Dataset | Exact Match (EM) | F1 Score | Notes |
| :--- | :--- | :---: | :---: | :--- |
| ParsBERT (Fine-Tuned) | PQuAD | 73.47% | 86.28% | Optimized for Persian extractive QA |

---

### Detailed Breakdown (HasAns vs. NoAns)

To evaluate real-world robustness against unanswerable or ambiguous queries, performance is broken down by answer availability:

| Question Type | Exact Match (EM) | F1 Score | Description |
| :--- | :---: | :---: | :--- |
| HasAns (Answerable) | 71.8% | 84.6% | Context contains the explicit answer span |
| NoAns (Unanswerable) | 75.2% | 88.0% | Correctly abstaining / detecting missing answers |

---

### Error Categorization Analysis

Error patterns on the validation set fall into three primary failure modes:

1. Span Boundary Mismatch: The model locates the correct sentence but includes extraneous context tokens or truncates dependent clauses.
2. False Negatives: The model predicts no answer when a subtle or implicit answer exists within the text.
3. False Positives: The model predicts an entity or phrase from the context when the question actually lacks sufficient evidence to be answered.
