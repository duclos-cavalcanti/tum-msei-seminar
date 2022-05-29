# Basics

1. [Notebook](#topic)
    1. [Machine Learning](#ml)
    2. [Neural Networks](#nn)
    3. [Reinforcement Learning](#rl)
2. [Links](#links)

<a name="basics"/>

## 1. Notebook
### 1.1 Machine Learning
Types:
- Supervised Learning (Labels)
    - Classification (Discrete Data)
    - Regression (Continuous Data)
    - Optimization and Control (Modified system or control parameters)
- Unsupervised Learning (No Labels)
    - Data mining - an Unsupervised algorithm finds out / learns clusters of data of distinguishing features and also
    learn that there are different categories to be classified from these clusters.
        - Clustering (Discrete Data)
        - Pattern/Feature extraction (Discrete Data)
- Semi-Supervised Learning
    - Reinforcement Learning (Modifies system or control parameters)
    - Generative Models (Model)

### 1.2 Neural Networks
#### 1.2.1 Basics
Computational Graphs / Functions
- `Parameters` / `Hyperparameters`
- `Score` Function
- `Loss` Function + Regularization
    - `Optimization`: Finding parameters 'w' that minimizes Loss
        - Can be done by computing gradient of said function
        - `Backpropagation` is a method to fine tune parameters to approach the best solution.
        This is done by leveraging the computational graph format of neural networks and
        their nodes.

Neural Networks
- are just a `class of functions / graph` where simpler functions are stacked upon each other in a hierarchical
manner in order to make a more complex non-linear function. Essentially multiple stages of
hierarchical computation.
- a different number of layers (NN) gives more precision and flexibility to the purpose of the neural network.
In the example of image classification, extra layers can be seen as extra templates to recognize an image.
- the "abstraction" of a `layer` has the nice property that it allows us to use efficient **vectorized**
code (e.g. matrix multiplies)

Training (example Mini-Batch Stochastic Gradient Descent or SGD)

Loop:
1. `Sample` a batch of data
2. `Forward` prop it through the graph (network), get loss
3. `Backprop` to calculate the gradients
4. `Update` the parameters using the gradient


#### 1.2.2 Types
1. Fully Connected Layers
All nodes of layer (i - 1) are connected to nodes of layer i.

2. Convolutional Neural Networks
- Used for images

3. Recurrent Neural Networks ([link](https://www.ibm.com/cloud/learn/recurrent-neural-networks))
- Used for Audio/Temporal signals

Neural Network that uses sequential data or time-series data.
- Has **Memory**, they take info from prior inputs to influence the current input and output.
- Utilize Training data to learn (as well).


### 1.3 Reinforcement Learning ([link](https://www.youtube.com/watch?v=0MNVhXEX9to))
A branch of ML that can be seen as a framework for learning how to interact with the environment
from experience.

- Ocasionally, very ocasionally gets a reward
- Is in its core an optimization problem, where we aim to find the optimal policy set.

```

       ------------------------------------------
       |                                        |
       | Reward: r                              |
       v                                        |
----------------------                          |
|    Agent           |----------------->  ENVIRONMENT
|    Policy: p(s, a) |    Action: a             |
----------------------                          |
        ^                                       |
        |            State: s                   |
        ----------------------------------------

            Value Function: Vpi(s)

```
Value Function:
- Expected Reward I'd get in the future if I start at that state(s) and I enact
  that policy(pi)

- Computes the value of being in a certain state(s) given a policy(pi).

## 2. Links
