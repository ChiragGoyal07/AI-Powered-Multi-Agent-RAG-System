# **📌 Langraph-RAG: Intelligent Question Routing & Retrieval**
An advanced **Retrieval-Augmented Generation (RAG) system** that dynamically routes user queries to **either a vector store or Wikipedia search** based on context. Built using **LangChain, Langraph, AstraDB, and Groq API**, this system enables **intelligent document retrieval and knowledge augmentation** over structured and unstructured data sources.

---

## **🚀 Features**
- **Hybrid Query Routing**: Uses **LLM-based classification** to determine whether to fetch results from a **vector database (RAG)** or perform a **Wikipedia search**.
- **AstraDB Vector Store Integration**: Stores and retrieves embeddings using **HuggingFace sentence embeddings**.
- **Langraph for Workflow Execution**: Implements a **graph-based state machine** for efficient knowledge retrieval.
- **Real-time Query Handling**: Enables interactive question-answering over indexed documents.
- **Web-Based Document Ingestion**: Indexes key research articles on **agents, prompt engineering, and adversarial attacks**.

---

## **🛠 Tech Stack**
- **LangChain**: Orchestrates retrieval-based question answering.
- **Langraph**: Implements workflow graph execution for intelligent routing.
- **AstraDB (Cassandra)**: Stores vector embeddings for efficient retrieval.
- **HuggingFace Embeddings**: Generates dense text representations for similarity matching.
- **Groq API (Gemma2-9b)**: Processes user queries for query routing.

---

## **📂 Project Structure**
```
📁 Langraph-RAG
│── 3_langraph_with_astradb.py  # Main pipeline script
│── requirements.txt            # Dependencies
│── README.md                   # Project Documentation
```

---

## **⚡ Quick Start**
### **1️⃣ Install Dependencies**
```bash
pip install langchain langgraph cassio langchain_community tiktoken langchain-groq langchainhub chromadb langchain_huggingface arxiv wikipedia
```

### **2️⃣ Configure AstraDB**
Replace the following placeholders in `3_langraph_with_astradb.py` with your **AstraDB credentials**:
```python
ASTRA_DB_APPLICATION_TOKEN = "Your_AstraDB_Token"
ASTRA_DB_ID = "Your_AstraDB_ID"
cassio.init(token=ASTRA_DB_APPLICATION_TOKEN, database_id=ASTRA_DB_ID)
```

### **3️⃣ Run the System**
```bash
python 3_langraph_with_astradb.py
```
---

## **🎯 How It Works**
### **📌 Step 1: Web Document Indexing**
- Loads and splits research papers into **chunks of 500 tokens**.
- Generates embeddings using **HuggingFace Sentence Transformers**.
- Stores embeddings in **AstraDB (Cassandra VectorStore)**.

### **📌 Step 2: Query Routing**
- Uses a **Groq LLM (Gemma2-9b)** to classify queries.
- Routes **LLM-related queries to AstraDB** and general knowledge queries to **Wikipedia**.

### **📌 Step 3: Answer Generation**
- Retrieves relevant documents using **semantic search**.
- Combines retrieved documents and user queries to generate **high-quality responses**.

---

## **📊 Example Queries**
| Query                          | Source |
|--------------------------------|--------|
| "What is agent memory?"        | RAG (AstraDB) |
| "Who is Shahrukh Khan?"        | Wikipedia |
| "Explain adversarial attacks?" | RAG (AstraDB) |

---

## **📌 Future Enhancements**
✅ **Multi-Modal Query Support** (Text + Image)  
✅ **Fine-tuned LLM Integration** for query understanding  
✅ **Caching Mechanism** to speed up responses  

---

This **Langraph-RAG system** demonstrates the power of **graph-based AI pipelines for knowledge retrieval**. 🚀  
Let me know if you need further refinements! 🚀
