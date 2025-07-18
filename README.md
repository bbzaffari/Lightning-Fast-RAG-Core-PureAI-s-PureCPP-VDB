# Chunking and Embedding Pipeline with PureCPP Bindings

This notebook demonstrates how to use the `purecpp_*_dev` Python bindings, which are built with PyBind11 over C++ code, to scrape web pages, split them into text chunks, generate embeddings, and run similarity searches. 

[https://colab.research.google.com/github/bbzaffari/Lightning-Fast-RAG-Core-PureAI-s-PureCPP-VDB/blob/main/chunk_VDB.ipynb](https://colab.research.google.com/github/bbzaffari/Lightning-Fast-RAG-Core-PureAI-s-PureCPP-VDB/blob/main/chunk_VDB.ipynb)

### What it does

- Uses `WebLoader` to scrape a page (tested with ESPN).
- Splits the text into overlapping chunks using `ChunkDefault`.
- Generates embeddings with different models:
  - `text-embedding-ada-002`
  - `text-embedding-3-small`
  - `text-embedding-3-large`
- Stores flattened embeddings in a contiguous vector for efficient querying.
- Runs similarity search queries (cosine, inner product, L2) on the embedded data using methods like `PureCosine` and `PureIP`.

### Key components

- **WebLoader:** simple page loader.
- **ChunkDefault:** configurable chunker with multithreading.
- **VDBdata:** flattened embeddings container with metadata.
- **ChunkQuery:** search adapter over the vector database.

### Why it's interesting

This project is part of a personal exploration into building lightweight RAG (Retrieval-Augmented Generation) pipelines, focusing on performance, minimal memory overhead, and clean integration between Python and C++.

It also serves as a sandbox for testing different embedding providers (OpenAI, Cohere, HuggingFace) and analyzing their performance over real-world text data.

### Notes

The code is work in progress, meant for experimentation. Some modules (like those with `*_dev` suffixes) are in active development.
[Deep ](https://github.com/bbzaffari/Open-Source-RAG-Engine-System-with-Modular-Vector-Processing)
