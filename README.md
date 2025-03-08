# PDF-Chatbot-with-RAG (Retriever-Augmented Generation using Langchain)
This project creates a Retriever-Augmented Generation (RAG) based chatbot, allowing users to interact with PDF files. The chatbot answers questions based on the content of the PDFs, and the backend uses Langchain to implement the RAG methodology. FAISS is used for vector-based search and retrieval, and SpacyEmbeddings is utilized for embedding the text data.

Features
Upload multiple PDF files and process them into searchable text.
Ask questions about the content of the uploaded PDFs.
The system uses Retriever-Augmented Generation (RAG) to retrieve relevant text and generate answers based on the provided context.
Utilizes FAISS for efficient similarity search and storage of text vectors.
SpacyEmbeddings is used for embedding textual data.
ChatOpenAI (GPT-3.5) is used to generate detailed responses based on the retrieved information.
Requirements
To run this project locally, you’ll need Python 3.7 or higher and the following libraries:

Required Libraries:
streamlit: For building the web app interface.
PyPDF2: For reading and extracting text from PDF files.
langchain: For implementing the RAG methodology and connecting LLMs with external tools.
langchain_community: For FAISS and Spacy embeddings.
faiss-cpu: For similarity search (CPU version).
spacy: For natural language processing and embeddings.
langchain_anthropic: For integrating Anthropic LLMs (optional based on your setup).
openai: For interacting with OpenAI's API (GPT-3.5 model).
dotenv: For environment variable management (used for API keys).
You can install the required libraries via the requirements.txt file.

Setup Instructions
1. Clone the repository
Clone the repository to your local machine:

bash
Copy
git clone https://github.com/your-username/PDF-Chatbot-with-RAG.git
cd PDF-Chatbot-with-RAG
2. Install dependencies
Create a virtual environment (optional but recommended) and install all dependencies:

bash
Copy
pip install -r requirements.txt
3. Setup environment variables
Create a .env file in the root directory of the project and add your OpenAI API key and any other necessary environment variables:

bash
Copy
OPENAI_API_KEY=your-openai-api-key
Note: If you're using any other language models or services (e.g., Anthropic), make sure to set the appropriate environment variables.

4. Install Spacy Model
Install the spacy language model used for embeddings:

bash
Copy
python -m spacy download en_core_web_sm
5. Run the app
Once everything is set up, you can run the app using the following command:

bash
Copy
streamlit run app.py
Usage
1. Upload PDF Files
On the sidebar, use the file uploader to upload one or more PDF files. After uploading, click on the "Submit & Process" button. This will extract text from the PDFs, split it into manageable chunks, and store it in the FAISS vector store.

2. Ask Questions
Once the PDFs are processed, you can ask questions related to their content. Type your question in the "Ask a Question from the PDF Files" text input box. The chatbot will search the vector store for relevant content and provide an answer based on the extracted text.

3. Conversational History
The system maintains conversational context, so you can have multiple interactions, and the model will keep track of the conversation and provide answers accordingly.

Workflow Overview
PDF Text Extraction:

When PDFs are uploaded, the text is extracted using the PyPDF2 library.
Text Chunking:

The extracted text is split into smaller chunks using the RecursiveCharacterTextSplitter to ensure efficient processing and retrieval.
Vector Store Creation:

The chunks are embedded into vectors using SpacyEmbeddings, and then stored in a FAISS vector store.
Question Processing:

When a user asks a question, the system retrieves the most relevant text chunks from the FAISS vector store.
These text chunks are passed to a ChatOpenAI model (GPT-3.5) to generate a detailed response.
File Structure
plaintext
Copy
.
├── app.py                    # Main Streamlit app to run the web interface
├── requirements.txt           # List of required dependencies for the project
├── .env                       # Environment configuration file for API keys
├── README.md                  # Project documentation
└── faiss_db                   # FAISS vector store (generated after processing PDFs)
Troubleshooting
Invalid API key: If the OpenAI API key is not set or is invalid, the model will not work. Ensure that the .env file contains the correct key.

FAISS vector store loading issue: If there are issues loading the FAISS vector store, try deleting the faiss_db directory and reprocessing the PDFs.

Missing dependencies: If any libraries are missing or causing errors, ensure you’ve installed all the dependencies from the requirements.txt file.

Contributing
Feel free to submit issues, suggestions, or pull requests. Contributions are welcome! If you’d like to add new features or improve the existing ones, open an issue or create a pull request for review.
