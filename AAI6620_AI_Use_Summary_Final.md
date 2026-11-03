# AI Use Summary — AAI 6620 NLP Midterm

## Project
**Comparing Three NLP Models: Bigram, LSTM, and Transformer**

I used ChatGPT as a learning and writing assistant while completing my individual NLP midterm project. Its assistance included understanding concepts, reviewing and debugging notebook code, organizing results, and editing explanations. I reviewed its suggestions, made changes to my work, and compared the written descriptions and numerical results with my notebook.

## How I Used ChatGPT

### Notebook structure and code guidance
- Asked ChatGPT to help plan the numbered steps of my Jupyter/Colab notebook, including which code to write in each step and how to organize the Goal, Explanation, code cells, and model comparisons.
- Used ChatGPT to provide and explain code examples when I did not understand how to implement parts of the models. One of the more complicated examples was the Transformer `forward()` method, particularly creating a **causal attention mask** with `torch.triu(...)` and passing it to `nn.MultiheadAttention` so the model could not attend to future character positions.
- Reviewed and adapted the suggested code to fit my notebook's variables and structure, and used the explanations to understand what the code was doing rather than copying it without review.

### Code review and debugging
- Asked ChatGPT to review versions of my Jupyter/Colab notebook for potential errors and unclear explanations. These were code reviews, not independent end-to-end execution tests by ChatGPT.
- Worked through a Bigram counting issue: the transition table must increment the count for each consecutive character pair (`bigram_counts[current_char, next_char] += 1`).

### Comparing models and interpreting results
- Used ChatGPT to help structure the model-performance comparison table, including training loss, validation loss, and training time.
- Asked ChatGPT to generate and format the generated-text comparison table for the Bigram, LSTM, and Transformer models, including sample excerpts, qualitative quality ratings, and observations. I checked the excerpts against my notebook outputs and updated them when the generated samples changed.

### Writing and editing
- Used ChatGPT to draft and organize this AI-use summary itself and to generate the initial draft of `README.md`.
