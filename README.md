```markdown
# DocuMind 🧠📄

**DocuMind** is a Retrieval-Augmented Generation (RAG) powered Document Q&A system. It allows users to upload PDF documents and ask questions in natural language, receiving highly accurate, context-grounded answers without AI hallucinations. 

## 🚀 Features
* **Document Parsing:** Instantly extracts and processes text from uploaded PDF files.
* **Semantic Search:** Uses `all-MiniLM-L6-v2` embeddings and ChromaDB for highly accurate vector similarity searches.
* **Smart Chunking:** Employs LangChain's RecursiveCharacterTextSplitter for optimal context window management.
* **Grounded AI Answers:** Combines retrieved context with LLMs (OpenAI/Claude) to provide cited, accurate answers.
* **Full-Stack Architecture:** Clean React frontend communicating with a lightning-fast FastAPI backend.

## 🛠️ Tech Stack
* **Backend:** Python, FastAPI, LangChain
* **Frontend:** React.js
* **Vector Database:** ChromaDB
* **Embeddings:** Sentence-Transformers (`all-MiniLM-L6-v2`)
* **Document Processing:** PyMuPDF (`fitz`)

## 💻 Quick Start

### 1. Clone the repository
```bash
git clone [https://github.com/chaitanyavarma24/DocuMind.git](https://github.com/chaitanyavarma24/DocuMind.git)
cd DocuMind
```

### 2. Backend Setup
Install the required Python dependencies:
```bash
pip install fastapi uvicorn langchain chromadb sentence-transformers openai pymupdf python-multipart
```
Run the FastAPI server:
```bash
uvicorn main:app --reload
```

### 3. Frontend Setup
Navigate to the frontend directory, install dependencies, and start the React app:
```bash
npx create-react-app frontend
cd frontend
npm install
npm start
```

## 🧠 Core RAG Pipeline
1. **Ingestion:** PDF -> PyMuPDF Text -> Recursive Text Chunking -> Sentence Transformer Embeddings -> ChromaDB.
2. **Retrieval:** User Query -> Query Embedded -> Top K Vector Search via ChromaDB.
3. **Generation:** Retrieved Context + User Query -> LLM Prompt -> Grounded Answer provided to the frontend.
```
