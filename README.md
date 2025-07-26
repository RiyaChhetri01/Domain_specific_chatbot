# 🧠💰 Domain-Specific Chatbot (Healthcare & Finance)

This project presents a **transformer-based, multilingual, retrieval-focused chatbot** designed to provide informative and context-aware responses in two critical domains: **medical** and **finance**. It utilizes advanced NLP models like **RoBERTa**, **BART**, and **Sentence-Transformers**, integrated with **sentiment analysis**, to enhance user interactions across multiple intents and linguistic styles.

---

## 📌 Table of Contents

- [📚 Project Overview](#-project-overview)
- [⚙️ System Architecture](#️-system-architecture)
- [📊 Dataset Description](#-dataset-description)
- [📎 Model Benchmark Summary](#-model-benchmark-summary)
- [💡 Features](#-features)
- [🚀 Setup Instructions](#-setup-instructions)
- [🧪 Usage Example](#-usage-example)
- [📈 Future Enhancements](#-future-enhancements)
- [📄 License](#-license)

---

## 📚 Project Overview

This chatbot is a **retrieval-based intelligent agent** capable of:

- 🏥 **Medical queries:** Symptom-based disease diagnosis, treatment advice, and healthcare guidance.  
- 💰 **Finance queries:** Banking, personal finance, and investment-related responses.  
- 🌐 **Multilingual support:** High-quality responses in 50+ languages using transformer-based embeddings.

The system employs **RoBERTa-based Sentence Transformers** for sentence embedding generation, with the **`paraphrase-multilingual-MiniLM-L12-v2`** model chosen for deployment due to its balance of speed and semantic accuracy.

---

## ⚙️ System Architecture

- **Input:** User query (text)  
- **Preprocessing:** Sentiment classification (`TextBlob`), lowercasing, cleaning  
- **Embedding:** Sentence-Transformers (`SBERT`)  
- **Retrieval:** Cosine similarity search from the query-response dataset  
- **Response Generation:** Top matching pre-defined answer  
- **Optional:** Multilingual support for global user base  

---

## 📊 Dataset Description

### 🏷️ Attributes

| Attribute | Description |
|----------|-------------|
| `domain` | Domain category (e.g., healthcare, finance) |
| `query` | Natural language user input |
| `response` | Corresponding system-generated/pre-defined response |
| `intent` | User’s intent (e.g., diagnosis, investment_info) |

### 🧾 Summary

- **Total Records:** 7,765  
- **Unique Queries:** 7,039  
- **Unique Responses:** 6,967  
- **Unique Intents:** 32  
- **Domains:** 12  
- **Most Frequent Domain:** `3_GHR_QA` (Genetic & Health-Related)

---

## 📎 Model Benchmark Summary

To determine the most suitable sentence transformer for our chatbot, multiple models were benchmarked:

### 🔍 Evaluated Models

- **`paraphrase-multilingual-mpnet-base-v2`**  
  Supports over 50 languages with 768-dimensional embeddings. Best Score: `0.8703`. Fast inference and excellent for cross-lingual tasks.

- **`paraphrase-albert-small-v2`**  
  English-only, 768-dimensional embeddings. Best Score: `0.8633`. Lightweight and suitable for resource-limited environments.

- **`paraphrase-multilingual-MiniLM-L12-v2`**  
  Supports 50+ languages, 384-dimensional embeddings. Best Score: `0.9801`. Fast and highly accurate. ✅ **Selected for deployment.**

- **`paraphrase-MiniLM-L3-v2`**  
  English-only, 384-dimensional embeddings. Best Score: `0.9595`. Very fast and lightweight, ideal for real-time apps.

- **`distiluse-base-multilingual-cased-v1`**  
  Supports 50+ languages, 512-dimensional embeddings. Best Score: `0.8338`. Balanced for multilingual use cases.

- **`distiluse-base-multilingual-cased-v2`**  
  Supports 15+ languages, 512-dimensional embeddings. Best Score: `0.79203`. Slightly faster than v1 with comparable capabilities.

- **`all-mpnet-base-v2`**  
  English-only, 768-dimensional embeddings. Best Score: `0.72351`. High semantic accuracy but moderate inference time.

---

## 💡 Features

- 🔍 **Retrieval-based approach** for reliable, high-speed answers  
- 🤖 **Transformer embeddings** powered by SBERT  
- 💬 **Sentiment-aware** responses using TextBlob  
- 🌐 **Multilingual support** across 50+ languages  
- 🏥🪙 **Dual-domain expertise** in Healthcare and Finance  
- 🧠 **Intent classification** for context-aware replies  
- 📈 **Domain-specific fine-tuning** with `nlpaug` for robust language variations  

---

## 🚀 Setup Instructions

### 🔧 Prerequisites

- Python 3.7+
- pip
- Virtualenv (recommended)

### 🛠️ Installation

```bash
git clone https://github.com/yourusername/domain-specific-chatbot.git
cd domain-specific-chatbot
python -m venv venv
source venv/bin/activate        # For Linux/macOS
venv\Scripts\activate           # For Windows

pip install -r requirements.txt
