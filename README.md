# Awesome Topos Theory in AI

A curated learning map for people who want to understand what topos theory can
and cannot currently contribute to artificial intelligence.

This repository is deliberately conservative. It does not claim that "topos
theory explains AI." Instead, it organizes the parts of topos theory that may
help with questions about structure, semantics, local-to-global consistency,
logic, type theory, and compositional systems.

## Scope

Topos theory is a deep branch of category theory. AI uses many categorical
ideas, but not every categorical idea is topos theory. This list separates:

- **Core Topos**: presheaves, sheaves, Grothendieck topologies, elementary
  topoi, subobject classifiers, internal logic, geometric morphisms.
- **Applied Category Theory**: monoidal categories, operads, lenses, coalgebras,
  Markov categories, categorical probability, compositional semantics.
- **AI-Relevant**: work with explicit connections to machine learning,
  knowledge representation, probabilistic reasoning, neural architectures,
  type theory, or data analysis.
- **Speculative Bridge**: plausible conceptual connections that should be read
  as research prompts, not settled results.
- **Verify First**: claims, papers, labs, or projects that need source checking
  before being listed as resources.

If an item is only "category theory in AI," it belongs here only when the
connection to topos theory is stated clearly.

## Learning Routes

### 1. Beginner Route

For readers who know basic abstract algebra or topology but not much category
theory.

1. Categories, functors, and natural transformations.
2. Universal properties, limits, colimits, and adjunctions.
3. Yoneda lemma and representable functors.
4. Cartesian closed categories.
5. Presheaf categories as generalized spaces.
6. Sheaves as locally defined data that glue.
7. Subobject classifiers and internal logic.
8. Elementary topoi and Grothendieck topoi.

See [docs/learning-paths.md](docs/learning-paths.md).

### 2. Mathematician Route

For readers with algebra, topology, algebraic geometry, or logic background.

1. Sites and Grothendieck topologies.
2. Sheafification and sheaf topoi.
3. Geometric morphisms.
4. Internal language.
5. Classifying topoi.
6. Examples from topology, algebraic geometry, and logic.

### 3. AI/ML Route

For readers mainly interested in AI.

1. Learn enough category theory to read functorial examples.
2. Study presheaves and sheaves as structured data over contexts.
3. Study local-to-global consistency through sheaf theory.
4. Read contextuality and sheaf-based data analysis.
5. Compare to related categorical AI tools: operads, lenses, Markov categories,
   coalgebras, and monoidal categories.
6. Treat direct "topos for AI" claims cautiously unless the paper proves a
   concrete theorem, builds a useful model, or clarifies semantics.

See [docs/ai-bridges.md](docs/ai-bridges.md).

## Core Topos Theory

### Recent Survey Entry Point

- Yiyang Jia, Guohong Peng, Zheng Yang, and Tianhao Chen,
  "Category-Theoretical and Topos-Theoretical Frameworks in Machine Learning:
  A Survey," *Axioms* 14, 204, 2025.
- DOI: <https://doi.org/10.3390/axioms14030204>
- Recommended use: read as a recent map of categorical machine learning and
  topos-oriented proposals, while keeping the speculative topos-based ML claims
  separate from established core topos theory.

### Categories, Functors, Natural Transformations

- Steve Awodey, *Category Theory*.
- Tom Leinster, *Basic Category Theory*.
- Emily Riehl, *Category Theory in Context*.

These are not topos books, but they prepare the language needed for serious
topos theory.

### Sheaves and Topoi

- Saunders Mac Lane and Ieke Moerdijk, *Sheaves in Geometry and Logic*.
- Peter Johnstone, *Sketches of an Elephant: A Topos Theory Compendium*.
- Olivia Caramello, *Theories, Sites, Toposes*.
- nLab pages on [topos](https://ncatlab.org/nlab/show/topos),
  [Grothendieck topos](https://ncatlab.org/nlab/show/Grothendieck+topos), and
  [elementary topos](https://ncatlab.org/nlab/show/elementary+topos).

Recommended first serious book: Mac Lane and Moerdijk. Recommended reference:
Johnstone.

### Internal Logic

Key ideas:

- A topos has a subobject classifier, which generalizes the set of truth values
  `{false, true}`.
- Logical connectives can be interpreted through categorical structure.
- Many topoi have intuitionistic rather than classical internal logic.
- Quantifiers arise from adjoints to pullback functors along projections.

Good entry points:

- Mac Lane and Moerdijk, chapters on logic in a topos.
- Johnstone, for advanced reference.
- nLab pages on
  [internal logic](https://ncatlab.org/nlab/show/internal+logic) and
  [subobject classifier](https://ncatlab.org/nlab/show/subobject+classifier).

## AI-Relevant Bridges

These areas are more defensible than broad claims that "topos theory explains
intelligence."

### Sheaves on Data

Sheaves model data distributed over contexts with restriction maps and gluing
conditions. This is relevant to sensor networks, consistency constraints,
distributed systems, and structured data analysis.

Representative directions:

- Michael Robinson, sheaf-theoretic methods for data and sensing.
- Cellular sheaves and sheaf neural networks in topological deep learning.
- Local-to-global consistency as an organizing principle for data fusion.

### Contextuality

Abramsky and Brandenburger's sheaf-theoretic account of contextuality is a
major example of sheaf ideas explaining why locally consistent observations may
fail to have a global explanation. This is directly mathematical and indirectly
relevant to reasoning under incompatible contexts.

### Type Theory and Internal Languages

Topoi connect geometry, logic, and type-theoretic semantics. This is relevant
to verified AI systems, program semantics, knowledge representation, and
structured reasoning, but the connection to mainstream machine learning is
mostly indirect.

### Categorical AI Nearby

Many useful categorical AI tools are not topos theory:

- monoidal categories for compositional systems;
- operads for wiring diagrams and modular composition;
- lenses and optics for bidirectional structure;
- coalgebras for state-based and dynamical systems;
- Markov categories for probability and stochastic maps;
- enriched categories and Lawvere metric spaces for generalized similarity.

They should be listed separately from core topos resources.

## What To Avoid

Avoid listing a resource as "topos theory in AI" when:

- it only mentions category theory in general;
- it is a generated-looking title without a real source;
- it uses "topos" metaphorically without definitions or theorems;
- it confuses sheaves, presheaves, topoi, and monoidal categories;
- it claims a direct AI breakthrough without reproducible content.

Use the checklist in [docs/resource-taxonomy.md](docs/resource-taxonomy.md).

## Repository Map

- [docs/learning-paths.md](docs/learning-paths.md): guided study routes.
- [docs/core-concepts.md](docs/core-concepts.md): compact concept map.
- [docs/resources.md](docs/resources.md): curated books, notes, and papers.
- [docs/ai-bridges.md](docs/ai-bridges.md): careful AI-facing bridge topics.
- [docs/resource-taxonomy.md](docs/resource-taxonomy.md): labels and inclusion
  criteria.
- [CONTRIBUTING.md](CONTRIBUTING.md): contribution rules for keeping the list
  reliable.

## Contribution Principle

Every listed item should answer at least one of these questions:

1. Does it teach a core topos concept accurately?
2. Does it use sheaves/topoi in a concrete AI-adjacent setting?
3. Does it clarify the boundary between topos theory and broader applied
   category theory?
4. Does it identify a speculative bridge honestly, without presenting it as
   established fact?

When in doubt, mark the item as **Speculative Bridge** or **Verify First**.
