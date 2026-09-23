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

## 📊 Evaluation & Metrics

The extractive components are evaluated on standard QA benchmark criteria:

| Model Architecture | Task Type | Key Strengths |
| :--- | :--- | :--- |
| DistilBERT | Extractive QA | High inference speed, lightweight, optimized for edge/CPU environments |
| RoBERTa | Extractive QA | Superior comprehension and contextual embeddings, higher F1 score |
| RAG (LangChain) | Generative / Context QA | Multi-document scalability, dynamic context retrieval |

- Exact Match (EM): Measures percentage of predictions matching ground truth character-for-character.
- F1 Score: Harmonic mean of token precision and recall against the reference answers.

---
