# DocsGuide

An AI-powered assistant helping Nepali citizens navigate government
document procedures with ease.

DocsGuide is a bilingual chatbot that simplifies the complex process of
obtaining government documents like citizenship certificates and
passports. Built using Retrieval-Augmented Generation (RAG), it provides
accurate, step-by-step guidance sourced directly from verified official
documents.

## 🚀 Why DocsGuide?

Navigating government procedures in Nepal can be confusing and
time-consuming. DocsGuide addresses this by:

-   Providing clear, conversational guidance in both Nepali and English
-   Delivering verified information from official government sources
-   Offering instant answers without searching through multiple
    documents
-   Citing sources for transparency and trust

## ✨ Features

-   🌐 *Bilingual Support* -- Seamlessly handles queries in Nepali and
    English
-   🔍 *Hybrid Search* -- Combines semantic understanding with keyword
    matching
-   📚 *Source Citations* -- Answers always reference official
    documents
-   💬 *Context-Aware* -- Maintains conversational flow
-   ✅ *Verified Information* -- Based on acts, rules, FAQs,
    guidelines

## 🛠️ Tech Stack

### *Backend*

-   FastAPI
-   PineconeDB
-   Gemini API

### *Embedding & Retrieval*

-   Embedding Model: universalml/Nepali_Embedding_Model (1024d)
-   Hybrid retrieval: Dense vectors + BM25 sparse search
-   Reranker: jinaai/jina-reranker-v2-base-multilingual

### *Frontend*

-   Next.js
-   Tailwind CSS

## 📁 Project Structure

    DOCSGUIDE/
    ├── data/                    # Raw data, processed chunks, QA pairs
    ├── frontend/                # Next.js application
    ├── src/
    │   ├── embeddings/          # Vector generation
    │   ├── generator/           # Response generation
    │   ├── preprocessing/       # Document chunking
    │   ├── retriever/           # Search strategies
    │   ├── server/              # FastAPI backend
    │   └── qa_test.ipynb        # Evaluation pipeline
    └── README.md

## ⚙️ Getting Started

### *Prerequisites*

-   Node.js 16+
-   Python 3.8+
-   PineconeDB account
-   Gemini API key

## 🧩 Installation

git clone https://github.com/fuseai-fellowship/DocsGuide-An-Assistant-for-Government-Document-Procedures

cd DOCSGUIDE

Install backend dependencies:

pip install -r requirements.txt

Install frontend dependencies:

cd frontend
npm install

## ▶️ Running the App

### *Start the backend*

cd src/server
uvicorn main:app --reload


### *Start the frontend*

cd frontend
npm run dev

Web app available at: *http://localhost:3000*

## 📚 Dataset

Knowledge base consists of official Nepali government documents
regarding:

-   Citizenship acts & regulations
-   Passport rules & guidelines
-   Government FAQs
-   Procedural guides & forms

Documents are chunked with metadata (type, section, tags, source links)
for precise retrieval.

### *Evaluation Data*

-   28 QA pairs for evaluation
-   15 QA pairs for testing
-   Manually labeled chunks as ground truth

## 📊 Performance

Our best configuration:

-   *85.77% / 89.3%* Answer Correctness (eval/test)
-   *90.23% / 88.9%* Recall@7
-   Uses hybrid search (50-50 dense/sparse split) with document-type
    filtering + reranking

Tested on *43* real-world citizenship/passport queries.

## ⚠️ Current Scope & Limitations

-   Supports only citizenship and passport procedures
-   Optimized for Nepali retrieval; English translation may vary
-   Evaluation dataset is relatively small

## 🛣️ Roadmap

-   [ ] Add more government document categories
-   [ ] Improve translation quality
-   [ ] Support mixed-language documents
-   [ ] Large-scale user testing
-   [ ] Mobile application

## 👥 Team

Built by:
*Andis Paudel*, *Bikash Pokhrel*, *Dipin Adhikari*, *Utsab
Dahal*

------------------------------------------------------------------------

Note: Set up environment variables for API keys and database credentials
before running the application.
