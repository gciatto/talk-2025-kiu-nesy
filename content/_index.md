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

{{< image src="./images/classification-vs-regression2.png" alt="Classification vs. Regression: finite vs. continous target feature" width="100%" max-h="60vh" >}}

{{% /section %}}