# PDF-Chatbot-with-RAG (Retriever-Augmented Generation using Langchain)

This project creates a **Retriever-Augmented Generation (RAG)** based chatbot, allowing users to interact with PDF files. The chatbot answers questions based on the content of the PDFs, and the backend uses **Langchain** to implement the RAG methodology. **FAISS** is used for vector-based search and retrieval, and **SpacyEmbeddings** is utilized for embedding the text data.

---

## Features

- **Upload multiple PDF files** and process them into searchable text.
- **Ask questions** about the content of the uploaded PDFs.
- Uses **Retriever-Augmented Generation (RAG)** to retrieve relevant text and generate answers.
- **FAISS** for efficient similarity search and storage of text vectors.
- **SpacyEmbeddings** for text embedding.
- **ChatOpenAI (GPT-3.5)** to generate detailed responses based on the extracted content.

---

## Requirements

### Python Version

- Python 3.7 or higher.

### Required Libraries

To run this project locally, you’ll need the following libraries:

- `streamlit`: For building the web app interface.
- `PyPDF2`: For reading and extracting text from PDF files.
- `langchain`: For implementing the RAG methodology and connecting LLMs with external tools.
- `langchain_community`: For FAISS and Spacy embeddings.
- `faiss-cpu`: For similarity search (CPU version).
- `spacy`: For natural language processing and embeddings.
- `langchain_anthropic`: For integrating Anthropic LLMs (optional based on your setup).
- `openai`: For interacting with OpenAI's API (GPT-3.5 model).
- `dotenv`: For environment variable management (used for API keys).

You can install the required libraries via the `requirements.txt` file.

---

Enjoy building your PDF Chatbot with RAG powered by Langchain!

