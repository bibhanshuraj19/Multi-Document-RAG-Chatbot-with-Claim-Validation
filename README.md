# 📚 DocuChat AI - Multi-Document RAG Chatbot

A beautiful, modern chatbot application that allows you to upload PDF documents and chat with them using Nebius AI. Built with Next.js frontend and FastAPI backend.

![DocuChat AI](https://img.shields.io/badge/Powered%20by-Nebius%20AI-blue)
![Next.js](https://img.shields.io/badge/Frontend-Next.js-black)
![FastAPI](https://img.shields.io/badge/Backend-FastAPI-green)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue)

## ✨ Features

- **📄 Multi-Document Support**: Upload multiple PDFs, DOCX, TXT, and MD files
- **📁 Folder Upload**: Process entire folders of documents at once
- **💬 Intelligent Chat**: Ask questions and get accurate answers with source citations
- **🔍 Semantic Search**: Find relevant information using advanced embeddings
- **📊 Document Statistics**: Track your indexed documents and chunks
- **🎨 Beautiful UI**: Modern, dark-themed interface with smooth animations
- **⚡ Real-time Responses**: Fast, streaming-like chat experience

## 🛠️ Tech Stack

### Frontend
- **Next.js 14** - React framework
- **TypeScript** - Type safety
- **Tailwind CSS** - Styling
- **Framer Motion** - Animations
- **Lucide React** - Icons
- **React Dropzone** - File uploads

### Backend
- **FastAPI** - Python API framework
- **Nebius AI** - LLM (openai/gpt-oss-20b) & Embeddings (BAAI/bge-en-icl)
- **ChromaDB** - Vector database
- **LangChain** - Document processing

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ and npm
- Python 3.9+
- Nebius API key

### Installation

1. **Clone or navigate to the project directory:**
   ```bash
   cd "Multi-Document RAG Chatbot with Claim Validation"
   ```

2. **Set up the Backend:**
   ```bash
   # Create virtual environment
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   
   # Install dependencies
   pip install -r backend/requirements.txt
   
   # Create .env file with your API key
   echo "NEBIUS_API_KEY=your_api_key_here" > .env
   ```

3. **Set up the Frontend:**
   ```bash
   cd frontend
   npm install
   ```

### Running the Application

1. **Start the Backend** (from project root):
   ```bash
   source venv/bin/activate  # If not already activated
   python backend/main.py
   ```
   Backend runs at `http://localhost:8000`

2. **Start the Frontend** (in a new terminal):
   ```bash
   cd frontend
   npm run dev
   ```
   Frontend runs at `http://localhost:3000`

3. **Open your browser** to `http://localhost:3000`

## 📖 How to Use

### Uploading Documents

1. **Drag & Drop**: Drag files directly onto the upload zone in the sidebar
2. **Click to Upload**: Click the upload zone to select files
3. **Folder Upload**: Enter a folder path and click the upload button

### Chatting with Documents

1. Once documents are uploaded, they're automatically indexed
2. Type your question in the chat input at the bottom
3. Press Enter or click the send button
4. The AI will search through your documents and provide relevant answers
5. Click on sources to see which documents were used

### Managing Documents

- **View Documents**: See all indexed documents in the sidebar
- **Delete Document**: Hover over a document and click the X to remove it
- **Clear Chat**: Remove conversation history
- **Clear All**: Remove all indexed documents and start fresh

## 📁 Project Structure

```
Multi-Document RAG Chatbot with Claim Validation/
├── backend/
│   ├── main.py              # FastAPI application
│   └── requirements.txt     # Python dependencies
├── frontend/
│   ├── src/
│   │   ├── pages/
│   │   │   ├── index.tsx    # Main chat page
│   │   │   ├── _app.tsx     # App wrapper
│   │   │   └── _document.tsx
│   │   ├── styles/
│   │   │   └── globals.css  # Global styles
│   │   └── lib/
│   │       └── utils.ts     # Utilities & types
│   ├── public/
│   ├── package.json
│   ├── tailwind.config.ts
│   └── tsconfig.json
├── src/
│   ├── __init__.py
│   ├── document_processor.py  # Document loading
│   ├── embedding_service.py   # Nebius embeddings
│   ├── vector_store.py        # ChromaDB storage
│   └── chatbot.py             # RAG logic
├── config.py                  # Configuration
├── env.example               # Environment template
└── README.md
```

## ⚙️ Configuration

Edit the `.env` file in the project root:

| Variable | Description | Default |
|----------|-------------|---------|
| `NEBIUS_API_KEY` | Your Nebius API key | Required |
| `LLM_MODEL` | LLM model to use | `openai/gpt-oss-20b` |
| `EMBEDDING_MODEL` | Embedding model | `BAAI/bge-en-icl` |
| `CHUNK_SIZE` | Size of document chunks | `1000` |
| `CHUNK_OVERLAP` | Overlap between chunks | `200` |
| `TOP_K_RETRIEVAL` | Number of chunks to retrieve | `5` |

## 🔧 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/health` | Health check |
| POST | `/api/chat` | Send a chat message |
| POST | `/api/upload` | Upload files |
| POST | `/api/upload-folder` | Process a folder |
| GET | `/api/stats` | Get document statistics |
| POST | `/api/clear-chat` | Clear chat history |
| POST | `/api/clear-all` | Clear all data |
| DELETE | `/api/document/{source}` | Delete a document |

## 🎨 Screenshots

The application features a beautiful dark theme with:
- Gradient accents (cyan to blue)
- Smooth Framer Motion animations
- Responsive sidebar design
- Source citation cards with relevance scores
- Real-time typing indicators

## 🤝 Contributing

Feel free to open issues or submit pull requests for improvements!

## 📄 License

MIT License - feel free to use this project for your own purposes.

---

Built with ❤️ using Nebius AI, Next.js, and FastAPI
