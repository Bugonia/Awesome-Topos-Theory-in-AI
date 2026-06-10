# Bridges to AI

This page records the AI-facing connections that are promising enough to study,
while keeping the claims modest.

## Stronger Bridges

### Sheaves for Local-to-Global Consistency

Many AI and data problems involve partial information:

- sensor readings over overlapping regions;
- labels or features defined over local contexts;
- distributed databases;
- multi-agent beliefs;
- incompatible observations;
- constraints that may or may not glue globally.

Sheaf theory gives a mathematical language for this pattern. A sheaf encodes
what data live locally, how they restrict to overlaps, and when compatible
local data determine a global section.

This is one of the most concrete bridges from topos-adjacent mathematics to AI.

### Contextuality

The sheaf-theoretic framework for contextuality shows how local consistency can
fail to extend to a global model. It began in quantum foundations, but the
pattern is relevant to any setting where observations are context-dependent.

AI-facing questions:

- Can model behavior depend on evaluation context in a way that lacks a single
  global explanation?
- Can incompatible local explanations be detected as obstructions?
- Can sheaf cohomology or related invariants diagnose inconsistency?

These are research questions, not established general answers.

### Cellular Sheaves and Neural Networks

Cellular sheaves assign vector spaces and restriction maps to cells of a graph
or cell complex. Sheaf neural networks use this structure to build learning
architectures that respect heterogeneity and local consistency.

Classification:

- AI-relevant: yes.
- Core topos theory: usually no.
- Sheaf-theoretic: yes.

This distinction is important. Sheaf neural networks are a serious topic in
topological deep learning, but they generally do not require the full machinery
of elementary or Grothendieck topoi.

### Internal Languages and Typed Reasoning

Topoi support internal languages. This connects to:

- type-theoretic semantics;
- program logics;
- verified systems;
- structured knowledge representation;
- constructive reasoning.

AI-facing relevance is currently indirect. It may matter more for reliable
symbolic-neural systems, proof assistants, agent reasoning, and semantics than
for ordinary predictive modeling.

## Weaker but Interesting Bridges

### Topos as Generalized Space of States

A topos can be seen as a generalized space. This suggests ways to think about
state spaces that are not ordinary sets or manifolds.

Use with care:

This is a conceptual bridge unless a specific construction is given.

### Topos as Generalized Universe of Sets

A topos behaves like a universe in which mathematics can be done internally.
This may be useful for formal semantics of agents or models, but it is not by
itself an AI method.

### Topos as Logic of Context

Topos logic can encode truth values that vary over context. This sounds highly
relevant to AI, but the relevance must be made precise through a model,
semantics, or theorem.

## Related Categorical AI That Is Not Topos Theory

These topics are often more immediately useful for AI than topos theory, but
they should not be mislabeled.

### Monoidal Categories

Useful for compositional systems, string diagrams, process theories, and
categorical quantum mechanics.

### Operads

Useful for modular composition, wiring diagrams, and hierarchical systems.

### Lenses and Optics

Useful for bidirectional transformations, update structures, differentiable
programming, and compositional systems.

### Coalgebras

Useful for automata, state-based systems, streams, transition systems, and
behavioral equivalence.

### Markov Categories

Useful for probability, stochastic maps, Bayesian networks, causality, and
statistical reasoning.

## Research Prompts

Potentially valuable questions:

1. Can sheaf obstructions diagnose inconsistent explanations in AI systems?
2. Can presheaves model context-dependent representations across tasks?
3. Can internal logic clarify reasoning in agents with partial information?
4. Can classifying topoi organize families of models or theories?
5. Can geometric morphisms describe changes of context, abstraction, or
   observation?

Each prompt needs concrete mathematical development before it should be
presented as an established AI result.
