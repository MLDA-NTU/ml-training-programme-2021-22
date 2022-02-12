# Attention in NLP

- The mother of all Transformers: [[All You Need Is Attention]](https://arxiv.org/abs/1706.03762)
- BERT - Bidirection Encoding Representations from Transformer: [[Paper]](https://arxiv.org/abs/1810.04805)

## The big picture: Encoder and Decoder

You can read the [HuggingFace's Types of Models](https://huggingface.co/docs/transformers/model_summary) for an alternative explanation.

Both RNN-based and transformer-based models share the same overall architecture: input sequence -> output sequence of the same length (at least in the encoder)

- Only their internal mathematics (implementations and mechanism) are different

For classification, you need an **Encoder** to obtain embeddings from the text. Then you can add a classifier (e.g. 1/2-layer MLP, SVM, Random forest) on top of the embeddings to do classification

- Sentence / text-level embeddings: text classification e.g. sentiment analysis, movie review prediction
- Token / word-level embeddings: token / word classification e.g. POS, NER

For text generation, you need a **Decoder** to output a sequence of embeddings from one (or a sequence) of another embeddings. Then again you can add a classifier on top to classify embeddings into tokens / words in your vocabulary.

- Most decoders are **auto-regressive** models: use past tokens (a sequence) to predict the next token
- If you only have a decoder, you can input a random noise vector as its input embedding to act as a seed to generate random text

For sequence-to-sequence tasks, you need **both an Encoder and a Decoder**. Encoder provides text understanding (one embedding or a sequence of embeddings), and decoder generates another text sequence from that text understanding

- Machine translation: encoder converts English text to embeddings. Decoder convert those embeddings to French text.
- Text summarization: encoder convert full text to embeddings. Decoder convert those embeddings to a shorter, summarized text.

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
