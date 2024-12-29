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
          * [6. Contextual Chunk Headers (CCH)](#6-contextual-chunk-headers-cch)
          * [7. Relevant Segment Extraction (RSE)](#7-relevant-segment-extraction-rse)
          * [8. Context Enrichment Window for Document Retrieval](#8-context-enrichment-window-for-document-retrieval)
          * [9. Semantic Chunking for Document Processing](#9-semantic-chunking-for-document-processing)
          * [10. Contextual Compression in Document Retrieval](#10-contextual-compression-in-document-retrieval)
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

##### 6. Contextual Chunk Headers (CCH)

Retrieval-Augmented Generation (RAG) systems often struggle with insufficient context within individual chunks, leading to retrieval errors or hallucinations during the response generation process. Contextual Chunk Headers (CCH) address this by augmenting chunks with higher-level context, ensuring better retrieval accuracy and comprehension by the language model.

###### Problems Addressed by CCH

- **Implicit References**: Chunks may refer to their subject using pronouns or vague references, making them difficult to retrieve or interpret accurately.
- **Context Dependency**: Many chunks lack standalone meaning and can only be properly understood within the broader context of the section or document, leading to potential misinterpretation.

###### Key Components

- **Contextual Chunk Headers**: This method enhances chunks by prepending them with headers that encapsulate higher-level context. These headers might include:
  - The document title.
  - A concise summary of the document.
  - The hierarchical structure of section and sub-section titles.

###### Benefits of CCH

- **Improved Context Representation**: Provides a more complete representation of the content and meaning of the text.
- **Enhanced Retrieval Accuracy**: Makes it easier to retrieve relevant chunks even when implicit references are used.
- **Reduced Hallucinations**: Helps the language model understand chunks within the appropriate context, minimizing errors in generated responses.

![CCH](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0004-CCH.png)

-----

##### 7. Relevant Segment Extraction (RSE)

![RSE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0005-RSE.png)

-----

##### 8. Context Enrichment Window for Document Retrieval

![ACEW](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0006-A-CEW.png)

![BCEW](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0006-B-CEW.png)

-----

##### 9. Semantic Chunking for Document Processing

![SCD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0007-SCD.png)

-----

##### 10. Contextual Compression in Document Retrieval

![CCR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0008-CCR.png)

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
