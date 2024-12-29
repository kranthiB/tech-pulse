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
          * [11. Document Augmentation through Question Generation for Enhanced Retrieval](#11-document-augmentation-through-question-generation-for-enhanced-retrieval)
        * [Advanced Retrieval Methods](#advanced-retrieval-methods)
          * [12. Fusion Retrieval in Document Search](#12-fusion-retrieval-in-document-search)
          * [13. Intelligent Reranking](#13-intelligent-reranking)
          * [14. Hierarchical Indices in Document Retrieval](#14-hierarchical-indices-in-document-retrieval)
          * [15. Multi-modal Retrieval](#15-multi-modal-retrieval)
        * [Iterative and Adaptive Techniques](#iterative-and-adaptive-techniques)
          * [16. Retrieval with Feedback Loops](#16-retrieval-with-feedback-loops)
          * [17. Adaptive Retrieval](#17-adaptive-retrieval)
        * [Evaluation](#evaluation)
          * [18. DeepEval Evaluation](#18-deepeval-evaluation)
          * [19. GroUSE Evaluation](#19-grouse-evaluation)
        * [Explainability and Transparency](#explainability-and-transparency)
          * [20. Explainable Retrieval in Document Search](#20-explainable-retrieval-in-document-search)
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

When chunking documents for Retrieval-Augmented Generation (RAG), determining the optimal chunk size involves balancing tradeoffs. Larger chunks offer better context for the language model but can make precise retrieval more difficult, while smaller chunks enable precise retrieval but may lack sufficient context. Relevant Segment Extraction (RSE) provides a dynamic approach to address these challenges by reconstructing multi-chunk segments of contiguous text from retrieved chunks, ensuring the appropriate context is presented to the language model.

###### Challenges in Chunking

- **Context vs. Precision**: Large chunks are ideal for complex or high-level queries but may retrieve irrelevant information. Small chunks are precise but lack the broader context needed for more nuanced queries.
- **Query Diversity**: Real-world RAG use cases often involve a mix of queries, from simple fact-based questions to complex, multi-faceted inquiries that require extensive context.

###### Key Components

- **Chunk Text Key-Value Store**: RSE relies on a database to quickly retrieve chunk text using a `doc_id` and `chunk_index` as keys. This ensures that even chunks not initially marked as relevant can be included if they are sandwiched between highly relevant chunks.
- **Segment Reconstruction**: Rebuilds segments of contiguous text from nearby chunks, preserving their order in the original document. This step enhances the context provided to the language model.


![RSE](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0005-RSE.png)

-----

##### 8. Context Enrichment Window for Document Retrieval

Traditional vector search methods often retrieve isolated chunks of text, which can lack the necessary context for complete understanding. The Context Enrichment Window enhances the standard retrieval process by including surrounding context for each retrieved chunk, resulting in more coherent and comprehensive information.

###### Key Components

1. **PDF Processing and Text Chunking**: Extracts and segments text into manageable chunks for effective analysis and retrieval.
2. **Vector Store Creation**: Uses advanced techniques such as FAISS and OpenAI embeddings to encode and store document chunks in a shared vector space.
3. **Custom Retrieval Function with Context Window**: Adds a configurable context window to enrich the retrieved chunks with surrounding text, ensuring completeness and coherence.
4. **Comparison Between Standard and Context-Enriched Retrieval**: Evaluates the effectiveness of context-enriched retrieval against traditional methods, highlighting its advantages in providing richer information.

###### Benefits of this Approach

1. **Improved Coherence**: Delivers results that are more contextually connected and meaningful.
2. **Enhanced Utility of Vector Search**: Retains the benefits of vector-based retrieval while addressing its limitations of returning fragmented text.
3. **Flexible Context Adjustment**: Allows fine-tuning of the context window size to meet specific retrieval needs, enabling adaptability for different use cases.

![ACEW](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0006-A-CEW.png)

![BCEW](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0006-B-CEW.png)

-----

##### 9. Semantic Chunking for Document Processing

Traditional text splitting methods often divide documents at arbitrary points, disrupting the flow of information and context. Semantic chunking addresses this limitation by splitting text at natural breakpoints, preserving semantic coherence within each chunk.

###### Key Components

1. **PDF Processing and Text Extraction**: Extracts raw text from PDF documents for further analysis.
2. **Semantic Chunking**: Utilizes advanced techniques, such as LangChain's SemanticChunker, to create meaningful and contextually consistent text segments.
3. **Vector Store Creation**: Encodes the semantically coherent chunks into a vector store using tools like FAISS and OpenAI embeddings.
4. **Retriever Setup**: Configures a retriever to query the semantically processed documents effectively.

###### Benefits of this Approach

1. **Improved Coherence**: Ensures that each chunk contains complete ideas or thoughts, enhancing their standalone clarity.
2. **Better Retrieval Relevance**: Maintains context within chunks, improving the accuracy of information retrieval.
3. **Adaptability**: Allows for customization of chunking methods based on document characteristics and retrieval requirements.
4. **Enhanced Understanding**: Facilitates better performance of LLMs and downstream tasks by providing more coherent and meaningful text segments.

![SCD](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0007-SCD.png)

-----

##### 10. Contextual Compression in Document Retrieval

Traditional document retrieval systems often return entire chunks or documents, which may include irrelevant information. Contextual compression tackles this inefficiency by extracting and compressing only the most relevant portions of retrieved documents. This results in a more focused and streamlined retrieval process.

###### Key Components

1. **Vector Store Creation from a PDF Document**: Encodes document content into a vector store using advanced embedding techniques.
2. **Base Retriever Setup**: Configures the initial retriever to fetch relevant document chunks.
3. **LLM-Based Contextual Compressor**: Employs a language model to analyze and compress retrieved chunks, focusing on the most relevant information.
4. **Contextual Compression Retriever**: Integrates the compressor with the retriever for optimized query results.
5. **Question-Answering Chain**: Utilizes the compressed retriever in a question-answering pipeline to provide concise and accurate answers.

###### Benefits of this Approach

1. **Improved Relevance**: Delivers only the most pertinent information, reducing noise in the results.
2. **Increased Efficiency**: Minimizes the volume of text the LLM needs to process, enhancing system performance.
3. **Enhanced Context Understanding**: Leverages the contextual analysis capabilities of LLMs to extract precise information aligned with the query intent.
4. **Flexibility**: Easily adaptable to various document types and query requirements, ensuring versatility in application.

![CCR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0008-CCR.png)

-----

##### 11. Document Augmentation through Question Generation for Enhanced Retrieval

This technique enhances document retrieval within a vector database by generating additional questions related to each text fragment. By incorporating these questions, the system improves the standard retrieval process, increasing the likelihood of identifying relevant documents to serve as context for generative question answering.

###### Key Components

1. **PDF Processing and Text Chunking**: Processes PDF documents and divides them into manageable text fragments for efficient analysis.
2. **Question Augmentation**: Utilizes OpenAI's language models to generate relevant questions at both the document and fragment levels.
3. **Vector Store Creation**: Encodes documents and generated questions into a vector store using OpenAI's embedding model and FAISS for similarity search.
4. **Retrieval and Answer Generation**: Leverages FAISS to retrieve the most relevant documents and uses the provided context to generate accurate answers.

###### Benefits of This Approach

1. **Enhanced Retrieval Process**: Improves the probability of retrieving the most relevant documents from the vector store for a given query.
2. **Flexible Context Adjustment**: Supports dynamic adjustment of the context window size for both documents and individual fragments, catering to diverse query requirements.
3. **High-Quality Language Understanding**: Employs OpenAI's advanced language models for generating meaningful questions and producing precise answers, ensuring a robust retrieval mechanism.


-----

#### Advanced Retrieval Methods

##### 12. Fusion Retrieval in Document Search

Traditional retrieval methods often rely on either semantic understanding (vector-based) or keyword matching (BM25). Each approach has its strengths and weaknesses. Fusion retrieval aims to combine these methods to create a more robust and accurate retrieval system that can handle a wider range of queries effectively.

###### Key Components

1. **PDF Processing and Text Chunking**: Prepares documents for analysis by splitting them into manageable chunks.
2. **Vector Store Creation**: Utilizes FAISS and OpenAI embeddings to build a vector-based semantic retrieval system.
3. **BM25 Index Creation**: Implements a keyword-based retrieval system using the BM25 algorithm.
4. **Custom Fusion Retrieval Function**: Combines vector-based and keyword-based retrieval methods to enhance search capabilities.

###### Benefits of This Approach

1. **Improved Retrieval Quality**: By combining semantic and keyword-based search, the system can capture both conceptual similarity and exact keyword matches.
2. **Flexibility**: The α parameter allows for adjusting the balance between vector and keyword search based on specific use cases or query types.
3. **Robustness**: The combined approach can handle a wider range of queries effectively, mitigating weaknesses of individual methods.
4. **Customizability**: The system can be easily adapted to use different vector stores or keyword-based retrieval methods.

![FRR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0009-FRR.png)

-----

##### 13. Intelligent Reranking

The primary motivation for reranking in RAG systems is to overcome limitations of initial retrieval methods, which often rely on simpler similarity metrics. Reranking allows for more sophisticated relevance assessment, taking into account nuanced relationships between queries and documents that might be missed by traditional retrieval techniques. This process aims to enhance the overall performance of RAG systems by ensuring that the most relevant information is used in the generation phase.

#### Key Components

1. **Initial Retriever**: Often a vector store using embedding-based similarity search.
2. **Reranking Model**: This can be either:
    * A Large Language Model (LLM) for scoring relevance
    * A Cross-Encoder model specifically trained for relevance assessment
3. **Scoring Mechanism**: A method to assign relevance scores to documents
4. **Sorting and Selection Logic**: To reorder documents based on new scores

#### Benefits of this Approach

1. **Improved Relevance**: By using more sophisticated models, reranking can capture subtle relevance factors.
2. **Flexibility**: Different reranking methods can be applied based on specific needs and resources.
3. **Enhanced Context Quality**: Providing more relevant documents to the RAG system improves the quality of generated responses.
4. **Reduced Noise**: Reranking helps filter out less relevant information, focusing on the most pertinent content.

![AIRR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0010-A-IRR.png)

![BIRR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0010-B-IRR.png)

-----

##### 14. Hierarchical Indices in Document Retrieval

![AHIR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0011-A-HIR.png)

![BHIR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0011-B-HIR.png)

-----

##### 15. Multi-modal Retrieval

![MMR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0012-MMR.png)

-----

#### Iterative and Adaptive Techniques

##### 16. Retrieval with Feedback Loops

![RFL](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0013-RFL.png)

-----

##### 17. Adaptive Retrieval

![ARR](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0014-ARR.png)

-----

#### Evaluation

##### 18. DeepEval Evaluation

-----

##### 19. GroUSE Evaluation

![GER](https://raw.githubusercontent.com/kranthiB/tech-pulse/main/images/rag/0019-GER.png)

-----

#### Explainability and Transparency

##### 20. Explainable Retrieval in Document Search

-----

#### Advanced Architectures

-----

#### Special Advanced Technique

-----
