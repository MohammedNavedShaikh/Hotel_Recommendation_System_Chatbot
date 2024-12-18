# Hotel Recommendation System Chatbot

## Overview

The **Hotel Recommendation System Chatbot** is a Streamlit-based web application that combines **Artificial Intelligence and Machine Learning** technologies, such as **LangChain**, **GroQ**, and **Google Generative AI**, to provide personalized hotel recommendations from a dataset of hotels in India. 

The chatbot answers user queries by leveraging **Retrieval-Augmented Generation (RAG)**, which enables it to retrieve relevant contextual data from a **vector database** and use a **Large Language Model (LLM)** for natural language understanding and response generation.

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

### 5. Set up the hotel dataset
The system processes hotel data from a PDF file located in the hotel_dataset/ directory. Ensure the file Locations.pdf containing hotel data is available in the specified location.

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

## Example Use Cases

- **Query**: "Recommend a hotel in Pune with swimming pool"
- **Response**: The chatbot will return a list of hotels located in Pune that have swimming pools, based on the document context.

![Hotel_Recommendation_System_Chatbot](https://github.com/user-attachments/assets/5357373e-8ef1-4591-92ac-37f71427f1d2)


## Support
If you encounter any issues while setting up or using the Hotel Recommendation System Chatbot, feel free to reach out for assistance.
- **Contact**: Mohammed Naved Shaikh
- **Email**: naveds1049@gmail.com

We are here to help with any queries, bugs, or feature requests!
