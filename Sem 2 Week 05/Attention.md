# Attention in NLP

- The mother of all Transformers: [[All You Need Is Attention]](https://arxiv.org/abs/1706.03762)
- BERT - Bidirection Encoding Representations from Transformer: [[Paper]](https://arxiv.org/abs/1810.04805)

## Attention mechanism

![attention](https://miro.medium.com/max/624/0*WbmLoUnqt4lESy-X.png)

**Idea 1**: Similar vectors have dot product equal to 1 (normalized). Also known as cosine similarity

**Idea 2**: We want to focus on (attend to) important information

Types of attentions

- Self-attention: when Q = V. Usually in encoder.
- Cross-attention: when Q <> V. Usually in decoder.

## Main ingredients of a transformer

- Positional encoding
- Multi-head attention
- MLP
