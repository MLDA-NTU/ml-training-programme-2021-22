# Introduction to NLP

Resources

- [CS224N: Natural Language Processing with Deep Learning](https://web.stanford.edu/class/cs224n/) (Highly recommended)
- [Coursera DeepLearning.AI's NLP Specialization](https://www.coursera.org/specializations/natural-language-processing) (Mostly same as above)
- [HuggingFace's Transformers Course](https://huggingface.co/course/) (only for transformers)

Things you can do with NLP

- **Classification**: word-level (NER - named entity recognition, POS - part of speech tagging), sentence-level (sentiment analysis), document-level
- **Sequence-to-Sequence**: machine translation, text summarization
- Text generation
- Question answering

Some libraries

- [spaCy](https://spacy.io/)
- [Natural Language Toolkit - nlkt](https://www.nltk.org/)

Some algorithms / models:

- TF-IDF (term frequency-inverse document freuency)
- Probabilistic models: Naive Bayes, (Hidden) Markov Model
- Recurrent-based: RNN, GRU, LSTM
- Attention-based: transformers

## Understand text data

**Keywords**: sequence, token, tokenization, unigram, bigram, n-gram, corpus

Wikipedia's Singapore page ([source](https://en.wikipedia.org/wiki/Singapore))

- English

  > Modern Singapore was founded in 1819 by Sir Stamford Raffles as a trading post of the British Empire. In 1867, the colonies in Southeast Asia were reorganised and Singapore came under the direct control of Britain as part of the Straits Settlements.
- Mandarin

  > 1819年，任職于英國不列颠东印度公司的斯坦福·莱佛士与柔佛苏丹签订条约，获准在新加坡建立交易站和殖民地，经莱佛士的努力，逐渐发展成繁荣的轉口港。由于地理位置特殊，新加坡在第二次世界大战以前一直是大英帝国在东南亚最重要的戰略据点。

- Vietnamese

  > Các hòn đảo của Singapore có con người định cư lần đầu tiên vào thế kỷ thứ II TCN và sau đó thuộc một số quốc gia bản địa. Năm 1819, chính trị gia người Anh Stamford Raffles đã thành lập nên Nhà nước Singapore hiện đại với vai trò là một trạm mậu dịch của Công ty Đông Ấn Anh, hành động này được Vương quốc Johor chấp thuận.

- Text is a sequence of words (or more correctly, tokens). Text can have variable length. A model consuming text data should be able to take variable-length inputs
- Token is the smallest unit in text data, similar to pixel in image data. Some popular choices: words, characters, sub-word (used in transformers)
- Tokenization is the process of converting text into tokens. It needs to handle some nasty cases, like punctuations (`NTU is awesome!!!`), short forms (`I am` vs `I'm`). Relevant keywords: lemmatization, stemming
- Unigram / Bigram / N-gram: 1-token, 2-token, or n-token
- Corpus: collection of texts

Some linguistic aspects

- Grammar and sentence/text structure
- Fluency from word phrases
- Complex interaction among the words: order is important!
- Long-range dependence (vs local dependence in image data)

## Text cleaning

- Python string functions: [Python's documentation](https://docs.python.org/3/library/string.html), [freecodecamp](https://www.freecodecamp.org/news/python-string-manipulation-handbook/)
- Regex: [builder](https://regexr.com/), [cheat sheet](https://www.rexegg.com/regex-quickstart.html)

Activity:

- Python string functions: indexing, split, replace, remove, combine (`+`, f-string, and `.join()`), lowercase, startswith
- Regex: match one or more, remove many characters in one step, punctuations, emojis

## Word vectors and Text embeddings

[TensorFlow's Projector](https://projector.tensorflow.org/)

Some cool properties of word embeddings

- Simimlar words are close together
- Similar transformations across word pairs
- Multilingual embeddings: same words across languages have similar embeddings

![word vectors](https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2017/06/06062705/Word-Vectors.png)

Some word embeddings algorithms: Word2Vec, GloVe, [fastText](https://fasttext.cc/)

We can build text embeddings from its constituent words' vectors

- Naive approach: sum/average word vectors (Bag of Words - BoW)
- Better approach: recurrent-based or attention-based

Note: we can build text embeddings without word vectors -> TF-IDF
