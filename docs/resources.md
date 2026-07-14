# Curated Resources

This page favors reliable starting points over long lists. Each item is labeled
so that readers can see whether it is core topos theory, sheaf-theoretic,
AI-relevant, or broader applied category theory.

## Recent Surveys

### Category Theory in Machine Learning

- Link: <https://arxiv.org/abs/2106.07032>
- Authors: Dan Shiebler, Bruno Gavranovic, Paul Wilson
- Labels: Applied Category Theory, AI-Relevant
- Level: intermediate
- Why it matters: A 2021 survey of category-theoretic approaches to machine
  learning, organized around gradient-based learning, categorical probability,
  and invariant/equivariant learning.
- Caution: This is a broad applied category theory survey rather than a
  topos-theoretic paper. Use it to understand the categorical ML background
  that later topos-based surveys build on.

### Category-Theoretical and Topos-Theoretical Frameworks in Machine Learning: A Survey

- Links: <https://arxiv.org/abs/2408.14014>,
  <https://doi.org/10.3390/axioms14030204>
- Authors: Yiyang Jia, Guohong Peng, Zheng Yang, Tianhao Chen
- Labels: Applied Category Theory, AI-Relevant, Speculative Bridge
- Level: intermediate to advanced
- Why it matters: A 2025 survey that organizes category-derived machine
  learning around gradient-based learning, probability-based learning,
  invariance/equivalence-based learning, and topos-based learning.
- Caution: Valuable as a map of recent claims and references, but many of the
  topos-based ML directions are still exploratory. Read its topos sections
  alongside primary sources and the taxonomy in this repository.

## Direct Topos-Based ML Proposals

### Some Possible Roles for AI of Grothendieck Topos Theory

- Link: <https://www.laurentlafforgue.org/Expose_Lafforgue_topos_AI_ETH_sept_2022.pdf>
- Author: Laurent Lafforgue
- Labels: Core Topos, AI-Relevant, Speculative Bridge
- Level: advanced
- Why it matters: A programmatic 2022 lecture sketching why Grothendieck
  topoi, sheaf-theoretic completions, sites, symmetries, and meaningful
  invariants might matter for AI.
- Caution: This is a research vision rather than a ready-made ML method. Read
  it after presheaves, sheaves, sites, and Grothendieck topoi are familiar.

### Topos and Stacks of Deep Neural Networks

- Link: <https://arxiv.org/abs/2106.14587>
- Authors: Jean-Claude Belfiore, Daniel Bennequin
- Labels: Core Topos, AI-Relevant, Speculative Bridge
- Level: advanced
- Why it matters: Proposes that deep neural networks can be represented as
  objects in canonical Grothendieck topoi, with learning dynamics as morphism
  flows and invariance structures modeled through Giraud stacks. The arXiv v3
  manuscript is a long, technically ambitious 2022 treatment connecting DNN
  architectures, stacks, internal logics, model categories, homology, and
  type-theoretic semantics.
- Caution: Ambitious and technically heavy. Treat it as a research framework,
  not a standard ML method. Requires sheaves, Grothendieck topoi, fibered
  categories/stacks, and some logic or type-theoretic maturity.

### The Topos of Transformer Networks

- Link: <https://arxiv.org/abs/2403.18415>
- Authors: Mattia Jacopo Villani, Peter McBurney
- Labels: Core Topos, AI-Relevant, Speculative Bridge, Verify First
- Level: advanced
- Why it matters: Studies transformer expressivity through topos theory,
  arguing that common neural architectures embed in a pretopos of
  piecewise-linear functions while transformers live in its topos completion.
- Caution: The arXiv page marks the paper as withdrawn and requiring major
  revision. Treat it as a pointer to an idea, not as a stable result. Best read
  only after learning pretopoi, topos completion, and the basic categorical view
  of neural architectures.

### Topos Theory for Generative AI and LLMs

- Link: <https://arxiv.org/abs/2508.08293>
- Author: Sridhar Mahadevan
- Labels: AI-Relevant, Speculative Bridge
- Level: advanced
- Why it matters: Explores whether universal constructions in topos theory can
  inspire new generative AI and LLM architectures.
- Caution: Treat as a speculative recent proposal. Check the mathematical
  assumptions carefully before using it as a foundation.

### PROMETHEUS: Automating Deep Causal Research Integrating Text, Data and Models

- Link: <https://arxiv.org/abs/2605.12835>
- Author: Sridhar Mahadevan
- Labels: Sheaf-Theoretic, AI-Relevant, Speculative Bridge
- Level: advanced
- Why it matters: Proposes "causal atlases" and "Topos World Models" built from
  sheaf-like families of local causal predictive-state models over explicit
  covers of research corpora, with restriction maps and gluing diagnostics for
  agreement, drift, contradiction, and underdetermination.
- Caution: This is a recent speculative AI-research framework rather than
  established Grothendieck topos theory. Read it as an LLM/causal-research
  application idea using sheaf/topos language.

## Information Cohomology and Semantic Information

### The Homological Nature of Entropy

- Link: <https://doi.org/10.3390/e17053253>
- Authors: Pierre Baudot, Daniel Bennequin
- Labels: Applied Category Theory, AI-Relevant, Speculative Bridge
- Level: advanced
- Why it matters: Develops entropy, mutual information, and related
  information quantities as cohomological invariants of information structures,
  including classical, quantum, and dynamic probability settings.
- Caution: This is not a machine learning architecture paper. It is useful
  background for the semantic-information and homological language used in
  later DNN/topos proposals, especially Belfiore-Bennequin.

### Information Structures and Their Cohomology

- Link: <https://arxiv.org/abs/1709.07807>
- Author: Juan Pablo Vigneaux
- Labels: Core Topos, Applied Category Theory, AI-Relevant
- Level: advanced
- Why it matters: Recasts information structures as categories of observables,
  ringed sites, and sheaf/topos-flavored objects, extending information
  cohomology as a derived-functor construction.
- Caution: Best read as mathematical background on contextuality, entropy, and
  information cohomology rather than as a direct topos-based ML method.

## Category Theory Prerequisites

### Basic Category Theory

- Link: <https://arxiv.org/abs/1612.09375>
- Author: Tom Leinster
- Labels: Applied Category Theory, prerequisite
- Level: beginner
- Why it matters: A clear route through the basic categorical language needed
  before reading about topoi.

### Category Theory in Context

- Link: <https://emilyriehl.github.io/files/context.pdf>
- Author: Emily Riehl
- Labels: Applied Category Theory, prerequisite
- Level: intermediate
- Why it matters: Strong on adjunctions, limits, Kan extensions, and the style
  of categorical reasoning used later in topos theory.

### Category Theory

- Link: <https://global.oup.com/academic/product/category-theory-9780199237180>
- Author: Steve Awodey
- Labels: Applied Category Theory, Core Topos
- Level: beginner to intermediate
- Why it matters: A standard entry point with material on cartesian closed
  categories and elementary topoi.

### Sites and Grothendieck Toposes: An Introduction

- Link: <https://arxiv.org/abs/2508.21609>
- Authors: Olivia Caramello, Laurent Lafforgue
- Labels: Core Topos
- Level: intermediate
- Why it matters: A progressive introduction from categories and sheaves to
  Grothendieck topologies, sites, Giraud-style foundations, morphisms, points,
  subtoposes, and classifying topoi.
- Caution: More relevant after the first pass through basic category theory and
  presheaves.

## Core Topos Theory

### Sheaves in Geometry and Logic

- Link: <https://link.springer.com/book/10.1007/978-1-4612-0927-0>
- Authors: Saunders Mac Lane, Ieke Moerdijk
- Labels: Core Topos
- Level: intermediate
- Why it matters: The most natural first serious book on sheaves, sites,
  Grothendieck topoi, and logic.

### Sketches of an Elephant

- Link: <https://global.oup.com/academic/product/sketches-of-an-elephant-a-topos-theory-compendium-volume-1-9780198534259>
- Author: Peter Johnstone
- Labels: Core Topos
- Level: advanced
- Why it matters: A major reference for serious topos theory. Best used after
  a first pass through Mac Lane and Moerdijk or equivalent notes.

### nLab: Topos

- Link: <https://ncatlab.org/nlab/show/topos>
- Labels: Core Topos
- Level: intermediate to advanced
- Why it matters: Useful as a reference map, especially for related concepts
  and terminology.
- Caution: nLab is dense. It is better as a companion reference than as a first
  textbook.

### nLab: Grothendieck Topos

- Link: <https://ncatlab.org/nlab/show/Grothendieck+topos>
- Labels: Core Topos
- Level: intermediate to advanced
- Why it matters: Connects the sheaf-on-a-site definition with broader
  categorical and geometric perspectives.

### nLab: Elementary Topos

- Link: <https://ncatlab.org/nlab/show/elementary+topos>
- Labels: Core Topos
- Level: intermediate
- Why it matters: Gives the finite-limits, exponentials, and subobject
  classifier perspective.

## Sheaves, Data, and Contextuality

### The Sheaf-Theoretic Structure of Non-Locality and Contextuality

- Link: <https://arxiv.org/abs/1102.0264>
- Authors: Samson Abramsky, Adam Brandenburger
- Labels: Sheaf-Theoretic, AI-Relevant
- Level: intermediate to advanced
- Why it matters: A landmark example of using sheaf-theoretic language to
  analyze when locally consistent observations fail to admit a global model.
- Caution: The original setting is quantum foundations. AI connections should
  be drawn carefully.

### Sheaf Neural Networks

- Link: <https://arxiv.org/abs/2012.06333>
- Authors: Jakob Hansen, Thomas Gebhart
- Labels: Sheaf-Theoretic, AI-Relevant
- Level: intermediate
- Why it matters: Introduces neural architectures using cellular sheaf
  structure on graphs.
- Caution: This is sheaf-theoretic/topological deep learning, not full topos
  theory.

### Neural Sheaf Diffusion

- Link: <https://arxiv.org/abs/2202.04579>
- Authors: Cristian Bodnar, Francesco Di Giovanni, Benjamin Paul Chamberlain,
  Pietro Liò, Michael M. Bronstein
- Labels: Sheaf-Theoretic, AI-Relevant
- Level: intermediate
- Why it matters: Develops cellular-sheaf diffusion models for graph learning,
  showing how non-trivial sheaf structure changes heterophily and oversmoothing
  behavior compared with standard graph diffusion and GNNs.
- Caution: Classify as sheaf-based graph learning, not as core topos theory.

### Sheaf Neural Networks with Connection Laplacians

- Link: <https://arxiv.org/abs/2206.08702>
- Authors: Federico Barbero, Cristian Bodnar, Haitz Sáez de Ocáriz Borde,
  Michael Bronstein, Petar Veličković, Pietro Liò
- Labels: Sheaf-Theoretic, AI-Relevant
- Level: intermediate
- Why it matters: Computes sheaves for graph learning via connection
  Laplacians inspired by Riemannian geometry, using manifold- and graph-aware
  orthogonal maps to align tangent spaces while reducing the overhead of fully
  learned sheaves.
- Caution: A practical sheaf neural network method, not full topos theory.

### Sheaf Hypergraph Networks

- Link: <https://arxiv.org/abs/2309.17116>
- Authors: Iulia Duta, Giulia Cassarà, Fabrizio Silvestri, Pietro Liò
- Labels: Sheaf-Theoretic, AI-Relevant
- Level: intermediate
- Why it matters: Extends cellular sheaves to hypergraphs and introduces
  linear and non-linear sheaf hypergraph Laplacians, yielding neural and
  convolutional models for higher-order node classification.
- Caution: Strongly relevant to sheaf/topological deep learning; still distinct
  from Grothendieck topos semantics.

### Heterogeneous Sheaf Neural Networks

- Link: <https://arxiv.org/abs/2409.08036>
- Authors: Luke Braithwaite, Alessio Borgi, Gabriele Onorato, Kristjan
  Tarantelli, Francesco Restuccia, Fabrizio Silvestri, Pietro Liò
- Labels: Sheaf-Theoretic, AI-Relevant
- Level: intermediate
- Why it matters: Uses cellular sheaves to encode heterogeneous graph types
  directly in the data structure through type-aware local feature spaces and
  learned restriction maps, with a stalk-space pooling method for graph-level
  prediction.
- Caution: Useful for typed/heterogeneous graph learning; not a general
  topos-based AI theory.

### Cooperative Sheaf Neural Networks

- Link: <https://arxiv.org/abs/2507.00647>
- Authors: André Ribeiro, Ana Luiza Tenório, Juan Belieni, Amauri H. Souza,
  Diego Mesquita
- Labels: Sheaf-Theoretic, AI-Relevant
- Level: intermediate
- Why it matters: Introduces cellular sheaves over directed graphs to overcome
  the lack of message directionality in prior sheaf diffusion methods, enabling
  cooperative listen/propagate behavior and potentially mitigating
  oversquashing.
- Caution: Accepted to ICLR 2026 according to the arXiv metadata. Treat as a
  recent sheaf diffusion architecture, not core topos theory.

### Sheaf Representation Learning

- Link: local PDF reviewed; public repository URL to verify
- Author: Thomas Gebhart
- Labels: Sheaf-Theoretic, AI-Relevant, Verify First
- Level: intermediate to advanced
- Why it matters: A 2023 doctoral dissertation developing sheaf-theoretic
  representation learning, including sheaf neural networks, sheaf embeddings,
  topologically constrained representation learning, and knowledge graph
  reasoning through sheaf-based consistency objectives.
- Caution: The local PDF identifies the University of Minnesota dissertation,
  but a stable public URL should be verified before relying on the link in a
  public bibliography.

## Topological Deep Learning Near Topos and Sheaves

### TopoU-Net: A U-Net Architecture for Topological Domains

- Link: <https://arxiv.org/abs/2605.10091>
- Authors: Gaurav Gaurav, Ibrahem ALJabea, Yaroslav Zakomornyy, Eric Frank,
  Mohamed Elhamdadi, Theodore Papamarkou, Mustafa Hajij
- Labels: AI-Relevant, Applied Category Theory
- Level: intermediate
- Why it matters: A 2026 architecture paper that extends the U-Net
  encoder-decoder principle to combinatorial complexes, using rank paths,
  incidence-based transport, and matched-rank skip connections across nodes,
  edges, faces, hyperedges, and other cells.
- Caution: This is topological deep learning on combinatorial complexes, not
  topos theory. It is useful background for higher-order structured data and
  sheaf/topology-adjacent ML.

### Tangent Bundle Convolutional Learning: From Manifolds to Cellular Sheaves and Back

- Link: <https://doi.org/10.1109/TSP.2024.3379862>
- Authors: Claudio Battiloro, Zhiyang Wang, Hans Riess, Paolo Di Lorenzo,
  Alejandro Ribeiro
- Labels: Sheaf-Theoretic, AI-Relevant, Applied Category Theory
- Level: advanced
- Why it matters: Introduces tangent bundle filters and tangent bundle neural
  networks, then discretizes them through cellular sheaves, showing a principled
  link between continuous tangent-bundle learning and sheaf neural networks.
- Caution: This is sheaf/topological deep learning and geometric signal
  processing, not full Grothendieck topos theory.

## Broader Applied Category Theory Near AI

### Category Theory for the Sciences

- Link: <https://mitpress.mit.edu/9780262028134/category-theory-for-the-sciences/>
- Author: David I. Spivak
- Labels: Applied Category Theory
- Level: beginner to intermediate
- Why it matters: A practical entry point into categorical modeling, databases,
  and compositional systems.
- Caution: Useful background, but not specifically topos theory.

### Seven Sketches in Compositionality

- Link: <https://arxiv.org/abs/1803.05316>
- Authors: Brendan Fong, David I. Spivak
- Labels: Applied Category Theory
- Level: beginner to intermediate
- Why it matters: Good for compositional thinking, wiring diagrams, and applied
  categorical style.
- Caution: Mostly broader applied category theory.

### Position: Categorical Deep Learning is an Algebraic Theory of All Architectures

- Link: <https://proceedings.mlr.press/v235/gavranovic24a.html>
- Labels: Applied Category Theory, AI-Relevant
- Level: advanced
- Why it matters: A serious categorical deep learning position paper that helps
  situate architecture-level ideas in algebraic and categorical language.
- Caution: This is important for categorical AI, but it should not be presented
  as core topos theory.

### Geometric Deep Learning: Grids, Groups, Graphs, Geodesics, and Gauges

- Link: <https://facundoq.github.io/assets/gdl/main.html>
- Labels: AI-Relevant
- Level: intermediate
- Why it matters: A major unifying framework for neural architectures over
  structured domains.
- Caution: This is geometric and categorical-adjacent background, not topos
  theory.

### Kan Extension Transformers: A Categorical Unification of Attention, Diffusion, and Predict-Detach Self-Conditioning

- Link: <https://arxiv.org/abs/2605.27259>
- Author: Sridhar Mahadevan
- Labels: Applied Category Theory, AI-Relevant, Speculative Bridge
- Level: advanced
- Why it matters: Frames Transformer layers as weighted structured extension
  operators, connecting standard attention, sparse incidence mixing,
  higher-order simplicial neighborhoods, and diffusion-style completion through
  Kan-extension language.
- Caution: Categorical Transformer work rather than topos theory. Include it as
  nearby categorical AI background, especially for readers interested in LLMs.

## How To Read This List

Recommended order:

1. Learn category theory basics.
2. Learn presheaves and sheaves.
3. Learn elementary and Grothendieck topoi.
4. Study one AI-relevant bridge, preferably sheaves on data or contextuality.
5. Only then evaluate speculative "topos for AI" claims.

If a resource does not clearly fit any label, put it in **Verify First** before
adding it to this page.
