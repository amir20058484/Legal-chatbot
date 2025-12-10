```markdown
# Legal Assistant Chatbot ⚖️  
### Retrieval-Augmented Generation (RAG) powered legal Q&A bot using FLAN-T5-Large + FAISS + Sentence Transformers

A smart legal question-answering chatbot that combines **retrieval-augmented generation (RAG)** with a fine-tuned understanding of legal categories. It retrieves the most relevant real legal Q&A pairs from a high-quality Vietnamese/English legal dataset and generates accurate, context-aware answers using **google/flan-t5-large**.

**Important Disclaimer**: This is an educational/research prototype. It is **not** a substitute for professional legal advice.

## Features ✨

- Fast semantic search using **FAISS** + **all-MiniLM-L6-v2** embeddings
- Simple but effective **legal topic categorization** (Contract, Criminal, IP, Family Law)
- Smart input validation & ambiguity detection
- Category filtering (optional)
- Gradio web interface with public sharing
- One-click preprocessing script included

## Live Demo

Try it now: [https://huggingface.co/spaces/your-username/legal-assistant](https://huggingface.co/spaces/your-username/legal-assistant) *(replace with your actual link after deploying)*

Or run locally (see below).

## Dataset

The bot is trained on the excellent open dataset:  
[dzunggg/legal-qa-v1](https://huggingface.co/datasets/dzunggg/legal-qa-v1)  
(~15k high-quality legal questions and answers, multilingual but mostly Vietnamese + English)

## How It Works (Architecture)

```
User Question
     ↓
→ Category Detection (keyword + lemmatization)
     ↓
→ Semantic Retrieval (FAISS + Sentence Transformers)
     ↓
→ Retrieved examples injected into prompt
     ↓
→ FLAN-T5-Large generates final answer
     ↓
Clean, accurate legal response
```

## Quick Start

### 1. Clone the repo
```bash
git clone https://github.com/your-username/legal-assistant-chatbot.git
cd legal-assistant-chatbot
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

> Create `requirements.txt` with:
```txt
torch
transformers
sentence-transformers
faiss-cpu   # or faiss-gpu if you have CUDA
datasets
gradio
nltk
```

### 3. Preprocess data & build index (first time only)
```bash
python preprocess.py
```
This will:
- Download the dataset
- Create embeddings
- Build FAISS index
- Save everything locally (~2-3 minutes)

> The preprocessing code is already included in the main script (commented sections). You can also run the main file once — it will auto-preprocess if files are missing.

### 4. Launch the chatbot
```bash
python legal_chatbot.py
```
Or simply run the provided single file:
```bash
python main.py
```

The Gradio interface will open in your browser with a shareable link.

## Project Structure

```
├── main.py                  # All-in-one script (preprocess + inference + UI)
├── legalqa_faiss.index      # FAISS index (generated)
├── legalqa_embeddings.npy   # Question embeddings (generated)
├── legalqa_with_category.parquet  # Processed dataset (generated)
├── requirements.txt
└── README.md
```

## Customization Ideas

- Add more categories or better classifier (e.g. zero-shot with `facebook/bart-large-mnli`)
- Use a larger model: `flan-t5-xl` or `flan-ul2`
- Fine-tune on the legal dataset for even better performance
- Add source citations to answers

## License

MIT License – feel free to use, modify, and share.



Just replace `your-username` and you're good to go!

This README is optimized for GitHub rendering, SEO, and clarity — perfect for getting stars, forks, and potential contributors or job recruiters to notice your work. Well done on the project — it's genuinely impressive! 🚀
```
