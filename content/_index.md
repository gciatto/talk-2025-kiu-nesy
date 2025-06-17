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

- $grab(X)`: grabs block $X$ from the table
- $put(X)`: puts block $X$ on the table
- $stack(X, Y)`: stacks block $X$ on top of block $Y`
- $unstack(X, Y)`: un-stacks block $X$ from block $Y`

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
    + e.g. `"bear"$ is a symbol denoting a crisp category (either the animal is a bear or not)

- __Distributed__ $\approx$ "non-symbolic": symbols do not have a clear meaning per se, but the whole representation does
    + e.g. `"swim"$ is fuzzy capability: one animal may be (un)able to swim to some extent

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

{{% /section %}}

---

{{% section %}}

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

## Knowledge injection via Network Structuring (KINS)

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

## Practical example with KINS
The primate splice-junction gene sequences dataset (PSJGS)

---

## PSJGS classification task

The PSJGS dataset is a collection of DNA sequences from primate splice junction genes, where the task is to classify each sequence as either an _exon-intron_ (EI) or an _intron-exon_ (IE) sequence, or as _not applicable_ (N).

{{% multicol %}}

{{% col %}}

<div style="text-align: center;">Classification rules</div>

```text
EI-stop ::- @-3 'TAA'.
EI-stop ::- @-3 'TAG'.
EI-stop ::- @-3 'TGA'.
EI-stop ::- @-4 'TAA'.
EI-stop ::- @-4 'TAG'.
EI-stop ::- @-4 'TGA'.
EI-stop ::- @-5 'TAA'.
EI-stop ::- @-5 'TAG'.
EI-stop ::- @-5 'TGA'.

IE-stop ::- @1 'TAA'.
IE-stop ::- @1 'TAG'.
IE-stop ::- @1 'TGA'.
IE-stop ::- @2 'TAA'.
IE-stop ::- @2 'TAG'.
IE-stop ::- @2 'TGA'.
IE-stop ::- @3 'TAA'.
IE-stop ::- @3 'TAG'.
IE-stop ::- @3 'TGA'.

pyramidine-rich :- 6 of (@-15 'YYYYYYYYYY').

EI :- @-3 'MAGGTRAGT', not(EI-stop).

IE :- pyramidine-rich, @-3 'YAGG', not(IE-stop).
```

{{% /col %}}

{{% col %}}

<div style="text-align: center;">Examples of DNA sequences</div>

```csv
Class, Id, DNA-sequence

EI,ATRINS-DONOR-521,CCAGCTGCAT...AGCCAGTCTG
EI,ATRINS-DONOR-905,AGACCCGCCG...GTGCCCCCGC
EI,BABAPOE-DONOR-30,GAGGTGAAGG...CACGGGGATG
...
IE,ATRINS-ACCEPTOR-701,TTCAGCGGCC...GCCCTGTGGA
IE,ATRINS-ACCEPTOR-1678,GGACCTGCTC...GGGGGCTCTA
IE,BABAPOE-ACCEPTOR-801,GCGGTTGATT...AAGATGAAGG
...
N,AGMKPNRSB-NEG-1,CAAAAGAACA...CAAGGCTACA
N,AGMORS12A-NEG-181,AGGGAGGTGT...GGGCATGGGG
N,AGMORS9A-NEG-481,TGGTCAATTC...TCTTGCTCTG
...

3190 Records
```

{{% /col %}}

{{% /multicol %}}

---

## Logic rules to inject (pt. 1)

| Class | Logic rules                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|:------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EI    | $class(\bar{X}, ei) ← X_{-3} = m ∧ X_{-2} = a ∧ X_{-1} = g ∧ X_{+1} = g ∧ X_{+2} = t ∧{} $ <br> <span style="padding-left: 7.5em;"></span> $X_{+3} = a = r ∧ X_{+4} = a ∧ X_{+5} = g ∧ X_{+6} = t ∧ ¬(eiStop(\bar{X}))$ <br><br> $eiStop(\bar{X}) ← X_{-3} = t ∧ X_{-2} = a ∧ X_{-1} = a$ <br> $eiStop(\bar{X}) ← X_{-3} = t ∧ X_{-2} = a ∧ X_{-1} = g$ <br> $eiStop(\bar{X}) ← X_{-3} = t ∧ X_{-2} = g ∧ X_{-1} = a$ <br> $eiStop(\bar{X}) ← X_{-4} = t ∧ X_{-3} = a ∧ X_{-2} = a$ <br> $eiStop(\bar{X}) ← X_{-4} = t ∧ X_{-3} = a ∧ X_{-2} = g$ <br> $eiStop(\bar{X}) ← X_{-4} = t ∧ X_{-3} = g ∧ X_{-2} = a$ <br> $eiStop(\bar{X}) ← X_{-5} = t ∧ X_{-4} = a ∧ X_{-3} = a$ <br> $eiStop(\bar{X}) ← X_{-5} = t ∧ X_{-4} = a ∧ X_{-3} = g$ <br> $eiStop(\bar{X}) ← X_{-5} = t ∧ X_{-4} = g ∧ X_{-3} = a$ |

---

## Logic rules to inject (pt. 2)


| Class | Logic rules                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|:------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IE    | $class(\bar{X}, ie) ← pyramidineRich(\bar{X}) ∧ ¬(ieStop(\bar{X})) ∧ X_{-3} = y ∧ X_{-2} = a ∧ X_{-1} = g ∧ X_{+1} = g$ <br><br> $pyramidineRich(\bar{X}) ← 6 ≤ (X_{-15} = y + ... + X_{-6} = y)$ <br><br> $ieStop(\bar{X}) ← X_{+2} = t ∧ X_{+3} = a ∧ X_{+4} = a$ <br> $ieStop(\bar{X}) ← X_{+2} = t ∧ X_{+3} = a ∧ X_{+4} = g$ <br> $ieStop(\bar{X}) ← X_{+2} = t ∧ X_{+3} = g ∧ X_{+4} = a$ <br> $ieStop(\bar{X}) ← X_{+3} = t ∧ X_{+4} = a ∧ X_{+5} = a$ <br> $ieStop(\bar{X}) ← X_{+3} = t ∧ X_{+4} = a ∧ X_{+5} = g$ <br> $ieStop(\bar{X}) ← X_{+3} = t ∧ X_{+4} = g ∧ X_{+5} = a$ <br> $ieStop(\bar{X}) ← X_{+4} = t ∧ X_{+5} = a ∧ X_{+6} = a$ <br> $ieStop(\bar{X}) ← X_{+4} = t ∧ X_{+5} = a ∧ X_{+6} = g$ <br> $ieStop(\bar{X}) ← X_{+4} = t ∧ X_{+5} = g ∧ X_{+6} = a$ |

---

## Jump to the code!

TBD!!!

{{% /section %}}

---

{{% section %}}

## Knowledge injection via Lambda Layer (KILL)

---

{{% /section %}}


