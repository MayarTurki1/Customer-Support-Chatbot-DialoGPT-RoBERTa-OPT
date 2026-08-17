# Intelligent Customer Support Chatbot Using DialoGPT, RoBERTa, and OPT

A customer support chatbot project that explores transformer-based models for query classification, sentiment analysis, and contextual response generation.

## Project Overview

This project focuses on developing an intelligent customer support chatbot capable of understanding customer queries and generating relevant responses.

The system explores three pretrained transformer models, with each model serving a specific role:

- DialoGPT for conversational response generation
- OPT-125M for lightweight and efficient text generation
- RoBERTa for query classification and sentiment analysis

The project aims to improve automated customer support by generating contextual responses while reducing the workload associated with repetitive customer queries.

## Objectives

- Develop an intelligent customer support chatbot using transformer-based models.
- Generate contextual and relevant responses to customer queries.
- Classify customer queries into appropriate categories.
- Analyze customer sentiment.
- Compare the capabilities and limitations of different transformer models.
- Evaluate chatbot responses using quantitative and qualitative metrics.

## Dataset

The dataset used in this project consists of 5,000 sampled records from a larger 27,000-record customer support dataset.

The dataset contains structured customer interactions, including:

- Customer ID
- Query category
- Customer query
- Support response
- Sentiment
- Response time
- Resolution status

The query and response pairs were used to support the development and evaluation of the chatbot system.

## Methodology

The project follows the following workflow:

**Data Preprocessing → Tokenization → Model Fine-Tuning → Response Generation / Classification → Evaluation**

### Data Preprocessing

The preprocessing stage includes:

- Removing missing values
- Text normalization
- Lowercasing
- Punctuation normalization
- Removing redundant spaces
- Tokenization
- Padding sequences
- Adding special tokens to distinguish between user queries and chatbot responses

The dataset was divided into:

- 80% Training
- 20% Testing

## Models

### DialoGPT

DialoGPT was used for conversational response generation.

It was selected for its ability to generate natural and contextually relevant responses while maintaining conversational context.

### OPT-125M

OPT-125M was used as a lightweight text generation model.

It provides a balance between response generation quality and computational efficiency, making it suitable for scenarios where faster responses are important.

### RoBERTa

RoBERTa was used for query classification and sentiment analysis.

The model was fine-tuned to classify customer queries and analyze sentiment to support more context-aware chatbot interactions.

## Evaluation

Several evaluation metrics were used to assess the chatbot and classification performance:

- Accuracy
- Precision
- Recall
- F1-score
- BLEU
- ROUGE-L
- Perplexity (PPL)
- Manual evaluation of response coherence, fluency, and contextual relevance

## Results

### DialoGPT

When the input sequence length was increased from 100 to 150 tokens, the reported accuracy increased from **30% to 62%**.

For a sample of 50 queries, the reported results included:

| Metric | Score |
|---|---:|
| Accuracy | 62% |
| Precision | 100% |
| Recall | 62% |
| F1-score | 77% |
| ROUGE-L | 0.39 |

The model generated more complete and contextual responses with the increased token length.

### OPT-125M

OPT-125M provided faster response generation and lower computational requirements.

However, the evaluation identified limitations in handling complex contextual queries. The reported results included:

| Metric | Score |
|---|---:|
| Recall | 62% |
| F1-score | 77% |
| ROUGE-L | 0.39 |

The model sometimes produced repetitive or less detailed responses.

### RoBERTa

RoBERTa was primarily used for query classification and sentiment analysis.

The reported evaluation showed:

| Metric | Score |
|---|---:|
| Accuracy | 32.7% |
| F1-score | 25% |

The results indicated that RoBERTa was more suitable for classification and sentiment-related tasks than for open-ended response generation.

## Key Findings

- Increasing the token length from 100 to 150 improved the reported DialoGPT accuracy from 30% to 62%.
- DialoGPT demonstrated stronger conversational performance and contextual response generation.
- OPT-125M provided a faster and more lightweight alternative but showed weaker contextual understanding for complex queries.
- RoBERTa was more suitable for query classification and sentiment analysis than free-form response generation.
- Model selection should depend on the specific requirements of the chatbot, including accuracy, response quality, computational efficiency, and contextual understanding.

## Technologies

- Python
- PyTorch
- Hugging Face Transformers
- NLTK
- spaCy
- Google Colab
- DialoGPT
- OPT-125M
- RoBERTa

## Repository Contents

- `filtered_questions_answers.csv` — Customer support dataset
- `Customer Support Chatbot Using DialoGPT, RoBERTa, and OPT.pdf` — Research paper documenting the project

## Research Paper

[View the Research Paper](./Customer%20Support%20Chatbot%20Using%20DialoGPT%2C%20RoBERTa%2C%20and%20OPT.pdf)
