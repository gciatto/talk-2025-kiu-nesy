+++

title = "SKE & SKI: Theory and Methods"
description = "Symbolic Knowledge Extraction and Injection: Theory and Methods"
outputs = ["Reveal"]

+++

{{% section %}}

# Symbolic Knowledge Extraction and Injection:<br>Theory and Methods

{{< gc >}} and {{< mm >}}
<br>Dipartimento di Informatica — Scienza e Ingegneria (DISI), Sede di Cesena,
<br> Alma Mater Studiorum—Università di Bologna

<span class="hint">(last built on: {{< today >}})</span>

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
    + e.g. 
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
Both require some basic understanding of how machine learning works
{{% /fragment %}}

---

# Machine Learning 101

---

TBD