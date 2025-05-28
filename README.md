# RAG Bot for Specialized Question Answering

This project implements a **Retrieval-Augmented Generation (RAG)** bot that answers specialized queries using structured data (CSV) and unstructured data (Markdown). It combines **OpenAI embeddings**, **FAISS**, and **Google's FLAN-T5** for scalable and intelligent question answering.

---

##  Objective

- Build a flexible RAG pipeline that can:
  - Embed and store structured & unstructured documents
  - Retrieve context based on user query
  - Generate informed answers using a large language model
- Evaluate performance on hybrid datasets:
  - A structured dataset of cars
  - An unstructured country facts file

---

##  Data Sources

- **cars_dataset.csv**  
  Structured dataset containing car specifications.

- **country_data.md**  
  Unstructured Markdown document containing country-related facts and descriptions.

---

## ⚙Core Components

| Module                     | Purpose                                                                 |
|----------------------------|-------------------------------------------------------------------------|
| `langchain + langgraph`    | For building dynamic dataflow and RAG logic                            |
| `OpenAIEmbeddings`         | Embedding generator for retrieval indexing                              |
| `FAISS`                    | Vector store for efficient similarity search                            |
| `FLAN-T5 Large`            | Response generation via Hugging Face Transformers                       |
| `TextSplitter`             | Chunking unstructured text into retrievable documents                   |

---

## Workflow

1. **Preprocess Data**:
   - Load and clean structured (`csv`) and unstructured (`md`) data
   - Chunk and format them into `Document` objects

2. **Embed & Index**:
   - Generate embeddings using OpenAI
   - Store in a FAISS vector DB

3. **Query Flow**:
   - Input question → retrieve similar chunks → pass to T5 → return answer

---

## Project Structure

```bash
.
├── RAG_Bot_For_Specialized_Question_Answering.ipynb  # Full pipeline notebook
├── cars_dataset.csv                                  # Structured dataset
├── country_data.md                                   # Unstructured text file
├── README.md                                         # Project documentation
└── requirements.txt                                  # Python dependencies
