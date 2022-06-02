# Seminar-NAS

1. [Topic](#topic)
2. [Papers](#papers)
    1. [Base Papers](#bp)
    2. [Chosen Papers](#cp)
3. [Notebook](#notebook)
    1. [NAS](#nas)
    2. [Evolutionary Algorithms](#ea)
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

[Here](https://ml4aad.org/automl/literature-on-neural-architecture-search/) you can find a great database of all relevant
publications around NAS.

### 2.1 Base Papers
<table>
<tr>
  <th>Title</th>
  <th>Summary</th>
</tr>
<tr>
  <td> <a href="https://arxiv.org/abs/1611.01578">
  Neural Architecture Search with Reinforcement Learning
  </a> (Zoph and Lee 2017) </td>
  <td>
  Paper that sparked Neural Architecture Search to the mainstream. They obtained competetive performance on the
  CIFAR 10 and Penn Treebank benchmarks with a search strategy based on reinforcement learning. Vast computational
  resources were necessary: 800 GPUs for 3 to 4 Weeks. Future efforts were made on top of this paper to reduce computational
  costs and improve performance.

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
  <td>   </td>
  <td>   </td>
</tr>
</table>

### 2.2 Chosen Papers (For the Survey)
<table>
<tr>
  <th>Title</th>
  <th>Summary</th>
</tr>
<tr>
  <td> <a href="https://arxiv.org/abs/1611.01578">
  Neural Architecture Search: A Survey
  </a>
  <br>
  &#9200 Survey
  </td>
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
  <td>
    <a href="https://arxiv.org/abs/1611.01578">
      Neural Architecture Search with Reinforcement Learning
    </a> (Zoph and Lee 2017)
    <br>
    &#9889  Search: RL
  </td>
  <td>
  Paper that sparked Neural Architecture Search to the mainstream. They obtained competetive performance on the
  CIFAR 10 and Penn Treebank benchmarks with a search strategy based on reinforcement learning. Vast computational
  resources were necessary: 800 GPUs for 3 to 4 Weeks. Future efforts were made on top of this paper to reduce computational
  costs and improve performance.

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
  <td>
    <a href="https://arxiv.org/pdf/1802.03268.pdf">
      Efficient Neural Architecture Search via Parameters Sharing
    </a>
    (Hieu Pham, Melody Y. Guan, Barret Zoph, Quoc V. Le, Jeff Dean 2018)
    <br>
    &#9889  Search: RL
  </td>
  <td>
  Reduced computation costs significantly in comparison to Zoph and Lee. Search takes less than 16 hours and have a lower test error on CIFAR-10. Trick is to share computations among experiments. All with one desktop GPU. The time consuming step was training/sampling all childs in parallel. Here the different networks are trained "together" and share the same weights (somehow it works). Also another trick is to
use/inject prior human knowledge to fix "macros" AKA basically giving an initial skeleton of the architecture, making the search space smaller with less degrees of freedom. Then they do a "micro search" which is basically searching within cells themselves instead of varying different architecture compositions etc.

  <br>
  <br>
  Cited 1971 times, 2018
  </td>
</tr>
<tr>
  <td> <a href="https://openaccess.thecvf.com/content_ECCV_2018/html/Chenxi_Liu_Progressive_Neural_Architecture_ECCV_2018_paper.html">
  Progressive Neural Architecture Search
  </a>
  (Chenxi Liu, Barret Zoph, Maxim Neumann, Jonathon Shlens, Wei Hua, Li-Jia Li, Li Fei-Fei, Alan Yuille, Jonathan Huang, Kevin Murphy 2018)
    <br>
    &#9889 Search: Evolutionary
  </td>
  <td>
  No controller, No RL. They grow networks using algorithms based on genetic/evolutionary algos. Simple procedure, search time is much much lower than NASNet. Performance is okay.

  <br>
  <br>
  Cited 1510 times, 2018
  </td>
</tr>
<tr>
  <td> <a href="https://arxiv.org/abs/1806.09055">
  DARTS
  </a>
  (Hanxiao Liu, Karen Simonyan, Yiming Yang 2018)
    <br>
    &#9889 Search: Discrete Derivative Problem / Gradient-based
  </td>
  <td>
  No controller, No intermediate performance prediciton which may cause diversion.
  Outperforms everything before it and achieves state of the art on Cifar 10. Continuous relaxation
  of a discrete search problem. Does mostly cell (micro) search!
  <br>
  <br>
  &#9989 Very Promising! Exposes RL as a very slow search space method for NAS!
  <br>
  <br>
  &#9940 Reread this! Complicated

  <br>
  <br>
  Cited  2568 times, 2018
  </td>
</tr>
<tr>
  <td> <a href="https://www.sciencedirect.com/science/article/abs/pii/S0925231221018439?via%3Dihub">
  A Review of Neural Architecture Search
  </a>
  (Dilyara Baymurzinaa, Eugene Golikova, Mikhail Burtsev 2022)
  <br>
  &#9200 Survey
  </td>
  <td>
  More recent review/survey

  <br>
  <br>
  Cited 2 times, 2021/2022
  </td>
</tr>
</table>


<a name="notebook"/>

## 3. Notebook
### 3.1 NAS ([link](https://www.youtube.com/watch?v=wL-p5cjDG64))
#### NAS; Dimensions
NAS Methods can be categorized/differentiated by three dimensions:
1. `Search Space`
    - Defines which architectures can be represented. Incorporating prior knowledge reduces.
    - Problem: Even with constrains, remains i) non-continuous and ii) high dimensional
    search space size (good), however it also introduces bias (bad).
2. `Search Strategy`
    - premature convergence vs find well performing architectures quickly (exploration-exploitation trade off)
    - examples of strategies: random search, Bayesian optimization, evolutionary methods, RL and gradient based
    methods.
3. `Performance Estimation Strategy`
    - Standard training and validation is computationally expensive and limits
    the number of architectures that can be explored.
    - However, training each architecture to be evaluated from scratch frequently yields computational demands in the order
    of thousand of GPU days.
    - Naturally this created the need to develop methods for speeing up performance estimation which is done in this
    section of the process/dimension.
    - Speed-up Methods:
        - Lower fidelity estimates
        - learning curve extrapolation
        - weight inheritance/Network Morphisms
        - One-Shot Models/Weight Sharing

![image](.imgs/nas.png)

#### Nas Timeline
1. `RL`: They framed NAS as an interaction problem, as they do not know the transitions
among the search space and also have differentiable rewards. This gives some reason to
frame NAS as an RL problem with usage of policy gradient to fine tune the parameters.
This was done in 1. and 2.

2. `Evolutionary`: Done in 3.
3. `Continuous relaxation of a discrete search / gradient based`. : Done in 4.

##### 1. Zoph and Lee (2017), used 8000 GPUs
- Posed as a policy gradient/RL problem: (Not good)
- The controller (RNN) is the policy in itself, it samples architectures with probability P and trains a child arch.
- 8000 GPUs, 6 months
- beat human architectures in an automated fashion, kickstarted NAS

![image](.imgs/nas_idea.png)

##### 2. ENAS - Efficient NAS
- Reduced computation costs significantly in comparison to Zoph and Lee.
- Search takes less than 16 hours and have a lower test error on CIFAR-10.
- One of the tricks is to share computations among experiments.
- All with one desktop GPU.

##### 3. Progressive Neural Architecture Search
- Grows networks, no controller, no RL.
- Similar to Genetic/Evolutionary Algorithms, fit parents are passed along, mutation, etc
- Use intermediate performance predictors to predict performance and save time training layers until
the end.

##### 4. DARTS
- No controllers, no intermediate performance prediction
- outperforms everything else before it
- Doesn't cast NAS as an RL problem
- Continuous relaxation of a discrete search problem.
- Does mostly cell (micro) search!


[First Video](https://www.youtube.com/watch?v=wL-p5cjDG64)
[Second Video](https://www.youtube.com/watch?v=BAtBwgV1fG0)


### 3.2 Evolutionary Algorithms ([link](https://www.youtube.com/watch?v=CZE86BPDqCI))
Based on the biological principal of natural selection.

Process:
- Establish population of control laws
- Let theme compete, see how effective they are and rate them based on their fitness
- Breed the "next-generation" of control laws based on the most effective ones

Notes:
- Miller et al. 1989: First used genetic algorithms to propose architectures and use backpropagation to
optimize their weights.
- Nowadays SGD-based weight optimization outperform raw evolutionary ones, however the evolutionary algorithms
are still used to propose new architectures / optimize the current architecture.
- Ev. Algorithms mutations in this context are local operations such as adding or removing a layer, altering the hyperparameters
of a layer, adding skip connections, as well as altering training hyperparameters. After training the offsprings, their fitness
is evaluated and they are added to the population.


## 4. Links
