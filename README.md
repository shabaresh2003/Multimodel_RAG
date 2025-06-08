🤖 Enhanced Multimodal RAG System with Gemini
This project is a sophisticated Retrieval-Augmented Generation (RAG) system capable of processing and understanding information from multiple sources (PDFs and websites) and modalities (text, tables, and images). It leverages the power of Google's Gemini models through LangChain to provide context-aware answers to user questions. The entire application is wrapped in a user-friendly web interface created with Gradio.

🚀 Key Features
Multi-Source Ingestion: Process documents from both local PDF files and public URLs.

Multimodal Data Extraction: Intelligently extracts not just text, but also tables and images from documents.

Advanced RAG Pipeline: Implements a multi-vector retriever strategy where documents are summarized for efficient retrieval, but full original content is used for generation.

Powerful AI Core: Uses Gemini 1.5 Flash for high-speed summarization and Gemini 1.5 Pro for generating high-quality, context-aware answers.

Image-in-Chat: Displays relevant images from the source documents directly in the chat, providing visual context to answers.

Interactive UI: A clean, tab-based user interface built with Gradio for easy document processing, chatting, and context inspection.

🛠️ Technology Stack
AI & Orchestration: LangChain, Google Gemini 1.5 Pro, Google Gemini 1.5 Flash

Vector Storage: ChromaDB

Web Interface: Gradio

Document Processing: PyMuPDF (fitz), BeautifulSoup4

Core Libraries: Pillow, Requests

🔧 Setup and Installation
Follow these steps to get the application running on your local machine.

1. Prerequisites
Python 3.8 or higher.

A Google Gemini API key. You can get one from Google AI Studio.

2. Clone the Repository
git clone <your-repository-url>
cd <your-repository-name>

3. Install Dependencies
Install all the required Python packages using the provided requirements.txt file.

pip install -r requirements.txt

4. Configure Your API Key
Open the main Python script (your_script_name.py) and locate the following section at the bottom:

if __name__ == "__main__":
    # IMPORTANT: Paste your Gemini API key here
    api_key = "YOUR_GEMINI_API_KEY_HERE"

Replace "YOUR_GEMINI_API_KEY_HERE" with your actual Google Gemini API key.

▶️ How to Run and Use the Application
Running the Script
Once the setup is complete, run the application from your terminal:

python your_script_name.py

Gradio will start a local web server and provide you with a URL (usually http://127.0.0.1:7860). Open this URL in your browser to access the interface.

Using the Interface
The application has three main tabs:

📄 Document Processing
This is where you add documents to the knowledge base.

Upload PDFs: Click the "Upload PDFs" box to select one or more PDF files from your computer.

Enter URLs: Type or paste website URLs into the textbox, with each URL on a new line.

Process: Click the "Process All Sources" button. The system will ingest all provided documents, extract content, and store it in the vector database. The status window will show the progress and results.

💬 Chat Interface
Ask questions about the documents you've processed.

Type your question into the input box at the bottom.

Press Enter or click the "Ask" button.

The chatbot will display the answer. If a relevant image is found in the context, it will be displayed directly in the chat.

🔍 View Context
Inspect the specific information the AI used to generate an answer.

Enter the same question you asked in the chat tab.

Click the "Show Context" button.

The interface will display the raw text chunks and images that were retrieved from the knowledge base to answer your question.

⚙️ How It Works
The system follows a Retrieval-Augmented Generation (RAG) pipeline optimized for multimodal content.

Ingestion & Extraction: When a source is provided, its content is extracted. PyMuPDF is used for PDFs (to get text, tables, and images), and BeautifulSoup is used for URLs (to get text and images).

Summarization & Indexing (Multi-Vector Retriever):

Each extracted element (text chunk, table, image) is summarized by Gemini 1.5 Flash.

These summaries are converted into vector embeddings and stored in ChromaDB.

The original, full-resolution elements (the actual text, table data, and base64-encoded images) are stored in a simple in-memory key-value store. A link (ID) is maintained between each summary vector and its original element.

Retrieval & Augmentation:

When you ask a question, it is converted into a vector embedding.

ChromaDB performs a similarity search to find the most relevant summary vectors.

The system uses the IDs from the retrieved summaries to fetch the corresponding full-quality original documents/images from the in-memory store.

Generation:

The retrieved text and the most relevant image are passed to Gemini 1.5 Pro along with the original question.

Gemini uses this rich, multimodal context to generate a comprehensive and accurate answer.

📜 License
This project is licensed under the MIT License. See the LICENSE file for details.
