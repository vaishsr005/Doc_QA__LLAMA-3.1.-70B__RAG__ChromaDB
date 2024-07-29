# Document-QA using: LLAMA-3.1.70B - RAG - ChromaDB

## Overview

The project involves creating a Retrieval-Augmented Generation (RAG) system utilizing Meta's Llama 3.1 70B model, integrated with ChromaDB as the vector store and LangChain. The Llama 3.1 model is loaded with Groq, demonstrating the use of the `Chroma` library to establish a document database. The integration leverages `LLAMA` language models for efficient document retrieval and question answering (QA). Additionally, the project employs HuggingFace embeddings and Groq models, enhancing the capabilities for processing and querying textual data.

## Features
- **Document Database Creation**: Utilizes `Chroma` to store and manage documents.
- **Embedding Generation**: Employs HuggingFace embeddings for transforming documents into vector representations.
- **Vector Database**: Constructs a vector database for efficient retrieval.
- **RetrievalQA Chain**: Implements a QA system using the `LLAMA` language model for answering queries based on document content.

## Project Structure
- **Load Data and Create Database**: Loads textual data, generates embeddings, and creates a document database.
- **Query Processing**: Uses a retrieval-based approach to process user queries and fetch relevant information from the document database.
- **Model Integration**: Integrates the `LLAMA` language model to provide sophisticated answers to user queries.

## How It Works
1. **Embeddings Creation**:
The project starts by generating embeddings for the input documents using the `HuggingFaceEmbeddings` class. These embeddings convert the textual data into a numerical format suitable for vector operations.

2. **Persisting Data**:
A directory named `doc_db` is created to persist the vectorized documents. This directory ensures that the embeddings and documents are stored and can be reused without recalculating embeddings each time.

3. **Vector Database Setup**:
The `Chroma` library is used to create a vector database from the document embeddings. This database supports efficient similarity searches and retrieval operations.

4. **Retriever Setup**:
A retriever is initialized from the vector database. The retriever is responsible for fetching relevant documents based on the similarity of the query embeddings.

5. **LLAMA Model Integration**:
The `LLAMA` language model, specifically the `ChatGroq` implementation, is integrated. The model is configured with the `llama-3.1-70b-versatile` model and a temperature setting of `0` to ensure deterministic responses.

6. **QA Chain Creation**:
- A QA chain is constructed using the `RetrievalQA` class. This chain combines the retriever and the language model to process user queries and return answers along with the source documents.

7. **Query Execution**:
- The QA chain is invoked with a sample query. The response includes the answer generated by the `LLAMA` model and the source document from which the information was retrieved.

