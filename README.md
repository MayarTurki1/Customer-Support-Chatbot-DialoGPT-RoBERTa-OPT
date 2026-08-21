# Intelligent Customer Support Chatbot

An NLP-based customer support chatbot project exploring multiple approaches for understanding customer queries and retrieving appropriate responses.

---

## Overview

This project explores different Natural Language Processing approaches for building an intelligent customer support chatbot.

The implementation includes several approaches for processing customer queries and generating or retrieving responses, including:

* Transformer-based text classification using **RoBERTa**
* Text generation experiments using **GPT-2**
* Semantic similarity search using **Sentence Transformers**
* Efficient vector search using **FAISS**

The project explores how different NLP techniques can be combined to build more responsive and context-aware customer support systems.

---

## Dataset

The project uses customer support and conversational datasets containing pairs of questions/queries and corresponding responses.

The main customer support dataset contains:

* `Customer_Query`
* `Support_Response`

Additional conversational data is loaded from `Conversation.csv` using:

* `question`
* `answer`

---

## Approach 1 — RoBERTa Classification

A pretrained **RoBERTa-base** model was fine-tuned for customer query classification.

### Process

1. Load customer queries and support responses.
2. Tokenize the input text using the RoBERTa tokenizer.
3. Fine-tune RoBERTa for sequence classification.
4. Predict the class corresponding to the appropriate response.
5. Map the predicted class to a support response.

### Training Configuration

* Model: `roberta-base`
* Epochs: `3`
* Training batch size: `8`
* Evaluation batch size: `8`
* Weight decay: `0.01`

The trained model and tokenizer were saved for later inference.

---

## Approach 2 — GPT-2 Text Generation

The project also explores **GPT-2** for response generation.

The implementation experiments with different generation settings, including:

* Maximum new tokens
* Temperature
* Top-p sampling
* Repetition penalty
* Sampling-based generation

This approach was explored as a generative alternative to predefined response retrieval.

---

## Approach 3 — Semantic Retrieval with Sentence Transformers

A semantic retrieval approach was implemented using:

**Sentence Transformers + FAISS**

The `all-MiniLM-L6-v2` model was used to convert questions and responses into numerical embeddings.

These embeddings were indexed using **FAISS** to enable similarity-based retrieval.

### Query-to-Response Retrieval

The user's input is converted into an embedding and compared against the indexed questions.

The most similar question is retrieved, and its corresponding response is returned.

```text
User Query
    │
    ▼
Sentence Transformer
    │
    ▼
Query Embedding
    │
    ▼
FAISS Similarity Search
    │
    ▼
Most Similar Question
    │
    ▼
Corresponding Support Response
```

---

## Conversational Retrieval

The project also explores a conversational interaction approach where:

1. The chatbot presents a question.
2. The user provides an answer.
3. The user's response is converted into an embedding.
4. FAISS retrieves the most semantically similar question.
5. The chatbot continues the conversation using the retrieved question.

This approach explores semantic similarity for maintaining a conversational flow based on available dialogue data.

---

## Technologies

### NLP & Machine Learning

* Python
* Hugging Face Transformers
* RoBERTa
* GPT-2
* Sentence Transformers
* PyTorch
* Scikit-learn

### Semantic Search

* FAISS
* Vector Embeddings
* Cosine Similarity

### Data Processing

* Pandas
* NumPy

---

## Project Workflow

```text
                    Customer / Conversation Data
                              │
                              ▼
                       Text Processing
                              │
                ┌─────────────┼─────────────┐
                ▼             ▼             ▼
             RoBERTa        GPT-2      Sentence
          Classification   Generation   Transformers
                │             │             │
                │             │             ▼
                │             │          Embeddings
                │             │             │
                │             │             ▼
                │             │            FAISS
                │             │             │
                └─────────────┴─────────────┘
                              │
                              ▼
                    Customer Support Response
```

---

## Key Features

* Customer query classification using RoBERTa.
* Exploratory response generation using GPT-2.
* Semantic retrieval using Sentence Transformers.
* Similarity search using FAISS.
* Interactive command-line chatbot implementations.
* Support for question-to-response and response-to-question retrieval.

---

## Project Contents

The project notebook contains the complete implementation and experiments, including:

* Data loading and validation
* RoBERTa fine-tuning
* Model evaluation
* GPT-2 generation experiments
* Sentence embedding generation
* FAISS indexing
* Semantic similarity retrieval
* Interactive chatbot functions

---

## Key Takeaway

This project explores multiple NLP strategies for customer support automation, comparing classification, generative, and semantic retrieval approaches.

The implementation demonstrates how transformer models, text embeddings, and vector similarity search can be used to build different components of an intelligent customer support system.
