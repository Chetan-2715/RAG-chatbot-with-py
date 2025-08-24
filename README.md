# 🧠 RAG Chatbot with Python

This project is a collection of Jupyter Notebooks that demonstrate how to build a **Retrieval-Augmented Generation (RAG) chatbot**. It takes you step-by-step, starting from basic language model interactions to building a complete and runnable RAG pipeline.

---

## 🔍 What is Retrieval-Augmented Generation (RAG)?

**Retrieval-Augmented Generation (RAG)** is a powerful technique that combines the strength of **large language models (LLMs)** with **external knowledge sources**.  
Instead of relying only on pre-trained knowledge, a RAG system:

1. **Retrieves** relevant information from external documents or databases.  
2. **Augments** the input with that knowledge.  
3. **Generates** a more accurate, context-aware response.

---

## ⚙️ Core Steps in RAG

1. **Document Loading & Chunking** – Read external documents (like PDFs) and split them into smaller text chunks.  
2. **Embedding & Indexing** – Convert chunks into numerical vectors (embeddings) and store them in a vector database.  
3. **Retrieval** – For a user query, retrieve the most relevant chunks based on semantic similarity.  
4. **Generation** – Provide the retrieved chunks as context to an LLM, which generates the final response.  

---

## 📂 Project Files Overview

This repository contains multiple Jupyter Notebooks, each explaining a specific part of the RAG pipeline.

### 1. `1st.ipynb`
**Purpose:** Introduces basic interaction with a large language model.  

- Using **LangChain** and **Ollama** to load a local model (`gemma3:1b`).  
- Configuring model parameters like **temperature** (creativity) and **num_predict** (token limit).  
- Invoking the model with a simple query.  

---

### 2. `2nd_prompts.ipynb`
**Purpose:** Demonstrates how to create structured and dynamic prompts.  

- Utilizing **ChatPromptTemplate** from LangChain.  
- Creating reusable prompt templates with placeholders for variables.  
- Generating tailored model outputs with different inputs.  

---

### 3. `3rd_chains.ipynb`
**Purpose:** Explains how to chain different components in a LangChain app.  

- Introduction to **LangChain Expression Language (LCEL)**.  
- Combining a **prompt**, **LLM**, and an **output parser** into one chain.  
- Using **StrOutputParser** to convert model output into plain text.  

---

### 4. `PDF_Reading_with_gemini.ipynb`
**Purpose:** Data ingestion and vector storage using **Google’s Gemini** model.  

- Reading PDFs with **PyPDF2**.  
- Splitting text using **CharacterTextSplitter**.  
- Creating embeddings with **HuggingFaceEmbeddings**.  
- Storing & retrieving vectors with **FAISS**.  

---

### 5. `RAG_with_Ollama.ipynb`
**Purpose:** A complete RAG pipeline using **Ollama**.  

- Generating embeddings with **OllamaEmbeddings**.  
- Creating a LangChain vector store (**FAISS + InMemoryDocstore**).  
- Performing **similarity search** to find relevant chunks.  
- Converting the vector store into a **retriever object**.  

---

### 6. `CHATBOT_WITH_OLLAMA.ipynb`
**Purpose:** Final implementation of a **RAG chatbot**.  

- Defining a prompt template with a `{context}` variable.  
- Building the **rag_chain** using `RunnablePassthrough`.  
- Demonstrating how retrieval + generation creates **informed responses**.  
