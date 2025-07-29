# Watheeq: Saudi Legal Assistant ⚖️🇸🇦

**Watheeq** is an Arabic-language legal chatbot designed to simplify access to Saudi legal documents. It utilizes a Retrieval-Augmented Generation (RAG) pipeline to provide accurate and explainable answers to users' legal questions.

---

## Project Overview

Legal documents in Saudi Arabia can be complex and hard to navigate. **Watheeq** makes it easier by:

- Answering legal questions in Arabic
- Retrieving information from official Saudi laws (scraped from هيئة الخبراء)
- Using plain language to explain laws and procedures
- Supporting the Saudi Vision 2030 goals for digital transformation

---

## How It Works

This notebook implements a full RAG pipeline:

1. **Data Loading**  
   Loads `.txt` files containing Saudi laws (e.g., labor laws, legal procedures).

2. **Chunking**  
   Splits long documents into 500-character chunks with 50-character overlap for better context during retrieval.

3. **Embeddings**  
   Uses `CohereEmbeddings` to create vector representations of legal text.

4. **Vector Store (ChromaDB)**  
   Stores embedded documents in a persistent ChromaDB store for efficient similarity search.

5. **LLM with Groq API**  
   Queries are answered using `Llama3` via Groq for fast and high-quality response generation.

6. **Chain Construction**  
   Combines document retriever + prompt template + LLM into a LangChain `RetrievalQA` pipeline.

---

## Example Use Case

Ask a question like:

> "ما مضمون المادة السابعة من نظام العمل؟"

The system will:

- Search for relevant text chunks
- Send the context to the LLM
- Return a grounded, natural-language answer

---

## 📁 Folder Structure

```bash
Watheeq_Final.ipynb     # Full notebook with all code
/laws                   # Folder containing .txt legal files
/chroma_laws_db         # Vector store directory (generated)
