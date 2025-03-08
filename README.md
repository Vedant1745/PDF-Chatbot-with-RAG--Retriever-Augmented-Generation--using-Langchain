PDF-Chatbot-with-RAG (Retriever-Augmented Generation) using Langchain
This project allows users to interact with a chatbot that answers questions based on the content of PDF documents. It leverages Retriever-Augmented Generation (RAG) to provide detailed answers from a set of uploaded PDF files. The backend uses Langchain, a popular library for building advanced language models with external tools, and FAISS (Facebook AI Similarity Search) for vector-based search and retrieval.

Features
Upload multiple PDF files and process them into searchable text.
Ask questions related to the content of the uploaded PDFs.
The system uses Langchain's Retriever-Augmented Generation (RAG) method to find relevant information from PDFs and generate answers.
Uses FAISS for vector store and similarity search to efficiently retrieve chunks of text from the PDFs.
SpacyEmbeddings is used to embed the text data for FAISS storage.
Supports ChatOpenAI (GPT-3.5) to generate responses based on the extracted content.
Requirements
Python 3.7 or higher.
Install the necessary dependencies by running the following command:
bash
Copy
pip install -r requirements.txt
Required Libraries:
Streamlit: For building the web app interface.
PyPDF2: For extracting text from PDF files.
Langchain: For building the chatbot and retrieval system.
SpacyEmbeddings: For embedding text data.
FAISS: For fast similarity search.
dotenv: For environment variable management.
langchain_anthropic: For Anthropic models.
OpenAI: For GPT-3.5 integration (ChatOpenAI).
langchain_community: For embeddings and vector stores.
Make sure to have a valid OpenAI API key or appropriate environment variables set up to use the LLM.

Setup Instructions
Clone the repository:

bash
Copy
git clone https://github.com/your-username/PDF-Chatbot-with-RAG.git
cd PDF-Chatbot-with-RAG
Install dependencies:

bash
Copy
pip install -r requirements.txt
Create a .env file and add the following to configure the OpenAI API key (or any other required environment variables):

env
Copy
OPENAI_API_KEY=your-api-key
Make sure you have the Spacy model installed:

bash
Copy
python -m spacy download en_core_web_sm
Run the app:

bash
Copy
streamlit run app.py
Usage
Upload PDFs: Use the file uploader on the sidebar to upload your PDF files.

Process PDFs: Once you have uploaded the PDF files, click on the "Submit & Process" button. This will extract text from the PDFs, split it into chunks, and create a vector store to store the embedded text.

Ask Questions: Once the PDFs are processed, type a question related to the content of the uploaded PDFs in the input box at the top. The chatbot will search the processed content and provide an answer.

Conversational History: The chatbot remembers your questions and interactions, ensuring you can have a dynamic conversation with the bot based on the document content.

Workflow
PDF Reading: The uploaded PDFs are read and their content is extracted using the PyPDF2 library.

Text Chunking: The extracted text is split into smaller chunks using the RecursiveCharacterTextSplitter to enable more efficient processing.

Vector Store Creation: The text chunks are embedded using SpacyEmbeddings, and stored in a FAISS vector store.

Retrieval and Generation: When a user asks a question, the system retrieves relevant text chunks using FAISS and passes them to a ChatOpenAI model (GPT-3.5) to generate an answer.

File Structure
plaintext
Copy
.
├── app.py                    # Main Streamlit app
├── requirements.txt           # List of dependencies
├── .env                       # Configuration file for API keys
└── README.md                  # Project documentation
Troubleshooting
Invalid API key: Ensure your OpenAI API key is set correctly in the .env file.
FAISS vector store loading issue: If you face issues with the FAISS vector store, try deleting the faiss_db directory and reprocessing the PDFs.
Contributing
Feel free to submit issues or pull requests to improve the functionality of this project. Contributions are welcome!
