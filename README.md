# AAI 6620 Midterm: Comparing Three NLP Models

## Project Overview

This project compares three different NLP models: Bigram, LSTM, and Transformer, to predict the next character based on previous text. The goal is to understand how different model architectures process language, compare their performance, and examine how attention influences language modeling.

## Dataset

I used the Tiny Shakespeare dataset from Andrej Karpathy's char-rnn repository, which contains Shakespeare-style dialogue and text.

**Dataset:** https://raw.githubusercontent.com/karpathy/char-rnn/master/data/tinyshakespeare/input.txt

The dataset was tokenized at the character level, creating a vocabulary of 65 unique characters. I used 90% of the data for training and 10% for validation, with a context length of 32 characters and a batch size of 32.

## Models

### 1. Bigram Model

The Bigram model predicts the next character based only on the immediately previous character. It uses character-pair frequencies to calculate probabilities but cannot capture longer relationships in text. Its main advantage is its simplicity, while its limitation is that it ignores broader context.

### 2. LSTM Model

The LSTM processes characters sequentially and uses memory cells and gates to retain or forget information. This allows it to learn longer patterns compared to the Bigram model. However, it can still struggle with long-range dependencies because important information may weaken as it passes through multiple sequential steps.

### 3. Transformer Model

The Transformer uses token embeddings, positional embeddings, causal self-attention, feedforward layers, and an output layer. Self-attention allows it to identify relationships between characters within a context window. Unlike the LSTM, the Transformer can process multiple positions in parallel during training. However, its performance depends on factors such as model size, context length, and training configuration.

## Results

| Model | Training Loss | Validation Loss | Training Time |
|---|---:|---:|---:|
| Bigram | 2.4512 | 2.5005 | 33.97 s |
| LSTM | 2.0705 | 2.1103 | 14.58 s |
| Transformer | 2.3140 | 2.3500 | 6.85 s |

The LSTM achieved the lowest training and validation losses and appeared to generate the most recognizable text in this experiment. The Transformer had the shortest recorded training time and performed better than the Bigram model, but it did not outperform the LSTM in prediction accuracy.


## Generated Text Comparison

| Model | Generated Text Sample | Generated Text Quality | Observation |
|---|---|---|---|
| Bigram | `s the, shanghestheroole aitinehes hintoe Pis coulo` | Low | Mostly random character combinations with some recognizable word patterns and punctuation. |
| LSTM | `save eritioh` | Medium | Some recognizable character patterns, but the generated text remains difficult to understand. |
| Transformer | `s pink,` | Low | Some recognizable words, but the overall output contains incomplete or nonsensical patterns. |

## What Did Attention Improve?

Self-attention allows the Transformer to examine relationships between multiple characters within its context window instead of relying on sequential memory like the LSTM. It calculates attention scores to determine which previous characters are more relevant when predicting the next character. This helps the model focus on important contextual information and capture relationships between distant characters.


In this experiment, the Transformer performed better than the Bigram model because it could use information from multiple previous characters rather than relying only on the immediately previous character. However, it did not outperform the LSTM. Its small architecture, context length of 32 characters, and limited training may have restricted its ability to fully benefit from self-attention.

Although the Transformer trained the fastest, its additional complexity did not produce better prediction accuracy than the LSTM under the conditions of this experiment.

## What I Learned

This experiment taught me that model performance depends on factors such as architecture, context length, dataset size, and training configuration. Initially, I expected the Transformer to perform better because of its self-attention mechanism. However, the LSTM achieved the lowest training and validation losses.

This helped me understand that a more complex architecture does not automatically result in better performance. If I repeated this experiment, I would experiment with longer context lengths, additional training iterations, and different hyperparameters. I would also compare more generated samples to evaluate text quality more reliably.

## How to Run

1. Open `AAI6620_Midterm_MS.ipynb` in Google Colab or Jupyter Notebook.
2. Run the cells in order, starting with dataset loading.
3. The notebook downloads the Tiny Shakespeare dataset using the source URL provided above.
4. Run the Bigram, LSTM, and Transformer training cells.
5. Evaluate each model using the training and validation data.
6. Review the generated text samples and model comparison tables.

**Requirements:** Python, PyTorch, pandas, and a Jupyter-compatible environment such as Google Colab. Training times may vary depending on hardware and runtime conditions.

## AI Use

I used ChatGPT to help understand NLP concepts, debug code, organize model comparisons, and improve explanations throughout my notebook. I also used ChatGPT to generate the initial draft of my README.md based on my NLP midterm project, including the dataset description, model explanations, results table, findings, and instructions for running the notebook. I reviewed the AI-generated suggestions and README content, made necessary changes, and ensured that the information accurately reflected my implementation, experimental results, and understanding of the project.
