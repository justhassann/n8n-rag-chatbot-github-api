# Chat with GitHub API Documentation using RAG

[cite_start]This workflow demonstrates how to build a Retrieval-Augmented Generation (RAG) chatbot using n8n. [cite: 141] The chatbot is specifically designed to answer questions about the GitHub API by leveraging its OpenAPI specification. [cite_start]It uses OpenAI for generating embeddings and responses, and Pinecone as the vector database. [cite: 142]

## Overview

This project is divided into two main parts:
1.  [cite_start]**Indexing:** Extracts the GitHub OpenAPI specification, chunks it into smaller pieces, generates vector embeddings using OpenAI, and stores them in a Pinecone vector database[cite: 139].
2.  **Querying and Response Generation:** Provides a chat interface where a user can ask questions. [cite_start]An AI agent queries the Pinecone database for relevant context and uses an LLM (GPT-4o-mini) to generate an accurate answer based on that context[cite: 140].

## Features

* [cite_start]**Data Ingestion:** Fetches the latest GitHub API OpenAPI V3 specification directly from the official GitHub repository[cite: 137, 139].
* **Vectorization:** Uses OpenAI's embedding models to convert the documentation into vector representations.
* **Vector Storage:** Stores and indexes the document chunks in Pinecone for efficient similarity search.
* [cite_start]**RAG-Powered Agent:** Utilizes an AI Agent equipped with a `Vector Store Tool` to retrieve relevant information from the documentation before answering a question[cite: 138].
* **Interactive Chat:** Deploys a chat trigger that allows users to interact with the assistant in real-time.

## Technologies Used

* n8n
* [cite_start]OpenAI (Embeddings and `gpt-4o-mini` LLM) [cite: 142]
* [cite_start]Pinecone (Vector Database) [cite: 142]

## Setup & Configuration

Before you begin, ensure you have the following:
* An OpenAI account and API key.
* A Pinecone account and API key.
* A Pinecone index created. This workflow uses an index named `"n8n-demo"`. You can change this in the `Pinecone Vector Store` nodes.
* Add your OpenAI and Pinecone credentials to your n8n instance.

## How to Use

1.  **Index the Documentation:**
    * Open the workflow in n8n.
    * Run the workflow starting from the `When clicking ‘Test workflow’` node. This will fetch the GitHub API spec, process it, and populate your Pinecone index. This only needs to be done once, or whenever you want to update the knowledge base.

2.  **Chat with the Assistant:**
    * Activate the workflow.
    * Use the chat interface provided by the `When chat message received` trigger.
    * Ask questions about the GitHub API, for example, "How do I list repositories for a user?" or "What are the parameters for creating an issue?".

[Book a chat with me😁](https://cal.com/closegem/coffee-chat)
