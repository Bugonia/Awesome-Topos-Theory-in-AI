# Learning Paths

This page turns the repository from a link list into a study map. The goal is
to make each step answer: what should I learn, why does it matter, and what can
I read next?

## Path A: First Contact With Topos Theory

Use this path if you know some algebra, topology, or logic, but have not studied
category theory seriously.

### Stage 1: Category Theory Basics

Learn:

- category, object, morphism;
- functor;
- natural transformation;
- product, coproduct, equalizer, coequalizer;
- limit and colimit;
- adjunction;
- Yoneda lemma.

Why it matters:

Topos theory is written almost entirely in the language of universal properties.
Without adjunctions and Yoneda, the definitions will look more mysterious than
they really are.

Suggested references:

- Tom Leinster, *Basic Category Theory*.
- Steve Awodey, *Category Theory*.
- Emily Riehl, *Category Theory in Context*.

### Stage 2: Presheaves

Learn:

- presheaf as a functor `C^op -> Set`;
- representable presheaves;
- Yoneda embedding;
- presheaf category `[C^op, Set]`;
- restriction maps as changing context.

Why it matters:

Presheaf categories are the cleanest first examples of topoi. They already show
how a topos behaves like a universe of variable sets.

### Stage 3: Sheaves

Learn:

- covers;
- compatible families;
- gluing;
- sites;
- Grothendieck topology;
- sheafification.

Why it matters:

Sheaves formalize local-to-global reasoning. This is one of the most promising
interfaces between topos theory and data problems.

### Stage 4: Elementary Topos

Learn:

- finite limits;
- exponentials;
- subobject classifier;
- power objects;
- internal logic.

Why it matters:

An elementary topos is a category that behaves enough like `Set` to support
logic and set-like reasoning, but may have different truth values and different
logical principles.

### Stage 5: Grothendieck Topos

Learn:

- sheaves on a site;
- geometric morphism;
- points of a topos;
- classifying topoi;
- relation to geometry and logic.

Why it matters:

Grothendieck topoi are the central objects connecting generalized spaces,
sheaves, logic, and geometry.

## Path B: Mathematician Route

Use this path if you are comfortable with topology, algebraic geometry, logic,
or homological algebra.

1. Review adjunctions and Kan extensions.
2. Study presheaf categories and the Yoneda embedding.
3. Study Grothendieck topologies and sites.
4. Work through sheafification.
5. Study geometric morphisms.
6. Study internal language and Kripke-Joyal semantics.
7. Learn classifying topoi.
8. Compare examples: topological spaces, locales, etale spaces, schemes,
   syntactic sites.

Main reference:

- Mac Lane and Moerdijk, *Sheaves in Geometry and Logic*.

Advanced reference:

- Johnstone, *Sketches of an Elephant*.

## Path C: AI/ML Route

Use this path if your motivation is artificial intelligence.

1. Learn the categorical language needed for compositionality.
2. Learn presheaves as data varying over contexts.
3. Learn sheaves as local-to-global consistency structures.
4. Study examples from sensor networks, databases, and contextuality.
5. Read sheaf neural network papers as topological deep learning, not as full
   topos theory.
6. Study internal logic only after you understand subobjects and exponentials.
7. Compare with Markov categories for probability and monoidal categories for
   compositional systems.

Critical warning:

Most AI uses of category theory are not uses of topos theory. This is not a
defect. It is a reason to label the mathematics precisely.

## Path D: Logic and Type Theory Route

Use this path if you care about semantics, proof assistants, or foundations.

1. Cartesian closed categories.
2. Curry-Howard-Lambek correspondence.
3. Subobject classifier and Heyting algebras.
4. Internal language of a topos.
5. Kripke-Joyal semantics.
6. Realizability topoi.
7. Classifying topoi.
8. Homotopy type theory and higher topos theory, only after the 1-topos basics
   are stable.

## Minimal Reading Sequence

If you want the shortest serious path:

1. Leinster, *Basic Category Theory*.
2. Awodey, selected chapters on limits, adjunctions, Yoneda, CCCs, topoi.
3. Mac Lane and Moerdijk, early chapters on sheaves and topoi.
4. One application area: contextuality, sheaves on data, or type-theoretic
   semantics.
