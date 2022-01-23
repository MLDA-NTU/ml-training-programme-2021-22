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

## Understand text data

**Keywords**: sequence, token, tokenization, unigram, bigram, n-gram, corpus

Wikipedia's Singapore page ([source](https://en.wikipedia.org/wiki/Singapore))

- English

  > Modern Singapore was founded in 1819 by Sir Stamford Raffles as a trading post of the British Empire. In 1867, the colonies in Southeast Asia were reorganised and Singapore came under the direct control of Britain as part of the Straits Settlements.
- Mandarin

  > 1819年，任職于英國不列颠东印度公司的斯坦福·莱佛士与柔佛苏丹签订条约，获准在新加坡建立交易站和殖民地，经莱佛士的努力，逐渐发展成繁荣的轉口港。由于地理位置特殊，新加坡在第二次世界大战以前一直是大英帝国在东南亚最重要的戰略据点。

- Vietnamese

  > Các hòn đảo của Singapore có con người định cư lần đầu tiên vào thế kỷ thứ II TCN và sau đó thuộc một số quốc gia bản địa. Năm 1819, chính trị gia người Anh Stamford Raffles đã thành lập nên Nhà nước Singapore hiện đại với vai trò là một trạm mậu dịch của Công ty Đông Ấn Anh, hành động này được Vương quốc Johor chấp thuận.


## Text cleaning

- Python string functions: [Python's documentation](https://docs.python.org/3/library/string.html), [freecodecamp](https://www.freecodecamp.org/news/python-string-manipulation-handbook/)
- Regex: [builder](https://regexr.com/), [cheat sheet](https://www.rexegg.com/regex-quickstart.html)

Activity:

- Python string functions: indexing, split, replace, remove, combine (`+`, f-string, and `.join()`), lowercase, startswith
- Regex: match one or more, remove many characters in one step, punctuations, emojis

## Probabilistic Sequence Modelling


