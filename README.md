# ⚖️ Pakistan Law Chatbot — RAG System

> A document-grounded AI chatbot that answers questions from uploaded Pakistani law PDFs using Retrieval-Augmented Generation (RAG), LangChain, Hugging Face embeddings, ChromaDB, and Ollama.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![LangChain](https://img.shields.io/badge/LangChain-RAG-orange)
![ChromaDB](https://img.shields.io/badge/ChromaDB-Vector%20DB-purple)
![Ollama](https://img.shields.io/badge/Ollama-Local%20LLM-black)
![Gradio](https://img.shields.io/badge/Gradio-UI-orange)

---

## 📌 Overview

Pakistan Law Chatbot is a Retrieval-Augmented Generation application designed to answer questions using information contained in uploaded Pakistani law documents.

The system combines:

* PDF document processing
* text chunking
* semantic embeddings
* vector retrieval
* local LLM inference
* conversational interaction

Instead of generating an answer from the language model alone, the application first retrieves relevant content from the uploaded documents and provides that context to the model.

---

## 🎯 Problem

Legal documents can be long and difficult to search manually.

This project explores how a RAG pipeline can make document-based legal information easier to access through natural-language questions.

The application is designed for **document exploration and information retrieval**, not as a replacement for a qualified legal professional.

---

## ✨ Features

* 📄 Multi-PDF document upload
* 🔍 Automatic PDF text extraction
* ✂️ Configurable text chunking
* 🧠 Semantic search using Hugging Face embeddings
* 🗄️ Persistent local ChromaDB vector storage
* 🤖 Local LLM inference through Ollama
* 💬 Natural-language question answering
* 🖥️ Simple Gradio interface
* 🏠 Local-first processing workflow

---

## 🏗️ RAG Architecture

```text id="24kwbh"
               PDF Documents
                     │
                     ▼
              Text Extraction
                     │
                     ▼
                 Chunking
                     │
                     ▼
        Hugging Face Embeddings
                     │
                     ▼
               ChromaDB
            Vector Database
                     │
                     │
User Question ──────┘
        │
        ▼
 Semantic Retrieval / Top-K
        │
        ▼
 Retrieved Document Context
        │
        ▼
 Ollama Local LLM
        │
        ▼
 Generated Answer
```

---

## 🧠 How It Works

### 1. Document Ingestion

Users upload one or more Pakistani law PDFs.

### 2. Text Extraction

Text is extracted from the uploaded PDF documents.

### 3. Chunking

Large documents are divided into smaller chunks to improve retrieval.

### 4. Embedding Generation

The text chunks are converted into vector representations using a Hugging Face embedding model.

### 5. Vector Storage

Generated embeddings are stored in a persistent ChromaDB collection.

### 6. Semantic Retrieval

When the user asks a question, the system searches for the most relevant document chunks.

### 7. Answer Generation

The retrieved context is provided to the locally running Ollama model to generate the response.

---

## 🛠️ Tech Stack

| Component           | Technology                           |
| ------------------- | ------------------------------------ |
| Language            | Python                               |
| RAG Framework       | LangChain                            |
| Embeddings          | Hugging Face / Sentence Transformers |
| Vector Database     | ChromaDB                             |
| LLM Runtime         | Ollama                               |
| LLM                 | LLaMA-family model                   |
| Interface           | Gradio                               |
| Document Processing | PyPDF                                |

---

## 📂 Project Structure

```text id="8p8o2j"
Pakistan-Law-Chatbot-RAG-System/
│
├── Law-chatbot.py
│   └── Document ingestion, retrieval,
│       generation, and Gradio interface
│
└── README.md
```

The current implementation is intentionally compact, with the main application logic contained in `Law-chatbot.py`.

---

## ⚙️ Getting Started

### Prerequisites

Install:

* Python 3.x
* Git
* Ollama

---

### 1. Clone the Repository

```bash id="1q4x5r"
git clone https://github.com/abdullahk970/Pakistan-Law-Chatbot-RAG-System.git

cd Pakistan-Law-Chatbot-RAG-System
```

---

### 2. Create a Virtual Environment

```bash id="on08ke"
python -m venv venv
```

#### Windows

```bash id="rxhhws"
venv\Scripts\activate
```

#### Linux / macOS

```bash id="i3n8j9"
source venv/bin/activate
```

---

### 3. Install Dependencies

```bash id="wwr8gb"
pip install langchain chromadb sentence-transformers gradio pypdf
```

---

### 4. Start Ollama

Start the local Ollama service:

```bash id="v6rbh4"
ollama serve
```

Then download the model used by the application:

```bash id="ikb3qs"
ollama pull llama2
```

> Make sure the model name matches the configuration used by the current application.

---

## ▶️ Run the Application

```bash id="qapikf"
python Law-chatbot.py
```

The Gradio interface will provide a local URL for interacting with the chatbot.

---

## 📡 RAG Pipeline

The core retrieval flow can be summarized as:

```text id="4lmcqj"
Documents
   ↓
Text Extraction
   ↓
Chunking
   ↓
Embeddings
   ↓
ChromaDB
   ↓
Top-K Retrieval
   ↓
Retrieved Context
   ↓
Local LLM
   ↓
Answer
```

---

## 🧪 Evaluation

RAG quality should be evaluated using a defined set of questions and expected source documents.

Useful evaluation metrics for this project include:

* Retrieval Recall@K
* Retrieval Precision@K
* MRR
* Answer relevance
* Context relevance
* Faithfulness of generated answers

No numerical benchmark is claimed here until a reproducible evaluation dataset and methodology are defined.

---

## ⚠️ Limitations

This project has several limitations:

* Retrieval quality depends on document chunking and embedding quality.
* The language model can generate incorrect or incomplete responses.
* Similarity retrieval does not guarantee that the retrieved passage is legally sufficient.
* Uploaded PDFs may contain formatting or extraction problems.
* The current implementation does not provide formal legal verification.
* Answers should not be treated as professional legal advice.

---

## 🔐 Privacy & Security Considerations

Because the application may process legal documents, production deployments should carefully consider:

* secure document handling
* temporary-file cleanup
* protection of stored vector data
* access control
* avoiding sensitive information in logs
* secure model/service configuration

Do not upload confidential legal documents to an environment that is not trusted or properly secured.

---

## 🔮 Future Improvements

Potential improvements include:

* Urdu-language query support
* Citation-based answers
* Page and section references
* Hybrid retrieval
* Retrieval reranking
* RAG evaluation dataset
* Better handling of scanned PDFs
* Document metadata filtering
* Improved answer verification
* Web deployment with appropriate security controls

---

## 👨‍💻 Author

**Muhammad Abdullah Khan**

* GitHub: [abdullahk970](https://github.com/abdullahk970)
* LinkedIn: [Muhammad Abdullah Khan](https://www.linkedin.com/in/muhammad-abdullah-khan-9b0980316?utm_source=share_via&utm_content=profile&utm_medium=member_android)

---

## 📄 License

This project is licensed under the MIT License.
