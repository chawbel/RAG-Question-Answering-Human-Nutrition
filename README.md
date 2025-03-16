# RAG Pipeline for Question Answering

This project is a **Retrieval-Augmented Generation (RAG)** pipeline designed to answer questions from the textbook **"Human Nutrition 2e"** 
by the University of Hawai'i (~1200 pages). It combines **FAISS** (vector-based retrieval) and **BM25** (keyword-based retrieval)
for hybrid document search, with a reranking model to refine results and a quantized **Gemma 2 7B** model for generating answers. 
The pipeline also includes an API endpoint built with **FastAPI** and exposed via **Ngrok** for temporary access.

---

## Features
- **Hybrid Retrieval**: Combines FAISS (semantic search) and BM25 (keyword search) for robust document retrieval.
- **Reranking**: Uses `cross-encoder/ms-marco-MiniLM-L-6-v2` to improve search result relevance.
- **Quantized Model**: Leverages **Gemma 2 7B** quantized to 4-bit precision for faster inference.
- **API Integration**: FastAPI server with Ngrok for temporary URL accessibility.
- **Document Processing**: Parses and splits text from PDFs using `pymupdf` and `langchain`.

---

## Libraries Used
- `llama-index`  
- `pymupdf`  
- `langchain`  
- `faiss-cpu`  
- `rank-bm25`  
- `nltk`  
- `langchain-community`  
- `bitsandbytes`  
- `accelerate`  
- `uvicorn`  
- `fastapi`  
- `pyngrok`  
- `sentence-transformers`  
- `transformers`  
- `numpy`  

---

## Installation Instructions
1. Clone the repository:
   ```bash
   git clone https://github.com/chawbel/rag-pipeline.git
   cd rag-pipeline

2. Install dependencies:
      ```bash
      pip install -r requirements.txt

---

## Running the Application 

1. Start the FastAPI server:
   ```bash     
   uvicorn main:app --host 0.0.0.0 --port 8000
 
2. Expose the server to the web using Ngrok:
   ```bash
   ngrok http 8000
  
3. Access the API endpoint at the Ngrok URL provided (e.g., https://random.ngrok.io/docs).
