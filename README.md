# ⚖️ Pakistan Law Chatbot (RAG System)

> An AI-powered legal assistant that answers questions from uploaded Pakistani law PDFs using Retrieval-Augmented Generation (RAG), built with LangChain, HuggingFace embeddings, ChromaDB, and Ollama (LLaMA 2).

![Python](https://img.shields.io/badge/Python-3.x-blue) ![LangChain](https://img.shields.io/badge/LangChain-RAG-orange) ![ChromaDB](https://img.shields.io/badge/ChromaDB-Vector%20DB-purple) ![Ollama](https://img.shields.io/badge/Ollama-LLaMA2-black)

## 🚀 Overview

Pakistan Law Chatbot lets users upload legal PDF documents and ask questions about them in natural language. The system extracts text, generates embeddings, stores them in a local vector database, and uses a locally-run LLM to generate context-grounded legal answers — fully offline and privacy-friendly.

## ✨ Features

- Multi-PDF upload and automatic text extraction
- Configurable chunking for accurate retrieval
- Semantic search via HuggingFace embeddings (`all-MiniLM-L6-v2`)
- Local, persistent vector storage (ChromaDB) — no cloud dependency
- Answers grounded strictly in retrieved document content
- Simple Gradio chat interface

## 🏗️ Tech Stack

- Python 3
- LangChain
- HuggingFace Transformers (embeddings)
- ChromaDB (persistent vector store)
- Ollama — LLaMA 2 7B Chat
- Gradio (UI)

## ⚙️ How It Works

```
User Uploads PDF
      │
      ▼
Text Extraction
      │
      ▼
Chunking (LangChain Splitter)
      │
      ▼
HuggingFace Embeddings (MiniLM)
      │
      ▼
ChromaDB Vector Storage
      │
      ▼
User Question → Semantic Retrieval (Top-K) → LLaMA 2 (Ollama) → Answer
```

## 📂 Project Structure

```
Pakistan-Law-Chatbot-RAG-System/
│
├── Law-chatbot.py    # Main application — ingestion, retrieval, and Gradio UI
└── README.md
```

## ⚙️ Installation

```bash
git clone https://github.com/abdullahk970/Pakistan-Law-Chatbot-RAG-System.git
cd Pakistan-Law-Chatbot-RAG-System

python -m venv venv
source venv/bin/activate    # Windows: venv\Scripts\activate

pip install langchain chromadb sentence-transformers gradio pypdf

# Install and run Ollama
ollama serve
ollama pull llama2
```

## 🚀 Run

```bash
python Law-chatbot.py
```

Gradio will open a local link, typically `http://127.0.0.1:7860`.

## ⚡ Performance Notes

- Lightweight embedding model (MiniLM) for fast retrieval
- Fully local vector database — no cloud API costs or latency
- Optimized to run on CPU-only systems

## 🔮 Possible Future Improvements

- Urdu-language query support
- Citation-based answers (referencing exact law sections)
- Cloud deployment option (Hugging Face Spaces)

## 👨‍💻 Author

**Muhammad Abdullah Khan**
