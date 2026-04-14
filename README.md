# Praktikum Wirtschaftsinformatik – Exercise Sheet 3
**Course:** Praktikum Wirtschaftsinformatik  
**Supervisor:** Prof. Dr. Mirjam Minor, M.Sc. Tolga Tel

## Overview
This exercise uses a RAG pipeline built with Haystack to automatically 
generate textual descriptions of BPMN process models using a local LLM (LLaMA 3.1).

## Pipeline Structure
- **Document Store:** Embedded BPMN .txt files (InMemoryDocumentStore)
- **Embedder:** sentence-transformers/all-MiniLM-L6-v2
- **Retriever:** InMemoryEmbeddingRetriever
- **Prompt Builders:** Role Prompting, Few-Shot, Zero-Shot
- **Generator:** Ollama (LLaMA 3.1:8b, local)
- **Custom Component:** ResultMerger – merges outputs of all 3 generators

## Requirements
- Python 3.11+
- Haystack
- haystack-integrations (Ollama)
- Ollama running locally on port 11434

## How to Run
1. Start Ollama locally: `ollama run llama3.1:8b`
2. Place BPMN .txt files in the same directory
3. Run the notebook cell by cell