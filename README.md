# Attention Is (Almost) All You Need

## Overview
This project aims to explain the concept of self-attention in large language models by building it from scratch and visualizing its inner workings. In lab 3, I demonstrated attention through canonical heat maps generated through random weights, in this project I amed to show how training these weights can reveal meaninful linguistic patters and relationships.

## Methods
This guide is a bottom-up approach to explaining self-attention. It starts with tokenization and embeddings, then introduces single-head scaled dot-product attention, emphasizing the importance of learned projection matrices ($W_Q, W_K, W_V$). Multi-head attention is also explored to illustrate how different heads can specialize. To demonstrate the learning capabilities of attention, a minimal single-head attention classifier is trained on a small, custom dataset to classify masked tokens as either content words (nouns, verbs, adjectives) or function words (prepositions, articles, auxiliaries). This task encourages the model to learn contextual dependencies, which are then reflected in the attention patterns. 

## Key Results
Before training, the attention patterns are largely random and unstructured, often concentrating disproportionately on individual tokens. After training, the attention weights transform into smoother and more stable distributions. Instead of collapsing into sharp, arbitrary spikes, tokens begin allocating attention in a more distributed and context-sensitive manner. This shift reveals increasingly interpretable structure. The model exhibits clearer syntactic and semantic dependencies, with attention patterns reflecting relationships such as modifiers linking to the words they describe, subjects aligning with predicate elements, and semantically related tokens showing stronger interactions. Function words tend to display more diffuse attention, while content-bearing words retain more focused patterns, consistent with their differing linguistic roles. Overall, the model transitions from noisy, coincidental attention behavior to more organized and meaningful relational structure. Despite the simplified architecture and extremely small dataset, retraining demonstrates how attention mechanisms can move toward capturing underlying linguistic dependencies without explicit supervision.

## How to Run
1.  **Open the notebook** in Google Colab or any compatible Jupyter environment.
2.  **Run all cells sequentially** from top to bottom.
    *   Ensure all necessary packages are installed (see Requirements section).
    *   The notebook will perform tokenization, embedding, demonstrate single-head and multi-head attention (with random weights), and then train a single-head attention classifier. Note the training is computationally intensive, so I would recommend using selecting GPU as your resource in Google Colab.
    *   Finally, it will visualize the attention patterns before and after training.

## Requirements
This project requires the following Python packages, which can be installed via `pip`:
*   `torch`
*   `numpy`
*   `matplotlib`
*   `seaborn`
*   `transformers`

```bash
pip install torch numpy matplotlib seaborn transformers
```