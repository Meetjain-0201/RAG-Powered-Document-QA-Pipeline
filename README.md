# RAG Pipeline with Qdrant and Gemini

A modular Retrieval Augmented Generation system built on top of **Qdrant**, **SentenceTransformers**, and **Google Gemini**. This project turns PDF collections into a searchable knowledge base and generates context-aware answers using modern LLMs.

<div align="center">  
<img src="https://img.shields.io/badge/VectorDB-Qdrant-ff4f5a" />  
<img src="https://img.shields.io/badge/LLM-Google%20Gemini-4285F4" />  
<img src="https://img.shields.io/badge/Framework-LangChain-3B7EFC" />  
<img src="https://img.shields.io/badge/PDF-PyMuPDF-8A2BE2" />  
</div>

---

## 📌 Project Highlights

This pipeline automates everything from document ingestion to answer generation.

### What it does

• Reads and preprocesses PDFs from a selected folder
• Breaks documents into optimal chunks for retrieval
• Generates embeddings using SentenceTransformers
• Stores and indexes all embeddings inside Qdrant
• Uses Gemini to produce context-rich answers
• Supports a **hybrid retrieval strategy** combining vector and keyword search
• Ranks results using **Reciprocal Rank Fusion (RRF)**

---

## 🧠 Architecture Overview

```
        ┌──────────────┐
        │    PDFs      │
        └───────┬──────┘
                │
                ▼
      ┌──────────────────┐
      │ Document Loader  │
      └──────────┬───────┘
                 │
                 ▼
     ┌────────────────────┐
     │ Text Chunking      │
     └──────────┬─────────┘
                │
                ▼
  ┌───────────────────────────┐
  │ SentenceTransformer Embed │
  └──────────────┬────────────┘
                 │
                 ▼
      ┌───────────────────┐
      │   Qdrant Vector   │
      │      Store        │
      └───────┬───────────┘
              │
              ▼
   ┌──────────────────────┐
   │ Hybrid Search (RRF)  │
   └───────────┬──────────┘
               │
               ▼
        ┌──────────────┐
        │   Gemini LLM │
        └──────────────┘
```

---

## 🧰 Technologies

| Component                | Purpose                                             |
| ------------------------ | --------------------------------------------------- |
| **LangChain**            | Manages LLM pipelines, loaders, and retrieval logic |
| **Qdrant**               | Vector database for similarity search               |
| **Google Gemini**        | LLM for generating answers                          |
| **SentenceTransformers** | Embedding generation                                |
| **PyMuPDF**              | PDF parsing and text extraction                     |

---

## ⚙️ Installation

Clone the project

```
git clone https://github.com/AtharvaKulkarniIT/rag-qdrant-pipeline.git
cd rag-qdrant-pipeline-main
```

Install Python dependencies

```
pip install langchain PyMuPDF
pip install langchain_google_genai
pip install sentence-transformers
```

Set environment variables

```
export QDRANT_API_KEY="your_key"
export GEMINI_API_KEY="your_key"
```

---

## 🚀 How to Use

1. Place your PDF files in the `data/` folder
2. Run the notebook or script to populate Qdrant
3. Query using any question of your choice

Example

```python
query = "Describe the rivers in Maharashtra"
response = get_gemini_response(query)
print(response)
```

---

## 🔍 Hybrid Retrieval (Vector + Keywords)

This system merges:

• **Semantic similarity** from Qdrant
• **Keyword matches** from original text

The final ranking uses **Reciprocal Rank Fusion (RRF)**, giving you the most relevant context regardless of phrasing.

---

## 🧪 Example Use Cases

• Intelligent FAQ systems
• Document assistants
• Academic research helpers
• PDF-based chatbots
• Enterprise knowledge search

---

## 🤝 Contributing

Suggestions, feature requests, and PRs are always welcome!
Feel free to open an issue if you want to discuss ideas.

---

## 📄 License

Distributed under the MIT License.
See the `LICENSE` file for full details.


Just tell me your preference.
