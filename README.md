# Zero-Shot Sentiment Classification with Dimensionality Reduction

## Goal
The goal is to apply a zero-shot learning approach to sentiment classification of IMDB reviews using OpenAI embeddings, where the model is not explicitly trained on our dataset but instead utilizes pre-trained embeddings to understand and classify sentiments. This technique allows the model to generalize from seen to unseen data without the need for fine-tuning.

## Motivation
Zero-shot learning is particularly appealing when we have limited or no labeled data for the task at hand or when we want to avoid the expensive and time-consuming process of training a model. Using OpenAI's powerful embeddings pre-trained on diverse data, we can tap into their understanding of language and sentiment without additional training.

## Key Points

- **Dimensionality Reduction**: Before classification, we use PCA to reduce the dimensionality of the embeddings. This step simplifies the computational requirements and may also improve generalization by focusing on the most informative aspects of the data.

- **Encoding Sentiments as Embeddings**: Instead of training a model, we create embeddings for sentiment labels ('positive' and 'negative') using the same embedding model. These label embeddings serve as reference points for classification.

- **Zero-Shot Classification**: We classify each review by measuring its similarity to the sentiment label embeddings. The sentiment whose embedding is closest to the review embedding in the reduced-dimensional space determines the predicted sentiment.

- **Evaluation Metrics**: We use precision, recall, and F1-score to evaluate the performance of the zero-shot classification. These metrics provide insight into the accuracy and reliability of the model's predictions.

- **Dimensionality Exploration**: By experimenting with different numbers of principal components (100, 10, and 1000), we assess how dimensionality impacts the zero-shot classification performance. This helps in finding an efficient yet effective representation for the classification task.

## Results and Conclusion
The results indicate that even with zero-shot learning, sentiment classification can be performed effectively using OpenAI embeddings combined with dimensionality reduction. The PCA with 100 dimensions achieved the best results, indicating that a moderate level of dimensionality reduction preserves the necessary semantic information for accurate sentiment classification. These findings demonstrate the potential of pre-trained embeddings for zero-shot learning, enabling rapid deployment of NLP models in situations where labeled data is scarce or the domain is dynamic.
