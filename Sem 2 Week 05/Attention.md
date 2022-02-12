# Attention in NLP

- The mother of all Transformers: [[All You Need Is Attention]](https://arxiv.org/abs/1706.03762)
- BERT - Bidirection Encoding Representations from Transformer: [[Paper]](https://arxiv.org/abs/1810.04805)

## Attention mechanism

![attention](https://miro.medium.com/max/624/0*WbmLoUnqt4lESy-X.png)

- Q: query
- K: key
- V: value

**Idea 1**: Similar vectors have dot product equal to 1 (normalized). Also known as cosine similarity

**Idea 2**: We want to focus on (attend to) important information

**Attention**: For a query vector Q, Attention is the weighted sum of relevant vectors V

Notes:

- K (key) and V (value) are always the same
- When Q = K -> self-attention (attend to itself). Usually in encoder
- When Q != -> cross-attention (attend to another sequence). Usually in decoders

## Main ingredients of a transformer

- Positional encoding
- Multi-head attention
- MLP
