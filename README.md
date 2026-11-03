# AAI 6620 Midterm: Comparing Three NLP Models

## Project Overview

This project compares three different NLP models, Bigram, LSTM and Transformer model, to predict the next character based on previous text. The goal is to understand how different model architectures process language and how attention influences language modeling.

## Dataset

I used the Tiny Shakespeare dataset from Andrej Karpathy's char-rnn repository which contains Shakespeare-style dialogue and text.

Dataset: https://raw.githubusercontent.com/karpathy/char-rnn/master/data/tinyshakespeare/input.txt

The dataset was tokenized at the character level, creating a vocabulary of 65 unique characters. I used 90% of the data for training and 10% for validation, with a context length of 32 characters.

## Models

### 1. Bigram Model

The Bigram model predicts the next character based only on the immediately previous character. It uses character-pair frequencies to calculate probabilities but cannot capture longer relationships in text.

### 2. LSTM Model

The LSTM processes characters sequentially and uses memory cells and gates to retain or forget information. This allows it to learn longer patterns compared to the Bigram model.

### 3. Transformer Model

The Transformer uses token embeddings, positional embeddings, causal self-attention, feedforward layers, and an output layer. Self-attention allows it to identify relationships between characters within a context window.

## Results

| Model | Training Loss | Validation Loss | Training Time |
|---|---:|---:|---:|
| Bigram | 2.4512 | 2.5005 | 30.85 s |
| LSTM | 2.0757 | 2.1196 | 14.91 s |
| Transformer | 2.2986 | 2.3348 | 6.64 s |

The LSTM achieved the lowest training and validation losses and generated the most recognizable text in this experiment. The Transformer trained the fastest but did not outperform the LSTM in prediction accuracy.

## What Did Attention Improve?

Self-attention allowed the Transformer to examine relationships between multiple characters within its context window instead of relying on sequential memory like the LSTM. The Transformer performed better than the Bigram but did not achieve better results than the LSTM.

## What I Learned

This experiment taught me that model performance depends on factors such as architecture, context length, dataset size, and training configuration. Although Transformers have powerful self-attention mechanisms, they do not necessarily outperform simpler models in small experiments.

## How to Run

1. Open the project notebook in Google Colab.
2. Run the cells in order, starting with dataset loading.
3. The notebook downloads Tiny Shakespeare from the source URL above.
4. Train and evaluate each model, then review the generated text and comparison table.

## AI Use

I used ChatGPT to help understand NLP concepts, debug code, organize model comparisons, and improve explanations throughout my notebook. I also used ChatGPT to generate the initial draft of my README.md based on my NLP midterm project, including the dataset description, model explanations, results table, findings, and instructions for running the notebook. I reviewed the AI-generated suggestions and README content, made necessary changes, and ensured that the information accurately reflected my implementation, experimental results, and understanding of the project.
