# A Study on the Hierarchical Structure of Knowledge and the Cognition of Ignorance

*Kunihiro Sugiyama*  
kunihiros@gmail.com

## Introduction

Human knowledge possesses a multi-layered structure, and the ability to recognize one's own ignorance (metacognition) is crucial for learning and decision-making. This study proposes a recursive model of knowledge and ignorance based on a single core function: **$K$**, which represents epistemic recognition. By applying this function recursively—$K(x)$, $K(K(x))$, $K(K(K(x)))$, and so on—we formalize the hierarchical structure of self-awareness that distinguishes **Socratic wisdom** ("knowing that one does not know") from the **Dunning-Kruger effect** ("not knowing that one does not know").

Kant (1781), in his *Critique of Pure Reason*, posed the foundational question of epistemology: what are the limits of human cognition, and can reason examine itself? His answer—that reason must critique reason—established the recursive structure of self-reflection as a philosophical problem. Yet Kant's contribution was **descriptive**: he demonstrated that limits exist, but provided no apparatus for locating their precise coordinates or guiding their correction.

This study provides what classical epistemology could not: a **mathematical framework** that transforms the Kantian question from philosophical meditation into **operational methodology**. The function $K$ does not merely describe where cognition fails—it provides the coordinates for **targeted intervention**. By representing epistemic states on a continuous scale, we gain the capacity to **observe the phenomenon of intelligence itself, and to intervene in its structure**. This framework opens the possibility of not only understanding cognition but **actively shaping its trajectory toward new forms of knowing**.

This model integrates insights from **metacognition research**, **epistemology**, and **type theory** to address three aspects that have not been sufficiently unified in existing research:

1. The **recursive nature of self-awareness**: The same epistemic question ("Do I know?") can be applied at every level of reflection.
2. The **continuous gradation of knowledge**: Knowledge states exist on a continuum from complete misconception ($-1$) through ignorance ($0$) to accurate knowledge ($1$).
3. The **distinction between epistemic state and phenomenological confidence**: What one knows versus how certain one feels are orthogonal dimensions.

By presenting a mathematically rigorous yet philosophically grounded framework, this study seeks to deepen our understanding of the structure of knowledge and the cognitive mechanisms of ignorance.

### Contribution: A Conceptual Foundation

This paper establishes the **conceptual foundation** for a unified theory of recursive metacognition. The trichotomy of epistemic states—**knowing**, **not knowing**, and **misunderstanding**—is a universal human experience that transcends cultures, domains, and disciplines. Before elaborating measurement-theoretic models or conducting empirical validation, we must first **settle the conceptual vocabulary**.

**What this paper provides:**
1. A **single, unified operator $K$** that applies recursively at all levels of self-reflection
2. A **purely observational framework** where $K$ is not a mental process but an **observation protocol**
3. A **complete taxonomy** (27 patterns) that classifies all possible metacognitive configurations
4. A **resolution of apparent contradictions** (e.g., $K(0) = 0$ vs $K_1 = -1$) through layer independence

**What this paper deliberately does not provide:**
- Probabilistic measurement models (future work)
- Empirical validation (orthogonal contribution)
- Formal type-theoretic proofs (analogical treatment suffices for conceptual clarity)

These omissions are not gaps but **scope boundaries**. Measurement-theoretic elaboration and empirical validation require this conceptual foundation to be settled first. We invite the research community to build upon this foundation.


## Philosophical Foundation and Interpretive Notes

This section clarifies the philosophical motivation behind this paper and provides essential interpretive guidance to prevent misunderstanding of the proposed model.

### Theoretical Rationale

This study is grounded in the logical structure of recursive ignorance, exemplified by the proposition **"I don't know what I don't know."** If "knowing one's ignorance" (Socratic wisdom) is a recognized concept, then logically, "not knowing one's ignorance" must also exist. And if that exists, then so must "not knowing that one doesn't know one's ignorance"—and so on, recursively.

The goal of this paper is to **mathematically formalize this recursive structure of knowledge and ignorance**, not to judge or rank cognitive states.

### Descriptive Nature of the Scale

The values $-1$, $0$, and $1$ in this model function as **epistemic state descriptors**. They serve as epistemic coordinates rather than normative metrics (e.g., "good" or "bad").

| Value | Meaning |
|:---:|:---|
| $1$ | The subject holds correct knowledge. |
| $0$ | The subject lacks knowledge (ignorance). |
| $-1$ | The subject holds incorrect knowledge (misconception). |

A subject in state $-1$ (misconception) is not normatively inferior to a subject in state $0$ (ignorance); they occupy **distinct epistemic loci**. Whether one state is "preferable" to another depends on context, goals, and values—domains outside the scope of this model.

### Separation of Knowledge and Confidence

A fundamental distinction in this framework is that **the function $K$ measures epistemic state, not phenomenological confidence**. Confidence is a separate dimension that will be introduced later in the measurement section.

* $K(x)$: How accurately the subject recognizes object $x$ (epistemic state).
* $C$ (Confidence): How certain the subject feels about their recognition (phenomenological experience).

This separation is essential for capturing phenomena like the Dunning-Kruger effect, where $K(x) = 0$ (the subject does not know) but $K(K(x)) = -1$ (the subject misrecognizes their ignorance), often accompanied by high subjective confidence.


## Scope Clarification: Methodological Relativism

This section clarifies the scope and philosophical stance of this framework.

### What This Model Does

This model provides a **mathematical apparatus** for representing and manipulating the **structure of epistemic states** relative to a proposition. The function $K(x)$ measures the subject's epistemic state regarding proposition $x$:

| $K(x)$ | State | Interpretation |
|:---:|:---|:---|
| $1$ | Aligned | Subject's belief is consistent with $x$ |
| $0$ | Indeterminate | Subject has no determinate stance on $x$ |
| $-1$ | Opposed | Subject's belief is contrary to $x$ |

### What This Model Does Not Do

This model **does not adjudicate** what is "correct" or "true." The designation of a proposition as the "target" (such that $K(x) = 1$ represents success) is a **methodological choice** made by the experimenter, not a claim of this framework.

The proposition $x$ itself serves as the **implicit reference point**. What counts as "aligned" ($K(x) = 1$) versus "opposed" ($K(x) = -1$) is determined by the **experimental context** (e.g., expert consensus, empirical measurement, community agreement), not by this model.

### Methodological Relativism

This framework adopts a position of **methodological relativism**: the reference point is necessarily context-dependent, and the model operates on the structure of epistemic states relative to that chosen reference. This design allows researchers with different philosophical commitments (realism, relativism, pragmatism) to use the same mathematical framework while maintaining their preferred interpretation of what constitutes "correct" knowledge.

## The Recursive Structure: $K(K(K(x)))$

The cognitive structure of knowledge is modeled using a **recursive epistemic function** $K$. This model formalizes the intuition that the same question—"Do I know?"—can be applied at every level of self-reflection.

### Formal Definition of $K$

We adopt an **observational family** interpretation of $K$, which provides a clear and consistent framework for understanding recursive metacognition.

#### Formal Framework: Layered Observation Model

**Definition (Observation Family):**

Let $\{K^{(n)}\}_{n=0}^{\infty}$ be a family of observation functions, where each $K^{(n)}$ maps from a layer-specific state space to the epistemic scale $[-1, 1]$:

$$K^{(n)}: \mathcal{S}_n \to [-1, 1]$$

**Definition (State Hierarchy):**

- $\mathcal{S}_0$: First-order epistemic states (correctness of responses)
- $\mathcal{S}_1$: Metacognitive states (alignment between claims and $\mathcal{S}_0$)
- $\mathcal{S}_n$: n-th order states (alignment between claims and $\mathcal{S}_{n-1}$)

**Notational Convention:**

The notation $K(K(x))$ is a **shorthand** for $K^{(1)}(\text{State}_1(x))$, not numerical composition.

More precisely:
- $K_0(x) := K^{(0)}(\text{State}_0(x))$
- $K_1(x) := K^{(1)}(\text{State}_1(x))$
- $K_n(x) := K^{(n)}(\text{State}_n(x))$

**Shared Anchor Semantics:**

All $K^{(n)}$ share the same anchor constraints:
- $K^{(n)}(\text{"knowledge"}) = 1$
- $K^{(n)}(\text{"ignorance"}) = 0$
- $K^{(n)}(\text{"misconception"}) = -1$

This ensures cross-layer comparability while allowing distinct measurement procedures per layer.

#### Entry and Recursive Mappings

**1. Entry Mapping (Layer 0):**

For an abstract object $x$ (e.g., a proposition, a task item, or any epistemic target), the subject's first-order epistemic condition is represented as a continuous value:

$$k_0(x) \in [-1, 1]$$

This is the **only point** where the external object $x$ enters the model. The internal representation $k_0$ captures how the subject stands with respect to $x$.

**2. Recursive Mapping (Layers $n \ge 1$):**

At all higher layers, the observation family $\{K^{(n)}\}$ acts on layer-specific states:

$$K^{(n)}: \mathcal{S}_n \to [-1, 1]$$

The "object" of higher-order $K^{(n)}$ is not the numerical output of the previous layer but the **distinct state object** $\text{State}_n$.

**Output Interpretation (Prototypical Anchor Points):**

The values $-1$, $0$, and $1$ serve as **prototypical anchors** on the continuous scale $[-1, 1]$:

- $K(\cdot) = 1$: The subject accurately recognizes the target (full knowledge or accurate metacognition).
- $K(\cdot) = 0$: The subject has no determinate stance regarding the target (pure ignorance).
- $K(\cdot) = -1$: The subject misrecognizes the target (misconception or metacognitive failure).

All intermediate values represent **graded mixtures** of these prototypes (partial knowledge, partial misconception, uncertainty, etc.).

**Key Insight:** The function $K$ has **consistent semantics** across all layers: "How accurately does the subject recognize this target?" At Layer 0, the target is an external object $x$. At Layers $n \ge 1$, the target is the subject's own epistemic state $k_{n-1}$.

### Observation and Objects: The Purely Observational Framework

This framework adopts a **purely observational stance**: epistemic states are operationalized as observable responses, and metacognitive states as observable alignments between claims and performance. We do not posit internal "beliefs" or "perceptions" — only **states** that are measurable by an external observer.

**The Observer:**

In experimental settings, the "observer" is the **experimenter** who:
1. Presents a task/question
2. Records the respondent's answer
3. Compares the answer to a reference
4. Assigns a $K$ value based on the comparison

The Observer does not access internal "perception" or "belief." The Observer only sees **observable behavior**: answers, claims, responses.

**Formal Definition of State$_n$:**

**State$_0$ (First-Order Epistemic State):**

$$\text{State}_0(x) = f_0(\text{Response}(x), \text{Reference}(x))$$

Where:
- $\text{Response}(x)$: Subject's answer to item $x$
- $\text{Reference}(x)$: Ground truth or expert consensus
- $f_0$: Comparison function yielding {correct, incorrect, absent}

**State$_1$ (Metacognitive State):**

$$\text{State}_1(x) = f_1(\text{Claim}_1(x), \text{State}_0(x))$$

Where:
- $\text{Claim}_1(x)$: Subject's metacognitive claim ("I know" / "I don't know" / "I'm wrong")
- $f_1$: Alignment function yielding {aligned, uncertain, misaligned}

**State$_n$ (n-th Order State):**

$$\text{State}_n(x) = f_n(\text{Claim}_n(x), \text{State}_{n-1}(x))$$

**Graphical Model:**

```
Response(x) ──┐
              ├─→ f_0 ──→ State_0 ──→ K^(0) ──→ K_0
Reference(x) ─┘              │
                             ↓
Claim_1(x) ─────────────→ f_1 ──→ State_1 ──→ K^(1) ──→ K_1
                                    │
                                    ↓
Claim_2(x) ─────────────────────→ f_2 ──→ State_2 ──→ K^(2) ──→ K_2
```

**Operational Interpretation:**

- **State$_0$ (first-order epistemic state)**: The respondent's answer compared to a reference.
  - Operationalized as: "Is the answer correct, incorrect, or absent?"
  
- **State$_1$ (metacognitive state)**: The alignment between the respondent's metacognitive claim and their actual State$_0$.
  - Operationalized as: "Does the claim 'I know' match the actual correctness?"
  
- **State$_2$ (meta-metacognitive state)**: The alignment between the respondent's meta-metacognitive claim and their actual State$_1$.

**Example:**
- Respondent answers incorrectly → State$_0$ = "ignorance" → $K_0 = 0$
- Respondent claims "I know" → State$_1$ = "misalignment" → $K_1 = -1$
- Respondent claims "My self-assessment is accurate" → State$_2$ = "misalignment" → $K_2 = -1$

**Critical Clarification:**

Each $K_n$ is an **independent observation** of a **distinct object** (State$_n$):

- **$K_0(x)$**: Observer's measurement of **State$_0$**
- **$K_1(x)$**: Observer's measurement of **State$_1$**
- **$K_2(x)$**: Observer's measurement of **State$_2$**

$$K_1(x) \neq K(K_0(x))$$

$K_1$ is **not** "applying $K$ to the numerical value of $K_0$."
$K_1$ is "observing a different object (State$_1$) and reporting the measurement."

**Resolving the Apparent Contradiction ($K(0) = 0$ vs $K_1 = -1$):**

The axiom $K(0) = 0$ means: "If the observed state is 'ignorance' (0), the measurement result is 'ignorance' (0)."

In the Dunning-Kruger case:
- $K_0(x) = 0$: Observer measures State$_0$ → "ignorance"
- $K_1(x) = -1$: Observer measures State$_1$ → "misalignment"

**State$_1$ is not "0".** State$_1$ is the metacognitive state (alignment/misalignment), which the observer measures as "misrecognition" (-1).

The axiom $K(0) = 0$ does not apply because the input to $K_1$ is **not** the number "0". The input is **State$_1$**, a different object entirely.

**Analogy (Thermometer Calibration):**

Consider a thermometer and its calibration:
- **State$_0$ (temperature)**: The actual temperature of water = 20°C
- **State$_1$ (thermometer accuracy)**: Whether the thermometer correctly reads State$_0$

Measuring State$_0$ = 20°C does not constrain State$_1$. The thermometer might be:
- Accurate (State$_1$ = correct) → $K_1 = 1$
- Miscalibrated (State$_1$ = incorrect) → $K_1 = -1$

$K_1$ measures a **property of the measuring instrument**, not the original object. Similarly, $K_1$ measures the accuracy of **the respondent's self-monitoring**, not the first-order state itself.

### Type-Theoretic Foundation

To address concerns about mathematical rigor, we provide a type-theoretic justification for the recursive structure.

**Core Principle:** All epistemic states live on a **single continuous scale** $[-1, 1]$. The recursive structure is well-defined because $K$ maps this space to itself.

**Two-Stage Type Structure:**

```
-- Layer 0: Entry from abstract object to epistemic state
k0 : Object -> Real[-1, 1]

-- Layers n >= 1: Recursive self-application on the epistemic state space
K  : Real[-1, 1] -> Real[-1, 1]
```

**Recursive Application:**

Once we are on the epistemic state space $[-1, 1]$, recursion is straightforward:

```
k0 = k0(x)           -- Entry: external object -> epistemic state
k1 = K(k0)           -- Layer 1: metacognition of k0
k2 = K(k1)           -- Layer 2: metacognition of k1
...
```

**This is not a type error.** This is a **recursive type** with a well-defined structure, analogous to:
- **Lambda Calculus**: Self-application via $\lambda x. (\lambda y. y) x$
- **Fixed-Point Combinators**: $Y = \lambda f. (\lambda x. f(x x))(\lambda x. f(x x))$
- **Recursive Types**: $\mu \alpha. \alpha \to \alpha$

The recursive structure $K(K(x))$ is mathematically well-founded and has precedent in formal systems.

### Axiomatic Constraints on $K$

We impose the following minimal constraints on the epistemic function $K$:

**Definition: Objective Evaluation**

The function $K$ represents an **objective evaluation** of the subject's epistemic state by an external observer (or the system), distinct from the subject's subjective feeling of confidence ($C$).

- $K(x) = 1$: Objectively accurate recognition.
- $K(x) = -1$: Objectively inverted recognition (misconception).

**Axiom Scope:**

The axioms describe the behavior of the observation function $K$ **within a single layer**.

- $K(1) = 1$: If the observed state is "knowledge", report "knowledge"
- $K(0) = 0$: If the observed state is "ignorance", report "ignorance"
- $K(-1) = -1$: If the observed state is "misconception", report "misconception"

**Layer Independence:**

Each $K_n$ observes a **different object** (State$_n$). The axioms apply to each observation independently.

| Layer | Object Observed | Axiom Application |
|:---:|:---|:---|
| $K_0$ | State$_0$ (first-order epistemic state) | $K$(State$_0$) follows axioms |
| $K_1$ | State$_1$ (metacognitive state) | $K$(State$_1$) follows axioms |
| $K_2$ | State$_2$ (meta-metacognitive state) | $K$(State$_2$) follows axioms |

**Why $K_0 = 0$ and $K_1 = -1$ is NOT a contradiction:**

- $K_0 = 0$: Observer measures State$_0$ as "ignorance"
- $K_1 = -1$: Observer measures State$_1$ as "misrecognition"

State$_0 \neq$ State$_1$. They are different objects. The axiom $K(0) = 0$ applies to State$_0$, not to State$_1$.

**Monotonicity:**

Monotonicity applies **within each layer**: if State $>$ State', then $K$(State) $\geq$ $K$(State').

It does NOT constrain relationships **across layers** (e.g., $K_0$ vs $K_1$).

**Boundedness:**

$K: [-1, 1] \to [-1, 1]$

Each observation is bounded on this interval.

**Note:** We deliberately refrain from specifying stronger constraints (e.g., odd symmetry, Lipschitz constant, contraction mapping) at this stage. The framework is intended to be **descriptive** rather than **predictive**—it provides a vocabulary for classifying observed metacognitive states, not a generative model of metacognitive dynamics. Specifying a particular functional form for $K$ is a task for domain-specific empirical research.

### Recursive Application

**Notation:**

We use subscript notation to denote the layer of observation:

$$K_0(x) = K(\text{State}_0)$$
$$K_1(x) = K(\text{State}_1)$$
$$K_2(x) = K(\text{State}_2)$$

**Important Clarification:**

The traditional notation $K(K(x))$ is **shorthand** for $K_1(x)$, but it should **not** be interpreted as function composition (i.e., $K(K_0(x))$ where the numerical value of $K_0$ is passed to $K$).

Each $K_n$ observes a **distinct object** (State$_n$), not the numerical output of the previous layer.

**Interpretation:**

| Layer | Expression | Object Observed | Question |
|:---|:---|:---|:---|
| **Layer 0** | $K_0(x)$ | State$_0$ (first-order epistemic state) | "Is the respondent's answer correct?" |
| **Layer 1** | $K_1(x)$ | State$_1$ (metacognitive state) | "Is the respondent's self-assessment aligned with their actual State$_0$?" |
| **Layer 2** | $K_2(x)$ | State$_2$ (meta-metacognitive state) | "Is the respondent's meta-self-assessment aligned with their actual State$_1$?" |

**Same observation function $K$. Different objects (State$_n$). Independent measurements.**

### Examples

#### Example 1: Knowing Knowledge

- $K(x) = 1$: The subject knows that "water boils at 100°C."
- $K(K(x)) = 1$: The subject accurately recognizes that they know this fact.
- **Classification**: Knowing Knowledge (accurate self-awareness)

#### Example 2: Socratic Wisdom

- $K(x) = 0$: The subject does not know the boiling point of water.
- $K(K(x)) = 1$: The subject accurately recognizes their ignorance ("I know that I don't know").
- **Classification**: Knowing Ignorance (Socratic wisdom)

#### Example 3: Dunning-Kruger Effect

- $K(x) = 0$: The subject does not know the boiling point of water.
- $K(K(x)) = -1$: The subject misrecognizes their ignorance, believing they know.
- **Classification**: Unknowing Ignorance (Dunning-Kruger effect)

#### Example 4: Imposter Syndrome

- $K(x) = 1$: The subject knows that "water boils at 100°C."
- $K(K(x)) = -1$ or $0$: The subject does not recognize their knowledge ("I don't think I know this").
- **Classification**: Unknowing Knowledge (imposter syndrome)

### The Four Quadrants of Metacognition

The relationship between $K(x)$ (actual state) and $K(K(x))$ (metacognitive accuracy) produces four archetypal patterns:

| $K(x)$ | $K(K(x))$ | Classification | Interpretation |
|:---:|:---:|:---|:---|
| $1$ (Know) | $1$ (Accurate) | **Knowing Knowledge** | Accurate self-awareness |
| $0$ (Ignorant) | $1$ (Accurate) | **Knowing Ignorance** | Socratic wisdom |
| $0$ (Ignorant) | $-1$ (Misrecognition) | **Unknowing Ignorance** | Dunning-Kruger effect |
| $1$ (Know) | $-1$ or $0$ | **Unknowing Knowledge** | Imposter syndrome |

**Important Note:** The value $K(K(x)) = -1$ for "Unknowing Ignorance" does **not** mean it is "bad" in a normative sense. It simply describes an epistemic state where the subject **misrecognizes their own ignorance**. Whether this is problematic depends on context and goals.

### Complete Taxonomy: K₀ × K₁ × K₂ (27 Patterns)

With three prototypical values {-1, 0, 1} at each of three layers, there are 27 possible configurations. This taxonomy demonstrates the theoretical value of higher-order reflection ($K_2$).

#### K₀ = 1 (Knowledge)

| $K_0$ | $K_1$ | $K_2$ | Interpretation |
|:---:|:---:|:---:|:---|
| 1 | 1 | 1 | ✓ Perfect self-awareness (Ideal) |
| 1 | 1 | 0 | Knowing Knowledge, uncertain about meta |
| 1 | 1 | -1 | Knowing Knowledge, misrecognizes meta |
| 1 | 0 | 1 | Uncertain about knowledge, recognizes uncertainty |
| 1 | 0 | 0 | Generally uncertain |
| 1 | 0 | -1 | Uncertain about knowledge, misrecognizes it |
| 1 | -1 | 1 | **Imposter Syndrome (self-aware)** |
| 1 | -1 | 0 | Imposter Syndrome (ambiguous) |
| 1 | -1 | -1 | **Severe Imposter Syndrome** |

#### K₀ = 0 (Ignorance)

| $K_0$ | $K_1$ | $K_2$ | Interpretation |
|:---:|:---:|:---:|:---|
| 0 | 1 | 1 | ✓ **Perfect Socratic Wisdom** |
| 0 | 1 | 0 | Socratic Wisdom, uncertain about meta |
| 0 | 1 | -1 | Socratic Wisdom, misrecognizes meta |
| 0 | 0 | 1 | Uncertain about ignorance, recognizes uncertainty |
| 0 | 0 | 0 | Generally uncertain |
| 0 | 0 | -1 | Uncertain about ignorance, misrecognizes it |
| 0 | -1 | 1 | **Dunning-Kruger (self-aware)** — can improve |
| 0 | -1 | 0 | Dunning-Kruger (ambiguous) |
| 0 | -1 | -1 | **Severe Dunning-Kruger** — resistant to correction |

#### K₀ = -1 (Misconception)

| $K_0$ | $K_1$ | $K_2$ | Interpretation |
|:---:|:---:|:---:|:---|
| -1 | 1 | 1 | ✓ Self-aware misconception (rare, correctable) |
| -1 | 1 | 0 | Knowing Misconception, uncertain about meta |
| -1 | 1 | -1 | Knowing Misconception, misrecognizes meta |
| -1 | 0 | 1 | Uncertain about misconception, recognizes uncertainty |
| -1 | 0 | 0 | Generally uncertain |
| -1 | 0 | -1 | Uncertain about misconception, misrecognizes it |
| -1 | -1 | 1 | **Confident wrong (self-aware)** |
| -1 | -1 | 0 | Confident wrong (ambiguous) |
| -1 | -1 | -1 | **Most dangerous: Severe confident wrong** |

**Theoretical Value of $K_2$:**

The third layer ($K_2$) enables modeling of **metacognitive interventions** and their effectiveness:

- $K_2 = 1$ with $K_1 = -1$: Subject recognizes their metacognitive failure → **teachable moment**
- $K_2 = -1$ with $K_1 = -1$: Subject does not recognize their failure → **resistant to intervention**

Higher-order reflection ($K_2$, $K_3$, ...) provides diagnostic power for identifying when and how metacognitive correction is possible.

### Connection with Metacognition Research

**Flavell (1979)** defined metacognition as "the ability to monitor and control one's own cognitive activities." The recursive structure ($K \to K(K) \to K(K(K))$) formalizes this concept mathematically.

**Nelson & Narens (1990)** introduced the influential **monitoring/control framework**, distinguishing between the **object level** (cognitive processes) and the **meta level** (monitoring and control of cognition). Our framework directly corresponds to this structure:

| Nelson & Narens | This Framework |
|:---|:---|
| Object level | State$_0$ (first-order epistemic state) |
| Meta level (monitoring) | State$_1$ (metacognitive state) |
| Control signal | Not modeled (orthogonal dimension) |

Our $K_0$ and $K_1$ formalize the object/meta distinction with a **single unified operator**, providing mathematical precision to Nelson & Narens' conceptual framework.

**Koriat (1993)** proposed the **cue-utilization theory**, explaining how confidence arises from accessibility and familiarity cues rather than direct access to accuracy. This distinction between cue-based confidence and actual accuracy corresponds precisely to our separation of $C$ (confidence) and $K$ (epistemic state). Our framework accommodates cue-based confidence as a component of $C$, while $K$ measures the objective alignment between the subject's state and reality.

**Kruger and Dunning (1999)** demonstrated that individuals with low competence tend to overestimate their abilities. In our model, this corresponds to $K_0 = 0$ (ignorance) but $K_1 = -1$ (misrecognition of ignorance).

**Fleming and Daw (2017)** proposed a general Bayesian framework for metacognitive computation, modeling metacognition as "second-order inference" about the reliability of first-order cognitive processes. Their distinction between first-order states and second-order inference corresponds to our State$_0$/State$_1$ hierarchy. While their approach is Bayesian (modeling uncertainty about internal states) and ours is observational (measuring alignment between claims and performance), both frameworks capture the fundamental insight that metacognition operates on a different level from cognition itself. The K-C dissociation in our framework (epistemic state vs phenomenological confidence) parallels their analysis of how confidence can diverge from accuracy.

**Meta-d' (Maniscalco & Lau, 2012)** provides a signal detection-theoretic measure of metacognitive sensitivity. While meta-d' quantifies **how well** subjects discriminate their own correct from incorrect responses, our framework provides a **structural vocabulary** for **what** metacognitive states exist. The two approaches are complementary: meta-d' measures the quality of monitoring; our $K$ classifies the content of monitoring.

**Novel Contribution:** Our model provides a **structural formalization** of recursive self-awareness that:
1. Unifies the object/meta distinction (Nelson & Narens) with a single recursive operator
2. Separates epistemic state from cue-based confidence (Koriat)
3. Classifies all possible metacognitive configurations (27 patterns)
4. Explicitly distinguishes "Knowing Ignorance" (Socratic wisdom) as a high metacognitive achievement

### Why a Single Unified K?

One might ask: "Why not introduce separate operators for different levels?" The answer lies in the **universality of the epistemic question**.

**Philosophical Motivation:**

The question "Do I know?" is the same question at every level:
- "Do I know the answer?" → $K_0$
- "Do I know whether I know the answer?" → $K_1$
- "Do I know whether I know whether I know?" → $K_2$

**The question is universal. Only the object changes.**

A thermometer measures temperature. The same thermometer can measure the temperature of water, air, or metal. We do not need separate "water-thermometers" and "air-thermometers." The instrument is the same; the objects differ.

Similarly, $K$ is an **observation protocol**, not a mental process. The same protocol applies to different objects (State$_0$, State$_1$, State$_2$). Introducing separate operators ($R$, $E$, etc.) would obscure this fundamental unity and sacrifice the elegance of a single recursive structure.

**Practical Implementation:**

While the **semantic anchors** are shared (-1/0/1 for misconception/ignorance/knowledge), the **measurement procedures** $K^{(n)}$ may differ:

| Layer | Observable | Measurement Procedure |
|:---:|:---|:---|
| $K^{(0)}$ | Response vs Reference | Accuracy scoring |
| $K^{(1)}$ | Claim vs State$_0$ | Alignment scoring |
| $K^{(2)}$ | Meta-claim vs State$_1$ | Meta-alignment scoring |

**Parameter Tying (Optional):**

For parsimony, one may assume:
- Same noise model across layers
- Same link function (e.g., logistic)

Or allow layer-specific parameters if data supports it.

**The key constraint is shared anchor semantics, not identical functional forms.**

**The beauty of $K$ is its universality.** Knowing, not knowing, and misunderstanding are universal human experiences. The same operator captures them all.



## Measurement Theory

This section describes how the theoretical constructs ($K(x)$, $K(K(x))$) can be operationalized and measured empirically.

### Why Continuous Scale?

The continuous scale $[-1, 1]$ provides several advantages over binary or categorical representations:

**1. Intermediate States:**

Captures partial knowledge, uncertain beliefs, and mixed states that binary representations cannot express.

- Example: $K_0 = 0.3$ represents "mostly ignorant but with some relevant information"
- Example: $K_1 = -0.5$ represents "moderate overconfidence, not extreme"

**2. Change Tracking:**

Enables measurement of **gradual transitions and intervention effects**.

- Example: After metacognitive training, $K_1$ moves from $-0.8$ to $-0.2$
  - This shows improvement within the "overconfidence" category
  - Binary classification would show no change (both are "overconfident")

**3. Aggregation:**

Permits meaningful averaging across items, domains, or time points.

- Example: Average $K_1$ across 50 items yields a stable estimate
- Example: Compare $K_1$ across domains (math vs. history)

**4. Statistical Modeling:**

Compatible with standard regression, Bayesian inference, and psychometric methods.

- Linear models: $K_1 \sim K_0 + \text{training} + \epsilon$
- Hierarchical models: Subject-level and item-level random effects

**5. Geometric Extension (Future Work):**

Enables connection to **information geometry** and manifold-based analysis:

- Cognitive states as points on a manifold
- Interventions as trajectories
- Distance metrics for comparing metacognitive profiles
- Curvature analysis for stability of states

**Design Choice:**

The trichotomy $\{-1, 0, 1\}$ represents **prototypical anchors** on the continuous scale, not the only valid values. Researchers may:
- Use discrete elicitation and embed into continuous scale
- Use probabilistic elicitation for direct continuous measurement
- Aggregate discrete responses to obtain continuous estimates

### Measurement-Theoretic Interpretation

Mathematically, all epistemic states live on a **single continuous scale**:

$$K_n \in [-1, 1] \quad (n = 0, 1, 2, \dots)$$

The values $-1$, $0$, and $1$ function as **prototypical anchor points** on this continuum:

| Value | Prototype | Interpretation |
|:---:|:---|:---|
| $1$ | Full correct knowledge | Subject's state is maximally aligned with the chosen reference |
| $0$ | Pure ignorance | Subject has no determinate stance regarding the object |
| $-1$ | Full misconception | Subject's state is maximally opposed to the reference |

All intermediate values in $(-1, 0)$ and $(0, 1)$ represent **graded mixtures** of these prototypes (partial knowledge, partial misconception, uncertainty, mixtures across items, etc.).

**Operationalization Options (always mapping back to $[-1, 1]$):**

1. **Discrete elicitation → Discrete embedding**: Use trichotomous responses (True/False/I don't know), then embed into $[-1, 1]$ via $K(x) \in \{-1, 0, 1\}$ as prototype points.

2. **Probabilistic elicitation → Continuous embedding**: Elicit a subjective probability $p(x)$ and map it into $[-1, 1]$ using a proper scoring rule or a simple linear transform (e.g., centered Brier-type scores).

3. **Aggregation → Continuous embedding**: Average prototype-valued $K(x_i) \in \{-1, 0, 1\}$ across multiple items or contexts to obtain a continuous summary in $[-1, 1]$.

Conceptually, the **continuum $[-1, 1]$ is primary**; the trichotomy $\{-1, 0, 1\}$ is a convenient way to name salient regions on this line, not a separate codomain. Experimental designs may choose discrete or continuous elicitation, but in all cases the resulting data are interpreted as points (or distributions) on the same underlying scale $[-1, 1]$.

### Continuous Estimation of $K(K(x))$

The categorical inference of $K(K(x))$ from a single "Do you know?" claim is a **simplified operationalization**. For more robust measurement, we propose:

**Option 1: Aggregation Across Items**

For a subject responding to multiple items within a domain:

$$K(K)_{aggregate} = 2 \cdot P(\text{meta-claim matches actual state}) - 1$$

where $P$ is estimated across all items. This yields a continuous value in $[-1, 1]$.

**Option 2: Hierarchical Bayesian Estimation**

Model $K(K(x))$ as a latent variable with:
- Prior distribution over subjects
- Item-level random effects
- Observation model linking latent $K(K(x))$ to categorical claims

This approach accommodates noise, individual differences, and item difficulty.

**Option 3: Probabilistic Elicitation**

Instead of categorical "Yes/No/Unsure", elicit:
- "How confident are you that your previous answer was correct?" (0-100%)

Map this to $K(K(x))$ via a proper scoring rule or calibration analysis.

### The Challenge of Measuring Second-Order States

$K(K(x))$ is a **second-order epistemic state**: it represents the subject's recognition of their own first-order state $K(x)$. We cannot directly observe $K(K(x))$; we must infer it from observable behavior.

### Operational Definition of Confidence ($C$)

To fully characterize the phenomenological experience of metacognition, we additionally measure **subjective confidence** $C$.

**Definition:**

Confidence $C$ is a **phenomenological self-report** of subjective certainty, measured on a scale (e.g., 0-100% or 1-7 Likert).

$$C(x) \in [0, 1] \quad \text{(or any bounded interval)}$$

**Key Distinction: K vs C**

| Dimension | K (Epistemic State) | C (Confidence) |
|:---|:---|:---|
| **What it measures** | Alignment with reference | Subjective feeling |
| **Anchor** | Correct/Incorrect/Absent | Certain/Uncertain |
| **Sign** | Signed (−1 to 1) | Unsigned (0 to 1) |
| **Basis** | External validation | Internal experience |

**Orthogonality:**

$K$ and $C$ are **conceptually orthogonal**:

| Pattern | $K_0$ | $C$ | Interpretation |
|:---|:---:|:---:|:---|
| Confident correct | 1 | High | Ideal |
| Confident wrong | −1 | High | Dangerous misconception |
| Unconfident correct | 1 | Low | Imposter-like |
| Unconfident wrong | −1 | Low | Appropriate uncertainty |

**Diagnostic Role:**

$C$ helps distinguish subtypes within the same $K$ pattern:
- DK ($K_0=0$, $K_1=-1$) with **high $C$** → Overconfident ignorance
- DK ($K_0=0$, $K_1=-1$) with **low $C$** → Uncertain but still wrong claim

**K-C Dissociation Hypothesis:**

Subjects can have:
- High $K_0$ with low $C$ (Imposter syndrome)
- Low $K_0$ with high $C$ (Dunning-Kruger effect)

This dissociation is empirically testable and clinically meaningful.

**Measurement Protocol for C:**

1. Elicit response → compute $K_0$
2. Elicit confidence (0-100%) → record $C$
3. Elicit metacognitive claim ("Do you know?") → compute $K_1$
4. Analyze $K \times C$ jointly for full characterization

**Important Distinction (Summary):**
- $K(x)$: Epistemic state (how accurately the subject recognizes $x$)
- $C$: Phenomenological confidence (how certain the subject feels)

These are **orthogonal dimensions**. A subject can have:
- $K(x) = 0$ (ignorance) with $C = 1$ (high confidence) — Dunning-Kruger
- $K(x) = 1$ (knowledge) with $C = 0.5$ (moderate confidence) — Underconfidence

### Measurement Protocol

#### Step 1: Establish Reference Context

For each proposition $x$, establish what counts as "aligned" ($K(x) = 1$) via the experimental context (e.g., expert consensus, empirical measurement, community agreement). The proposition $x$ itself serves as the implicit reference point.

#### Step 2: Measure $K(x)$ via Task Performance

**Task:** Subject answers: "Is proposition $x$ true, false, or unknown?"

| Subject's Answer | Reference | Inferred $K(x)$ |
|:---|:---:|:---:|
| "True" | Aligned | $1$ (correct knowledge) |
| "False" | Aligned (proposition is false) | $1$ (correct knowledge) |
| "I don't know" | any | $0$ (ignorance) |
| "True" | Opposed | $-1$ (misconception) |
| "False" | Opposed (proposition is true) | $-1$ (misconception) |

#### Step 3: Measure Confidence $C_0$

**Question:** "On a scale from 0 to 1, how confident are you in your answer?"

This captures the phenomenological dimension of certainty.

#### Step 4: Elicit Metacognitive Claim

**Question:** "Do you know the answer to the previous question?"

| Subject's Claim | Interpretation |
|:---|:---|
| "Yes, I know" | Subject claims $K(K(x)) = 1$ |
| "No, I don't know" | Subject claims $K(K(x)) = 0$ |
| "I'm not sure" | Subject claims $K(K(x)) \approx 0.5$ |

#### Step 5: Infer Actual $K(K(x))$ via Comparison

Compare the subject's **metacognitive claim** (Step 4) to their **actual state** (Step 2):

| Actual $K(x)$ | Subject's Claim | Inferred $K(K(x))$ | Classification |
|:---:|:---|:---:|:---|
| $1$ (knows) | "I know" | $1$ | **Knowing Knowledge** |
| $0$ (ignorant) | "I don't know" | $1$ | **Knowing Ignorance** (Socratic) |
| $0$ (ignorant) | "I know" | $-1$ | **Unknowing Ignorance** (Dunning-Kruger) |
| $1$ (knows) | "I don't know" | $-1$ or $0$ | **Unknowing Knowledge** (Imposter) |

**Key Insight:** $K(K(x))$ is inferred by checking whether the subject's **metacognitive claim matches their actual state**.

### Analyzing Discrepancies

#### Metacognitive Discrepancy

The discrepancy between actual state and metacognitive claim is captured directly by $K(K(x))$:
- $K(K(x)) = 1$: Accurate metacognition (claim matches reality)
- $K(K(x)) = 0$: Partial metacognitive failure
- $K(K(x)) = -1$: Complete metacognitive failure (claim contradicts reality)



## Experimental Design: The Metacognitive Alignment Test (MAT)

To demonstrate the falsifiability and measurability of this model, we propose the **Metacognitive Alignment Test (MAT)**.

### Objectives

1. Measure $K(x)$ (first-order epistemic state)
2. Measure $K(K(x))$ (second-order metacognitive state)
3. Measure confidence $C$ (phenomenological dimension)
4. Validate the distinction between Socratic Wisdom and Dunning-Kruger effect

### Protocol

**Phase 1: Knowledge Assessment**
- Present factual questions with established reference answers (e.g., expert consensus)
- Subject responds: True / False / I don't know
- Calculate $K(x)$ based on alignment with reference

**Phase 2: Confidence Rating**
- Subject rates confidence: "How confident are you?" (0-1 scale)
- Record $C_0$

**Phase 3: Metacognitive Claim**
- Ask: "Do you know the answer to the previous question?"
- Subject responds: Yes / No / Unsure
- Infer $K(K(x))$ by comparing claim to actual $K(x)$

**Phase 4: Validation Tasks**
- Present decision-making scenarios requiring self-assessment
- Measure performance on tasks like:
  - Deciding when to seek help
  - Allocating study time
  - Deferring to experts

### Validation Hypothesis

**Hypothesis:** Subjects with high $K(K(x))$ (accurate metacognition) will perform better on validation tasks, **regardless of their raw $K(x)$ score**.

This would validate the model's claim that:
- **Knowing Ignorance** ($K(x) = 0, K(K(x)) = 1$) is a valuable cognitive state
- Metacognitive accuracy is distinct from first-order knowledge
- Socratic wisdom has measurable benefits

### Expected Patterns

| Pattern | $K(x)$ | $K(K(x))$ | $C$ | Expected Behavior |
|:---|:---:|:---:|:---:|:---|
| Socratic Wisdom | $0$ | $1$ | Low | Seeks help appropriately |
| Dunning-Kruger | $0$ | $-1$ | High | Overconfident errors |
| Accurate Expert | $1$ | $1$ | High | Confident and correct |
| Imposter Syndrome | $1$ | $-1$ or $0$ | Low | Underconfident but correct |

### Relationship to Established Metrics

The MAT is designed to **complement, not replace**, existing metacognitive measures:

| Metric | What it measures | Relationship to MAT |
|:---|:---|:---|
| **meta-d'** | Metacognitive sensitivity (discrimination) | Can be computed from MAT data; provides aggregate validation |
| **Brier Score** | Probabilistic calibration | Applicable if confidence is elicited as probability |
| **ECE** | Expected calibration error | Measures bias in confidence-accuracy relationship |
| **AUROC** | Discrimination ability | Can be derived from confidence ratings vs. accuracy |
| **IRT** | Item difficulty and discrimination | Can model item-level variance in MAT responses |

**Recommended Analysis Pipeline:**

1. Compute $K(x)$ and $K(K(x))$ per item using MAT protocol
2. Compute meta-d' across trials as aggregate metacognitive sensitivity
3. Compute calibration metrics (Brier, ECE) from confidence ratings
4. Compare $K(K(x))$ patterns (Socratic, Dunning-Kruger, etc.) with meta-d' to validate convergent validity
5. Use IRT to account for item-level heterogeneity

**Hypothesis:** High $K(K(x))$ (accurate metacognition) should correlate with high meta-d'/d' ratio and good calibration, but $K(K(x))$ provides additional structural information (e.g., distinguishing Socratic wisdom from mere low confidence).



## Related Work

### Relationship to Epistemic Logic

Traditional epistemic logics (e.g., S5, KD45) model knowledge via modal operators with introspection axioms:

- **Positive Introspection**: $Kp \to KKp$ ("If I know $p$, I know that I know $p$")
- **Negative Introspection**: $\neg Kp \to K\neg Kp$ ("If I don't know $p$, I know that I don't know $p$")

**Comparison to Our Framework:**

| Aspect | Epistemic Logic | Our $K(K(x))$ |
|:---|:---|:---|
| **Representation** | Binary (knows/doesn't know) | Continuous $[-1, 1]$ |
| **Misconception** | Not modeled | $K(x) = -1$ |
| **Metacognitive failure** | Violates introspection axioms | $K(K(x)) \neq \text{sign}(K(x))$ |
| **Dunning-Kruger** | Not expressible | $K(x) = 0, K(K(x)) = -1$ |

**Key Departure:** Epistemic logics typically assume idealized agents with perfect introspection. Our framework explicitly models **failures of introspection**—cases where $K(K(x)) \neq \text{sign}(K(x))$. This captures the Dunning-Kruger effect and imposter syndrome, which are empirically observed but cannot be expressed in standard epistemic logics without violating the introspection axioms.

Our approach can be seen as a **graded, psychologically realistic** extension of epistemic logic that relaxes the introspection axioms to accommodate metacognitive failures.

### Relationship to Graded Epistemic Logics

Recent work in graded epistemic logics (e.g., S5G frameworks) models knowledge with continuous plausibility values in $[0, 1]$. Our framework differs in key respects:

| Aspect | Graded Epistemic Logics | Our $K(K(x))$ |
|:---|:---|:---|
| **Scale** | $[0, 1]$ (plausibility) | $[-1, 1]$ (includes misconception) |
| **Misconception** | Typically not modeled | $K(x) = -1$ |
| **Metacognition** | Introspection axioms | Explicit recursive operator |
| **Focus** | Idealized agents | Psychologically realistic failures |

**Formal Correspondence:**

Our $K$ can be viewed as a **graded, psychologically realistic** extension that:

1. Relaxes positive/negative introspection axioms to accommodate metacognitive failures
2. Extends the scale to include misconception (negative values)
3. Focuses on the **gap** between actual and recognized epistemic states, rather than idealized consistency

Whether $K$ is idempotent ($K(K(x)) = K(x)$ for accurate metacognizers) or contractive (higher-order reflection converges) is an **empirical question** that our framework can accommodate but does not presuppose.

### Metacognitive Sensitivity: meta-d'

Maniscalco and Lau (2012) developed the *meta-d'* framework for measuring metacognitive sensitivity—the ability to discriminate between correct and incorrect responses via confidence ratings.

**Comparison:**

| Aspect | meta-d' | Our $K(K(x))$ |
|:---|:---|:---|
| **Focus** | Discrimination ability (sensitivity) | Structural accuracy (recognition) |
| **Measurement** | Statistical correlation across trials | Per-item metacognitive state |
| **Granularity** | Aggregate across trials | Per-item |
| **"I don't know"** | Treated as low confidence | $K(x)=0, K(K(x))=1$ (Socratic wisdom) |
| **Statistical Model** | Noise-tolerant (SDT) | Deterministic match/mismatch |
| **Theoretical Basis** | Signal Detection Theory | Recursive epistemology |

**Key Difference:** meta-d' measures whether confidence ratings **correlate** with accuracy. Our model measures whether metacognitive claims **match** actual states. Crucially, we recognize that **accurately knowing one's ignorance** ($K(x) = 0, K(K(x)) = 1$) is a **high metacognitive achievement**, not a failure.

**Complementary Relationship:** These approaches are **not mutually exclusive**. meta-d' provides a noise-tolerant aggregate measure of metacognitive sensitivity; our $K(K(x))$ provides per-item structural classification with explicit treatment of Socratic wisdom. An integrated approach could:
- Use meta-d' for aggregate sensitivity analysis across trials
- Use $K(K(x))$ for per-item classification and Socratic wisdom detection
- Define a continuous version: $K(K(x)) = 2 \cdot P(\text{meta-claim matches actual state}) - 1$, estimated across trials via hierarchical Bayesian methods

### Information-Theoretic Metacognition: meta-I

Dayan (2023) introduced *meta-I*, a **model-free** information-theoretic measure of metacognitive sensitivity:

$$\text{meta-I} = H(\text{accuracy}) - H(\text{accuracy} | \text{confidence})$$

This measures mutual information between confidence and accuracy, quantifying how much confidence reduces uncertainty about accuracy.

**Comparison:**

| Aspect | meta-I | Our $K$ Framework |
|:---|:---|:---|
| **Theoretical Basis** | Information Theory | Recursive Epistemology |
| **Model Dependency** | Model-free | Model-free (observational) |
| **Direction** | Unsigned (sensitivity only) | **Signed** (over/under-confidence) |
| **Layers** | Single layer | **Recursive** ($K_0, K_1, K_2, \ldots$) |
| **Output** | Bits (continuous) | $[-1, 1]$ (continuous) |
| **Granularity** | Can measure response granularity | Per-item structural classification |

**Key Distinction:**

Both meta-I and $K$ are **model-free** (unlike meta-d' which requires SDT assumptions), but they serve different purposes:

- **meta-I** answers: "How well does confidence track accuracy?" (quantitative sensitivity)
- **$K$** answers: "What type of metacognitive pattern is this?" (qualitative classification)

**Complementary Use Case:**

Two subjects with identical meta-I = 0.3 bits (low sensitivity):
- Subject A: $K_0=0$, $K_1=-1$ → Dunning-Kruger → needs awareness intervention
- Subject B: $K_0=1$, $K_1=-1$ → Imposter → needs confidence-building

meta-I cannot distinguish these cases; $K$ can.

**Analogy:**
- meta-d' / meta-I = **Thermometer** (measures metacognitive temperature)
- $K$ = **Weather map** (classifies metacognitive patterns, guides intervention)

### Calibration Metrics (Brier Score, ECE)

Calibration metrics measure whether confidence aligns with accuracy across many trials.

**Comparison:**

| Aspect | Calibration Metrics | Our $K(K(x))$ |
|:---|:---:|:---|
| **Granularity** | Aggregate statistics | Individual items |
| **Purpose** | Probabilistic accuracy | Epistemic state recognition |
| **Socratic Wisdom** | Not explicitly modeled | Explicitly formalized |

**Complementary Relationship:** Calibration metrics and $K(K(x))$ measure different aspects of metacognition. A subject can have good calibration (confidence matches accuracy on average) but poor $K(K(x))$ on specific items (e.g., confidently wrong about specific facts).

### Belief Functions and Uncertainty (Dempster-Shafer Theory)

Dempster-Shafer theory handles **epistemic uncertainty** and **conflicting evidence** via belief functions.

**Comparison:**

| Aspect | Dempster-Shafer | Our Model |
|:---|:---|:---|
| **Focus** | Uncertainty quantification | Metacognitive discrepancy |
| **Application** | Evidence combination | Self-awareness structure |
| **Ignorance** | Represented as belief mass | $K(x) = 0$ (epistemic state) |

**Complementary Relationship:** Dempster-Shafer theory could be used to model uncertainty about the reference point when expert consensus is incomplete. Our model specifically targets the **gap between what one knows and what one thinks one knows**.

### Dunning-Kruger Effect (Empirical Psychology)

Kruger and Dunning (1999) empirically demonstrated that low-competence individuals overestimate their abilities.

**Our Contribution:** We provide a **formal mathematical model** of this phenomenon:
- $K(x) = 0$ (low competence)
- $K(K(x)) = -1$ (misrecognition: believes they have competence)
- Often accompanied by $C = 1$ (high confidence)

This formalization enables:
1. Precise measurement protocols
2. Distinction from related phenomena (e.g., imposter syndrome)
3. Extension to arbitrary depths of self-reflection

### Application to AI Metacognition

The $K$ framework provides a structured vocabulary for evaluating metacognition in Large Language Models (LLMs), an increasingly important area as AI systems are deployed in high-stakes domains.

**Mapping LLM Behaviors:**

| LLM Pattern | $K_0$ | $K_1$ | $K_2$ | Interpretation |
|:---|:---:|:---:|:---:|:---|
| Correct + confident | 1 | 1 | 1 | Ideal calibration |
| Hallucination + confident | −1 | −1 | ? | Confident wrong (dangerous) |
| Correct + hedging | 1 | −1 | ? | Underconfident (imposter-like) |
| Admits uncertainty | 0 | 1 | 1 | Appropriate uncertainty (Socratic) |
| "I don't know" when wrong | −1 | 1 | ? | Partial awareness of limits |

**Testbed Proposal:**

Using decoupled confidence elicitation (analogous to AFCE-style protocols):

1. **Query LLM for answer** → compute $K_0$ (against ground truth)
2. **Query LLM for confidence** → record $C$ (0-100%)
3. **Query LLM: "Do you know this?"** → elicit $\text{Claim}_1$
4. **Compute $K_1$** from $\text{Claim}_1$ vs $K_0$

This protocol allows testing:
- **K vs C dissociation** in LLMs (do they exhibit Dunning-Kruger or Imposter patterns?)
- **Domain-specific calibration** (are LLMs more self-aware in some domains?)
- **Intervention effects** (does prompting for self-reflection improve $K_1$?)

**Why K is Useful for LLM Evaluation:**

Current LLM calibration research focuses primarily on confidence-accuracy correlation (analogous to meta-d' or meta-I). The $K$ framework adds:

1. **Pattern classification**: Identifying *which type* of miscalibration
2. **Directional information**: Distinguishing overconfidence from underconfidence
3. **Intervention guidance**: Suggesting targeted prompting strategies

**Future Work:** Operationalizing $K_n$ for LLMs using abstention behavior, self-consistency checks, and metamorphic testing remains an open challenge (see Limitations).

### Novel Contributions

This study is novel in:

1. **Recursive Formalization**: Extending metacognition to arbitrary depths ($K \to K(K) \to K(K(K))$)
2. **Socratic Wisdom as Achievement**: Explicitly modeling "knowing ignorance" as $K(x)=0, K(K(x))=1$
3. **Type-Theoretic Foundation**: Justifying $K(K(x))$ via recursive types
4. **Orthogonal Dimensions**: Separating epistemic state ($K$) from phenomenological confidence ($C$)
5. **Per-Item Granularity**: Measuring metacognition at the individual item level, not just aggregate statistics



## Conclusion and Future Challenges

This study constructed a recursive epistemic model based on the hierarchical structure of knowledge. Using a single core function $K$ applied recursively—$K(x)$, $K(K(x))$, $K(K(K(x)))$—we provide a mathematically rigorous yet philosophically grounded framework that captures:

1. The **recursive nature of self-awareness**: The same epistemic question applies at every level of reflection.
2. The **hierarchical structure of metacognition**: Distinguishing "knowing ignorance" (Socratic wisdom) from "unknowing ignorance" (Dunning-Kruger effect).
3. The **continuous gradation of knowledge**: Knowledge states exist on a continuum from misconception ($-1$) through ignorance ($0$) to accurate knowledge ($1$).

### Main Results

1. We proposed a **recursive epistemic function $K$** with type-theoretic justification and axiomatic constraints (anchor preservation, monotonicity, boundedness), demonstrating that $K(K(x))$ is not a type error but a well-founded recursive structure.
2. We adopted a stance of **methodological relativism**, treating the proposition $x$ itself as the implicit reference point and leaving the designation of "correct" to the experimental context.
3. We provided the **Four Quadrants of Metacognition**, clearly distinguishing "Knowing Ignorance" (Socratic wisdom, $K(x)=0, K(K(x))=1$) from "Unknowing Ignorance" (Dunning-Kruger effect, $K(x)=0, K(K(x))=-1$).
4. We separated **epistemic state** ($K$) from **phenomenological confidence** ($C$), recognizing them as orthogonal dimensions.
5. We proposed the **Metacognitive Alignment Test (MAT)** as an experimental protocol to validate the model, with specific predictions about the benefits of Socratic wisdom.

### Theoretical Contributions

- **Recursive Formalization**: Extending metacognition to arbitrary depths while maintaining mathematical consistency
- **Type-Theoretic Foundation**: Justifying self-application via recursive types
- **Socratic Wisdom as Achievement**: Explicitly modeling "knowing ignorance" as a high metacognitive state
- **Per-Item Granularity**: Measuring metacognition at the individual item level, complementing aggregate statistical measures

### Limitations

This framework is a **conceptual scaffold** for organizing metacognitive phenomena, not a complete predictive model. We acknowledge the following limitations:

1. **Formal Model:** We adopt an observational family interpretation to resolve the recursion/observation tension. This is a modeling choice, not the only possibility.

2. **Single Dimension (Scope Boundary):** 
   - The $[-1,1]$ scale assumes a **single axis of correctness** with one "opposite" direction.
   - **What this captures:** Directional errors (overconfidence vs underconfidence, correct vs incorrect).
   - **What this does NOT capture:** Multiple, qualitatively different misconceptions (e.g., "thinks A" vs "thinks B" when truth is C).
   - **Design rationale:** This simplification enables tractable measurement and clear intervention design. Multi-dimensional misconceptions require a different formalism (e.g., vector-valued $K$ or belief distributions) and are outside the current scope.
   - **Future extension:** Vector-valued $K \in [-1,1]^d$ or embedding in a latent space could address this limitation.

3. **Minimal Axiomatic Theory:** We provide basic constraints on $K$ (anchor preservation, monotonicity, boundedness) but do not specify a unique functional form. The specific dynamics of $K$ (e.g., whether it is contractive, has fixed points beyond $\{-1, 0, 1\}$) are empirical questions.

4. **No Generative Model:** We do not provide a noise model or generative account of how states are produced. This is a task for computational cognitive modeling.

5. **Observation Protocol:** The mapping from observable behavior to $K_n$ values requires operational definitions. While we provide guidelines (e.g., alignment between claims and performance), the specific elicitation methods depend on the application domain.

6. **$K_2$ Identifiability:** Higher-order estimates ($K_2$, $K_3$) require more items and may be less reliable.
   - **Guideline:** For reliable $K_2$ estimation, use $N \geq 50$ items with noise $< 0.2$.
   - **Confidence intervals:** Report 95% CI via bootstrap; if CI width $> 0.3$, interpret with caution.

7. **Simulation Validation Pending:** We have not yet provided simulated evidence that different metacognitive profiles (Socratic, Dunning-Kruger, Imposter) are identifiable under realistic noise. This is planned for future work.

8. **Analogical Type Theory:** The type-theoretic justification is analogical rather than formally constructed. A full domain-theoretic or typed lambda-calculus treatment is beyond the current scope.

9. **LLM Operationalization Incomplete:** Applying $K_n$ to LLMs requires addressing question-side shortcuts and model-side signals. Specific methods (conformal coverage, debate protocols) are suggested but not developed here.

### Future Directions

1. **Empirical Validation**: Conduct MAT experiments to validate the model's predictions about Socratic wisdom and Dunning-Kruger effect, and compare with meta-d' and calibration metrics.
2. **Simulation Studies**: Simulate agents with known $K$/$C$ profiles to demonstrate identifiability and estimate required sample sizes.
3. **Formal Type Theory**: Develop a typed calculus or algebraic data type where $K$'s self-application is a well-typed endomorphism.
4. **AI Safety Applications**: Operationalize $K(K(x))$ for LLMs using abstention behavior, self-consistency, and metamorphic testing.
5. **Cultural and Domain Variation**: Investigate whether the symmetry assumption (misconception vs. knowledge) holds across cultures and domains.

### Why R/E Separation is Unnecessary

One alternative formalization might introduce two separate maps: a subject-level recognition/report map $R$ and an evaluator/alignment map $E$. We argue that such separation is **unnecessary** for our framework.

**The Misunderstanding:**

Such a proposal typically interprets $K(K(x))$ as:
1. $K(x)$ = first-order state (a number)
2. $K(K(x))$ = applying $K$ to that number
3. Therefore $K(0)$ should equal $0$

**The Reality:**

Our $K$ is purely **observational**:
1. $K_0$ = observation of State$_0$ (first-order epistemic state)
2. $K_1$ = observation of State$_1$ (metacognitive state)
3. $K_2$ = observation of State$_2$ (meta-metacognitive state)

**Each layer observes a different object.** There is no "subject's report" vs "evaluator's assessment" — there is only **observation of states**.

**Why R/E Adds Unnecessary Complexity:**

| R/E Approach | Our Approach |
|:---|:---|
| Introduces "subject" as agent | No subject, only states |
| Requires modeling "perception" | States exist, observer measures |
| Two functions (R, E) | One function ($K$) |
| Subjective/objective split | Purely objective |

**Our framework is simpler and more elegant because it does not reify "the subject" as a separate entity with "perceptions."**

All that exists are **states** and **observations**. $K$ observes states. That's it.



## References

1. Kant, I. (1781). *Critique of Pure Reason*.
2. Flavell, J. H. (1979). Metacognition and cognitive monitoring: A new area of cognitive-developmental inquiry. *American Psychologist*, *34*(10), 906-911.
3. Nelson, T. O., & Narens, L. (1990). Metamemory: A theoretical framework and new findings. In G. H. Bower (Ed.), *The Psychology of Learning and Motivation* (Vol. 26, pp. 125-173). Academic Press.
4. Koriat, A. (1993). How do we know that we know? The accessibility model of the feeling of knowing. *Psychological Review*, *100*(4), 609-639.
5. Kruger, J., & Dunning, D. (1999). Unskilled and unaware of it: How difficulties in recognizing one's own incompetence lead to inflated self-assessments. *Journal of Personality and Social Psychology*, *77*(6), 1121-1134.
6. Maniscalco, B., & Lau, H. (2012). A signal detection theoretic approach for estimating metacognitive sensitivity from confidence ratings. *Consciousness and Cognition*, *21*(1), 422-430.
7. Shafer, G. (1976). *A Mathematical Theory of Evidence*. Princeton University Press.
8. Fleming, S. M., & Daw, N. D. (2017). Self-evaluation of decision-making: A general Bayesian framework for metacognitive computation. *Psychological Review*, *124*(1), 91-114.
9. Dayan, P. (2023). Metacognitive information theory. *bioRxiv*. https://doi.org/10.1162/opmi_a_00091