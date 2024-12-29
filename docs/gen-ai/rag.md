---
id: gen-ai/rag
title: Retrieval-Augmented Generation (RAG)
sidebar_label: Retrieval-Augmented Generation (RAG)
previous_page: gen-ai/llm-tier
next_page: gen-ai/ai-driven-software-development
---

Table of contents
=================

<!--ts-->
   * [Retrieval-Augmented Generation](#retrieval-augmented-generation-rag)
      * [RAG Techniques](#rag-techniques)
        * [Foundational RAG Techniques](#foundational-rag-techniques)
            * [1. Simple RAG for PDF and CSV Files](#1-simple-rag-for-pdf-and-csv-files)
            * [2. Reliable RAG](#2-reliable-rag)
            * [3. Propositions Chunking](#3-propositions-chunking)
        * [Query Enhancements](#query-enhancements)
        * [Context and Content Enrichment](#context-and-content-enrichment)
        * [Advanced Retrieval Methods](#advanced-retrieval-methods)
        * [Iterative and Adaptive Techniques](#iterative-and-adaptive-techniques)
        * [Evaluation](#evaluation)
        * [Explainability and Transparency](#explainability-and-transparency)
        * [Advanced Architectures](#advanced-architectures)
        * [Special Advanced Technique](#special-advanced-technique)
<!--te-->

## Retrieval-Augmented Generation (RAG)

Retrieval-Augmented Generation (RAG) is an advanced approach that combines the capabilities of information retrieval systems with generative AI models. By leveraging external knowledge sources during the generation process, RAG ensures the creation of accurate, contextually relevant, and up-to-date content. This hybrid methodology bridges the gap between static generative models and dynamic, information-rich environments, making it a powerful tool for applications requiring precise and reliable outputs.

-----

### RAG Techniques

#### Foundational RAG Techniques

##### 1. Simple RAG for PDF and CSV Files
A basic Retrieval-Augmented Generation (RAG) system processes and queries PDF/CSV documents by encoding their content into a vector store, which can then be queried to retrieve relevant information.

###### Key Components

- **PDF Processing and Text Extraction**: Efficiently extract text from PDF documents for further processing.
- **Loading and Splitting CSV Files**: Seamlessly load and handle CSV files, splitting them into manageable units for processing.
- **Text Chunking**: Divide document content into smaller, manageable chunks to ensure smooth processing and retrieval for PDF documents.
- **Vector Store Creation**: Use advanced similarity search techniques like FAISS and embeddings (e.g., OpenAI embeddings) to create an efficient vector store for storing and retrieving document content.
- **Retriever Setup**: Configure a retriever to enable querying of the processed documents for relevant information.
- **Evaluation of the RAG System**: Assess the system’s performance to ensure accurate and relevant retrieval of information.

-----

##### 2. Reliable-RAG
The "Reliable-RAG" method enhances the traditional Retrieval-Augmented Generation (RAG) approach by incorporating additional layers of validation and refinement to ensure the accuracy and reliability of retrieved information. Designed specifically for web-based documents, this system encodes content into a vector store and retrieves the most relevant segments, ensuring precise and dependable answers.

###### Key Components

- **Document Loading and Chunking**: Web-based documents are loaded and divided into smaller, manageable chunks to facilitate efficient vector encoding and retrieval.
- **Vector Store Creation**: Leverages advanced tools like Chroma and Cohere embeddings to encode document chunks into a vector store, enabling similarity-based retrieval.
- **Document Relevancy Check**: Implements a relevance-checking mechanism using a language model to filter out non-relevant documents before generating answers.
- **Answer Generation**: Uses a language model to produce concise and accurate answers based on the relevant documents retrieved.
- **Hallucination Detection**: Includes a dedicated step to identify and eliminate unsupported or erroneous information, ensuring that generated answers are grounded in the retrieved documents.
- **Document Snippet Highlighting**: Identifies and highlights the specific document segments directly used in generating the answer, providing transparency and traceability.

![REL](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0001-REL.png)

-----

##### 3. Propositions Chunking

Inspired by recent ([research from Tony Chen et al.](https://arxiv.org/abs/2312.06648)), the Propositions Chunking method enhances document processing by breaking input text into smaller, atomic units called propositions. These propositions are designed to be factual, self-contained, and concise, enabling efficient encoding into a vector store for future retrieval.

###### Key Components

- **Document Chunking**: Dividing the document into smaller sections to facilitate easier analysis and processing.
- **Proposition Generation**: Utilizing large language models (LLMs) to distill document chunks into concise, factual, and independent propositions.
- **Proposition Quality Check**: Assessing the generated propositions for their accuracy, clarity, completeness, and conciseness to ensure reliability.
- **Embedding and Vector Store**: Encoding both the refined propositions and larger document chunks into a vector store to support fast and efficient retrieval.
- **Retrieval and Comparison**: Conducting retrieval tests with various query sizes, comparing the results from proposition-based retrieval with those from larger chunk-based models to highlight the advantages of this approach.

![PRP](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0002-PRP.png)

-----

#### Query Enhancements

-----

#### Context and Content Enrichment

-----

#### Advanced Retrieval Methods

-----

#### Iterative and Adaptive Techniques

-----

#### Evaluation

-----

#### Explainability and Transparency

-----

#### Advanced Architectures

-----

#### Special Advanced Technique

-----
