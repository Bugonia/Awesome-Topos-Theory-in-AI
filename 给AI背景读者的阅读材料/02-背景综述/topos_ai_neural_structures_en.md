# Topos-Theoretic Frameworks for Neural Networks and LLMs

## Abstract

This article surveys a recent line of work whose common claim is not that
topos theory has already produced a mature engineering paradigm for artificial
intelligence, but rather that certain neural-network and large-language-model
structures can be represented, completed, or semantically organized inside
categorical and topos-theoretic frameworks. We give a unified preliminary
account of the categorical language used in these works, beginning with
categories, functors, natural transformations, limits, adjunctions, presheaves,
Yoneda, sheaves, sites, Grothendieck topologies, Grothendieck topoi, internal
logic, and stacks. We then explain how this language is used in several
representative proposals: Lafforgue's programmatic use of Grothendieck topoi for
AI, Belfiore and Bennequin's topos-and-stack framework for deep neural networks,
the withdrawn but suggestive proposal on the topos of transformer networks,
Mahadevan's topos-theoretic proposal for generative AI and LLMs, and the 2025
survey by Jia, Peng, Yang, and Chen. The emphasis is on what is mathematically
constructed or claimed, what is merely programmatic, and which notions from
topos theory are actually doing work.

## 1. Introduction

Modern neural networks are usually described as parametrized maps

\[
N_\theta:X\longrightarrow Y
\]

or as composites of layers

\[
N_\theta
=f_L\circ f_{L-1}\circ\cdots\circ f_1.
\]

This description is effective for optimization, implementation, and empirical
evaluation, but it says relatively little about several structural questions:

1. How should local representations, layerwise data, modules, symmetries, and
   invariances be organized into global semantic structures?
2. Can a neural network be represented as an object in a category rich enough to
   support local-to-global reasoning?
3. Can the expressive power of transformers or LLMs be described through
   categorical completions, function objects, subobjects, or internal logic?
4. Can model composition be governed by universal constructions such as
   pullbacks, pushouts, equalizers, coequalizers, and exponentials?

Topos theory is relevant to these questions because a Grothendieck topos is,
roughly, a universe of sheaves on a site:

\[
\mathcal{E}\simeq \mathbf{Sh}(\mathcal{C},J).
\]

Here \(\mathcal{C}\) is a category of contexts, \(J\) is a Grothendieck topology
encoding which families count as covers, and \(\mathbf{Sh}(\mathcal{C},J)\) is
the category of sheaves satisfying a local-to-global gluing condition. Such a
category behaves simultaneously like a generalized space, a generalized universe
of sets, and a universe with its own internal logic.

The works discussed below should be read with care. Some contain precise
categorical constructions; some are programmatic; some are speculative; and one
important transformer-related proposal is marked withdrawn on arXiv. Their
common contribution is not a uniform theorem about test accuracy or
generalization, but a family of mathematical attempts to place neural
architectures in richer semantic environments.

## 2. Unified Notation

We use the following notation throughout.

| Symbol | Meaning |
|---|---|
| \(\mathcal{C},\mathcal{D}\) | categories, often small when presheaves are formed |
| \(A,B,C,U,V\) | objects of a category |
| \(f:A\to B\) | a morphism |
| \(\mathbf{Set}\) | category of sets and functions |
| \(\mathbf{PSh}(\mathcal{C})\) | presheaf category \([\mathcal{C}^{op},\mathbf{Set}]\) |
| \(F,G\) | functors or presheaves |
| \(\eta:F\Rightarrow G\) | natural transformation |
| \(y:\mathcal{C}\to \widehat{\mathcal{C}}\) | Yoneda embedding |
| \(yA\) | representable presheaf \(\mathrm{Hom}_{\mathcal{C}}(-,A)\) |
| \(J\) | Grothendieck topology on \(\mathcal{C}\) |
| \((\mathcal{C},J)\) | a site |
| \(\mathbf{Sh}(\mathcal{C},J)\) | category of sheaves on a site |
| \(\mathcal{E},\mathcal{F}\) | topoi |
| \(\Omega\) | subobject classifier |
| \(N_\theta\) | neural network with parameters \(\theta\) |
| \(h_\ell\) | hidden representation at layer \(\ell\) |
| \(T_\theta\) | transformer or LLM-type model |

For neural networks we use a deliberately light notation. A feedforward network
is a composite

\[
h_{\ell+1}=f_{\ell,\theta_\ell}(h_\ell),
\qquad
N_\theta=f_{L,\theta_L}\circ\cdots\circ f_{1,\theta_1}.
\]

A transformer block may be written schematically as

\[
H_{\ell+1}
=\mathrm{FFN}_\ell\bigl(\mathrm{Attn}_\ell(H_\ell)\bigr),
\]

where \(H_\ell\) is a sequence of hidden states. The exact algorithmic details
are not central here; the categorical question is how such maps, layers, heads,
states, symmetries, and tasks may be organized as categorical objects and
morphisms.

## 3. Categorical Preliminaries

### 3.1 Categories, Functors, and Natural Transformations

A category \(\mathcal{C}\) consists of objects, morphisms, identity morphisms,
and associative composition. For any objects \(A,B\in\mathcal{C}\), the set of
morphisms from \(A\) to \(B\) is denoted

\[
\mathrm{Hom}_{\mathcal{C}}(A,B).
\]

A functor

\[
F:\mathcal{C}\to\mathcal{D}
\]

sends objects to objects and morphisms to morphisms while preserving identities
and composition:

\[
F(\mathrm{id}_A)=\mathrm{id}_{F(A)},\qquad
F(g\circ f)=F(g)\circ F(f).
\]

A natural transformation \(\eta:F\Rightarrow G\) between two functors
\(F,G:\mathcal{C}\to\mathcal{D}\) assigns to every \(A\in\mathcal{C}\) a
morphism

\[
\eta_A:F(A)\to G(A)
\]

such that for every \(f:A\to B\),

\[
G(f)\circ \eta_A=\eta_B\circ F(f).
\]

In the topos-AI literature, functors are used to express structured translation:
from geometric data to semantic data, from network components to categorical
objects, or from syntactic descriptions to semantic models. Natural
transformations express compatibility between such translations.

### 3.2 Limits and Universal Properties

Limits are categorical constructions defined by universal properties. The most
important finite limits are terminal objects, products, equalizers, and
pullbacks.

A pullback of

\[
A\xrightarrow{f}C\xleftarrow{g}B
\]

is an object \(A\times_C B\) equipped with projections

\[
p_1:A\times_C B\to A,\qquad p_2:A\times_C B\to B
\]

such that

\[
f\circ p_1=g\circ p_2,
\]

and universal with this property. In \(\mathbf{Set}\),

\[
A\times_C B
=\{(a,b)\in A\times B\mid f(a)=g(b)\}.
\]

In AI language, pullbacks model alignment over a shared semantic target. If
\(I\to S\) and \(T\to S\) map image and text representations into a shared
semantic space \(S\), then \(I\times_S T\) models semantically compatible
image-text pairs. This is not yet topos theory, but it is the kind of universal
construction that later appears inside topoi.

### 3.3 Adjunctions

An adjunction

\[
L\dashv R
\]

between \(L:\mathcal{C}\to\mathcal{D}\) and
\(R:\mathcal{D}\to\mathcal{C}\) is a natural bijection

\[
\mathrm{Hom}_{\mathcal{D}}(LC,D)
\cong
\mathrm{Hom}_{\mathcal{C}}(C,RD).
\]

Left adjoints often perform free constructions or completions; right adjoints
often forget or restrict structure. Examples include:

\[
\text{free group }F:\mathbf{Set}\to\mathbf{Grp}
\quad\dashv\quad
U:\mathbf{Grp}\to\mathbf{Set}.
\]

Adjunctions are central in topos theory. Sheafification is a left adjoint to the
inclusion of sheaves into presheaves. Geometric morphisms are adjoint pairs of
functors. Existential and universal quantification in internal logic can also be
expressed via adjoints.

### 3.4 Presheaves and Yoneda

For a category \(\mathcal{C}\), a presheaf is a functor

\[
F:\mathcal{C}^{op}\to\mathbf{Set}.
\]

The category of presheaves is

\[
\widehat{\mathcal{C}}
=\mathbf{PSh}(\mathcal{C})
=[\mathcal{C}^{op},\mathbf{Set}].
\]

For \(A\in\mathcal{C}\), the representable presheaf \(yA\) is

\[
yA=\mathrm{Hom}_{\mathcal{C}}(-,A).
\]

The Yoneda lemma states that for every presheaf \(F\),

\[
\mathrm{Nat}(yA,F)\cong F(A).
\]

Thus an element of \(F(A)\) is equivalent to a natural way of producing
\(F\)-data from every generalized element \(X\to A\). The Yoneda embedding

\[
y:\mathcal{C}\to\widehat{\mathcal{C}}
\]

is fully faithful:

\[
\mathrm{Hom}_{\mathcal{C}}(A,B)
\cong
\mathrm{Nat}(yA,yB).
\]

This is why presheaf categories are natural completions of a starting category:
they contain the original category fully faithfully and add generalized
context-dependent objects.

### 3.5 Sites, Sheaves, and Sheafification

A Grothendieck topology \(J\) on a category \(\mathcal{C}\) specifies, for each
object \(U\), which families

\[
\{U_i\to U\}_{i\in I}
\]

count as covers. The pair \((\mathcal{C},J)\) is called a site.

A presheaf \(F:\mathcal{C}^{op}\to\mathbf{Set}\) is a sheaf if compatible local
sections over every covering family glue uniquely to a global section. In the
classical topological case, this says: if

\[
U=\bigcup_i U_i
\]

and \(s_i\in F(U_i)\) satisfy

\[
s_i|_{U_i\cap U_j}=s_j|_{U_i\cap U_j},
\]

then there exists a unique \(s\in F(U)\) such that

\[
s|_{U_i}=s_i.
\]

The sheafification of a presheaf \(F\) is a sheaf \(aF\) equipped with a map
\(F\to iaF\), where \(i:\mathbf{Sh}(\mathcal{C},J)\hookrightarrow
\mathbf{PSh}(\mathcal{C})\) is the inclusion. It is characterized by the
adjunction

\[
a\dashv i.
\]

Concretely, sheafification repairs two failures:

1. local equality should imply global equality;
2. compatible local data should have a global gluing.

This is one of the main reasons sheaves are relevant to neural systems: they
formalize the passage from local descriptions to coherent global descriptions.

### 3.6 Grothendieck Topoi

A Grothendieck topos is a category equivalent to the category of sheaves on a
site:

\[
\mathcal{E}\simeq\mathbf{Sh}(\mathcal{C},J).
\]

It has three complementary interpretations:

1. a generalized space;
2. a generalized universe of sets varying over contexts;
3. a universe with an internal logic.

Examples include:

\[
\mathbf{Set}\simeq\mathbf{Sh}(*),
\]

the sheaf topos \(\mathbf{Sh}(X)\) of a topological space \(X\), and every
presheaf category

\[
[\mathcal{C}^{op},\mathbf{Set}].
\]

In the AI works discussed below, a Grothendieck topos is often used as a
semantic environment: a place where local structures, invariances, data, and
logical assertions can be organized coherently.

### 3.7 Subobject Classifiers and Internal Logic

An elementary topos has finite limits, exponentials, and a subobject classifier
\(\Omega\). The subobject classifier generalizes the two-element set of truth
values. In \(\mathbf{Set}\), a subset \(S\subseteq X\) is classified by its
characteristic function

\[
\chi_S:X\to\{0,1\}.
\]

In a topos \(\mathcal{E}\), a subobject \(S\hookrightarrow X\) is classified by
a morphism

\[
\chi_S:X\to\Omega.
\]

Thus predicates become subobjects, and truth values live in \(\Omega\). A topos
therefore supports an internal logic. This matters for AI proposals that seek
to represent semantic assertions, concept membership, interpretability claims,
or contextual truth inside a categorical universe rather than as external
Boolean labels.

### 3.8 Stacks

A sheaf glues set-valued local data. A stack glues category-valued local data,
including not only objects but also morphisms or isomorphisms between objects.
Very roughly:

\[
\text{sheaf}:\text{ local objects glue},
\qquad
\text{stack}:\text{ local objects and equivalences glue}.
\]

Stacks are invoked in the DNN literature when local representations are not
expected to match strictly but only up to isomorphism, symmetry, gauge
transformation, or change of coordinates. This is particularly natural for
neural-network layers, heads, and feature spaces, where equivalent
representations need not be literally equal.

## 4. Minimal AI Background

For the purposes of this article, a feedforward DNN is a parametrized composite

\[
N_\theta=f_{L,\theta_L}\circ\cdots\circ f_{1,\theta_1}.
\]

A CNN adds locality and translation-equivariant filters; an RNN or LSTM adds
stateful sequence processing; a transformer uses attention mechanisms to
compute contextualized token representations. A large language model is a
large-scale transformer trained to predict or model token distributions.

The topos-theoretic works surveyed below do not usually depend on the numerical
details of training. Instead, they abstract neural architectures as structured
systems of components, maps, states, parameters, symmetries, and semantic
relations.

## 5. Lafforgue: Grothendieck Topoi as Semantic Completions for AI

Laurent Lafforgue's 2022 lecture note, "Some Possible Roles for AI of
Grothendieck Topos Theory," is programmatic. Its central motivation is that
neural networks manipulate numerical functions, but mathematical meaning often
comes from structured geometric or logical origins. The proposed role of
Grothendieck topoi is to preserve and enrich such meaningful origins.

In categorical terms, one begins with a category \(\mathcal{C}\) of meaningful
objects, such as geometric shapes, symbolic structures, or knowledge objects.
Through the Yoneda embedding,

\[
y:\mathcal{C}\to\widehat{\mathcal{C}},
\]

the original category is embedded into a presheaf universe. By imposing a
Grothendieck topology \(J\) and passing to sheaves,

\[
\mathbf{Sh}(\mathcal{C},J),
\]

one obtains a richer category in which local-to-global structure, generalized
functions, and semantic invariants can be handled.

The conclusion is not an implemented learning algorithm. It is a research
program:

\[
\text{meaningful category}
\longrightarrow
\text{presheaf completion}
\longrightarrow
\text{sheaf/topos completion}.
\]

The relevant preliminary notions are Yoneda, sheafification, sites,
Grothendieck topologies, and Grothendieck topoi. Lafforgue's proposal uses
topos theory as a semantic completion mechanism, not as a direct replacement
for gradient-based learning.

## 6. Belfiore and Bennequin: Topoi and Stacks of Deep Neural Networks

Jean-Claude Belfiore and Daniel Bennequin's paper "Topos and Stacks of Deep
Neural Networks" is one of the most ambitious direct proposals connecting DNNs
to Grothendieck topoi and stacks.

Its central claim can be summarized as:

\[
\boxed{
\text{known deep neural networks can be represented as objects in canonical
Grothendieck topoi, and their invariance structures can be described by stacks.}
}
\]

The idea is that a DNN is not merely a function

\[
N_\theta:X\to Y,
\]

but a structured object involving layers, states, parameters, transformations,
symmetries, and learning dynamics. These structures can be organized into
categories and sites. The associated Grothendieck topoi provide global semantic
environments for the network, while stacks encode invariance and equivalence
data.

Several preliminary notions are directly relevant:

- **Presheaves and sheaves.** Layerwise or local network data may be viewed as
  data assigned to contexts, with restriction and gluing.
- **Grothendieck topoi.** The network is placed in a sheaf-theoretic universe.
- **Internal logic.** Semantic assertions about network behavior can be
  interpreted inside the topos.
- **Stacks.** CNNs, LSTMs, or other structured architectures may involve
  invariances and equivalences that should glue only up to isomorphism.

This framework should be read as a structural encoding proposal. It does not by
itself prove that a DNN generalizes, nor does it give a standard training
algorithm. Rather, it proposes a categorical semantics in which DNNs and their
symmetries may be represented more faithfully than by a bare composite of
functions.

## 7. The Topos of Transformer Networks: A Withdrawn but Suggestive Proposal

Villani and McBurney's "The Topos of Transformer Networks" attempts to relate
transformer expressivity to topos-theoretic completion. The arXiv page marks the
paper as withdrawn and requiring major revision, so its claims must be treated
as unstable.

The proposed picture is roughly as follows. Many conventional neural-network
architectures are said to embed in a pretopos-like category of piecewise-linear
functions. Transformers, by contrast, are argued to require a richer topos
completion, reflecting their contextual, higher-order, and attention-based
structure.

The relevant preliminary notions are:

- **Pretopos.** A category with finite limits, disjoint finite coproducts, and
  effective quotients in a suitable sense.
- **Topos completion.** A process of embedding a weaker categorical environment
  into a richer topos-like one.
- **Exponentials and internal logic.** Transformers are interpreted as needing
  richer function-object and higher-order expressive capacity.

Because the paper is withdrawn, the responsible conclusion is not that
transformers have been rigorously characterized by a stable topos theorem.
Rather, this work points toward a research question:

\[
\text{Does attention-based contextual computation require categorical
structure beyond ordinary first-order neural-network semantics?}
\]

This is a useful idea, but not currently a settled result.

## 8. Mahadevan: Topos Theory for Generative AI and LLMs

Mahadevan's "Topos Theory for Generative AI and LLMs" proposes that categories
of LLM-like systems may possess topos-theoretic structure and that universal
constructions can guide the design of compositional AI architectures.

The claimed direction is:

1. treat LLMs or generative models as objects or morphisms in a category;
2. show the resulting category has limits, colimits, exponentials, and
   subobject-classifier-like structure;
3. use universal constructions to design or analyze model composition.

For example:

- pullbacks model semantic alignment;
- pushouts model modular fusion;
- equalizers model agreement between model outputs;
- coequalizers model quotienting by behavioral equivalence;
- exponentials model conditional or higher-order model spaces;
- subobject classifiers model predicates or classifiers over model behavior.

This work therefore uses almost every major preliminary notion above: limits,
colimits, exponentials, subobjects, truth values, and categorical universes.
The main caution is that the construction depends heavily on how the category
of models is defined. Without a precise category and precise morphisms, the
statement "LLMs form a topos" is a guiding slogan rather than a mathematical
theorem.

## 9. Jia-Peng-Yang-Chen Survey

The survey "Category-Theoretical and Topos-Theoretical Frameworks in Machine
Learning" classifies categorical machine learning into several broad tracks:

1. gradient-based learning;
2. probability-based learning;
3. invariance and equivalence-based learning;
4. topos-based learning.

The first three tracks are closer to established applied category theory:
Cartesian differential categories, lenses, Markov categories, categorical
probability, and equivariant learning. The fourth track collects more
exploratory work involving Grothendieck topoi, stacks, sheaves, and internal
logic.

The survey is useful as a map, not as a single theorem. Its main contribution is
to identify where topos-theoretic proposals sit relative to more mature
categorical ML frameworks.

## 10. Comparison of the Works

| Work | Main construction or claim | Topos notions used | Status |
|---|---|---|---|
| Lafforgue | Grothendieck topoi as semantic completions for meaningful AI objects | Yoneda, sheaves, sites, topoi | programmatic |
| Belfiore-Bennequin | DNNs as objects in canonical Grothendieck topoi; invariance via stacks | Grothendieck topoi, stacks, internal logic | ambitious structural framework |
| Transformer topos paper | transformers require topos completion beyond pretopos-like neural categories | pretopos, topos completion, exponentials | withdrawn; research pointer |
| Mahadevan | LLM categories may form topoi; universal constructions guide AI composition | limits, colimits, exponentials, subobject classifier | speculative proposal |
| Jia-Peng-Yang-Chen | survey of categorical and topos-theoretic ML | broad survey | literature map |

The common theme is not an empirical theorem but a structural thesis:

\[
\text{neural systems should be studied as objects in categories rich enough to
encode context, locality, semantics, invariance, and internal logic.}
\]

## 11. What Is Actually Proved?

It is useful to distinguish four levels of claim.

### Level 1: Established Topos Theory

The definitions and theorems about presheaves, sheaves, sheafification,
Grothendieck topoi, internal logic, and geometric morphisms are classical
mathematics. These are reliable.

### Level 2: Structural Representation Claims

Some works claim that certain neural architectures can be represented in
topos-theoretic or stack-theoretic settings. These are mathematical modeling
claims. Their value depends on whether the representation preserves important
network structure rather than merely encoding everything trivially.

### Level 3: Semantic Interpretation Claims

Claims about meaning, interpretability, contextual truth, and internal logic are
philosophically and mathematically suggestive, but require careful definitions
of the relevant predicates, contexts, covers, and semantic objects.

### Level 4: Algorithmic or Empirical Claims

Very few of these works establish direct performance improvements, generalization
bounds, or practical algorithms comparable to standard ML papers. Such claims
remain largely open.

## 12. Research Outlook

The most plausible near-term research directions are:

1. **Sheaf-theoretic consistency for model outputs.** Use local-to-global
   structures to measure whether local explanations or predictions glue.
2. **Categorical semantics for modular model composition.** Use pullbacks,
   pushouts, equalizers, and coequalizers to define principled composition.
3. **Topos-inspired knowledge representation.** Treat contextual truth and
   evidence as internal logical structure rather than global Boolean labels.
4. **Stack-like invariance in representations.** Use stacks or groupoids to
   describe equivalences between learned representations.
5. **Precise categories of LLMs.** Define objects and morphisms carefully enough
   that claims about limits, exponentials, and subobject classifiers become
   genuine theorems.

## 13. Conclusion

Topos-theoretic approaches to neural networks and LLMs are best understood as a
developing semantic and structural program. Their central claim is that
neural-network architectures are not merely numerical functions but structured
objects involving local data, context dependence, invariance, and logical
content. Grothendieck topoi, sheaves, stacks, and internal logic provide a
language for organizing these features.

The responsible reading is therefore twofold. The categorical preliminary
material is stable and powerful; its application to AI is promising but uneven.
The most mature neighboring area is sheaf and topological deep learning. Direct
topos-based accounts of DNNs, transformers, and LLMs remain exploratory, but
they identify a coherent mathematical ambition: to move from black-box
parametrized maps to structured semantic universes in which local computation,
global meaning, and contextual truth can be studied together.

## References

- Jean-Claude Belfiore and Daniel Bennequin,
  [Topos and Stacks of Deep Neural Networks](https://arxiv.org/abs/2106.14587).
- Laurent Lafforgue,
  [Some Possible Roles for AI of Grothendieck Topos Theory](https://www.laurentlafforgue.org/Expose_Lafforgue_topos_AI_ETH_sept_2022.pdf).
- Mattia Jacopo Villani and Peter McBurney,
  [The Topos of Transformer Networks](https://arxiv.org/abs/2403.18415).
  The arXiv record marks this paper as withdrawn and requiring major revision.
- Sridhar Mahadevan,
  [Topos Theory for Generative AI and LLMs](https://arxiv.org/abs/2508.08293).
- Yiyang Jia, Guohong Peng, Zheng Yang, and Tianhao Chen,
  [Category-Theoretical and Topos-Theoretical Frameworks in Machine Learning:
  A Survey](https://arxiv.org/abs/2408.14014);
  published version:
  [Axioms 2025, 14, 204](https://doi.org/10.3390/axioms14030204).
- Saunders Mac Lane and Ieke Moerdijk, *Sheaves in Geometry and Logic*.
- Peter Johnstone, *Sketches of an Elephant: A Topos Theory Compendium*.
- Steve Awodey, *Category Theory*.
