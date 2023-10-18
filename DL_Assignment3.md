1. Is it OK to initialize all the weights to the same value as long as that value is selected
randomly using He initialization?

2. Is it OK to initialize the bias terms to 0?

3. Name three advantages of the SELU activation function over ReLU.

4. In which cases would you want to use each of the following activation functions: SELU, leaky
ReLU (and its variants), ReLU, tanh, logistic, and softmax?

5. What may happen if you set the momentum hyperparameter too close to 1 (e.g., 0.99999)
when using an SGD optimizer?

6. Name three ways you can produce a sparse model.

7. Does dropout slow down training? Does it slow down inference (i.e., making predictions on
new instances)? What about MC Dropout?

# Answers

1. Initializing all weights to the same value, even if randomly selected using He initialization, is not recommended. While He initialization helps in preventing the vanishing gradient problem for deep neural networks, initializing all weights to the same value could lead to symmetry problems. Symmetry means that neurons in a given layer would have the same weights and gradients, making them learn the same features, and this would hinder the network's learning capability. Weight initialization should be random, but with a mean of 0, to break the symmetry.

2. Initializing bias terms to 0 is a common and generally acceptable practice. Bias terms are meant to provide the network with the flexibility to fit the data properly. Initializing them to 0 is a reasonable starting point, and the network can learn the appropriate bias values during training. However, you can experiment with non-zero initializations in some cases, but it's essential to do so with care and monitor the training process for any issues.

3. Advantages of the SELU activation function over ReLU:

SELU can prevent vanishing and exploding gradients, making it well-suited for deep networks.
It is self-normalizing, which means it maintains a stable mean and variance of activations during training, reducing the need for batch normalization.
SELU is capable of producing sparsity in the network, which can be beneficial for specific tasks.

4. Use cases for various activation functions:

SELU: Suitable for deep neural networks, particularly when you want self-normalization and sparse activations.
Leaky ReLU and its variants (e.g., Parametric Leaky ReLU, Randomized Leaky ReLU): Good alternatives to ReLU to mitigate the dying ReLU problem. They can be used in most cases where ReLU is applicable.
ReLU: A popular choice for most applications but may suffer from the dying ReLU problem in deep networks.
tanh: Suitable for feedforward neural networks and recurrent neural networks (RNNs) when you need values in the range of -1 to 1.
Logistic (Sigmoid): Typically used in binary classification problems and as an output activation function in the last layer.
Softmax: Used in the output layer of multi-class classification problems to obtain probability distributions over multiple classes.

5. Setting the momentum hyperparameter too close to 1 (e.g., 0.99999) in stochastic gradient descent (SGD) can lead to slow convergence and oscillations during training. When the momentum is very high, the update from the previous iterations has a more significant influence, potentially causing the optimizer to overshoot the minimum of the loss function and resulting in instability.

6. Three ways to produce a sparse model:

L1 Regularization: Add an L1 penalty term to the loss function, which encourages some model weights to become exactly zero.
Dropout: During training, randomly set a fraction of neuron activations to zero. This effectively prunes the network, creating a sparse structure.
Weight Pruning: Train the model normally and then remove or set small weights to zero based on certain criteria, such as magnitude or importance.
Dropout can slow down training because it introduces randomness and effectively reduces the capacity of the network during training. However, it often leads to better generalization and prevents overfitting. During inference (making predictions on new instances), dropout is typically turned off, so it does not slow down inference.

7. MC Dropout (Monte Carlo Dropout) is a technique used during inference to estimate model uncertainty. It involves running the model multiple times with dropout enabled and averaging the results. This does slow down inference, as it requires multiple forward passes, but it provides valuable information about the model's uncertainty and can be useful in applications like Bayesian neural networks and uncertainty quantification.


```python

```
