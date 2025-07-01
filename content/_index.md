+++

title = "SKE & SKI: Theory and Methods"
description = "Symbolic Knowledge Extraction and Injection: Theory and Methods"
outputs = ["Reveal"]

+++

{{% section %}}

# Symbolic Knowledge Extraction and Injection:<br>Theory and Methods

<span class="hint">(last built on: {{< today >}})</span>

{{< gc >}} and {{< mm >}}
<br>Dipartimento di Informatica — Scienza e Ingegneria (DISI), Sede di Cesena,
<br> Alma Mater Studiorum—Università di Bologna

<br>[Mini-school](https://sites.google.com/view/woa2025/mini-school) @ [WOA 2025, the 26th Workshop From Objects to Agents](https://sites.google.com/view/woa2025)
<br>2nd July 2025, Trento, Italy

<br>
<span class="hint">
This talk is partially supported by the “ENGINES — ENGineering INtElligent Systems around intelligent agent technologies”
project funded by the Italian MUR program “PRIN 2022” under grant number 20229ZXBZM.
</span>
<br>{{< image src="./images/engines_logo.jpg" alt="ENGINES project logo" width="70px" >}}

---

## Link to these slides

<{{< slides-url >}}>

{{< qrcode >}}

[<i class="fa fa-print" aria-hidden="true"></i> printable version](?print-pdf&pdfSeparateFragments=false)

{{% /section %}}

---

{{< slide id="background" >}}

# Background

Quick overview on symbolic vs. sub-symbolic AI

---

## Overview on AI

{{< image src="./images/ai-map.svg" alt="AI map" width="100%" >}}

- wide field of research, with many _sub-fields_
- each sub-field has its own relevant _tasks_ (problems) ...
- ... and each task comes with many useful _methods_ (algorithms)

---

## Symbolic vs. Sub-symbolic AI

Two broad categories of AI approaches:

{{< image src="./images/ai-map2.svg" alt="AI map with a focus on symbolic vs sub-symbolic" width="100%" >}}


---

{{% section %}}

## Why the wording "Symbolic" vs. "Sub-symbolic"? (pt. 1)

### Local vs. Distributed Representations

{{% multicol %}}
{{% col %}}
{{< image src="./images/local-distributed-representations.png" alt="Local vs. Distributed Representations of a bunch of animals" width="100%" max-h="60vh" >}}
{{% /col %}}
{{% col %}}
<br>

- __Local__ $\approx$ "symbolic": each symbol has a clear, distinct meaning
    + e.g. `"bear"` is a symbol denoting a crisp category (either the animal is a bear or not)

- __Distributed__ $\approx$ "non-symbolic": symbols do not have a clear meaning per se, but the whole representation does
    + e.g. `"swim"` is fuzzy capability: one animal may be (un)able to swim to some extent

<br>

{{% fragment %}}
> Let's say we need to represent $N$ classes, how many columns would the tables have?
{{% /fragment %}}

{{% /col %}}
{{% /multicol %}}

---

## Why the wording "Symbolic" vs. "Sub-symbolic"? (pt. 2)

### What is a "symbol" after all? Aren't numbers symbols too?

According to [Tim van Gelder in 1990](https://doi.org/10.1007/978-3-642-76070-9_6):

> __Symbolic__ representations of knowledge
> - involve a _set of symbols_
> - which can be _combined_ (e.g., concatenated) in (possibly) infinitely many ways,
> - following precise _syntactical rules_,
> - where both elementary symbols and any admissible combination of them can be _assigned with meaning_

---

## Why "*Sub*-symbolic" instead of "Non-symbolic" or just "Numerical"?

- There exist approaches where symbols are combined with numbers, e.g.:
    + **Probabilistic logic programming**: where logic statements are combined with probabilities
    + **Fuzzy logic**: where logic statements are combined with degrees of truth
    + **Bayesian networks**: a.k.a. graphical models, where nodes are symbols and edges are conditional dependencies with probabilities, e.g.
        ![Example of a Bayesian network](./images/bn.png)

- These approaches are _not purely symbolic_, but they are _not purely numeric_ either, so we call the overall category __"sub-symbolic"__

{{% /section %}}

---

{{% section %}}

## Examples of Symbolic AI (pt. 1)

- **Logic programming**: SLD resolution (e.g., Prolog)
- **Knowledge representation**: Semantic Web (e.g., OWL), Description Logics (e.g., ALC)
- **Automated reasoning**: Theorem proving, Model checking
- **Planning**: STRIPS, PDDL

---

## Examples of Symbolic AI (pt. 2)

### Logic programming with SLD resolution

{{< image src="./images/proof-tree.png" alt="Example of SLD resolution on a simple theory" width="100%" max-h="60vh" >}}

---

## Examples of Symbolic AI (pt. 3)

### Ontology definition in OWL

{{< image src="./images/ontology-example.png" alt="Example of ontology definition in OWL" width="80%" max-h="60vh" >}}

---

## Examples of Symbolic AI (pt. 4)

### Model-checking (as opposed to testing)

{{< image src="./images/model-checking-vs-testing.webp" alt="Main differences among model-checking and testing for verifying computational systems" width="80%" max-h="60vh" >}}

---

## Examples of Symbolic AI (pt. 5)

### Planning in STRIPS

{{% multicol %}}
{{% col %}}
{{< image src="./images/planning.png" alt="Example of start vs goal state + state branching" width="100%" max-h="60vh" >}}
{{% /col %}}
{{% col %}}

<br>

#### Available actions

- `grab(X)`: grabs block `X` from the table
- `put(X)`: puts block `X` on the table
- `stack(X, Y)`: stacks block `X` on top of block `Y`
- `unstack(X, Y)`: un-stacks block `X` from block `Y`

{{% /col %}}
{{% /multicol %}}

{{% /section %}}

---

## What do these _symbolic_ approaches have in common?

- **Structured representations**: knowledge (I/O data) is represented in a structured, formal way (e.g., logic formulas, ontologies)

- **Algorithmic manipulation of representations**: each approach relies on algorithms that manipulate these structured representations following exact rules

- **Crisp semantics**: the meaning of the representations is well-defined, and the algorithms produce exact results
    + representations are either _well-formed or not_, algorithms rely on rules which are either _applicable or not_

- **Model-driven**: algorithms may commonly work in zero- or few-shot settings, humans must commonly model and encode knowledge in the target structure

- **Clear computational complexity**: the decidability, complexity, and tractability of the algorithms are well understood

---

{{% section %}}

## Examples of Sub-symbolic AI (pt. 1)

- **Machine learning**: supervised, unsupervised, and reinforcement learning
    * _Supervised_ learning: fitting a discrete (classification) or a continuous function (regression) from examples
    * _Unsupervised_ learning: clustering, dimensionality reduction
    * _Reinforcement_ learning: learning a policy to maximize a reward signal, via simulation

- **Probabilistic reasoning**: Bayesian networks, Markov models, probabilistic logic programming

---

## Examples of Sub-symbolic AI (pt. 2)

### Supervised learning

{{< image src="./images/supervised.png" alt="Overview on the supervised learning process" width="100%" max-h="60vh" >}}

---

## Examples of Sub-symbolic AI (pt. 3)

### Supervised learning – Classification vs. Regression (1/2)

Data separation vs. curve fitting:

{{< image src="./images/classification-vs-regression1.png" alt="Classification vs. Regression: separation vs. curve fitting" width="100%" max-h="60vh" >}}

---

## Examples of Sub-symbolic AI (pt. 4)

### Supervised learning – Classification vs. Regression (2/2)

Focus on the target feature:

{{< image src="./images/classification-vs-regression2.png" alt="Classification vs. Regression: finite vs. continuous target feature" width="100%" max-h="60vh" >}}

---

## Examples of Sub-symbolic AI (pt. 5)

### Unsupervised learning – Clustering

{{< image src="./images/clustering.png" alt="Example of the clustering task" width="100%" max-h="60vh" >}}

---

## Examples of Sub-symbolic AI (pt. 6)

### Unsupervised learning – Reinforcement learning (metaphor)

{{< image src="./images/reinforcement.svg" alt="Main idea behind reinforcement learning" width="100%" max-h="60vh" >}}

---

## Examples of Sub-symbolic AI (pt. 7)

### Reinforcement learning – Reinforcement learning (policy)

{{< image src="./images/q-table.png" alt="The goal of reinforcement learning is to estimate a policy, i.e. a function (e.g. a table) estimating the expected reward per each state–action pair" width="100%" max-h="60vh" >}}

{{% /section %}}

---

## What do these _sub-symbolic_ approaches have in common?

- **Numeric representations**: knowledge (I/O data) is represented in a less structured way, often as vectors/matrices/tensors of numbers

- **Differentiable manipulation of representations**: algorithms rely on mathematical operations involving these numeric representations, most-commonly undergoing some optimization process
    + e.g., sum, product, max, min, etc.

- **Fuzzy/continuous semantics**: representations are from continuous spaces, where similarities and distances are defined in a continuous way, and algorithms may yield fuzzy results

- **Data-driven** + **Usage vs. training**: algorithms are often trained on data, to be later re-used on other data
    + usage is commonly impractical or impossible without training

- **Unclear computational complexity**: strong reliance on greedy or time-limited optimization methods, lack of theoretical guarantees on the quality of the results

---


## Long-standing dualism

### Intuition vs. Reasoning

1. Esprit de _finesse_ vs. Esprit de _géométrie_ (Philosophy) --- [Blaise Pascal, 1669](https://en.wikipedia.org/wiki/Pens%C3%A9es)
2. _Cognitive_ vs. _Behavioural_ Psychology --- [B.F. Skinner, 1950s](https://doi.org/10.1111/j.2044-8295.1985.tb01953.x)
3. _System 1_ (fast, intuitive) vs. _System 2_ (slow, rational) --- [Daniel Kahneman, 2011](https://en.wikipedia.org/wiki/Thinking,_Fast_and_Slow)

##

{{% fragment %}}
{{% multicol %}}
{{% col %}}
#### Sub-symbolic AI

- Provides mechanisms emulating human-like _intuition_
- _Quick_, possibly _error-prone_, but often _effective_
- Requires _learning_ from data
- Often _opaque_, hard to interpret or explain
{{% /col %}}
{{% col %}}
#### Symbolic AI

- Provides mechanisms emulating human-like _reasoning_
- _Slow_, but _precise_ and _verifiable_
- Requires symbolic _modeling_ and _encoding_ knowledge
- Often _transparent_, easier to interpret and explain
{{% /col %}}
{{% /multicol %}}
{{% /fragment %}}

---

## Need for integration

- the [NeSy community](https://www.nesy-ai.org/) has long recognized the _complementarity_ among symbolic and sub-symbolic approaches...
- ... with a focus on __neural-networks__ (_NN_) based sub-symbolic methods, as they are very _flexible_

{{% fragment %}}

### Patterns of _integration_ or _combination_ (cf. [Bhuyan et al., 2024](https://link.springer.com/article/10.1007/s00521-024-09960-z))

1. `Symbolic Neuro-Symbolic`: symbols $\rightarrow$ vectors $\rightarrow$ NNs $\rightarrow$ vectors $\rightarrow$ symbols
2. `Symbolic[Neuro]`: symbolic module $\xrightarrow{invokes}$ NN $\rightarrow $ output
3. `Neuro | Symbolic`: NN $\xrightarrow{cooperates}$ symbolic module $\xrightarrow{cooperates}$ NN $\rightarrow$ ...
4. `Neuro-Symbolic → Neuro`: symbolic knowledge $\xrightarrow{influences}$ NN
5. <code>Neuro<sub>Symbolic</sub></code>: symbolic knowledge $\xrightarrow{constrains}$ NN
6. `Neuro[Symbolic]`: symbolic module $\xrightarrow{embedded in}$ NN

{{% /fragment %}}

---

## Focus on two main approaches

(cf. [Ciatto et al., 2024](https://doi.org/10.1145/3645103))

- Symbolic Knowledge **Extraction** (_SKE_): extracting symbolic knowledge from sub-symbolic models
    * for the sake of _explainability_ and _interpretability_ in machine learning

- Symbolic Knowledge **Injection** (_SKI_): injecting symbolic knowledge into sub-symbolic models
    * for the sake of _trustworthiness_ and _robustness_ in machine learning

{{% fragment %}}
Both require some basic understanding of how _supervised_ __machine learning__ works
{{% /fragment %}}

---

{{< slide id="ml">}}

{{% section %}}

# Supervised Machine Learning 101

---

## Supervised Machine Learning 101 (pt. 1)

1. Let's say you have a __dataset__ of vectors in $\mathbb{R}^n$

{{% multicol %}}
{{% col %}}
2. Let's say the vectors are _labelled differently_ (2 colors)

{{< image src="./images/classification-1.png" alt="Example of vectors to be separated" width="100%" max-h="60vh" >}}

3. Let's say you want to __separate__ them
{{% /col %}}
{{% col %}}
2. Let's say the vectors are _aligned_ (along a curve)

{{< image src="./images/regression-1.png" alt="Example of vectors to be interpolated" width="100%" max-h="60vh" >}}

3. Let's say you want to __interpolate__ them
{{% /col %}}
{{% /multicol %}}

---

## Supervised Machine Learning 101 (pt. 2)

4. Then, need to _approximate_ the function _$f$_...

{{% multicol %}}
{{% col %}}
4. ... __separating them__ (the sigmoid here)

{{< image src="./images/classification-2.png" alt="Example of vectors to be separated, and the corresponding decision boundary" width="100%" max-h="60vh" >}}

5. The function $f$ is the __decision boundary__ (a.k.a. _classifier_)
{{% /col %}}
{{% col %}}
4. ...__interpolating them__ (the parabola here)

{{< image src="./images/regression-2.png" alt="Example of vectors to be interpolated, and the corresponding curve" width="100%" max-h="60vh" >}}

5. The function $f$ is the __regression curve__ (a.k.a. _regressor_)
{{% /col %}}
{{% /multicol %}}

6. <span style="color: red;">How to compute such a function $f$?</span>

---

## Supervised Machine Learning 101 (pt. 3)

### Let's formalize the problem (1/2)
<br>

1. Let's assume the data represented as a set of vectors in a __dataset__ $D \subset \mathbb{R}^n$ s.t. $|D| = m$
    - e.g. $D = \{(x_1, y_1, c_1), (x_2, y_2, c_2), \ldots, (x_m, y_m, c_m)\}$ for the classification dataset
    - e.g. $D = \{(x_1, y_1), (x_2, y_2), \ldots, (x_m, y_m)\}$ for the regression dataset
2. Let $\mathcal{X}$ (resp. $\mathcal{Y}$) be the _input_ (resp. output or _target_) _space_ of the data at hand
    - so $\exists X \in \mathcal{X}$ and $\exists Y \in \mathcal{Y}$ s.t. $(X, Y) \equiv D$
    - i.e. $X$ is the _input data_ and $Y$ is the _target data_ in $D$

{{< image src="./images/target.png" alt="Modelling of the dataset" width="50%" max-h="60vh" >}}

---

## Supervised Machine Learning 101 (pt. 4)

### Let's formalize the problem (2/2)
<br>

3. Let $\mathcal{H} = \lbrace f \mid f: \mathcal{X} \to \mathcal{Y}\rbrace$ be the set of all possible functions mapping $\mathcal{X}$ to $\mathcal{Y}$
    - i.e. the so-called __hypothesis space__
4. We need now to find __the best__ $f^* \in \mathcal{H}$
    - best w.r.t to what?
5. We need to define a __loss function__ $\mathcal{L}$ that quantifies the _difference_ between the _predicted output_ $f(X)$ and the _true output_ $Y$
    - for any possible $f \in \mathcal{H}$
6. So, our __learning problem__ is as simple as a __search problem__ in the hypothesis space:
    $$ f^* = \arg\min_{f \in \mathcal{H}} \mathcal{L}(f(X), Y) $$
7. Ok, but in _practice_, how do we do that?

---

## Supervised Machine Learning 101 (pt. 5)

### Let's solve the problem

<br>

1. How to _explore_ the _hypothesis space_, depends on what _sorts of functions_ it contains
2. There exist several sorts functions for which an __exploration algorithm__ is known
    - e.g. $\mathcal{H}$ $\equiv$ polynomials of degree $1$ (i.e. _lines_: $f(\bar{x}) = \beta + \bar{\omega} \cdot \bar{x} = \beta + \omega_1 x_1 + \ldots + \omega_n x_n$)
    - e.g. $\mathcal{H}$ $\equiv$ polynomials of degree $2$ (i.e. _parabolas_: $f(\bar{x}) = \beta + \omega_1 x_1 + \ldots + \omega_n x_n + \omega_1^2 x_1^2 + \ldots + \omega_n^2 x_n^2$)
    - e.g. $\mathcal{H}$ $\equiv$ decision trees (i.e. _if-then-else_ rules: $f(\bar{x}) = \text{if } x_1 \leq c_1 \text{ then } y_1 \text{ else if } x_2 \leq c_2 \text{ then } y_2 \ldots$)
    - e.g. $\mathcal{H}$ $\equiv$ $k$-nearest neighbors ($f(\bar{x}) = \text{class of (most of) the } k \text{ nearest neighbors of } \bar{x}$)
    - e.g. $\mathcal{H}$ $\equiv$ neural networks (i.e. _NNs_: $f(\bar{x}) = \sigma(\beta + \bar{\omega} \cdot \bar{x})$ where $\sigma$ is a non-linear activation function, e.g. sigmoid, ReLU, etc.)

{{% fragment %}}
> __Remark__: because of the ["no free lunch" theorem](https://en.wikipedia.org/wiki/No_free_lunch_theorem), _no_ single algorithm is the best in _the general case_
>  - i.e., each learning problem may be better addressed by a different learning algorithm
{{% /fragment %}}

---

## Supervised Machine Learning 101 (pt. 6)

### Let's solve the problem with __neural networks__

{{% multicol %}}
{{% col %}}
{{< image src="./images/neuron.png" alt="Functioning of a single neuron" width="100%" max-h="60vh" >}}

Single neuron
{{% /col %}}
{{% col %}}
{{< image src="./images/neural-network.png" alt="Functioning of a feed-forward neural network" width="100%" max-h="60vh" >}}

(Feed-forward)
<br>
Neural network $\equiv$ cascade of _layers_
{{% /col %}}
{{% col %}}
{{< image src="./images/nn-zoo.png" alt="Many sorts of neural architectures" width="100%" max-h="60vh" >}}

[Many admissible architectures](https://www.asimovinstitute.org/neural-network-zoo/)
{{% /col %}}
{{% /multicol %}}

{{% fragment %}}
> __Remark__: NN are [universal approximators](https://en.wikipedia.org/wiki/Universal_approximation_theorem), provided that they have enough neurons
{{% /fragment %}}

---

## Supervised Machine Learning 101 (pt. 7)

### Let's solve the problem with __gradient descent__

- NNs (and other ML algorithms) explore the hypothesis space by using a _gradient descent_ algorithm
- In this case:
    * the hypothesis space _$\mathcal{H}$ $\equiv$ "the set of all possible NNs with a given architecture"_
        + e.g. 4 input neurons, 2 hidden layers with 3 neurons each, and 1 output neuron, all layers fully connected, using ReLU activation functions
    * the loss function _$\mathcal{L}$ $\equiv$ "the difference between the predicted output and the true output"_
        + e.g. $\mathcal{L}(f(X), Y) = \frac{1}{n} \sum_{i=1}^{n} (f(x_i) - y_i)^2$ __(mean-squared error)__ for regression
        + e.g. $\mathcal{L}(f(X), Y) = -\sum_{i=1}^{n} y_i \log(f(x_i)) + (1 - y_i) \log(1 - f(x_i))$ __(cross-entropy)__ for classification
    * the algorithm _initializes the weights_ of the NN __randomly__, and then iteratively updates them by minimising the __gradient of the loss function__ w.r.t. the _weights_
        + i.e. $w_{i+1} = w_i - \eta \nabla_w \mathcal{L}(f(X), Y)$ where $\eta$ is the learning rate

    {{< image src="./images/gradient-descent.jpg" alt="Gradient descent algorithm (visualization of local minima)" width="45%" max-h="40vh" >}}
    <span width="10%"/>
    {{< image src="./images/train-loss.png" alt="Training loss over time" width="45%" max-h="40vh" >}}

    * the approach is _greedy_ and sensitive to _local minima_, but very _effective_ in practice

---

## Supervised Machine Learning 101 (pt. 8)

### How things may go wrong – *Under*fitting vs. *Over*fitting

{{< image src="./images/bias-variance-tradeoff-class.png" width="60%" max-h="40vh" alt="Bias-variance tradeoff for classification" >}}

{{< image src="./images/bias-variance-tradeoff-regr.png" width="60%" max-h="40vh" alt="Bias-variance tradeoff for regression" >}}

---

## Supervised Machine Learning 101 (pt. 9)

### How to address: Test-Set Separation

{{< image src="./images/train-test-separation.webp" alt="Train-test separation for supervised learning" width="100%" max-h="40vh" >}}

---

## Supervised Machine Learning 101 (pt. 10)

### How things may go wrong – Training is __stochastic__

{{% multicol %}}
{{% col %}}
Depending on its start, training may yield _different results_:

{{< image src="./images/gradient-descent.jpg" alt="Gradient descent algorithm (visualization of local minima)" width="100%" max-h="40vh" >}}
{{% /col %}}
{{% col %}}
Solution is __coss-validation__:

{{< image src="./images/k-fold.svg" alt="K-fold cross validation" width="100%" max-h="40vh" >}}
{{% /col %}}
{{% /multicol %}}

1. Train the _$k$ different models_ (same architecture) on $k$ different subsets of the training set
2. _Average_ the _results_ of the $k$ models
3. If average is good, the model is considered more _robust_ and _reliable_
     * useful when _comparing_ different _architectures_ or hyper-parameters

---

## Supervised Machine Learning 101 (pt. 11)

### How things may go wrong – Data may not be numeric

<br>

#### Solution: __change encoding__

{{% multicol %}}
{{% col %}}
{{< image src="./images/ordinal-encoding.png" alt="Example of ordinal encoding" width="80%" max-h="60vh" >}}

(_Ordinal_ encoding)
{{% /col %}}
{{% col %}}
{{< image src="./images/one-hot-encoding.png" alt="Example of one-hot encoding" width="100%" max-h="60vh" >}}

(_One-hot_ encoding)
{{% /col %}}
{{% /multicol %}}

---

## Supervised Machine Learning 101 (pt. 12)

### How things may go wrong – Data may _not_ be __separable__ by a proper function...

<br>

#### Solution: __feature engineering__ (map data into a different space)


{{% multicol %}}
{{% col %}}
{{< image src="./images/non-separable.png" alt="Non-linearly-separable data" width="100%" max-h="50vh" >}}

Non-linearly-separable data ...
<br>
$(x, y)$
{{% /col %}}
{{% col %}}
{{< image src="./images/non-separable-polar.png" alt="Linearly-separable data" width="100%" max-h="50vh" >}}

... may be separable in _another space_
<br>
$(\rho = \sqrt{x^2 + y^2}$, $\theta = \arctan(y/x))$
{{% /col %}}
{{% /multicol %}}


{{% /section %}}

---

{{< slide id="ske" >}}

# Symbolic Knowledge Extraction (SKE)

How to extract symbolic knowledge from sub-symbolic predictors

---

{{% section %}}

## Definition and Motivation (pt. 1)

> any _algorithmic procedure_ accepting trained sub-symbolic predictors as input and producing _symbolic_ knowledge as output, so that the extracted knowledge reflects the behaviour of the predictor with high _fidelity_.

---

## Definition and Motivation (pt. 2)

- **Explainable AI (XAI)**: SKE methods are often used to provide explanations for the decisions made by sub-symbolic predictors, making them more interpretable and understandable to humans (a.k.a. _post-hoc explainability_)
  - _local explanations_: explanations for individual predictions
  - _global explanations_: explanations for the overall behaviour of the predictor

- **Knowledge discovery**: SKE methods can help discover patterns and relationships in the data that may not be immediately apparent, thus providing insights into the underlying processes

- **Model compression**: SKE methods can simplify complex sub-symbolic models by extracting symbolic rules that approximate their behaviour, thus reducing the model's size and complexity

---


## Explainability vs Interpretability

They are _not_ synonyms in spite of the fact that they are often used interchangeably!

{{% multicol %}}

{{% col %}}

<h3 style="text-align: center; color: blue">
Explanation
</h3>

- elicits _relevant aspects_ of objects (to ease their interpretation)

- it is an operation that transform poorly interpretable objects into _more interpretable_ ones

- search of a _surrogate_ interpretable model

{{% /col %}}

{{% col %}}

<h3 style="text-align: center; color: blue">
Interpretation
</h3>

- binds objects with _meaning_ (what the human mind does)

- it is _subjective_

- it does not need to be measurable, only _comparisons_

{{% /col %}}

{{% /multicol %}}

---

## Concepts

Main entities and how to extract symbolic knowledge from sub-symbolic predictors

---

## Entities

{{% multicol %}}

{{% col %}}

<h3 style="text-align: center; color: blue">
Sub-symbolic predictor
</h3>

{{< image src="./images/nn-iris.png" alt="Example of a neural network trained on the Iris dataset" width="100%" max-h="60vh" >}}

{{% /col %}}

{{% col %}}

<h3 style="text-align: center; color: blue">
Symbolic knowledge
</h3>

<div style="margin-top: 10vh; margin-left: 5vw;">


| Logic Rule                                                                                                   |
|--------------------------------------------------------------------------------------------------------------|
| Class = setosa ← PetalWidth ≤ 1.0                                                                            |
| Class = versicolor ← PetalLength > 4.9 ∧ <br><div style="margin-left: 15vw;"> SepalWidth ∈ [2.9, 3.2] </div> |
| Class = versicolor ← PetalWidth > 1.6                                                                        |
| Class = virginica ← SepalWidth ≤ 2.9                                                                         |
| Class = virginica ← SepalLength ∈ [5.4, 6.3]                                                                 |
| Class = virginica ← PetalWidth ∈ [1.0, 1.6]                                                                  |

</div>

{{% /col %}}

{{% /multicol %}}

---

## How SKE works

{{% multicol %}}

{{% col %}}

<h3 style="text-align: center; color: blue">
Decompositional SKE
</h3>

> if the method _needs_ to inspect (even partially) the internal parameters of the underlying black-box predictor, e.g., neuron biases or connection weights for NNs, or support vectors for SVMs

{{% /col %}}

{{% col %}}

<h3 style="text-align: center; color: blue">
Pedagogical SKE
</h3>

> if the algorithm _does not need_ to take into account any internal parameter, but it can extract symbolic knowledge by only relying on the predictor’s outputs.

{{% /col %}}

{{% /multicol %}}

{{% /section %}}

---

## Overview
SKE methods: theory and practice

---

{{% section %}}

## CART (pt. 1)
Classification and regression trees (cf. [Breiman et al., 1984](https://doi.org/10.1201/9781315139470))

---

## CART (pt. 2)

{{< image src="./images/dt-kyphosis.png" alt="Example of a decision tree" width="80%" max-h="60vh" >}}

An example decision tree estimating the probability of kyphosis after spinal surgery, given the _age_ of the patient and the vertebra at which surgery was _start_ ed (rf. [wiki:dt-learning](https://en.wikipedia.org/w/index.php?title=Decision_tree_learning)).
Notice that all decision trees subtend a partition of the input space, and that those trees themselves provide intelligible representations of _how_ predictions are attained.

---

## CART (pt. 3)

1. generate a _synthetic_ dataset by using the predictions of the sub-symbolic predictor

2. _train_ a decision tree on the synthetic dataset

3. compute the _fidelity_ and repeat step 2 until satisfied

4. [optional] rewrite the tree as a set of symbolic _rules_

{{% /section %}}

---

{{% section %}}

## Practical example of SKE
The Adult dataset (cf. [Becker Barry and Kohavi Ronny, 1996](https://doi.org/10.24432/C5XW20))

---

## Adult classification task

The Adult dataset contains the records (48,842) of individuals based on census data (this dataset is also known as Census Income).
The dataset has many features (14) related to the individuals' demographics, such as age, education, and occupation.
The target feature is whether the individual earns more than $50,000 per year.

<br>

<div style="text-align: center; color: blue;">Examples of Adult records</div>

<br>

| age | workclass        | education | ... | hours-per-week | native-country | income |
|-----|------------------|-----------|-----|----------------|----------------|--------|
| 39  | State-gov        | Bachelors | ... | 40             | United-States  | <=50K  |
| 50  | Self-emp-not-inc | Bachelors | ... | 13             | United-States  | <=50K  |
| 38  | Private          | HS-grad   | ... | 40             | United-States  | <=50K  |
| 53  | Private          | 11th      | ... | 40             | United-States  | <=50K  |
| 28  | Private          | Bachelors | ... | 40             | Cuba           | <=50K  |
| 37  | Private          | Masters   | ... | 40             | United-States  | <=50K  |
| 49  | Private          | 9th       | ... | 16             | Jamaica        | <=50K  |
| 52  | Self-emp-not-inc | HS-grad   | ... | 45             | United-States  | >50K   |
| 31  | Private          | Masters   | ... | 50             | United-States  | >50K   |
| 42  | Private          | Bachelors | ... | 40             | United-States  | >50K   |


---

## What we will do

1. Download the Adult dataset and preprocess it

2. Train a sub-symbolic predictor -- a *neural network* -- on the Adult dataset

3. Use a *pedagogical SKE method* -- CART -- to extract symbolic knowledge from the trained neural network

4. Visualise the extracted symbolic knowledge as a *decision tree* and as a set of *rules*

---

## Jump to the code

GitHub repository at [github.com/MatteoMagnini/demo-2025-woa-nesy/blob/master/notebook/extraction.ipynb](https://github.com/MatteoMagnini/demo-2025-woa-nesy/blob/master/notebook/extraction.ipynb)

{{< image src="./images/ske-notebook-qr.svg" alt="QR code to the Jupyter notebook" width="20%" >}}

{{% /section %}}

---

{{% section %}}

## Taxonomy of SKE methods (pt. 1)

{{< image src="./images/ske-taxonomy.svg" alt="Taxonomy of SKE methods" width="80%" >}}

---

## Taxonomy of SKE methods (pt. 2)

{{% multicol %}}

{{% col %}}

{{% /col %}}

{{% col %}}

<h3 style="color: blue">
Target AI task
</h3>

- _classification_<br> $f: 𝒳 ⊆ ℝⁿ → 𝒴 s.t. |𝒴| = k$

- _regression_<br> $f: 𝒳 ⊆ ℝⁿ → 𝒴 ⊆ ℝᵐ$

{{% /col %}}

{{% col %}}

<h3 style="color: blue">
Input data
</h3>

- _binary_<br> $𝒳 ≡ {0, 1}ⁿ$

- _discrete_<br> $𝒳 ∈ {x₁, ..., xₙ}ⁿ$

- _continuous_<br> $𝒳 ⊆ ℝⁿ$

{{% /col %}}

{{% /multicol %}}

---

## Taxonomy of SKE methods (pt. 3)

{{% multicol %}}

{{% col %}}

<h3 style="text-align: center; color: blue">
Shape
</h3>

- _rule list_, ordered sequences of if-then-else rules

- _decision tree_, hierarchical set of if-then-else rules involving a comparison among a variable and a constant

- _decision table_, 2D tables summarising decisions for each possible assignment of the input variables

{{% /col %}}

{{% col %}}

<h3 style="text-align: center; color: blue">
Expressiveness
</h3>

- _propositional_, boolean statements + logic connectives, including arithmetic comparisons among variables and constants

- _fuzzy_, hierarchical set of if-then-else rules involving a comparison among a variable and a constant

- _oblique_, boolean statements + logic connectives + arithmetic comparisons

- _M-of-N_, any of the above + statements of the form "at least $k$ of the following statements are true"

{{% /col %}}

{{% /multicol %}}

{{% /section %}}

---

{{% section %}}

## Discussion

{{% multicol %}}

{{% col %}}

### **Notable remarks**

- discretisation of the input space

- discretisation of the output space

- features should have semantic meaning

- rules constitutes global explanations

{{% /col %}}

{{% col %}}

### **Limitations**

- tabular data as input, no images

- high dimensional datasets could lead to poorly readable rules

- high variable input spaces could do the same

{{% /col %}}

{{% /multicol %}}

---

## Future research activities

- target images or highly dimensional data in general

- target reinforcement learning (when based on NN)

- target unsupervised learning

- design and prototype your own extraction algorithm

{{% /section %}}

---

{{< slide id="ski" >}}

# Symbolic Knowledge Injection (SKI)

How to inject symbolic knowledge into sub-symbolic predictors

---

{{% section %}}

## Definition and Motivation (pt. 1)


> Any algorithmic procedure affecting how sub-symbolic predictors draw their inferences in such a way that predictions are either _computed_ as a function of, or _made consistent_ with, some given symbolic knowledge.

---

## Definition and Motivation (pt. 2)

- **Improve predictive performance**: by injecting symbolic knowledge, we can
  - _guide_ the learning process in order to _penalise_ inconsistencies with the symbolic knowledge, or
  - _structure_ the model's architecture to _mimic_ the symbolic knowledge

- **Enhance interpretability**: with SKI we can make predictors that are
  - interpretable by _transparent box design_, as they are built to mimic symbolic knowledge
  - interpretable using _symbols as constraints_, as they are built to respect symbolic knowledge

- **Robustness to data degradation**: symbolic knowledge can help sub-symbolic models maintain performance even in the presence of noisy or scarcity of data

- **Enhance fairness**: by incorporating symbolic knowledge about fairness constraints, we can ensure that sub-symbolic models make decisions that align with ethical considerations

- **And more**: SKI can simplify the predictor's architecture, in particular it can reduce the number of weights in a neural network, thus improving its efficiency and reducing the risk of overfitting

---

## Concepts
Main entities and how to inject symbolic knowledge into sub-symbolic predictors

---

## Entities

- **Predictor**: a sub-symbolic model that makes predictions based on input data, usually a neural network

- **Symbolic knowledge**: structured, formal knowledge that can be represented in a symbolic form. The most common forms of symbolic knowledge are
  - _Propositional logic_, simple rules with if-then structure
  - _Datalog_, a subset of first-order logic with no function symbols, only constants and variables

- **Fuzzification**: the process of converting symbolic knowledge into a form that can be used by sub-symbolic predictors, e.g. by assigning degrees of truth to symbolic statements

- **Injector**: the main component that injects symbolic knowledge into the predictor, by modifying its architecture, its training process or by other means

---

## Structuring


{{< image src="./images/workflow-structuring.svg" alt="Overview of structuring injection mechanism" width="80%" >}}

---

## Constraining

{{< image src="./images/workflow-constraining.svg" alt="Overview of constraining injection mechanism" width="80%" >}}

---

## Embedding

{{< image src="./images/workflow-embedding.svg" alt="Overview of embedding injection mechanism" width="80%" >}}

{{% /section %}}

---

## Overview

SKI methods: theory and practice

---

{{% section %}}

## Knowledge Injection via Network Structuring (KINS)
(ref. [Magnini et al., 2023](https://doi.org/10.1093/LOGCOM/EXAD037))

---

## Fuzzification

| Formula                  | C. interpretation                                      | Formula                                       | C. interpretation                      |
|--------------------------|--------------------------------------------------------|-----------------------------------------------|----------------------------------------|
| $[[ \neg \phi ]]$        | $\eta(1 - [[ \phi ]])$                                 | $[[ \phi \le \psi ]]$                         | $\eta(1 + [[ \psi ]] - [[ \phi ]])$    |
| $[[ \phi \wedge \psi ]]$ | $\eta(\min([[ \phi ]], [[ \psi ]]))$                   | $[[ class(\bar{X}, {y}_i) \leftarrow \psi ]]$ | $[[ \psi ]]^{*}$                       |
| $[[ \phi \vee \psi ]]$   | $\eta(\max([[ \phi ]], [[ \psi ]]))$                   | $[[ \text{expr}(\bar{X}) ]]$                  | $\text{expr}([[ \bar{X} ]])$           |
| $[[ \phi = \psi ]]$      | $\eta([[ \neg( \phi \ne \psi ) ]])$                    | $[[ \mathtt{true} ]]$                         | $1$                                    |
| $[[ \phi \ne \psi ]]$    | $\eta(\| [[ \phi ]] - [[ \psi ]]\|)$                   | $[[ \mathtt{false} ]]$                        | $0$                                    |
| $[[ \phi > \psi ]]$      | $\eta(\max(0, \frac{1}{2} + [[ \phi ]] - [[ \psi ]]))$ | $[[ X ]]$                                     | $x$                                    |
| $[[ \phi \ge \psi ]]$    | $\eta(1 + [[ \phi ]] - [[ \psi ]])$                    | $[[ k ]]$                                     | $k$                                    |
| $[[ \phi < \psi ]]$      | $\eta(\max(0, \frac{1}{2} + [[ \psi ]] - [[ \phi ]]))$ | $[[ p(\bar{X}) ]]^{**}$                       | $[[ \psi_1 \vee \ldots \vee \psi_k ]]$ |


> $^{*}$ encodes the value for the $i^{\text{th}}$ output
> $^{**}$ assuming $p$ is defined by $k$ clauses of the form:
> ${p}(\bar{X}) \leftarrow \psi_1,\ \ldots,\ {p}(\bar{X}) \leftarrow \psi_k$

---

## Injector (pt.1)

{{< image src="./images/neurons.svg" alt="Example of one possible mapping between the continuous interpretation of a symbolic formula and the neurons" width="80%" >}}

---

## Injector (pt. 2)

{{< image src="./images/net-architecture.svg" alt="Example of a neural network architecture with an injector" width="80%" >}}

{{% /section %}}

---

{{% section %}}

## Knowledge Injection via Lambda Layer (KILL)
(ref. [Magnini et al., 2022](https://ceur-ws.org/Vol-3261/paper5.pdf))

---

## Fuzzification

| **Formula**            | **C. interpretation**                                |   | **Formula**                                         | **C. interpretation**                |
|------------------------|------------------------------------------------------|---|-----------------------------------------------------|--------------------------------------|
| \[\[\neg \phi]]        | $\eta(1 - [[\phi]])$                                 |   | \[\[\phi \le \psi]]                                 | $\eta([[\phi]] - [[\psi]])$          |
| \[\[\phi \wedge \psi]] | $\eta(\max([[\phi]], [[\psi]]))$                     |   | $[\mathrm{class}(\bar{X}, {y}_i) \leftarrow \psi]]$ | $[[\psi]]^{*}$                       |
| \[\[\phi \vee \psi]]   | $\eta(\min([[\phi]], [[\psi]]))$                     |   | $[\text{expr}(\bar{X})]]$                           | $\text{expr}([[\bar{X}]])$           |
| \[\[\phi = \psi]]      | $\eta(\left\lvert [[\phi]] - [[\psi]] \right\rvert)$ |   | $[[\mathtt{true}]]$                                 | $0$                                  |
| \[\[\phi \ne \psi]]    | $[[\neg(\phi = \psi)]]$                              |   | $[[\mathtt{false}]]$                                | $1$                                  |
| \[\[\phi > \psi]]      | $\eta(\frac{1}{2} - [[\phi]] + [[\psi]])$            |   | $[[X]]$                                             | $x$                                  |
| \[\[\phi \ge \psi]]    | $\eta([[\psi]] - [[\phi]])$                          |   | $[[{k}]]$                                           | $k$                                  |
| \[\[\phi < \psi]]      | $\eta(\frac{1}{2} + [[\phi]] - [[\psi]])$            |   | $[\mathrm{p}(\bar{X})]]^{**}$                       | $[[\psi_1 \vee \ldots \vee \psi_k]]$ |

> $^{*}$ encodes the penalty for the $i^{\text{th}}$ neuron
> $^{**}$ assuming predicate $p$ is defined by $k$ clauses of the form:
> ${p}(\bar{X}) \leftarrow \psi_1,\ \ldots,\ {p}(\bar{X}) \leftarrow \psi_k$

---

## Injector (pt.1)

*Cost function*: whenever the neural network wrongly predicts a class and violates the prior knowledge a cost proportional to the violation is added.
In this way the output of the network differs more from the expected one and this affects the back propagation step.
<br><br>
<div style="border: 1px solid #ddd; padding: 1em; background-color: #f9f9f9; border-radius: 8px; overflow-x: auto;">
$$
\begin{aligned}
Y' &= f(Y, \mathrm{cost}) \\\\
f &= Y \times (\mathbf{1} + \mathrm{cost}) \\\\
\mathrm{cost}(X, Y) &= \eta(\mathrm{p}(X) - (\mathbf{1} - Y)) \quad \text{(}\mathbf{1} - Y\text{ because 0 means true)}
\end{aligned}
$$
</div>

---

## Injector (pt. 2)

{{< image src="./images/lambda-layer.svg" alt="Example of a neural network architecture with a lambda layer" width="80%" >}}

{{% /section %}}

---

{{% section %}}

## Practical example of SKI
The poker hand data set (PHDS) (cf. [Cattral Robert and Oppacher Franz, 2002](https://doi.org/10.24432/C5KW38))

---

## PHDS classification task

{{% multicol %}}

{{% col %}}

<div style="margin-top: 25vh; margin-left: 5vw;">

- Each record represents one poker hand

- 5 cards identified by 2 values: suit and rank

- Classes: 10

- Training set: 25,010

- Test set: 1,000,000

</div>

{{% /col %}}

{{% col %}}

| **id** | **S1** | **R1** | **S2** | **R2** | **S3** | **R3** | **S4** | **R4** | **S5** | **R5** | **class** |
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|-----------|
| 1      | 1      | 10     | 1      | 11     | 1      | 13     | 1      | 12     | 1      | 1      | 9         |
| 2      | 2      | 11     | 2      | 13     | 2      | 10     | 2      | 12     | 2      | 1      | 9         |
| 3      | 3      | 12     | 3      | 11     | 3      | 13     | 3      | 10     | 3      | 1      | 9         |
| 4      | 4      | 10     | 4      | 11     | 4      | 1      | 4      | 13     | 4      | 12     | 9         |
| 5      | 4      | 1      | 4      | 13     | 4      | 12     | 4      | 11     | 4      | 10     | 9         |
| 6      | 1      | 2      | 1      | 4      | 1      | 5      | 1      | 3      | 1      | 6      | 8         |
| 7      | 1      | 9      | 1      | 12     | 1      | 10     | 1      | 11     | 1      | 13     | 8         |
| 8      | 2      | 1      | 2      | 2      | 2      | 3      | 2      | 4      | 2      | 5      | 8         |
| 9      | 3      | 5      | 3      | 6      | 3      | 9      | 3      | 7      | 3      | 8      | 8         |
| 10     | 4      | 1      | 4      | 4      | 4      | 2      | 4      | 3      | 4      | 5      | 8         |
| 11     | 1      | 1      | 2      | 1      | 3      | 9      | 1      | 5      | 2      | 3      | 1         |
| 12     | 2      | 6      | 2      | 1      | 4      | 13     | 2      | 4      | 4      | 9      | 0         |
| 13     | 1      | 10     | 4      | 6      | 1      | 2      | 1      | 1      | 3      | 8      | 0         |
| 14     | 2      | 13     | 2      | 1      | 4      | 4      | 1      | 5      | 2      | 11     | 0         |
| 15     | 3      | 8      | 4      | 12     | 3      | 9      | 4      | 2      | 3      | 2      | 1         |


{{% /col %}}

{{% /multicol %}}

---

## Logic rules to inject (pt. 1)

| **Class**     | **Logic Formulation**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Pair**      | `class(R₁, ..., S₅, pair) ← pair(R₁, ..., S₅)`<br>`pair(R₁, ..., S₅) ← R₁ = R₂`<br>`pair(R₁, ..., S₅) ← R₁ = R₃`<br>`pair(R₁, ..., S₅) ← R₁ = R₄`<br>`pair(R₁, ..., S₅) ← R₁ = R₅`<br>`pair(R₁, ..., S₅) ← R₂ = R₃`<br>`pair(R₁, ..., S₅) ← R₂ = R₄`<br>`pair(R₁, ..., S₅) ← R₂ = R₅`<br>`pair(R₁, ..., S₅) ← R₃ = R₄`<br>`pair(R₁, ..., S₅) ← R₃ = R₅`<br>`pair(R₁, ..., S₅) ← R₄ = R₅`                                                                                                                                                                                                                                                                                                           |


---

## Logic rules to inject (pt. 2)

| **Class**     | **Logic Formulation**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Two Pairs** | `class(R₁, ..., S₅, two) ← two(R₁, ..., S₅)`<br>`two(R₁, ..., S₅) ← R₁ = R₂ ∧ R₃ = R₄`<br>`two(R₁, ..., S₅) ← R₁ = R₃ ∧ R₂ = R₄`<br>`two(R₁, ..., S₅) ← R₁ = R₄ ∧ R₂ = R₃`<br>`two(R₁, ..., S₅) ← R₁ = R₂ ∧ R₃ = R₅`<br>`two(R₁, ..., S₅) ← R₁ = R₃ ∧ R₃ = R₅`<br>`two(R₁, ..., S₅) ← R₁ = R₅ ∧ R₂ = R₃`<br>`two(R₁, ..., S₅) ← R₁ = R₂ ∧ R₄ = R₅`<br>`two(R₁, ..., S₅) ← R₁ = R₄ ∧ R₂ = R₅`<br>`two(R₁, ..., S₅) ← R₁ = R₅ ∧ R₂ = R₄`<br>`two(R₁, ..., S₅) ← R₁ = R₃ ∧ R₄ = R₅`<br>`two(R₁, ..., S₅) ← R₁ = R₄ ∧ R₃ = R₅`<br>`two(R₁, ..., S₅) ← R₁ = R₅ ∧ R₃ = R₄`<br>`two(R₁, ..., S₅) ← R₂ = R₃ ∧ R₄ = R₅`<br>`two(R₁, ..., S₅) ← R₂ = R₄ ∧ R₃ = R₅`<br>`two(R₁, ..., S₅) ← R₂ = R₅ ∧ R₃ = R₄` |

---

## Logic rules to inject (pt. 3)

| **Class**           | **Logic Formulation**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Three of a Kind** | `class(R₁, ..., S₅, three) ← three(R₁, ..., S₅)`<br>`three(R₁, ..., S₅) ← R₁ = R₂ ∧ R₁ = R₃`<br>`three(R₁, ..., S₅) ← R₁ = R₂ ∧ R₁ = R₄`<br>`three(R₁, ..., S₅) ← R₁ = R₂ ∧ R₁ = R₅`<br>`three(R₁, ..., S₅) ← R₁ = R₃ ∧ R₁ = R₄`<br>`three(R₁, ..., S₅) ← R₁ = R₃ ∧ R₁ = R₅`<br>`three(R₁, ..., S₅) ← R₁ = R₄ ∧ R₁ = R₅`<br>`three(R₁, ..., S₅) ← R₂ = R₃ ∧ R₂ = R₄`<br>`three(R₁, ..., S₅) ← R₂ = R₃ ∧ R₂ = R₅`<br>`three(R₁, ..., S₅) ← R₂ = R₄ ∧ R₂ = R₅`<br>`three(R₁, ..., S₅) ← R₃ = R₄ ∧ R₃ = R₅` |
| **Flush**           | `class(R₁, ..., S₅, flush) ← flush(R₁, ..., S₅)`<br>`flush(R₁, ..., S₅) ← S₁ = S₂ ∧ S₁ = S₃ ∧ S₁ = S₄ ∧ S₁ = S₅`                                                                                                                                                                                                                                                                                                                                                                                         |

---

## What we will do

1. Download the PHDS dataset and preprocess it

2. Define the *symbolic knowledge* to inject

3. Train a sub-symbolic predictor -- a *neural network* -- on the PHDS dataset

4. Train a second neural network with the symbolic knowledge injected

5. We will inject the knowledge in the *loss function*

6. Visualise and compare the results of the two predictors

---

## Jump to the code!

GitHub repository at [github.com/MatteoMagnini/demo-2025-woa-nesy/blob/master/notebook/injection.ipynb](http:github.com/MatteoMagnini/demo-2025-woa-nesy/blob/master/notebook/injection.ipynb)

{{< image src="./images/ski-notebook-qr.svg" alt="QR code to the Jupyter notebook" width="20%" >}}

{{% /section %}}

---

{{% section %}}

## Taxonomy of SKI methods (pt. 1)

{{< image src="./images/ski-taxonomy.svg" alt="Taxonomy of SKI methods" width="80%" >}}

---

## Taxonomy of SKI methods (pt. 2)

- **input knowledge**: how is the knowledge to-be-injected represented?
  - commonly, some sub-set of first-order logic (FOL)

- **target predictor**: which predictors can knowledge be injected into?
  - mostly, neural networks

- **strategy**: how does injection actually work?
  - _guided learning_: the input knowledge is used to _guide the training_ process
  - _structuring_: the _internal_ composition of the predictor is _(re-)structured_ to reflect the input knowledge
  - _embedding_: the input knowledge is _converted_ into numeric array form

- **purpose**: why is knowledge injected in the first place?
  - _knowledge manipulation_: improve / extend / reason about symbol knowledge—subsymbolically
  - _learning support_: improve the sub-symbolic predictor (e.g. speed, size, etc.)

{{% /section %}}

---

{{% section %}}

## Discussion

{{% multicol %}}

{{% col %}}

<h3 style="text-align: center; color: blue">
Notable remarks
</h3>

- Knowledge should express relations about input-output pairs

- embedding implies _extensional_ representation of knowledge

- guided learning and structuring support _intensional_ knowledge

- propositional knowledge implies binarising the I/O space

{{% /col %}}

{{% col %}}

<h3 style="text-align: center; color: blue">
Limitations
</h3>

- Recursive data structures are natively not supported

- extensional representation cost storage

- guided learning works poorly with lacking data

{{% /col %}}

{{% /multicol %}}

---

## Future research activities

- _foundational_<br> address recursion

- _practical_<br> find a language that is a good balance between expressiveness and ease of use

- _target_<br> apply to large language models

{{% /section %}}