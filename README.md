# PDF-Based RAG Pipeline with Google Gemini 

This repository features a complete **Retrieval-Augmented Generation (RAG)** system built with **LangChain**. The system enables "chatting with your data" by indexing a PDF document and using Google's **Gemini 2.5 Flash** to provide grounded, context-aware answers.

## Project Overview
Large Language Models (LLMs) often lack knowledge of specific or private documents. This project bridges that gap by implementing a RAG workflow: it loads a document (e.g., an AI research paper), breaks it into manageable chunks, generates vector embeddings, and retrieves relevant snippets to answer user queries accurately without hallucinations.


## Key Features
* **Document Ingestion**: Efficiently loading and parsing PDF content using `PyPDFLoader`.
* **Embedding & Retrieval**: Utilizing `HuggingFaceEmbeddings` and `DocArray` to create a high-performance, in-memory vector database for semantic search.
* **Context-Grounded Q&A**: Designing prompt templates that force the model to answer only based on the provided context, increasing factual reliability.
* **LCEL Orchestration**: Using LangChain Expression Language to pipe the retriever, prompt, and model into a single executable chain (`rag_chain`).

## Tech Stack
* **LLM**: Google Gemini 2.5 Flash
* **Framework**: LangChain (LCEL)
* **Embeddings**: Sentence-Transformers (HuggingFace)
* **Vector Store**: ChromaDB
* **Environment**: Google Colab / Jupyter Notebook

## Setup & Installation

### 1. Environment Configuration
Ensure you have a Python 3.10+ environment ready:

```bash
git clone https://github.com/Joe-Naz01/RAG.git
cd RAG

conda create -n rag python=3.10 -y
conda activate rag

# Install required libraries
pip install -r requirements.txt
jupyter notebook
