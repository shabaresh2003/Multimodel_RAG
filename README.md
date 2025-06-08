# 🤖 Enhanced Multimodal RAG System with Gemini

A powerful and intelligent Retrieval-Augmented Generation (RAG) system designed for multimodal understanding and context-aware answering, powered by **Google Gemini** and built using **LangChain** and **Gradio**.

---

## 🚀 Key Features

- **📥 Multi-Source Ingestion**: Ingests content from local **PDF files** and **web URLs**.
- **🧠 Multimodal Understanding**: Extracts **text**, **tables**, and **images** intelligently.
- **🔍 Advanced RAG Pipeline**:
  - Summarizes content for efficient vector storage.
  - Uses full-resolution content for response generation.
- **⚡ Gemini-Powered AI Core**:
  - **Gemini 1.5 Flash** for high-speed summarization.
  - **Gemini 1.5 Pro** for rich, multimodal response generation.
- **🖼️ Image-in-Chat**: Displays relevant images from source documents directly within chat.
- **🧑‍💻 Interactive Gradio UI**: Clean, tab-based interface for document handling, Q&A, and context inspection.

---

## 🛠️ Technology Stack

| Layer              | Tools Used                                        |
|-------------------|--------------------------------------------------|
| **AI Core**        | Gemini 1.5 Flash, Gemini 1.5 Pro, LangChain      |
| **Vector DB**      | ChromaDB                                          |
| **Document Parsing** | PyMuPDF (`fitz`), BeautifulSoup4              |
| **Image Processing** | Pillow                                          |
| **Web Interface**   | Gradio                                          |
| **Supporting Libraries** | Requests, base64, json, etc.              |

---

## ⚙️ Setup & Installation

### 1. Prerequisites

- Python 3.8 or higher.
- A Google Gemini API Key from [Google AI Studio](https://aistudio.google.com/app/apikey).

### 2. Clone the Repository

```bash
git clone https://github.com/shabaresh2003/Multimodel_RAG
cd Multimodel_RAG
