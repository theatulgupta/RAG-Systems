# Retrieval-Augmented Generation (RAG) System

## Overview
This project implements a Retrieval-Augmented Generation (RAG) system that allows users to ask questions about their own documents (such as PDFs).  
The system retrieves relevant document chunks using vector similarity search and then uses a Large Language Model (LLM) to generate accurate answers based on the retrieved context.

This approach reduces hallucinations and enables LLMs to work with custom data.

---

## RAG Architecture

Documents → Text Splitter → Embeddings → Vector DB (Chroma)
↓
User Query → Retriever → Context → LLM (Mistral) → Answer

---

## Features
- Load and process PDF documents
- Split documents into text chunks
- Generate embeddings for semantic search
- Store embeddings in Chroma Vector Database
- Retrieve relevant document chunks using similarity search
- Generate answers using Mistral LLM
- Interactive command-line chat interface
- Persistent vector database

---

## Tech Stack
- Python
- LangChain
- ChromaDB (Vector Database)
- Mistral AI (LLM)
- HuggingFace Embeddings
- dotenv

---

## Project Structure

RAG/
│
├── main.py          # RAG question-answering pipeline
├── index.py         # Document indexing script
├── chromadb/        # Vector database storage
├── .env             # API keys
├── requirements.txt
└── README.md

---

## Setup Instructions

### 1. Clone Repository

git clone https://github.com/yourusername/rag-system.git
cd rag-system

### 2. Create Virtual Environment

python -m venv .venv
source .venv/bin/activate

### 3. Install Dependencies

pip install -r requirements.txt

### 4. Add API Keys
Create a `.env` file:

MISTRAL_API_KEY=your_mistral_api_key
HF_TOKEN=your_huggingface_token

---

## Index Documents
Run indexing once to store document embeddings:

python index.py

This will:
- Load PDFs
- Split text
- Create embeddings
- Store them in ChromaDB

---

## Run RAG System

python main.py

Then ask questions related to your documents.

Example:

Your question: What is machine learning?
Answer: Machine learning is…

---

## How RAG Works
1. Documents are loaded and split into chunks.
2. Each chunk is converted into embeddings.
3. Embeddings are stored in a vector database.
4. When a user asks a question, similar chunks are retrieved.
5. Retrieved context is sent to the LLM.
6. LLM generates an answer based only on the retrieved documents.

---

## Future Improvements
- Streamlit chat UI
- FastAPI backend
- Support for multiple document formats
- Hybrid search (BM25 + Vector)
- Conversation memory
- Docker deployment

---

## Author
Atul Kumar Gupta

---

## License
This project is open-source and available under the MIT License.
