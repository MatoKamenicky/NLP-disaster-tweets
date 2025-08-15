# NLP with Disaster Tweets

This repository contains my solution for the [Kaggle NLP with Disaster Tweets competition](https://www.kaggle.com/competitions/nlp-getting-started),  
where the goal is to classify tweets as describing real disasters or not.

## 📌 Overview
- **Dataset**: tweets labeled as disaster or non-disaster.
- **Task**: Binary classification.
- **Model**:
  - Base: [BERTweet](https://huggingface.co/vinai/bertweet-base) - BERT-base model pretrained on English Tweets
  - Custom head:
  ```
  Linear(embedding_dim → hidden_dim1) → Dropout(0.3) → ReLU  
  → Linear(hidden_dim1 → hidden_dim2) → Dropout(0.2)  
  → Linear(hidden_dim2 → output_dim)
  ```

## 📘 Notebook
The notebook [NLP-disaster-tweets.ipynb](github.com/MatoKamenicky/NLP-disaster-tweets/blob/main/NLP-disaster-tweets.ipynb) contains the full solution pipeline, including:
- Data loading
- Exploratory Data Analysis (EDA)
- Tokenization
- Model building
- Training loop
- Model evaluation
- Kaggle submission file creation

## 📊 Results
- Best accuracy: 82.837%
- Predictions are generated in submission.csv format for direct Kaggle upload
- Additional preprocessing (removing URLs, special characters, etc.) did **not** improve performance — best results were achieved with simple tokenization only.
