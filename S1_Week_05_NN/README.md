# Neural Network

Geometric Deep Learning: [ICLR 2021 Keynote](https://www.youtube.com/watch?v=w6Pw4MOzMuo)

Universal approximation theorem: [Wikipedia](https://en.wikipedia.org/wiki/Universal_approximation_theorem)

Three main components of understanding an algorithm:

- **Formulation**: Equations, construction, how does the algorithm perform prediction?
- **Nonlinearity**: How do we introduce nonlinearity to the algorithm?
- **Training / Optimization**: How do we train the algorithm?

Resources

- [Deep Learning Book](https://www.deeplearningbook.org/)
- [CS230](https://cs230.stanford.edu/)

Notebook: [Autograd with PyTorch](Autograd_with_PyTorch.ipynb)

## Feed-forward, Fully-connected Neural Network

Play with Neural Network: [TensorFlow playground](https://playground.tensorflow.org/)

- Set activation to ReLU
- Activity 1: use various learning rates. Observe the results
- Activity 2: choose an appropriate learning rate. Use 0, 1, 2, 3 hidden layers, all with 4 neurons (width). You can change the dataset also
- Activity 3. use 2 hidden layers. Use 1, 2, 4, 8 neurons (width). You can change the dataset also
- Activity 4: try bottleneck and expansion structures.

Neural Network visualizer: [Netron](https://netron.app/)

Visualize transformations in Neural Network: [vcubingx's video](https://youtu.be/UOvPeC8WOt8?t=586)

- Construction as linear projection and non-linear activations
- Activation function: why we need it, common types, gradient problem
  - Traditional ones: tanh, relu, sigmoid
  - Modern one(s): swish
  - "Hard" activtions: hard-sigmoid, hard-swish
- Batch norm: why we need it, training and testing behavior, other types of norm layer
- Designing NN: depth and width
- Brief overview of data types and neural network types: convolution, recurrent, attention, graph

## Training a neural network

- Weight initialization [DeepLearning.AI notes](https://www.deeplearning.ai/ai-notes/initialization/)
  - Break the symmetry
  - Avoid exploding variance: Xavier and Kaiming initialization (read more [here](https://pouannes.github.io/blog/initialization/))
- Mini-batch training
- Gradient-based training [DeepLearning.AI notes](https://www.deeplearning.ai/ai-notes/optimization/)
  - Loss function
  - Optimizers: SGD, SGD with momentum, Adam, RMSprop
- Best practices: logging, checkpoints

## Common topologies

- Parallel heads (at output)
- Width expansion
- Auto-encoder / Bottleneck
- Skip-connections (ResNet, U-Net, HourGlass)
- Recurrent
