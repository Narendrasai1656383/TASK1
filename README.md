# TASK1
Task 1: Chat with PDF Using RAG Pipeline
Overview
The goal is to implement a Retrieval-Augmented Generation (RAG) pipeline that allows users to interact with semi-structured data in multiple PDF files. The system extracts, chunks, embeds, and stores the data for efficient retrieval. Users can query the PDFs to extract specific information or perform comparisons, with answers generated using a Large Language Model (LLM).

Functional Requirements
Data Ingestion

Input: PDF files containing semi-structured data.
Process:
Extract text and relevant structured data from PDF files.
Split text into logical chunks for better granularity.
Convert the chunks into vector embeddings using a pre-trained embedding model.
Store embeddings in a vector database for efficient retrieval.
Query Handling

Input: User's natural language question.
Process:
Convert the user's query into embeddings.
Perform similarity search in the vector database to retrieve the most relevant chunks.
Use the retrieved chunks with the LLM to generate an accurate response.
Comparison Queries

Input: User's query requiring comparisons.
Process:
Identify relevant terms or fields for comparison across PDF files.
Retrieve and aggregate chunks for comparison.
Generate structured responses in tabular or bullet-point format.
Response Generation

Input: Retrieved chunks and user query.
Process:
Use the LLM to generate fact-based responses with direct integration of retrieved data.
Example Data
Source PDF: Tables, Charts, and Graphs PDF
Tasks:

From Page 2, extract unemployment information based on the type of degree.
From Page 6, extract tabular data accurately.
Technology Stack
Libraries/Tools:
PyMuPDF (fitz) / pdfplumber (PDF extraction)
FAISS (Vector database)
Sentence Transformers (Embedding model)
Selected LLM for response generation
How to Run
Install dependencies:
bash
Copy code
pip install pdfplumber sentence-transformers faiss-cpu pymupdf
Place your PDFs in the working directory.
Run the script to process PDFs, perform queries, and test outputs.
Example query: "What is the unemployment rate for Bachelor's degree holders?"
Output
Query-specific responses with extracted data.
Comparison results for comparison-type queries.
