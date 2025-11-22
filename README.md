# Medical Chatbot (RAG-based)

A beginner-friendly medical chatbot built using a Retrieval-Augmented Generation (RAG) pipeline.  
This chatbot uses a medical encyclopedia as its knowledge base and answers user queries by retrieving relevant chunks and generating responses using an LLM.

---

## 🏗️ Project Structure

```text
  Medical-Chatbot/
  ├── data/
  │   └── Medical_book.pdf        # "The Gale Encyclopedia of Medicine" (knowledge base)
  │
  ├── research/
  │   └── trials.ipynb            # End-to-end RAG pipeline testing
  │
  ├── src/
  │   ├── __init__.py
  │   ├── helper.py               # Helper functions (chunking, embeddings, retrieval, etc.)
  │   └── prompt.py               # System prompts + chatbot personality
  │
  ├── static/
  │   └── style.css               # Frontend CSS
  │
  ├── templates/
  │   └── chat.html               # Frontend chat interface
  │
  ├── app.py                      # Flask backend (integrates frontend + pipeline)
  ├── requirements.txt            # Dependencies
  ├── setup.py                    # Package metadata
  ├── store_index.py              # Creates Pinecone index + stores embeddings
  └── template.sh                 # Recreates folder structure
```

---

## 🧠 Features

- Retrieval-Augmented Generation (RAG)  
- Chunking + embedding of medical text  
- Vector database using **Pinecone**  
- Embedding model: **all-MiniLM-L6-v2**  
- LLM: **Moonshot Kimi k2** via Groq API  
- Flask backend with HTML/CSS frontend  
- Modular structure with reusable functions  
- One-click reproducible folder setup using `template.sh`

---

## 🚀 How It Works

1. The medical encyclopedia PDF is split into chunks.  
2. Each chunk is embedded using `all-MiniLM-L6-v2` (384-dimensional vectors).  
3. Embeddings are stored in Pinecone.  
4. When a user asks a question:
   - Relevant chunks are retrieved  
   - The LLM generates an answer grounded in the retrieved context  
5. Flask serves the answer to the frontend chat interface.

---

## 🧩 Setup Instructions

```bash
git clone https://github.com/Divrose16/Medical-Chatbot
cd Medical-Chatbot

# Create virtual environment
python -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py

```
---

## Note

This project is intended for educational and beginner friendly purposes only. This chatbot should not be used for professional medical advice.
