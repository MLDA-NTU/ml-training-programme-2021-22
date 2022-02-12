# Deep Learning for NLP

- RNN cheatsheet from CS230: [link](https://stanford.edu/~shervine/teaching/cs-230/cheatsheet-recurrent-neural-networks)
- MIT's 6.S191 lecture on RNN: [YouTube](https://www.youtube.com/watch?v=SEnXr6v2ifU)

Notebooks

- Explore NLP and Word-frequency + Word-vectors: [NLP with Deep Learning](NLP_with_Deep_Learning.ipynb)
- RNN architecture: [RNN](RNN.ipypnb)

## Recurrent Neural Network

General form

![image](https://user-images.githubusercontent.com/26946864/152151123-9829e51e-5466-452e-891c-5707669fd5d5.png)

Where 

- `RNN_cell` is some function with trainable weights
- `input_i` is the input vector at position `i`
- `hidden_state` is a vector that **propagates information along the sequence dimension**, at position `i-1` (previous position) and `i` (current position).

E.g. Let the RNN cell be the function `f(i, h) = ReLU(3i - 4h + 1)`, and we have an input sequence `[3,5,7,5]`

- Initialize first hidden state `h_0 = 0`
- Next hidden state: `h_1 = ReLU(3x3 - 4x0 + 1) = 10`
- Next hidden state: `h_2 = ReLU(3x5 - 4x10 + 1) = 0`
- ...
- Final output sequence: `[10, 0, 22,0]`

Good things

- Can take input sequences with any length (CNN can do it too :o)
- Shared weights across the sequence dimension (so is CNN o:)
- Take into account **all** previous information (CNN does not 😠)

Bad things

- Have to compute sequentially -> very slow, even if you have a very fast GPU (transformer doesn't compute sequentially 🤗)
- "Polynomial" effect -> exploding and vanishing gradients + weak information flow for far-away inputs
