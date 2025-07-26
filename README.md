Domain-Specific Chatbot (Healthcare & Finance)

This project presents a transformer-based, multilingual, retrieval-focused chatbot designed to provide informative and context-aware responses in two critical domains: medical and finance. It utilizes advanced NLP models like RoBERTa, BART, and Sentence-Transformers, integrated with sentiment analysis, to enhance user interactions across multiple intents and linguistic styles.
📌 Table of Contents
📚 Project Overview
⚙️ System Architecture
📊 Dataset Description
🤖 Model Selection & Benchmarking
💡 Features
🚀 Setup Instructions
🧪 Usage Example
📈 Future Enhancements
📄 License
📚 Project Overview
This chatbot is a retrieval-based intelligent agent capable of:
Medical queries: Symptom-based disease diagnosis, treatment advice, and healthcare guidance.
Finance queries: Banking, personal finance, and investment-related responses.
Multilingual support: High-quality responses in 50+ languages using transformer-based embeddings.
The system employs RoBERTa-based Sentence Transformers for sentence embedding generation, with the paraphrase-multilingual-MiniLM-L12-v2 model chosen for deployment due to its balance of speed and semantic accuracy.
⚙️ System Architecture
Input: User query (text)
Preprocessing: Sentiment classification (TextBlob), lowercasing, cleaning
Embedding: Sentence-Transformers (SBERT)
Retrieval: Cosine similarity search from the query-response dataset
Response Generation: Top matching pre-defined answer
Optional: Multilingual support for global user base
📊 Dataset Description
Attribute	Description
domain	Domain category (e.g., healthcare, finance)
query	Natural language user input
response	Corresponding system-generated/pre-defined response
intent	User’s intent (e.g., diagnosis, investment_info)
🧾 Summary
Total Records: 7,765
Unique Queries: 7,039
Unique Responses: 6,967
Unique Intents: 32
Domains: 12
Most Frequent Domain: 3_GHR_QA (Genetic & Health-Related)

📎Model Benchmark Summary
To determine the most suitable sentence transformer for our domain-specific chatbot, several models were evaluated based on language support, embedding size, accuracy (Best Score), response time, and overall performance. Below is a detailed description of each model analyzed:
paraphrase-multilingual-mpnet-base-v2
This model supports over 50 languages and generates 768-dimensional embeddings. It achieves a Best Score of 0.8703 with fast inference time. It is known for producing high-quality multilingual embeddings and excels in cross-lingual semantic matching tasks.
paraphrase-albert-small-v2
Focused solely on English, this lightweight model provides 768-dimensional embeddings with a Best Score of 0.8633 and moderate response time. It's suitable for resource-constrained environments, though its accuracy is lower compared to other models in this study.
paraphrase-multilingual-MiniLM-L12-v2
Supporting over 50 languages, this model outputs 384-dimensional embeddings. It delivers the highest performance among all tested models with a Best Score of 0.9801 and fast inference. It strikes the best balance between speed and semantic accuracy, making it ideal for high-performance multilingual applications. This was selected as the final deployment model.
paraphrase-MiniLM-L3-v2
An English-only model that offers 384-dimensional embeddings. It achieved a Best Score of 0.9595 and is extremely fast, thanks to its lightweight architecture. It is well-suited for real-time applications where inference speed is a priority, though with a slight trade-off in accuracy.
distiluse-base-multilingual-cased-v1
This model supports more than 50 languages and generates 512-dimensional embeddings. It scored 0.8338 and has a moderate response time. It provides a good balance between multilingual capability and performance, making it suitable for general-purpose international applications.
distiluse-base-multilingual-cased-v2
Supporting 15+ languages, this variant of the DistilUSE model also produces 512-dimensional embeddings. It has a Best Score of 0.79203 and is slightly faster than version 1. It retains most of v1’s multilingual capabilities with slightly reduced semantic performance.
all-mpnet-base-v2
Limited to English, this model outputs 768-dimensional embeddings. It recorded a Best Score of 0.72351 and operates with a moderate inference time. While it offers high semantic precision for English queries, it is less suitable for time-critical or multilingual environments.

✅ Final Model Used: paraphrase-multilingual-MiniLM-L12-v2
💡 Features
🔍 Retrieval-based approach (high-speed, reliable answers)
🤖 Transformer embeddings via SBERT
💬 Sentiment-aware response tuning (TextBlob)
🌐 Multilingual query handling (50+ languages)
🏥🪙 Dual-domain support (Healthcare + Finance)
🧠 Context-aware intent classification
📈 Fine-tuned with domain-specific augmented data using nlpaug
🚀 Setup Instructions
🔧 Prerequisites
Python 3.7+
pip
Virtualenv (recommended)
🛠️ Installation
git clone https://github.com/yourusername/domain-specific-chatbot.git
cd domain-specific-chatbot
python -m venv venv
source venv/bin/activate  # For Linux/macOS
venv\Scripts\activate     # For Windows

pip install -r requirements.txt
🔍 Required Libraries
transformers
sentence-transformers
scikit-learn
textblob
numpy
pandas
nlpaug
🧪 Usage Example
from chatbot import ChatbotEngine

chatbot = ChatbotEngine(model_name="paraphrase-multilingual-MiniLM-L12-v2")
response = chatbot.get_response("What are the symptoms of dengue?")
print(response)
📈 Future Enhancements
 Integration with voice input/output (Speech-to-Text, TTS)
 GUI deployment using Streamlit or Flask
 Continuous learning using feedback loop
 Expansion to other domains (legal, education)



