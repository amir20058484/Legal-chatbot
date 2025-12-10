# Legal Chatbot ⚖️

A lightweight legal Q&A chatbot powered by **Retrieval-Augmented Generation (RAG)**.

### What it does
- Takes your legal question
- Retrieves the most relevant real Q&A pairs using **FAISS + all-MiniLM-L6-v2**
- Generates accurate, natural answers with **google/flan-t5-large**
- Automatically detects legal category (Contract Law, Criminal Law, IP, Family Law, etc.)

### Dataset
[dzunggg/legal-qa-v1](https://huggingface.co/datasets/dzunggg/legal-qa-v1) 

### Features
- Fast semantic search
- Optional category filtering
- Invalid/off-topic question detection
- Clean Gradio web interface

Single-file project (`main.py`) — no extra config needed.

**Disclaimer**: For educational/research purposes only. Not a substitute for professional legal advice.

License: MIT
