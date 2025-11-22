# Assignment 4 - Transformers
### Intro
The book I have decided to use for this assignment is Chapter 1 of the 1866 novel, Crime and Punishment, written by Fyodor Dostoevsky.
For this assignment I have opted to do the text summarization task using the HuggingFace Text summarization model.

## Transformer Architecture
The HuggingFace summarization pipeline uses a transformer model called DistilBART, which works in two steps: an encoder reads and understands the input text, and a decoder generates a shorter summary based on that understanding. The encoder uses attention to focus on important parts of the chapter, while the decoder produces the summary one word at a time. The pipeline handles all of this automatically, and settings like max_length, min_length, and num_beams control how long and detailed the final summary is. This transformer setup allows the model to create clear, coherent summaries without any manual rules.

## Transformer Hyperparameters
The main hyperparameter I tuned was max_length, num_beans, and no_repeat_ngram_size. max_length determines how long the summary can be, I found that around 100 words yeilds the best results. num_beams affects how many candidate summaries the model explores before choosing the best one, I found 2 to be optimal. no_repeat_ngram_size helps prevent the model from repeating the same phrases, for this I found 3 to be optimal.

## ROUGE Scores
| Metric     | Score      |
|------------|------------|
| ROUGE-1    | 0.21875    |
| ROUGE-2    | 0.01587    |
| ROUGE-L    | 0.14063    |
| ROUGE-Lsum | 0.14063    |


## ROUGE Analysis
The ROUGE scores for my Chapter I summary show moderate performance, which is expected when summarizing literary text. The ROUGE 1 score of 0.2187 indicates that the summary captures some of the key words from the reference summary, while the ROUGE L score of 0.1406 suggests that parts of the sentence structure or narrative order were preserved. The very low ROUGE 2 score of 0.0158 is normal for creative or narrative writing because bigram overlap is rare when the model paraphrases instead of copying phrases directly. Overall, these results show that the model produced a reasonably high-level summary of the chapter even though the exact wording and phrasing differed from the human reference, which is typical behavior for summarization on fiction.
