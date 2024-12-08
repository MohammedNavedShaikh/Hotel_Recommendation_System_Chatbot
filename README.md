# Hotel Recommendation System Chatbot

## Overview

The **Hotel Recommendation System Chatbot** is a Streamlit-based web application that utilizes **LangChain**, **GroQ**, and **Google Generative AI** to provide hotel recommendations from a dataset of hotels in India. The chatbot answers questions based on the content extracted from PDF documents containing hotel information. 

It uses **vector embeddings** to generate a similarity search mechanism to match the user's query with relevant documents, providing context-based recommendations. The system leverages **FAISS** for vector-based retrieval, **GoogleGenerativeAIEmbeddings** for document embeddings, and **GroQ** for natural language understanding.

## Technologies Used

- **Streamlit**: For building the interactive web interface.
- **LangChain**: For managing language model pipelines and document processing.
- **GroQ**: For executing the language model and understanding queries.
- **FAISS**: For fast similarity search based on vector embeddings.
- **Google Generative AI**: For generating embeddings.
- **PyPDF2**: For reading and processing PDF documents containing hotel data.
- **dotenv**: For managing environment variables.

## Features

- **Hotel Querying**: Users can input queries, and the chatbot will return relevant hotel recommendations based on the provided context (e.g., location, facilities).
- **Document Embedding**: The system extracts text from PDFs, splits it into chunks, and generates vector embeddings for efficient search.
- **Document Similarity Search**: The system searches for relevant documents using vector embeddings and returns the most relevant information.
- **Interactive UI**: Built using Streamlit, allowing users to enter their queries and interact with the chatbot.

## Installation

Follow the steps below to set up the project locally:

### Prerequisites

- Python 3.8+
- Google Cloud API key (for Google Generative AI)
- GroQ API key (for Llama model inference)
- Streamlit for the web interface

### 1. Clone the repository
```bash
git clone https://github.com/MohammedNavedShaikh/Hotel_Recommendation_System_Chatbot.git
cd Hotel_Recommendation_System_Chatbot
```

### 2. Set up a virtual environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install dependencies
Install the required packages from requirements.txt:
```bash
pip install -r requirements.txt
```

### 4. Set up environment variables
Create a .env file in the root directory of the project and add the following keys:
```bash
GOOGLE_API_KEY="YOUR-GOOGLE-API-KEY"
GROQ_API_KEY="YOUR-GROQ-API-KEY"
```

### 5. Set up the US Census PDF
The system processes hotel data from a PDF file located in the us_census/ directory. Ensure the file location.pdf containing hotel data is available in the specified location.

### 6. Run the Streamlit app
Start the application using Streamlit:
```bash
streamlit run app.py
```

## How It Works

- **Document Embedding**: The system loads PDF documents containing hotel information and processes them using PyPDF2. The documents are split into chunks using the RecursiveCharacterTextSplitter, and embeddings are generated using the GoogleGenerativeAIEmbeddings.
- **Vector Store**: The embeddings are stored in a FAISS vector store for efficient search.
- **User Query**: Users can input a question in the provided text input box. The question is processed using the ChatGroq model and compared with the relevant documents stored in the vector store.
- **Response**: The chatbot provides the most accurate response based on the context and the user's query. The system displays both the final answer and the relevant chunks from the documents that were used to generate the answer.
- **Document Similarity Search**: Users can view the most similar documents that contributed to the answer using the "Document Similarity Search" expander.

## Example Use Cases

- **Query**: "Hotels in Pune with a swimming pool"
- **Response**: The chatbot will return a list of hotels located in Pune that have swimming pools, based on the document context.

## Requirements
```bash
faiss-cpu
groq
langchain-groq
PyPDF2
langchain_google_genai
langchain
streamlit
langchain_community
python-dotenv
pypdf
google-cloud-aiplatform>=1.38
```

## Support
If you encounter any issues while setting up or using the Hotel Recommendation System Chatbot, feel free to reach out for assistance.
- **Contact**: Mohammed Naved Shaikh
- **Email**: naveds1049@gmail.com

We are here to help with any queries, bugs, or feature requests!
