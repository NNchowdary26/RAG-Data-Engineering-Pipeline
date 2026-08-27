# RAG-Data-Engineering-Pipeline
An end-to-end RAG data engineering pipeline for document ingestion, validation, preprocessing, chunking, embeddings, vector indexing, incremental processing, and semantic retrieval.

# Project Overview
This project demonstrates how to build a production-oriented data pipeline for Retrieval-Augmented Generation (RAG) systems. Instead of treating RAG as only an LLM application, this project focuses on the data engineering layer responsible for transforming raw documents into high-quality, searchable vector data. The pipeline supports PDF, TXT, and Markdown documents and implements document validation, text cleaning, SHA-256 based change detection, chunk generation, embedding creation, FAISS vector indexing, metadata management, and semantic retrieval.

# Architecture
                         DOCUMENT SOURCES
                                |
                    +-----------+-----------+
                    |                       |
                   PDF                  TXT / MD
                    |                       |
                    +-----------+-----------+
                                |
                                v
                       DOCUMENT INGESTION
                                |
                                v
                       DATA VALIDATION
                                |
                                v
                        TEXT CLEANING
                                |
                                v
                       DOCUMENT HASHING
                                |
                    +-----------+-----------+
                    |                       |
              NEW / MODIFIED           UNCHANGED
                    |                       |
                    v                       X
                 CHUNKING
                    |
                    v
                EMBEDDINGS
                    |
                    v
              FAISS VECTOR DB
                    |
                    v
              SEMANTIC RETRIEVAL
                    |
                    v
                    LLM
                    |
                    v
                RAG RESPONSE

# Key Features
 - PDF, TXT, and Markdown document ingestion
 - Automated document validation
 - Text preprocessing and cleaning
 - SHA-256 document hashing
 - New and modified document detection
 - Incremental document processing
 - Overlapping text chunking
 - Sentence Transformer embeddings
 - FAISS vector indexing
 - Metadata management
 - Semantic similarity search
 - Source and page-level retrieval
 - Pipeline statistics and logging
 - Data quality metrics
 - LLM-powered RAG responses

# Technology Stack
| Category               | Technology                       |
| ---------------------- | -------------------------------- |
| Programming            | Python                           |
| Data Processing        | Pandas, NumPy                    |
| Distributed Processing | PySpark                          |
| Document Processing    | PyPDF                            |
| Embeddings             | Sentence Transformers            |
| Vector Database        | FAISS                            |
| LLM                    | OpenAI API                       |
| Data Storage           | Local / Cloud Storage compatible |
| Development            | Google Colab                     |
| Version Control        | Git / GitHub                     |

# Project Structure

rag-data-engineering/
|
├── README.md
|
├── notebooks/
|   └── rag_pipeline.ipynb
|
├── src/
|   ├── ingestion.py
|   ├── validation.py
|   ├── preprocessing.py
|   ├── chunking.py
|   ├── embeddings.py
|   ├── vector_store.py
|   └── retrieval.py
|
├── data/
|   ├── raw/
|   └── processed/
|
├── metadata/
|   └── document_catalog.json
|
├── vector_store/
|   ├── faiss.index
|   └── chunks.pkl
|
├── logs/
|   └── pipeline_report.json
|
├── tests/
|   ├── test_ingestion.py
|   ├── test_validation.py
|   └── test_chunking.py
|
└── requirements.txt
