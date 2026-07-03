# Study Plan: From Basic Category Theory to Topos-Based Machine Learning

This plan is for a reader with some basic category theory who wants to understand
topos-based machine learning without getting lost in advanced abstraction too
early.

## Guiding Picture

The central bridge is:

```text
context-indexed data -> presheaves -> sheaves -> sheaf topoi -> internal logic
```

Machine learning enters through local/global structure, context dependence,
invariance, compositionality, and semantic interpretation. The current
topos-based ML literature is still exploratory, so the plan separates mature
mathematics from research proposals.

## Phase 1: Category Theory Refresher

Goal:

Understand the language in which presheaves, sheaves, and topoi are defined.

Learn:

- category, object, morphism;
- functor and natural transformation;
- product, pullback, equalizer;
- limit and colimit;
- adjunction;
- Yoneda lemma.

Checkpoint questions:

1. Why is a functor a structure-preserving translation?
2. Why is a natural transformation a comparison between translations?
3. Why do universal properties define objects up to unique isomorphism?
4. What does the Yoneda lemma say about knowing an object through its maps?

Recommended resources:

- Tom Leinster, *Basic Category Theory*.
- Steve Awodey, *Category Theory*.

## Phase 2: Presheaves as Context-Indexed Data

Goal:

See a presheaf as data that varies over contexts.

Definition:

```text
F : C^op -> Set
```

Interpretation:

- objects of `C` are contexts;
- `F(c)` is the set of possible data over context `c`;
- an arrow `c -> d` gives a restriction map `F(d) -> F(c)`.

ML intuition:

A model may have local observations, features, explanations, or labels living
over different contexts. Presheaves give a clean language for this dependence.

Checkpoint questions:

1. What is the difference between a dataset indexed by a set and a presheaf
   indexed by a category?
2. Why do restriction maps go in the opposite direction?
3. Why are presheaf categories already examples of topoi?

## Phase 3: Sheaves as Local-to-Global Consistency

Goal:

Understand what extra condition turns a presheaf into a sheaf.

Learn:

- covers;
- compatible families;
- gluing;
- uniqueness of gluing.

ML intuition:

Local features or local predictions may agree on overlaps. A sheaf asks whether
they glue to a coherent global object. Failure to glue can be interpreted as an
obstruction to global consistency.

Checkpoint questions:

1. What does it mean for local data to agree on overlaps?
2. What does a global section represent?
3. How might inconsistent model explanations appear as a failure of gluing?

Suggested applied bridge:

- Shiebler-Gavranovic-Wilson, *Category Theory in Machine Learning*.
- Abramsky-Brandenburger contextuality.
- Sheaf neural networks.
- Neural sheaf diffusion.
- Gebhart, *Sheaf Representation Learning*.
- Battiloro-Wang-Riess-Di Lorenzo-Ribeiro, *Tangent Bundle Convolutional
  Learning*.

## Phase 4: Sites and Grothendieck Topologies

Goal:

Understand that "local" is not fixed once and for all. A Grothendieck topology
chooses which families of maps count as covers.

Learn:

- sieve;
- covering family;
- Grothendieck topology;
- site `(C, J)`;
- sheaves on a site.

ML intuition:

Different ML tasks impose different notions of locality: spatial neighborhoods,
graph neighborhoods, contexts, modalities, patches, ranks, or semantic
relations. A site is a way to formalize the chosen locality.

Checkpoint questions:

1. Why is a topology on a category more flexible than open covers on a space?
2. What would count as a cover in a graph, hypergraph, or neural network layer
   category?
3. How does changing the topology change the sheaves?

## Phase 5: Grothendieck Topoi

Goal:

Understand a Grothendieck topos as a category of sheaves on a site.

Core idea:

```text
Sh(C, J)
```

is a universe of objects varying over the site `(C, J)`.

Learn:

- sheafification;
- geometric morphism;
- points of a topos;
- subtopos;
- classifying topos.

ML intuition:

The topos is not a single model. It is more like a structured universe in which
models, data, local descriptions, and semantics can live together.

Checkpoint questions:

1. Why is a topos a generalized space?
2. Why is a topos a generalized universe of sets?
3. What could a geometric morphism mean as a change of context or observation?

Recommended resource:

- Mac Lane and Moerdijk, *Sheaves in Geometry and Logic*.
- Caramello and Lafforgue, *Sites and Grothendieck Toposes: An Introduction*.

## Phase 6: Subobject Classifier and Internal Logic

Goal:

Understand why a topos carries its own logic.

Learn:

- subobject classifier `Omega`;
- characteristic maps;
- Heyting algebra of truth values;
- internal language;
- Kripke-Joyal semantics.

ML intuition:

Topos logic gives a way to reason inside a context-dependent universe. This is
why topos-based AI proposals often talk about semantics, interpretability,
knowledge representation, and reasoning rather than only numerical prediction.

Checkpoint questions:

1. How does `Omega` generalize `{false, true}`?
2. Why is internal logic often intuitionistic?
3. What would it mean for a proposition about data to be true only locally?

## Phase 7: Sheaf and Topological Deep Learning

Goal:

Read nearby ML papers before the more speculative topos papers.

Read:

- Sheaf Neural Networks.
- Neural Sheaf Diffusion.
- TopoU-Net.

What to look for:

- What is the underlying domain: graph, cell complex, hypergraph, or
  combinatorial complex?
- Where are local data stored?
- What maps move information between contexts or cells?
- Is there a genuine sheaf/topos structure, or only a topological/categorical
  analogy?

## Phase 8: Direct Topos-Based ML Proposals

Goal:

Read the ambitious papers with enough background to separate mathematics from
research vision.

Read in this order:

1. Shiebler-Gavranovic-Wilson, *Category Theory in Machine Learning*, for the
   broader applied category theory background.
2. Jia-Peng-Yang-Chen survey.
3. Lafforgue, *Some Possible Roles for AI of Grothendieck Topos Theory*.
4. Belfiore-Bennequin, *Topos and Stacks of Deep Neural Networks*.
5. Villani-McBurney, *The Topos of Transformer Networks*, noting that the
   arXiv version is withdrawn and should be treated as an unstable research
   pointer.
6. Optional: Mahadevan, *Topos Theory for Generative AI and LLMs*.
7. Optional semantic-information background: Baudot-Bennequin, *The
   Homological Nature of Entropy*, and Vigneaux, *Information Structures and
   Their Cohomology*.

For each paper, ask:

1. What is the site or category?
2. What are the sheaves or objects of the topos?
3. What ML structure is being modeled?
4. Is there a theorem, an architecture, an analogy, or a research proposal?
5. What would count as empirical or mathematical validation?

## First Lessons To Do With A Tutor

Lesson 1:

Presheaves as context-indexed data.

Lesson 2:

Sheaves as local-to-global gluing.

Lesson 3:

Sites and Grothendieck topologies as task-dependent locality.

Lesson 4:

The category of sheaves as a generalized space.

Lesson 5:

Subobject classifiers and internal truth values.

Lesson 6:

How sheaf neural networks use part of this language.

Lesson 7:

How Belfiore-Bennequin try to put DNNs into Grothendieck topoi and stacks.

Lesson 8:

How transformer networks motivate topos completion.

## Rule of Thumb

When reading a paper, classify each claim into one of four boxes:

- established topos theory;
- sheaf/topological deep learning;
- categorical analogy;
- speculative topos-based ML proposal.

This prevents the literature from becoming a fog of impressive words.
