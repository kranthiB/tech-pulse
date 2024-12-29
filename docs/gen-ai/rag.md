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
          * [4. Query Transformations](#4-query-transformations)
          * [5. Hypothetical Document Embedding (HyDE)](#5-hypothetical-document-embedding-hyde)
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

##### 4. Query Transformations

Retrieval-Augmented Generation (RAG) systems often encounter challenges when handling complex or ambiguous queries, leading to suboptimal retrieval of relevant information. Query transformation techniques address these challenges by reformulating or expanding queries to improve the match with relevant documents and retrieve more comprehensive information. Here are three key techniques used to enhance the retrieval process:

###### Techniques

- **Query Rewriting**: Reformulates the original query to make it more specific and detailed, improving the alignment with relevant documents.
- **Step-back Prompting**: Broadens the query context by generating higher-level or more generalized prompts to capture broader information.
- **Sub-query Decomposition**: Breaks down complex or multifaceted queries into simpler, more manageable sub-queries, facilitating targeted retrieval.

###### Benefits of these Techniques

- **Improved Relevance**: Query rewriting helps in retrieving more specific and relevant information.
- **Better Context**: Step-back prompting allows for retrieval of broader context and background information.
- **Comprehensive Results**: Sub-query decomposition enables retrieval of information that covers different aspects of a complex query.
- **Flexibility**: Each technique can be used independently or in combination, depending on the specific use case.

-----

##### 5. Hypothetical Document Embedding (HyDE)

Traditional retrieval methods often face challenges in bridging the semantic gap between brief queries and longer, more detailed documents. Hypothetical Document Embedding (HyDE) tackles this issue by transforming the query into a full hypothetical document, improving retrieval relevance by aligning the query's representation more closely with document representations in the vector space.

###### Key Components

- **PDF Processing and Text Chunking**: Efficiently processes documents by extracting and segmenting text into manageable chunks for analysis.
- **Vector Store Creation**: Utilizes advanced techniques like FAISS and OpenAI embeddings to encode documents and hypothetical queries into a shared vector space for similarity-based retrieval.
- **Language Model for Hypothetical Document Generation**: Leverages a language model to generate detailed hypothetical documents that enrich the query representation.

###### Benefits of this Approach

- **Improved Relevance**: By expanding queries into comprehensive documents, HyDE captures more nuanced and relevant matches within the dataset.
- **Handling Complex Queries**: Particularly beneficial for queries that are multi-faceted or difficult to match directly, enabling more precise retrieval.
- **Adaptability**: Supports a wide range of query types and document domains, making it flexible for various applications.
- **Potential for Better Context Understanding**: Expanded queries provide a richer representation of the context and intent, improving the overall retrieval quality.

![AHDE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0003-A-HDE.png)

![BHDE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0003-B-HDE.png)

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
