# Core Concepts

This is a compact map of the mathematical concepts that should anchor the
project.

## Presheaf

A presheaf on a category `C` is a functor:

```text
C^op -> Set
```

Intuition:

- objects of `C` are contexts, regions, observations, or stages;
- a presheaf assigns data to each context;
- morphisms in `C` induce restriction maps in the opposite direction.

Why it matters:

Presheaf categories are canonical examples of topoi. They give a precise way to
talk about data that depends on context.

## Sheaf

A sheaf is a presheaf satisfying a local-to-global gluing condition with respect
to a chosen notion of cover.

Intuition:

- local data can be restricted to overlaps;
- compatible local data have a unique global gluing;
- failure of gluing measures obstruction.

AI-facing relevance:

Sheaves are useful when information is distributed across contexts and global
consistency is nontrivial.

## Site

A site is a category equipped with a Grothendieck topology. It tells us which
families of morphisms should count as covers.

Why it matters:

Different choices of covers produce different sheaf theories and therefore
different topoi.

## Grothendieck Topos

A Grothendieck topos is, up to equivalence, a category of sheaves on a site.

Intuitions:

- a generalized space;
- a universe of variable sets;
- a setting for geometric logic.

## Elementary Topos

An elementary topos is a category with:

- finite limits;
- exponentials;
- a subobject classifier.

This definition abstracts the set-like and logical behavior of `Set`.

## Subobject Classifier

In `Set`, subsets of `X` are classified by characteristic functions:

```text
X -> {false, true}
```

In a topos, subobjects of `X` are classified by maps:

```text
X -> Omega
```

where `Omega` is the subobject classifier.

Why it matters:

`Omega` behaves like an object of truth values. In many topoi, truth is not just
binary classical truth.

## Internal Logic

Every elementary topos supports an internal higher-order intuitionistic logic.

Important points:

- conjunction and implication come from categorical structure;
- existential and universal quantifiers come from adjoints to pullback when
  they exist in the right form;
- excluded middle may fail;
- reasoning inside a topos can differ from external set-theoretic reasoning.

## Geometric Morphism

A geometric morphism between topoi is an adjoint pair:

```text
f^* : E -> F
f_* : F -> E
```

where `f^*` is left exact.

Intuition:

This is the topos-theoretic analogue of a continuous map between spaces.

## Classifying Topos

A classifying topos for a theory is a topos whose models in other topoi are
controlled by geometric morphisms into it.

Why it matters:

This is one of the strongest bridges between logic and geometry.

## Common Confusions

- A presheaf is not automatically a sheaf.
- A sheaf category can be a topos, but a single sheaf is not a topos.
- Monoidal categories are not topoi in general.
- A Markov category is about probability, not automatically about topos logic.
- Topos theory is not the same thing as homotopy type theory, although higher
  topos theory and HoTT are deeply related.
