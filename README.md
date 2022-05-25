# Seminar-NAS

1. [Topic](#topic)
2. [Papers](#papers)
    1. [Base Papers](#bp)
    2. [Chosen Papers](#cp)
3. [Notebook](#notebook)
    0. [Machine Learning](#ml)
    1. [Neural Networks](#nn)
    2. [NAS](#nas)
    3. [Reinforcement Learning](#rl)
    4. [Evolutionary Algorithms](#ea)
    5. [Search Space Design](#ea)
4. [Links](#links)

<a name="topic"/>

## 1. Topic

*NAS* using evolutionary algorithms with *RL* and goal attainment

Keywords:
- NAS
    - Network Architecture Search
    - Neural Architecture Search

- RL
    - Reinforcement Learning

- Goal Attainment
    - Selecting the fittest individuals


<a name="papers"/>

## 2. Papers

### 2.1 Base Papers
<table>
<tr>
  <th>Title</th>
  <th>Summary</th>
</tr>
<tr>
  <td> <a href="https://arxiv.org/abs/1611.01578">
  Neural Architecture Search with Reinforcement Learning
  </a> </td>
  <td>
  The paper that introduced Neural Architecture Search. The idea of using a recurrent neural network to compose
  neural network architectures. Presents a new research direction that which enables the automation of finding
  good neural network architectures.

  <br>
  <br>
  <ul>Questions
  <li>
  RNN as controller, provides flexible method, then able to search variable-length architecture space.
  What is that?
  </li>
  </ul>
  Cited 3979 times, 2017
  </td>
</tr>
<tr>
  <td>Foo</td>
  <td>Bar</td>
</tr>
</table>

### 2.2 Chosen Papers (Survey)
<table>
<tr>
  <th>Title</th>
  <th>Summary</th>
</tr>
<tr>
  <td> <a href="https://arxiv.org/abs/1611.01578">
  Neural Architecture Search: A Survey
  </a> </td>
  <td>
  Evaluates NAS as sub-field of Auto-ML and surveys the field as of the current
  state of the art during the publication of said paper. Also breaks down the main
  methods within NAS and shows what options exist to mix and match them. A great starting point
  to learn about this field!

  <br>
  <br>
  <ul>Questions
  <li>
  ?
  </li>
  </ul>
  Cited 1540 times, 2019
  </td>
</tr>
<tr>
  <td>Foo</td>
  <td>Bar</td>
</tr>
</table>


<a name="notebook"/>

## 3. Notebook
### 3.0 Machine Learning
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

### 3.1 Neural Networks
#### 3.1.1 Basics
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


#### 3.1.2 Types
1. Fully Connected Layers
All nodes of layer (i - 1) are connected to nodes of layer i.

2. Convolutional Neural Networks
- Used for images

3. Recurrent Neural Networks ([link](https://www.ibm.com/cloud/learn/recurrent-neural-networks))
- Used for Audio/Temporal signals

Neural Network that uses sequential data or time-series data.
- Has **Memory**, they take info from prior inputs to influence the current input and output.
- Utilize Training data to learn (as well).


### 3.2 NAS
NAS Methods can be categorized/differentiated by three main portions of their process:
1. Search Space
2. Search Strategy
3. Performance Estimation Strategy

### 3.3 Reinforcement Learning
A branch of ML that can be seen as a framework for learning how to interact with the environment
from experience.

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


```

### 3.4 Evolutionary Algorithms ([link](https://www.youtube.com/watch?v=CZE86BPDqCI))
Based on the biological principal of natural selection.

Process:
- Establish population of control laws
- Let theme compete, see how effective they are and rate them based on their fitness
- Breed the "next-generation" of control laws based on the most effective ones


### 3.5 Search Space Design

## 4. Links
