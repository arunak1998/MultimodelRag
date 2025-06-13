# Multimodal RAG with Unstructured and AstraDB


This repository contains code for building a **Multimodal Retrieval-Aided Generation (RAG)** system. It utilizes **Unstructured** for document parsing and **AstraDB** for vector storage, allowing you to efficiently process and retrieve information from  **text and images and tabels** within PDF documents.

## Features

- **PDF Partitioning**: Uses Unstructured to extract and structure text, tables, and images from PDF documents.
- **Multimodal Data Handling**: Designed to extract both textual content and table content and image payloads (base64 encoded) from PDFs.
- **Intelligent Chunking**: Leverages Unstructured's advanced strategies (like `by_title` and `max_characters`) to create semantically coherent document chunks.
- **Vector Database Integration**: Stores vector embeddings of text chunks and image summaries in AstraDB for efficient similarity search and retrieval.

## Strategy

The implemented RAG pipeline follows these steps:

1. **Image Summarization**: A multimodal LLM converts extracted images into rich text summaries.

2. **Table Summarization**: Extracted tables are parsed and summarized into a clear, condensed text format.

3. **Multimodal Embedding & Retrieval**: Both text chunks, image summaries, and table summaries are embedded and stored in separate collections for efficient similarity search.

4. **Answer Generation**: The retrieved text, images, and table content are fed into a multimodal LLM to generate comprehensive answers.

## Setup

1️⃣ **Clone the Repository**
```bash
git clone https://github.com/theserenecoder/MultiModel_RAG](https://github.com/arunak1998/multimodelrag
```

2️⃣ **Create a Virtual Environment**
```bash
conda create -n myenv python=3.12
conda activate myenv
```

3️⃣ **Install Python Dependencies**
```bash
pip install -r requirements.txt
```

Usage

1️⃣ Put your PDF documents (e.g., DietaryGuideliness.pdf) into the ./content/ directory.
2️⃣ Run the Jupyter notebook rag_multimodel.ipynb to execute the pipeline and view results.
