# Transformers

- Original Transformer paper: [link](https://arxiv.org/abs/1706.03762)
- BERT: the go-to transformer encoder. [paper](https://arxiv.org/abs/1810.04805)
- GPT series: text generation transformers from OpenAI. [GPT-1](https://s3-us-west-2.amazonaws.com/openai-assets/research-covers/language-unsupervised/language_understanding_paper.pdf) [GPT-2](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf) [GPT-3](https://arxiv.org/abs/2005.14165)
- T5: machine translation. [paper](https://arxiv.org/abs/1910.10683)

For practical purpose, please use [HuggingFace](https://huggingface.co/)

Notebook: [link](Attention_and_Transformers.ipynb)

## Main ingredients for a tranformer model

Component | Role
----------|-----
Positional encoding | Provide position information. Both multi-head attention and MLP do not care about position of vectors in a sequence (permutation-equivalriance).
Multi-head attention | Apply several attentions in parallel to learn different relationships among the tokens in a sequence. Each attention head applies some linear transformation (matrix multiplication) to the inputs, with trainable weights, so that each attention head is slightly different from each other. Information is mixed along the sequence (or time) dimension.
Multi-layer perception (MLP) | Also known as Feed-forward sub-network. Apply some transformations on each vectors individually. Information is mixed along the vector dimension.

## Transformers outside NLP

In vision tasks

- Image classification: Vision Transformers - [ViT](https://arxiv.org/abs/2010.11929). Follow the exact same structure as BERT. Divide an image into "patches", and flatten them into a sequence of patches
- Object detection: [DETR](https://ai.facebook.com/research/publications/end-to-end-object-detection-with-transformers). Use CNN + transformer encoder for embedding the image. Use a transformer decoder, with fixed inputs, to decode directly into object predictions (1 class + 4 bounding box coordinates)
