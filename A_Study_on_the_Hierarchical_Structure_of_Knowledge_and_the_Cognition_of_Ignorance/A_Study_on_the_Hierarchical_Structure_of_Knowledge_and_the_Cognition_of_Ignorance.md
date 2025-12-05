# A Study on the Hierarchical Structure of Knowledge and the Cognition of Ignorance

*Kunihiro Sugiyama*  
kunihiros@gmail.com

## Introduction

Human knowledge possesses a multi-layered structure, and the ability to recognize one's own ignorance (metacognition) is crucial for learning and decision-making. This study proposes a recursive model of knowledge and ignorance based on a single core function: **$K$**, which represents epistemic recognition. By applying this function recursively---$K(x)$, $K(K(x))$, $K(K(K(x)))$, and so on---we formalize the hierarchical structure of self-awareness that distinguishes **Socratic wisdom** ("knowing that one does not know") from the **Dunning-Kruger effect** ("not knowing that one does not know").

Kant (1781), in his *Critique of Pure Reason*, posed the foundational question of epistemology: what are the limits of human cognition, and can reason examine itself? His answer---that reason must critique reason---established the recursive structure of self-reflection as a philosophical problem. Yet Kant's contribution was **descriptive**: he demonstrated that limits exist, but provided no apparatus for locating their precise coordinates or guiding their correction.

This study provides what classical epistemology could not: a **mathematical framework** that transforms the Kantian question from philosophical meditation into **operational methodology**. The function $K$ does not merely describe where cognition fails---it provides the coordinates for **targeted intervention**. By representing epistemic states on a continuous scale, we gain the capacity to **observe the phenomenon of intelligence itself, and to intervene in its structure**. This framework opens the possibility of not only understanding cognition but **actively shaping its trajectory toward new forms of knowing**.

This model integrates insights from **metacognition research**, **epistemology**, and **type theory** to address three aspects that have not been sufficiently unified in existing research:

1. The **recursive nature of self-awareness**: The same epistemic question ("Do I know?") can be applied at every level of reflection.
2. The **continuous gradation of knowledge**: Knowledge states exist on a continuum from complete misconception ($-1$) through ignorance ($0$) to accurate knowledge ($1$).
3. The **distinction between epistemic state and phenomenological confidence**: What one knows versus how certain one feels are orthogonal dimensions.

By presenting a mathematically rigorous yet philosophically grounded framework, this study seeks to deepen our understanding of the structure of knowledge and the cognitive mechanisms of ignorance.

### Contribution: A Conceptual Foundation

This paper establishes the **conceptual foundation** for a unified theory of recursive metacognition. The trichotomy of epistemic states---**knowing**, **not knowing**, and **misunderstanding**---is a universal human experience that transcends cultures, domains, and disciplines. Before elaborating measurement-theoretic models or conducting empirical validation, we must first **settle the conceptual vocabulary**.

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

This study is grounded in the logical structure of recursive ignorance, exemplified by the proposition **"I don't know what I don't know."** If "knowing one's ignorance" (Socratic wisdom) is a recognized concept, then logically, "not knowing one's ignorance" must also exist. And if that exists, then so must "not knowing that one doesn't know one's ignorance"---and so on, recursively.

The goal of this paper is to **mathematically formalize this recursive structure of knowledge and ignorance**, not to judge or rank cognitive states.

### Descriptive Nature of the Scale

The values $-1$, $0$, and $1$ in this model function as **epistemic state descriptors**. They serve as epistemic coordinates rather than normative metrics (e.g., "good" or "bad").

| Value | Meaning |
|:---:|:---|
| $1$ | The subject holds correct knowledge. |
| $0$ | The subject lacks knowledge (ignorance). |
| $-1$ | The subject holds incorrect knowledge (misconception). |

A subject in state $-1$ (misconception) is not normatively inferior to a subject in state $0$ (ignorance); they occupy **distinct epistemic loci**. Whether one state is "preferable" to another depends on context, goals, and values---domains outside the scope of this model.

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

### Reconciling Objectivity and Methodological Relativism

**The Apparent Tension:**

This framework claims both:
1. **Objective evaluation**: $K_n$ values are determined by observable behavior, not subjective judgment
2. **Methodological relativism**: The reference standard ("correct" answer) is context-dependent

**Resolution: Objectivity as Operational Repeatability**

"Objective" in this framework means **operationally repeatable given a reference**:

$$\text{Objectivity} := \text{Repeatability} \mid \text{Reference}$$

| Aspect | Meaning |
|:-------|:--------|
| **Reference** | The designated ground truth (e.g., expert consensus, textbook answer) |
| **Procedure** | The MAT protocol (response -> claim -> comparison) |
| **Repeatability** | Different observers applying the same procedure to the same data obtain the same $K_n$ |

**The Relativism:**

The **choice of reference** is not determined by the framework. Different communities may designate different references:
- Scientific community: Peer-reviewed consensus
- Educational setting: Curriculum standards
- Clinical context: Diagnostic criteria

**What the Framework Provides:**

Once a reference is designated, the framework provides:
1. **Deterministic scoring**: Response + Claim + Reference -> $K_n$ (via $f_n$ and $g_n$)
2. **Cross-context comparability**: Same $K_n$ semantics across different domains
3. **Transparency**: All assumptions (reference, $f_n$, thresholds) are explicit

**Handling Reference Uncertainty:**

When the reference itself is uncertain or contested:

| Approach | Implementation |
|:---------|:---------------|
| **Probabilistic reference** | Model reference as a distribution; report $E[K_n]$ and uncertainty bounds |
| **Sensitivity analysis** | Report $K_n$ under multiple plausible references |
| **Higher-layer encoding** | Treat reference uncertainty as a property of State$_{n+1}$ |

**Scope Boundary:** Full treatment of contested references (e.g., scientific controversies) is beyond the current framework's scope and marked for future development.

## The Recursive Structure: $K(K(K(x)))$

The cognitive structure of knowledge is modeled using a **recursive epistemic function** $K$. This model formalizes the intuition that the same question---"Do I know?"---can be applied at every level of self-reflection.

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

#### Dual Notation System: Symbolic vs Formal

This paper employs two complementary notational systems that serve distinct purposes:

**1. Symbolic Notation: $K(K(K(x)))$**

| Aspect | Description |
|:---|:---|
| **Purpose** | Philosophical intuition and rhetorical clarity |
| **Meaning** | The recursive structure of "not knowing that one does not know" |
| **Origin** | The paper's foundational insight: ignorance of ignorance of ignorance |
| **Usage** | Introduction, motivation, conceptual discussion, examples |
| **Status** | Evocative shorthand, NOT operational definition |

**2. Formal Notation: $K_n(x)$**

| Aspect | Description |
|:---|:---|
| **Purpose** | Mathematical rigor and operational precision |
| **Definition** | $K_n(x) := K^{(n)}(\text{State}_n(x)) = \hat{K}(g_n(\text{State}_n(x)))$ |
| **Usage** | Definitions, axioms, measurement protocols, empirical analysis |
| **Status** | Operational definition for all formal purposes |

**Critical Distinction:**

The symbolic notation $K(K(x))$ is **NOT** numerical composition (i.e., $K$ applied to its own output value). It is a **rhetorical device** representing the philosophical insight that the same epistemic question ("Do I know?") applies recursively at every level of reflection.

$$K(K(x)) \not\equiv K(K_0(x)) \quad \text{(NOT numerical composition)}$$
$$K(K(x)) \equiv K_1(x) \quad \text{(notational equivalence only)}$$

**For all formal purposes---definitions, proofs, measurement, analysis---use $K_n(x)$ exclusively.**

**Why Both?**

- **$K(K(K(x)))$** captures the *philosophical essence*: the infinite regress of self-reflection
- **$K_n(x)$** enables *mathematical precision*: layer-specific observation with distinct objects

This dual system parallels established practice:
- Physics: $E = mc^2$ (iconic) vs tensor formulation (operational)
- Calculus: $\frac{dy}{dx}$ (Leibniz, intuitive) vs $\lim_{h \to 0}$ (rigorous)

---

**DEFINITION (Core Formal Apparatus):**

> 1. **State objects**: $\text{State}_n \in \{+1, 0, -1\}$ for each layer $n$
> 2. **State functions**: $f_n: (\text{State}_{n-1}, \text{Claim}_n) \to \text{State}_n$
> 3. **Embedding maps**: $g_n: \text{State}_n \to [-1, 1]$
> 4. **Observation**: $K_n(x) = \hat{K}(g_n(\text{State}_n(x)))$
> 5. **Anchor constraints**: $\hat{K}(-1) = -1$, $\hat{K}(0) = 0$, $\hat{K}(+1) = +1$
>
> **All formal work in this paper operates within this apparatus.**

---

#### Unified Formalization via Embedding Maps

To resolve the apparent type ambiguity between $K^{(n)}: \mathcal{S}_n \to [-1, 1]$ and the recursive $K: [-1, 1] \to [-1, 1]$, we introduce **embedding maps** that convert categorical states to the continuous scale.

**Definition (Embedding Maps):**

Each layer has an embedding map $g_n$ that converts categorical states to the continuous scale:

$$g_n: \mathcal{S}_n \to [-1, 1]$$

Where:
- $g_0: \{\text{correct}, \text{incorrect}, \text{absent}\} \to \{1, -1, 0\}$
- $g_1: \{\text{aligned}, \text{misaligned}, \text{uncertain}\} \to \{1, -1, 0\}$
- $g_n: \{\text{aligned}, \text{misaligned}, \text{uncertain}\} \to \{1, -1, 0\}$ for $n \geq 1$

**State$_0$ Canonical Mapping:**

| $f_0$ Output | $g_0$ Value | Interpretation |
|:---|:---:|:---|
| correct | 1 | Response matches reference |
| incorrect | -1 | Response contradicts reference |
| absent | 0 | No response / "I don't know" |

**Clarification:** "Ignorance" in the sense of $K_0 = 0$ means **absence of determinate stance**, not "being wrong." A wrong answer is a **misconception** ($K_0 = -1$), not ignorance.

**Definition (Unified Observation Scorer):**

After embedding, a single scorer $\hat{K}$ operates on the embedded space:

$$\hat{K}: [-1, 1] \to [-1, 1]$$

With the identity mapping for prototypical anchors: $\hat{K}(1) = 1$, $\hat{K}(0) = 0$, $\hat{K}(-1) = -1$.

**Composition:**

$$K_n(x) = \hat{K}(g_n(\text{State}_n(x)))$$

**Notational Convention (Unified):**

- $K_n$: The full pipeline (embedding + scoring) for layer $n$
- $K^{(n)}$: Shorthand for the same, emphasizing layer-specificity
- $K(K(x))$: Informal shorthand for $K_1(x)$, **not** numerical composition

This resolves the type ambiguity: $K$ is **not** applied to its own numerical output, but to the embedded representation of a distinct state object.

#### Error Model for State Functions

**Deterministic vs Probabilistic Interpretation:**

The functions $f_n$ and $g_n$ can be interpreted in two ways:

**Option A: Deterministic (Default)**

The comparison functions $f_n$ are deterministic mappings:

$$f_0: \text{Response}(x) \times \text{Reference}(x) \to \{\text{correct}, \text{incorrect}, \text{absent}\}$$

This assumes:
- Reference is unambiguous
- Response classification is clear-cut
- No measurement error in observation

**Use case**: Controlled experiments with factual questions and expert consensus.

**Option B: Probabilistic (Extended)**

For noisy or uncertain contexts, $f_n$ can be extended to probabilistic mappings:

$$f_0: \text{Response}(x) \times \text{Reference}(x) \to \Delta(\{\text{correct}, \text{incorrect}, \text{absent}\})$$

Where $\Delta(\cdot)$ denotes probability distributions over the outcome space.

**Noise Model (if Option B):**

$$P(\text{State}_n = s | \text{True State} = s^*) = \begin{cases}
1 - \epsilon_n & \text{if } s = s^* \\
\epsilon_n / 2 & \text{otherwise}
\end{cases}$$

Where $\epsilon_n$ is the layer-specific error rate.

**Recommendation:**

- Use **deterministic** interpretation for conceptual clarity (this paper)
- Use **probabilistic** extension for empirical work with measurement noise
- Always report which interpretation is assumed

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

This framework adopts a **purely observational stance**: epistemic states are operationalized as observable responses, and metacognitive states as observable alignments between claims and performance. We do not posit internal "beliefs" or "perceptions" --- only **states** that are measurable by an external observer.

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
Response(x) --+
              +--> f_0 --> State_0 --> K^(0) --> K_0
Reference(x) -+              |
                             v
Claim_1(x) --------------> f_1 --> State_1 --> K^(1) --> K_1
                                    |
                                    v
Claim_2(x) ----------------------> f_2 --> State_2 --> K^(2) --> K_2
```

#### Precise Specification of State Objects and Functions

The following tables provide complete, reproducible definitions for each layer.

**State$_0$: First-Order Epistemic State**

**Definition:**
$$\text{State}_0 \in \{\text{correct}, \text{incorrect}, \text{absent}\}$$

**State Function $f_0$:**

| Response $r$ | Reference $t$ | $\text{State}_0 = f_0(r, t)$ |
|:-------------|:--------------|:-----------------------------|
| Any answer $a$ | $a = t$ | correct |
| Any answer $a$ | $a \neq t$ | incorrect |
| No response / "I don't know" | Any | absent |

**$K_0$ Computation:**
$$K_0(x) = g_0(f_0(r, t))$$

---

**State$_1$: Second-Order Metacognitive State**

**Definition:**
$$\text{State}_1 \in \{\text{aligned}, \text{uncertain}, \text{misaligned}\}$$

**Claim Vocabulary $C_1$:**

| Claim | Meaning |
|:------|:--------|
| "I know this" | Subject claims knowledge |
| "I'm not sure" | Subject expresses uncertainty |
| "I don't know this" | Subject claims ignorance |

**State Function $f_1$:**

| $K_0$ (actual) | Claim$_1$ | $\text{State}_1 = f_1(K_0, \text{Claim}_1)$ |
|:---------------|:----------|:--------------------------------------------|
| $+1$ (knows) | "I know" | aligned |
| $+1$ (knows) | "I'm not sure" | uncertain |
| $+1$ (knows) | "I don't know" | misaligned |
| $0$ (ignorant) | "I don't know" | aligned |
| $0$ (ignorant) | "I'm not sure" | uncertain |
| $0$ (ignorant) | "I know" | misaligned |
| $-1$ (wrong) | "I don't know" | aligned* |
| $-1$ (wrong) | "I'm not sure" | uncertain |
| $-1$ (wrong) | "I know" | misaligned |

*Note: "I don't know" when holding a misconception is partial awareness; coded as "aligned" for monotonicity.

---

**State$_2$: Third-Order Meta-Metacognitive State**

**Definition:**
$$\text{State}_2 \in \{\text{meta-aligned}, \text{meta-uncertain}, \text{meta-misaligned}\}$$

**Claim Vocabulary $C_2$:**

| Claim | Meaning |
|:------|:--------|
| "My self-assessment is accurate" | Subject endorses their $K_1$ |
| "I'm not sure about my self-assessment" | Subject uncertain about $K_1$ |
| "My self-assessment may be wrong" | Subject doubts their $K_1$ |

**State Function $f_2$:**

| $K_1$ (actual) | Claim$_2$ | $\text{State}_2 = f_2(K_1, \text{Claim}_2)$ |
|:---------------|:----------|:--------------------------------------------|
| $+1$ (calibrated) | "accurate" | meta-aligned |
| $+1$ (calibrated) | "not sure" | meta-uncertain |
| $+1$ (calibrated) | "may be wrong" | meta-misaligned |
| $0$ (uncertain) | "not sure" | meta-aligned |
| $0$ (uncertain) | "accurate" or "may be wrong" | meta-misaligned |
| $-1$ (miscalibrated) | "may be wrong" | meta-aligned |
| $-1$ (miscalibrated) | "not sure" | meta-uncertain |
| $-1$ (miscalibrated) | "accurate" | meta-misaligned |

---

**Summary: The Complete Pipeline**

```
Response(x) -> f$_0$(Response, Reference) -> State$_0$ -> g$_0$ -> K$_0$
                                          v
Claim$_1$ + K$_0$ -> f$_1$(K$_0$, Claim$_1$) -> State$_1$ -> g$_1$ -> K$_1$
                                          v
Claim$_2$ + K$_1$ -> f$_2$(K$_1$, Claim$_2$) -> State$_2$ -> g$_2$ -> K$_2$
```

**Reproducibility:** Given the same (Response, Claim$_1$, Claim$_2$, Reference), any observer following this specification will compute identical $(K_0, K_1, K_2)$.

---

**Operational Interpretation:**

- **State$_0$ (first-order epistemic state)**: The respondent's answer compared to a reference.
  - Operationalized as: "Is the answer correct, incorrect, or absent?"
  
- **State$_1$ (metacognitive state)**: The alignment between the respondent's metacognitive claim and their actual State$_0$.
  - Operationalized as: "Does the claim 'I know' match the actual correctness?"
  
- **State$_2$ (meta-metacognitive state)**: The alignment between the respondent's meta-metacognitive claim and their actual State$_1$.

**Example:**
- Respondent answers incorrectly -> State$_0$ = "incorrect" -> $K_0 = -1$ (misconception)
- Respondent says "I don't know" -> State$_0$ = "absent" -> $K_0 = 0$ (ignorance)
- Respondent claims "I know" (when $K_0 = -1$) -> State$_1$ = "misalignment" -> $K_1 = -1$
- Respondent claims "My self-assessment is accurate" -> State$_2$ = "misalignment" -> $K_2 = -1$

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
- $K_0(x) = 0$: Observer measures State$_0$ -> "ignorance"
- $K_1(x) = -1$: Observer measures State$_1$ -> "misalignment"

**State$_1$ is not "0".** State$_1$ is the metacognitive state (alignment/misalignment), which the observer measures as "misrecognition" (-1).

The axiom $K(0) = 0$ does not apply because the input to $K_1$ is **not** the number "0". The input is **State$_1$**, a different object entirely.

**Analogy (Thermometer Calibration):**

Consider a thermometer and its calibration:
- **State$_0$ (temperature)**: The actual temperature of water = 20$^\circ$C
- **State$_1$ (thermometer accuracy)**: Whether the thermometer correctly reads State$_0$

Measuring State$_0$ = 20$^\circ$C does not constrain State$_1$. The thermometer might be:
- Accurate (State$_1$ = correct) -> $K_1 = 1$
- Miscalibrated (State$_1$ = incorrect) -> $K_1 = -1$

$K_1$ measures a **property of the measuring instrument**, not the original object. Similarly, $K_1$ measures the accuracy of **the respondent's self-monitoring**, not the first-order state itself.

#### Observation vs Intervention: Clarifying the Framework's Scope

**The Observational Stance:**

This framework is **observational** in the following sense:
- $K_n$ values are determined by observable behavior (responses, claims)
- No internal mental states are posited
- The observer does not require privileged access to the subject's mind

**The Interventional Possibility:**

The phrase "targeted intervention" in the Introduction refers to a **downstream application**, not a claim within the framework itself:

1. **Observation**: Measure $K_0$, $K_1$, $K_2$ via the MAT protocol
2. **Classification**: Identify metacognitive pattern (e.g., Dunning-Kruger: $K_0=0$, $K_1=-1$)
3. **Intervention design** (external to framework): Choose intervention based on classification
4. **Re-observation**: Measure $K_n$ again to assess intervention effect

**What the Framework Provides:**

- **Coordinates** for locating epistemic states
- **Taxonomy** for classifying metacognitive patterns
- **Outcome measures** for evaluating interventions

**What the Framework Does NOT Provide:**

- **Causal model** of how interventions change $K_n$
- **Mechanism** by which metacognition operates
- **Prescriptions** for which interventions to use

**Analogy:**

A thermometer (observation) does not itself heat or cool a room (intervention). But knowing the temperature enables targeted decisions about heating/cooling. Similarly, $K_n$ observes metacognitive states, enabling (but not specifying) targeted interventions.

### Symbolic Notation: A Conceptual Communication Tool

**Purpose and Status:**

The notation $K(K(x))$ serves as an **intuitive communication device** for conveying the core insight of recursive metacognition to interdisciplinary audiences. It captures the philosophical essence of "not knowing that one does not know" more vividly than indexed notation.

**Formal Status:**
- This notation is **NOT used in formal definitions, proofs, or measurement protocols**
- All formal operations are defined via $K_n(\text{State}_n)$ exclusively
- The symbolic notation has **NO independent operational semantics**

**Translation Convention:**

| Symbolic (intuitive) | Formal (operational) | Meaning |
|:---------------------|:---------------------|:--------|
| $K(x)$ | $K_0(x)$ | First-order epistemic observation |
| $K(K(x))$ | $K_1(x)$ | Second-order metacognitive observation |
| $K(K(K(x)))$ | $K_2(x)$ | Third-order meta-metacognitive observation |

**Why Retain Symbolic Notation?**

1. **Philosophical resonance**: The recursive imagery $K(K(K(...)))$ conveys the unbounded nature of self-reflection
2. **Interdisciplinary accessibility**: Non-technical readers grasp the recursive structure intuitively
3. **Historical continuity**: Echoes classical formulations (Socrates' "knowing that I do not know")

**What Symbolic Notation Does NOT Provide:**
- Mathematical type structure
- Operational definitions
- Measurement protocols
- Formal proofs

**The $K_n$ notation is the SOLE formal apparatus of this framework.**

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

**Monotonicity (Revised):**

**Definition (Order on Embedded States):**

For embedded values $k, k' \in [-1, 1]$, the natural order $k > k'$ applies.

**Monotonicity Axiom:**

For any scoring function $\hat{K}$:

$$\text{If } g_n(\text{State}_n) > g_n(\text{State}'_n), \text{ then } K_n \geq K'_n$$

This is trivially satisfied when $\hat{K}$ is the identity on anchors and monotonic elsewhere.

**Practical Interpretation:**

Monotonicity ensures that "more aligned" states receive higher $K$ values. This does not constrain the shape of $\hat{K}$ beyond anchor preservation.

Monotonicity applies **within each layer** only. It does NOT constrain relationships **across layers** (e.g., $K_0$ vs $K_1$).

**Boundedness:**

$K: [-1, 1] \to [-1, 1]$

Each observation is bounded on this interval.

**Note:** We deliberately refrain from specifying stronger constraints (e.g., odd symmetry, Lipschitz constant, contraction mapping) at this stage. The framework is intended to be **descriptive** rather than **predictive**---it provides a vocabulary for classifying observed metacognitive states, not a generative model of metacognitive dynamics. Specifying a particular functional form for $K$ is a task for domain-specific empirical research.

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

- $K(x) = 1$: The subject knows that "water boils at 100$^\circ$C."
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

- $K(x) = 1$: The subject knows that "water boils at 100$^\circ$C."
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

### Complete Taxonomy: $K_0 \times K_1 \times K_2$ (27 Patterns)

**Derivation:**

Each of $K_0$, $K_1$, $K_2$ takes values in $\{-1, 0, +1\}$ (discretized from continuous scale via thresholds).
Total configurations: $3 \times 3 \times 3 = 27$

**The Full Table:**

| # | $K_0$ | $K_1$ | $K_2$ | Name | Description |
|:--|:------|:------|:------|:-----|:------------|
| 1 | +1 | +1 | +1 | **Perfect Calibration** | Knows, knows they know, knows they know they know |
| 2 | +1 | +1 | 0 | **Unreflective Expert** | Knows and knows it, but unaware of this meta-state |
| 3 | +1 | +1 | -1 | **Doubting Expert** | Knows and knows it, but believes their self-knowledge is poor |
| 4 | +1 | 0 | +1 | **Agnostic Knower (Meta-aware)** | Knows but unsure if they know, aware of this uncertainty |
| 5 | +1 | 0 | 0 | **Agnostic Knower** | Knows but unsure if they know |
| 6 | +1 | 0 | -1 | **Falsely Uncertain** | Knows but unsure, believes wrongly they're certain |
| 7 | +1 | -1 | +1 | **Imposter (Self-aware)** | Knows but thinks they don't, aware of this pattern |
| 8 | +1 | -1 | 0 | **Classic Imposter** | Knows but thinks they don't know |
| 9 | +1 | -1 | -1 | **Deep Imposter** | Knows, thinks they don't, believes their self-doubt is accurate |
| 10 | 0 | +1 | +1 | **Aware Ignorance (Validated)** | Doesn't know, knows this, confident in this self-knowledge |
| 11 | 0 | +1 | 0 | **Socratic Wisdom** | Doesn't know and knows it ("I know that I know nothing") |
| 12 | 0 | +1 | -1 | **Doubting Socrates** | Doesn't know, knows it, but doubts this self-knowledge |
| 13 | 0 | 0 | +1 | **Pure Uncertainty (Meta-aware)** | Doesn't know, unsure if they know, aware of confusion |
| 14 | 0 | 0 | 0 | **Complete Uncertainty** | Doesn't know, unsure if they know, unsure about that |
| 15 | 0 | 0 | -1 | **Confused Certainty** | Doesn't know, unsure, but believes they're clear |
| 16 | 0 | -1 | +1 | **Dunning-Kruger (Self-aware)** | Doesn't know, thinks they know, aware of this bias |
| 17 | 0 | -1 | 0 | **Classic Dunning-Kruger** | Doesn't know but thinks they know |
| 18 | 0 | -1 | -1 | **Deep Dunning-Kruger** | Doesn't know, thinks they know, confident in false belief |
| 19 | -1 | +1 | +1 | **Aware Misconception (Validated)** | Has misconception, knows it, confident in this |
| 20 | -1 | +1 | 0 | **Aware Misconception** | Has misconception and knows it |
| 21 | -1 | +1 | -1 | **Doubting Awareness** | Has misconception, knows it, but doubts this knowledge |
| 22 | -1 | 0 | +1 | **Uncertain Misconception (Meta-aware)** | Has misconception, unsure, aware of uncertainty |
| 23 | -1 | 0 | 0 | **Uncertain Misconception** | Has misconception, unsure if they know |
| 24 | -1 | 0 | -1 | **Falsely Certain Misconception** | Has misconception, unsure, but thinks they're sure |
| 25 | -1 | -1 | +1 | **Confident Error (Self-aware)** | Has misconception, thinks it's knowledge, aware of this risk |
| 26 | -1 | -1 | 0 | **Confident Error** | Has misconception and thinks it's knowledge |
| 27 | -1 | -1 | -1 | **Entrenched Error** | Has misconception, thinks it's knowledge, certain of this |

**Completeness Argument:**

The taxonomy is complete by construction: every possible $(K_0, K_1, K_2) \in \{-1, 0, +1\}^3$ combination is enumerated. No configuration is possible outside this space under the discretized model.

**Notable Patterns:**

| Pattern | Configuration | Clinical/Educational Significance |
|:--------|:--------------|:----------------------------------|
| **Socratic Wisdom** | $(0, +1, \cdot)$ | Ideal starting point for learning |
| **Classic Dunning-Kruger** | $(0, -1, 0)$ | Intervention target: calibration training |
| **Classic Imposter** | $(+1, -1, 0)$ | Intervention target: confidence building |
| **Entrenched Error** | $(-1, -1, -1)$ | Most resistant to change; requires staged approach |
| **Perfect Calibration** | $(+1, +1, +1)$ | Ideal end state |

**Extension to Continuous Values:**

The 27-pattern table is a **discrete approximation**. For continuous $K_n \in [-1, 1]$, the taxonomy becomes a partition of the unit cube $[-1, 1]^3$ into 27 regions, with boundaries at $\pm 0.33$ (see Threshold Justification below).

**Partial Order Among Patterns:**

Some patterns are "better" than others in terms of metacognitive calibration:

$$\text{Calibration Quality} = \text{sign}(K_0 \cdot K_1) + \text{sign}(K_1 \cdot K_2)$$

| Quality | Meaning | Example Patterns |
|:--------|:--------|:-----------------|
| +2 | Fully calibrated | #1 (Perfect Calibration), #11 (Socratic Wisdom) |
| +1 | Partially calibrated | #2, #10 |
| 0 | Mixed | #5, #14 |
| -1 | Partially miscalibrated | #8, #17 |
| -2 | Fully miscalibrated | #18 (Deep Dunning-Kruger), #27 (Entrenched Error) |

This ordering is **descriptive**, not normative; specific contexts may value different patterns.

**Theoretical Value of $K_2$:**

The third layer ($K_2$) enables modeling of **metacognitive interventions** and their effectiveness:

- $K_2 = +1$ with $K_1 = -1$: Subject recognizes their metacognitive failure -> **teachable moment**
- $K_2 = -1$ with $K_1 = -1$: Subject does not recognize their failure -> **resistant to intervention**

Higher-order reflection ($K_2$, $K_3$, ...) provides diagnostic power for identifying when and how metacognitive correction is possible.

### Continuous-to-Categorical Mapping

The 27-pattern taxonomy uses prototypical anchors $\{-1, 0, 1\}$. For continuous $K$ values, we define thresholds:

| Continuous Range | Categorical Label |
|:---:|:---:|
| $K \in [-1, -0.33)$ | $-1$ (Misconception/Misaligned) |
| $K \in [-0.33, 0.33]$ | $0$ (Ignorance/Uncertain) |
| $K \in (0.33, 1]$ | $1$ (Knowledge/Aligned) |

**Rationale for $\pm 0.33$ Default**:

1. **Symmetric Tercile**: Divides $[-1, 1]$ into three equal-width regions
2. **Neutral Zone**: The central region captures "uncertain/indeterminate" states
3. **Statistical Interpretation**: Under uniform prior, each category has equal probability
4. **Robustness**: Not sensitive to small estimation errors near boundaries

#### Formal Justification for Thresholds

**Decision-Theoretic Grounding:**

The default thresholds $\pm 0.33$ can be justified via decision theory:

**Setup:**
- Agent must classify $K$ into {misconception, ignorance, knowledge}
- Utility function: $U(\text{action}, \text{true state})$
- Prior: Uniform over $[-1, 1]$

**Symmetric Loss:**

Under symmetric 0-1 loss (equal cost for all misclassifications):

$$\text{Optimal thresholds} = \arg\min_{\tau_1, \tau_2} E[\mathbb{1}(\text{misclassification})]$$

With uniform prior, this yields $\tau_1 = -1/3 \approx -0.33$, $\tau_2 = 1/3 \approx 0.33$.

**Asymmetric Loss (Alternative):**

If false positives (claiming knowledge when ignorant) are more costly:

$$L(\text{classify as } 1 | \text{true } 0) = c > 1$$

Optimal thresholds shift: $\tau_2 > 0.33$ (stricter knowledge criterion).

**Proper Scoring Rule Connection:**

Under Brier score:

$$\text{Brier}(p, y) = (p - y)^2$$

The thresholds $\pm 0.33$ correspond to the decision boundaries where expected Brier score is minimized under uniform prior.

**Empirical Calibration (Future Work):**

For domain-specific applications:
1. Collect pilot data with known ground truth
2. Compute ROC curve for each threshold
3. Select threshold maximizing Youden's J or F1 score
4. Report sensitivity analysis across threshold choices

**Alternative Thresholds**:

| Approach | Thresholds | Use Case |
|:---|:---|:---|
| **Tercile (default)** | $\pm 0.33$ | Balanced classification |
| **Quartile** | $\pm 0.5$ | Stricter knowledge/misconception criteria |
| **ROC-optimized** | Data-driven | Maximize classification accuracy |
| **Domain-specific** | Expert-defined | Match substantive theory |

**Recommendation**:
- Use $\pm 0.33$ as default for comparability across studies
- Report sensitivity analysis with alternative thresholds
- For intervention design, consider ROC-optimized thresholds

**Reporting Recommendation**:
- Report continuous $K$ values for statistical analysis
- Use categorical labels for interpretation and intervention design
- Always include confidence intervals from estimation

**Example**:

$$K_0 = 0.7, K_1 = -0.5, K_2 = 0.2$$

Categorical: $K_0 = 1, K_1 = -1, K_2 = 0$ -> "Knowing Misconception, uncertain about meta"

This enables both fine-grained analysis and interpretable classification.

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
- "Do I know the answer?" -> $K_0$
- "Do I know whether I know the answer?" -> $K_1$
- "Do I know whether I know whether I know?" -> $K_2$

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

1. **Discrete elicitation -> Discrete embedding**: Use trichotomous responses (True/False/I don't know), then embed into $[-1, 1]$ via $K(x) \in \{-1, 0, 1\}$ as prototype points.

2. **Probabilistic elicitation -> Continuous embedding**: Elicit a subjective probability $p(x)$ and map it into $[-1, 1]$ using a proper scoring rule or a simple linear transform (e.g., centered Brier-type scores).

3. **Aggregation -> Continuous embedding**: Average prototype-valued $K(x_i) \in \{-1, 0, 1\}$ across multiple items or contexts to obtain a continuous summary in $[-1, 1]$.

Conceptually, the **continuum $[-1, 1]$ is primary**; the trichotomy $\{-1, 0, 1\}$ is a convenient way to name salient regions on this line, not a separate codomain. Experimental designs may choose discrete or continuous elicitation, but in all cases the resulting data are interpreted as points (or distributions) on the same underlying scale $[-1, 1]$.

### Estimation Methods for K Values

The $K$ framework specifies **what to measure** (epistemic state coordinates); for **how to estimate**, we adopt established psychometric and signal-detection methods as "plug-in" engines. This separation preserves our conceptual contribution while leveraging validated estimation machinery.

#### $K_0$ Estimation (First-Order Epistemic State)

**Method**: Item Response Theory (2-Parameter Logistic Model)

$$P(\text{correct} | \theta_s, a_i, b_i) = \frac{1}{1 + e^{-a_i(\theta_s - b_i)}}$$

**Mapping to $K_0$**:

$$K_0 = 2 \cdot \Phi(\theta_s) - 1$$

Where $\Phi$ is the standard normal CDF, ensuring $K_0 \in [-1, 1]$.

**Misconception Detection**:
- High confidence + incorrect -> $K_0 = -1$
- Operationalized via Confidence-Accuracy calibration error

#### $K_1$ Estimation (Metacognitive Alignment)

**Method A**: Phi Coefficient

$$\phi = \frac{n_{11} n_{00} - n_{10} n_{01}}{\sqrt{(n_{11}+n_{10})(n_{01}+n_{00})(n_{11}+n_{01})(n_{10}+n_{00})}}$$

**Handling 3-Value State$_0$**:

State$_0$ has three outcomes {correct, incorrect, absent}. For Phi ($2 \times 2$), we binarize:

| Binarization Strategy | Positive ($K_0 > 0$) | Negative ($K_0 \leq 0$) |
|:---|:---|:---|
| **Strategy A (Strict)** | correct only | incorrect + absent |
| **Strategy B (Lenient)** | correct + absent | incorrect only |
| **Strategy C (Exclude)** | correct | incorrect (exclude absent) |

**Recommended**: Strategy A (Strict) --- aligns with the interpretation that "I know" should predict correctness, not just absence of misconception.

**Cell Definitions (Strategy A)**:
- $n_{11}$: correct + "I know"
- $n_{00}$: (incorrect OR absent) + "I don't know"
- $n_{10}$: correct + "I don't know"
- $n_{01}$: (incorrect OR absent) + "I know"

**Mapping**: $K_1 = \phi$ (already in $[-1, 1]$)

**Interpretation**:
- $\phi = 1$: Perfect metacognitive alignment
- $\phi = 0$: No relationship (random)
- $\phi = -1$: Perfect anti-alignment (systematic miscalibration)

**Method B**: meta-d' Ratio (Signal Detection Theory)

$$K_1 = f\left(\frac{\text{meta-d}'}{d'}\right)$$

Where:
- meta-d' = metacognitive sensitivity (Maniscalco & Lau, 2012)
- $d'$ = first-order sensitivity
- $f$: bounding function to ensure output in $[-1, 1]$

**Bounding Function Options**:

| Function | Formula | Properties |
|:---|:---|:---|
| **tanh** (default) | $\tanh(r)$ | Smooth, symmetric, saturates at $\pm 1$ |
| **Scaled CDF** | $2\Phi(r) - 1$ | Probabilistic interpretation |
| **Clipped linear** | $\max(-1, \min(1, r))$ | Simple, preserves scale near 0 |

**Rationale for tanh (default)**:
- Smooth monotonic transformation
- Natural saturation at extreme values
- Widely used in neural network literature
- **Alternative-agnostic**: Results qualitatively similar across choices

**Sensitivity Analysis Recommendation**: Report results with at least two bounding functions to confirm robustness.

**Choice Guidance**:
- Use Phi for simplicity and interpretability (no bounding needed)
- Use meta-d'/d' for SDT-compatible analyses (with explicit bounding function)

#### $K_2$ Estimation (Higher-Order Alignment)

**Method**: Hierarchical Bayesian GLM (cf. HiBayES, Fleming & Daw, 2017)

$$\text{Claim}_2 | \text{State}_1 \sim \text{Bernoulli}(\sigma(\alpha_s + \beta_i + \gamma_{s,i}))$$

**Advantages**:
- Stable estimation with $N \geq 20$ items
- Provides 95% credible intervals
- Decomposes subject and item effects

**Mapping**:

$$K_2 = 2 \cdot P(\text{Claim}_2 \text{ matches } \text{State}_1) - 1$$

Estimated from posterior predictive distribution.

#### Summary Table: Estimation Methods

| Layer | Observable | Method | Output |
|:---:|:---|:---|:---:|
| $K_0$ | Response vs Reference | IRT (2PL) | $[-1, 1]$ |
| $K_1$ | Claim$_1$ vs State$_0$ | Phi / meta-d'/d' | $[-1, 1]$ |
| $K_2$ | Claim$_2$ vs State$_1$ | Hierarchical Bayes | $[-1, 1]$ |
| $C$ | Self-reported confidence | Direct elicitation | $[0, 1]$ |

#### Identifiability Analysis

**Definition**: A parameter $\theta$ is **identifiable** if there exists a measurable function $\hat{\theta}$ such that, as $N \to \infty$, $\hat{\theta} \xrightarrow{p} \theta$ (i.e., the estimator converges in probability to the true value).

**Identifiability Conditions by Layer**:

**$K_0$ Identifiability**:
- **Requires**: Multiple items per subject to separate subject ability from item difficulty
- **Condition**: Variance in item difficulties $\text{Var}(b_i) > 0$
- **Minimum**: $N \geq 10$ items for stable 2PL estimation

**$K_1$ Identifiability**:
- **Requires**: Multiple trials per subject with varying $K_0$ outcomes
- **Condition**: Both correct and incorrect responses must occur
- **Minimum**: $N \geq 15$ trials with both positive and negative $K_0$ outcomes

**$K_2$ Identifiability**:
- **Requires**: Observed $K_1$ variation across trials
- **Condition**: Non-degenerate $K_1$ distribution (not all perfect or all random)
- **Minimum**: $N \geq 20$ trials for hierarchical Bayesian estimation

**Non-Identifiability Cases**:

| Scenario | Observable Pattern | Diagnosis |
|:---|:---|:---|
| Ceiling $K_0$ | All items correct | Cannot estimate $K_1$ (no error signal) |
| Floor $K_0$ | All items incorrect | Cannot distinguish misconception from guessing |
| Perfect $K_1$ | All metacognitive claims correct | $K_2$ undefined (no calibration error) |
| Random $K_1$ | $\phi = 0$ | Insufficient metacognitive signal for $K_2$ |

**Practical Guideline**:

| Layer | Minimum N | Recommended N | Estimation Method | Identifiability Check |
|:---:|:---:|:---:|:---|:---|
| $K_0$ | 10 | 30+ | IRT 2PL | SE($\theta_s$) < 0.5 |
| $K_1$ | 15 | 25+ | Phi / meta-d' | $n_{ij} \geq 5$ per cell |
| $K_2$ | 20 | 40+ | Hierarchical Bayes | Rhat < 1.1, ESS > 100 |

**Note**: These are minimum requirements. For individual-level claims about specific subjects, larger sample sizes or domain-specific validations are recommended.

#### Identifiability under Latent Variable Model

Given the latent variable formulation $K_n = \tanh(\beta_n \cdot \theta_n)$, we address identifiability:

**Location-Scale Indeterminacy:**

$\theta_n$ is identified only up to a scale factor (since $\tanh(\beta \theta) = \tanh((\beta c)(\theta/c))$ for any $c > 0$).

**Resolution:** Fix $\beta = 1$ (standard parameterization) or anchor to a reference population.

**Finite-Sample Identifiability:**

| Layer | Data Requirements | Identifiability Condition |
|:------|:------------------|:--------------------------|
| $K_0$ | $\geq 10$ items with known ground truth | Variance in ground truth states |
| $K_1$ | $K_0$ estimates + self-assessments | Variance in $(K_0, \text{Claim}_1)$ pairs |
| $K_2$ | $K_1$ estimates + meta-self-assessments | Non-degenerate $(K_1, \text{Claim}_2)$ |

**Practical Guideline:** For reliable estimation, collect data across the full range of $K_n$ values. Pure cases (all $+1$ or all $-1$) provide no information about the link function shape.

### Reliability and Validity Guidelines

#### Test-Retest Reliability

**Concern:** Are $K_n$ scores stable over time (assuming no true change)?

**Protocol:**
1. Administer MAT at time $t_1$
2. Re-administer at $t_2$ (recommended: 2-4 weeks)
3. Compute intraclass correlation (ICC) for $K_0$, $K_1$, $K_2$

**Expected Results:**

| Layer | Expected ICC | Rationale |
|:------|:-------------|:----------|
| $K_0$ | 0.7-0.9 | Knowledge is relatively stable |
| $K_1$ | 0.5-0.8 | Metacognition may fluctuate with context |
| $K_2$ | 0.4-0.7 | Meta-metacognition is more variable |

**Interpretation:** ICC > 0.7 indicates acceptable stability; lower values suggest either measurement noise or genuine state instability.

#### Inter-Rater Reliability

**Concern:** Do different observers compute the same $K_n$ from identical data?

**Protocol:**
1. Two+ independent raters apply the $f_n, g_n$ mappings
2. Compute Cohen's $\kappa$ for discretized $K_n$
3. Compute ICC for continuous $K_n$ estimates

**Expected Results:**

Given the deterministic nature of $f_n$ and $g_n$, inter-rater agreement should be **near-perfect** ($\kappa > 0.9$) for unambiguous responses. Disagreements indicate:
- Ambiguous claim interpretation (refine claim vocabulary)
- Reference disagreement (clarify ground truth designation)

#### Split-Half Reliability

**Concern:** Is $K_n$ estimation internally consistent across item subsets?

**Protocol:**
1. Randomly split items into two halves (A and B)
2. Compute $K_n^{(A)}$ and $K_n^{(B)}$ separately
3. Correlate the two estimates; apply Spearman-Brown correction

**Expected Results:**

| Layer | Expected Split-Half $r$ | Interpretation |
|:------|:------------------------|:---------------|
| $K_0$ | 0.7-0.9 | High internal consistency |
| $K_1$ | 0.5-0.8 | Moderate; depends on item heterogeneity |
| $K_2$ | 0.4-0.7 | Lower; meta-meta states are more variable |

**Guideline:** Spearman-Brown corrected $r > 0.7$ indicates acceptable internal consistency.

#### Measurement Invariance

**Concern:** Do $K_n$ scores have the same meaning across different populations or item sets?

**Protocol:**
1. Administer MAT to multiple groups (e.g., experts vs novices, domains A vs B)
2. Fit latent variable model $K_n = h(\theta_n)$ separately per group
3. Test whether link function parameters ($\beta$) are equivalent

**Interpretation:**
- Equivalent $\beta$ across groups -> Scores are comparable
- Different $\beta$ -> Group-specific calibration needed; interpret within-group only

#### Cross-Study Comparability

**Concern:** Can $K_n$ scores from different studies be meaningfully compared?

**Requirements for Comparability:**

| Requirement | Description | Verification |
|:------------|:------------|:-------------|
| **Same $f_n$ specification** | Identical claim vocabulary and alignment rules | Document and share protocol |
| **Comparable reference standards** | Similar ground-truth designation criteria | Report reference source |
| **Equivalent $\hat{K}$ parameterization** | Same link function and $\beta$ | Fix $\beta = 1$ or anchor to common scale |

**Recommended Practice:**

1. **Protocol registration**: Pre-specify $f_n$, $g_n$, and $\hat{K}$ before data collection
2. **Anchor items**: Include common items across studies for calibration
3. **Report uncertainty**: Provide confidence intervals for $K_n$ estimates

**When Comparability Fails:**

If studies use different references or $f_n$ specifications, direct $K_n$ comparison is invalid. Instead:
- Report within-study patterns (e.g., proportion of Dunning-Kruger patterns)
- Compare relative rankings, not absolute $K_n$ values

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

### Operational Semantics for Intermediate Values

**The Question:** What does $K_n = 0.6$ mean? The anchors ($-1$, $0$, $+1$) have clear semantics, but intermediate values require interpretation.

**Latent Variable Model:**

We interpret $K_n$ as the observable output of a latent alignment variable $\theta_n \in \mathbb{R}$, mapped to $[-1, 1]$ via a monotonic link function:

$$K_n = h(\theta_n) = \tanh(\beta \cdot \theta_n)$$

where:
- $\theta_n$: Latent alignment strength (unbounded)
- $\beta > 0$: Sensitivity parameter (determines curve steepness)
- $h$: Link function satisfying $h(0) = 0$, $\lim_{\theta \to \pm\infty} h(\theta) = \pm 1$

**Interpretation of Intermediate Values:**

| $K_n$ Value | Latent Interpretation | Operational Meaning |
|:------------|:---------------------|:--------------------|
| $K_n = +1$ | $\theta_n \to +\infty$ | Perfect alignment/knowledge |
| $K_n = +0.6$ | $\theta_n > 0$ (moderate) | Probable alignment with uncertainty |
| $K_n = 0$ | $\theta_n = 0$ | No systematic alignment or misalignment |
| $K_n = -0.6$ | $\theta_n < 0$ (moderate) | Probable misalignment with uncertainty |
| $K_n = -1$ | $\theta_n \to -\infty$ | Perfect misalignment/misconception |

**Alternative Link Functions:**

| Function | Formula | Properties |
|:---------|:--------|:-----------|
| **tanh** (default) | $\tanh(\beta \theta)$ | Smooth, symmetric, unbounded input |
| **Scaled probit** | $2\Phi(\theta) - 1$ | Probabilistic interpretation |
| **Clipped linear** | $\max(-1, \min(1, \theta))$ | Simple, piecewise linear |

The choice of link function is an **empirical question** to be settled by future validation studies.

**Why This Matters:**

Without latent variable semantics, intermediate values risk being "nominal with three anchors." The link function approach provides:
1. **Continuous gradation**: Values between anchors have principled meaning
2. **Estimation targets**: $\theta_n$ can be estimated via maximum likelihood
3. **Uncertainty quantification**: Standard errors on $\hat{\theta}_n$ yield confidence intervals for $K_n$

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
| **Sign** | Signed (-1 to 1) | Unsigned (0 to 1) |
| **Basis** | External validation | Internal experience |

**Orthogonality:**

$K$ and $C$ are **conceptually orthogonal**:

| Pattern | $K_0$ | $C$ | Interpretation |
|:---|:---:|:---:|:---|
| Confident correct | 1 | High | Ideal |
| Confident wrong | -1 | High | Dangerous misconception |
| Unconfident correct | 1 | Low | Imposter-like |
| Unconfident wrong | -1 | Low | Appropriate uncertainty |

**Diagnostic Role:**

$C$ helps distinguish subtypes within the same $K$ pattern:
- DK ($K_0=0$, $K_1=-1$) with **high $C$** -> Overconfident ignorance
- DK ($K_0=0$, $K_1=-1$) with **low $C$** -> Uncertain but still wrong claim

**K-C Dissociation Hypothesis:**

Subjects can have:
- High $K_0$ with low $C$ (Imposter syndrome)
- Low $K_0$ with high $C$ (Dunning-Kruger effect)

This dissociation is empirically testable and clinically meaningful.

**Measurement Protocol for C:**

1. Elicit response -> compute $K_0$
2. Elicit confidence (0-100%) -> record $C$
3. Elicit metacognitive claim ("Do you know?") -> compute $K_1$
4. Analyze $K \times C$ jointly for full characterization

**Important Distinction (Summary):**
- $K(x)$: Epistemic state (how accurately the subject recognizes $x$)
- $C$: Phenomenological confidence (how certain the subject feels)

These are **orthogonal dimensions**. A subject can have:
- $K(x) = 0$ (ignorance) with $C = 1$ (high confidence) --- Dunning-Kruger
- $K(x) = 1$ (knowledge) with $C = 0.5$ (moderate confidence) --- Underconfidence

### The C-K Joint Model: Empirical Handling of Confidence-Knowledge Interaction

**The Problem:**

Confidence ($C$) and epistemic state ($K$) are conceptually orthogonal, but empirically correlated. How should we handle cases like:
- **Dunning-Kruger**: $K_1 = -1$ (miscalibrated) with $C = \text{high}$
- **Imposter Syndrome**: $K_1 = -1$ (miscalibrated) with $C = \text{low}$

**Proposed Joint Model:**

We model the joint distribution of $(K_n, C)$ as a bivariate structure:

$$P(K_n, C) = P(K_n) \cdot P(C \mid K_n)$$

where:
- $P(K_n)$: Marginal distribution of epistemic alignment (from MAT protocol)
- $P(C \mid K_n)$: Conditional distribution of confidence given alignment

**Operationalization:**

| $K_1$ | Expected $C$ Pattern | Interpretation |
|:------|:--------------------|:---------------|
| $+1$ (calibrated) | $C$ correlates with $K_0$ | Confidence tracks knowledge |
| $0$ (uncertain) | $C$ near midpoint | Appropriate uncertainty |
| $-1$ (miscalibrated) | $C$ anti-correlates with $K_0$ | Confidence misleads |

**Dunning-Kruger vs Imposter Analysis:**

For subjects with $K_1 = -1$ (miscalibrated metacognition):

| Subtype | $K_0$ | $C$ | Interpretation | Intervention |
|:--------|:------|:----|:---------------|:-------------|
| **Dunning-Kruger** | $0$ or $-1$ | High | Overconfident ignorance | Calibration training |
| **Imposter Syndrome** | $+1$ | Low | Underconfident knowledge | Confidence building |

**Joint Reporting:**

Report $(K_0, K_1, K_2, C)$ as a 4-tuple for complete metacognitive characterization:

| $K_0$ | $K_1$ | $K_2$ | $C$ | Pattern Name |
|:------|:------|:------|:----|:-------------|
| $0$ | $-1$ | $-1$ | High | Deep Dunning-Kruger (overconfident) |
| $0$ | $-1$ | $+1$ | Low | Aware Dunning-Kruger (self-correcting) |
| $+1$ | $-1$ | $-1$ | Low | Deep Imposter (persistent self-doubt) |
| $+1$ | $-1$ | $+1$ | Low | Aware Imposter (recognizes pattern) |

**Why $C$ Cannot Replace $K$:**

While $C$ and $K_1$ are empirically correlated, they measure different things:
- $K_1$ = **Structural alignment** (does claim match state?)
- $C$ = **Phenomenological intensity** (how certain does subject feel?)

A subject with $K_1 = +1$ (accurate self-assessment) may have $C = 0.3$ (low confidence) --- they correctly identified their state but did not feel certain about it. The $(K, C)$ joint model captures this distinction.

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

**Key Departure:** Epistemic logics typically assume idealized agents with perfect introspection. Our framework explicitly models **failures of introspection**---cases where $K(K(x)) \neq \text{sign}(K(x))$. This captures the Dunning-Kruger effect and imposter syndrome, which are empirically observed but cannot be expressed in standard epistemic logics without violating the introspection axioms.

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

### Correspondence with Established Metrics

Before detailed comparisons, we provide a summary of how the $K$ framework relates to established metrics at each layer.

#### Layer-by-Layer Mapping

| Layer | K Framework | Established Metric | Correspondence |
|:------|:------------|:-------------------|:---------------|
| **$K_0$** | Epistemic state | IRT ability $\theta$ | $K_0 \approx 2\Phi(\theta) - 1$ (scaled) |
| **$K_0$** | Epistemic state | Accuracy | $K_0 = +1$ iff correct |
| **$K_1$** | Metacognitive alignment | meta-d' | $K_1 \propto \text{meta-}d' / d'$ (normalized sensitivity) |
| **$K_1$** | Metacognitive alignment | AUC (Type-2) | $K_1 = 2 \cdot \text{AUC} - 1$ |
| **$K_1$** | Metacognitive alignment | Calibration (ECE) | $K_1 \approx 1 - 2 \cdot \text{ECE}$ (inverse relationship) |
| **$K_2$** | Meta-metacognitive alignment | Stability of $K_1$ across contexts | Novel measure |

#### Detailed Correspondences

**$K_1$ vs meta-d':**

| Aspect | $K_1$ | meta-d' |
|:-------|:---|:--------|
| **Scale** | $[-1, +1]$ | $(-\infty, +\infty)$ |
| **Zero point** | No systematic alignment | Chance-level metacognition |
| **Aggregation** | Per-item, then averaged | Aggregate over item set |
| **Assumptions** | Minimal (monotonicity) | SDT model (Gaussian distributions) |

**Approximate Translation:**
$$K_1 \approx \tanh\left(\frac{\text{meta-}d'}{2}\right)$$

**$K_1$ vs Calibration Error (ECE):**

| Aspect | $K_1$ | ECE |
|:-------|:---|:----|
| **Direction** | +1 = perfect alignment | 0 = perfect calibration |
| **Meaning of negative** | Systematic misalignment | N/A (always $\geq$ 0) |
| **Confidence dimension** | Implicit in State$_1$ | Explicit (confidence bins) |

**Note:** $K_1$ captures *direction* of miscalibration (over- vs under-confidence), while ECE captures *magnitude* only. They are complementary, not redundant.

#### Joint Reporting Standard (Proposed)

For comprehensive metacognitive assessment, we recommend reporting:

| Measure | Source | Information Captured |
|:--------|:-------|:---------------------|
| **$K_0$** | This framework | Epistemic state (knowledge/ignorance/misconception) |
| **$K_1$** | This framework | Alignment direction and magnitude |
| **$K_2$** | This framework | Meta-metacognitive calibration |
| **meta-d'** | SDT | Aggregate sensitivity under SDT assumptions |
| **ECE** | Calibration | Confidence-accuracy gap magnitude |
| **Brier** | Calibration | Combined accuracy + calibration |

This joint profile provides a complete picture: $K_n$ for item-level structure, aggregate metrics for overall performance.

### Positioning Among Related Frameworks

Before comparing specific metrics, we clarify the **role of the $K$ framework** relative to existing approaches:

| Framework | Role | Relationship to $K$ |
|:---|:---|:---|
| **meta-d'** (Maniscalco & Lau) | Aggregate sensitivity metric | $K$ provides per-item classification |
| **meta-I** (Dayan, 2023) | Information-theoretic sensitivity | $K$ adds direction and recursion |
| **HiBayES** (Fleming & Daw, 2017) | Hierarchical estimation engine | $K$ defines what to estimate |
| **IRT** (psychometrics) | Latent trait estimation | $K_0$ uses IRT as estimation engine |
| **Calibration metrics** (Brier, ECE) | Confidence-accuracy alignment | $K$ adds structural classification |

**Key Distinction**:

These frameworks address **how well** metacognition works (sensitivity, efficiency).
The $K$ framework addresses **what type** of metacognitive state exists (classification, coordinates).

**Analogy**:
- meta-d' / meta-I = **Thermometer** (measures metacognitive temperature)
- $K$ = **Weather map** (classifies patterns, guides intervention)

**Integration Potential**:

The $K$ framework serves as a **common coordinate system** that unifies:
- Behavioral assessments (response-claim alignment)
- Signal-detection metrics (meta-d', AUROC)
- Hierarchical estimation (HiBayES)
- Calibration analysis (Brier, ECE)

This is not "reinventing the wheel" but **designing the axle** that connects existing wheels.

### Metacognitive Sensitivity: meta-d'

Maniscalco and Lau (2012) developed the *meta-d'* framework for measuring metacognitive sensitivity---the ability to discriminate between correct and incorrect responses via confidence ratings.

**Formal Correspondence with Type-2 SDT:**

In Type-2 SDT, subjects discriminate their own correct from incorrect responses.

| SDT Quantity | $K$ Framework Equivalent |
|:---|:---|
| Type-1 d' (sensitivity) | Derived from $K_0$ distribution |
| Type-2 Hit Rate | $P(\text{"I know"} | K_0 = 1)$ |
| Type-2 FA Rate | $P(\text{"I know"} | K_0 \leq 0)$ |
| meta-d' | Related to $K_1$ via: $K_1 \approx \tanh(\text{meta-d}'/d')$ |

**What $K$ Adds Beyond meta-d'**:

1. **Signed direction**: meta-d' is unsigned; $K_1$ distinguishes overconfidence ($-1$) from underconfidence
2. **Per-item granularity**: meta-d' is aggregate; $K_1$ can be computed per item
3. **Explicit ignorance**: "I don't know" is modeled as $K_0 = 0$, not low confidence
4. **Recursive hierarchy**: $K_2, K_3, \ldots$ extend beyond Type-2

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
- Subject A: $K_0=0$, $K_1=-1$ -> Dunning-Kruger -> needs awareness intervention
- Subject B: $K_0=1$, $K_1=-1$ -> Imposter -> needs confidence-building

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
| Hallucination + confident | -1 | -1 | ? | Confident wrong (dangerous) |
| Correct + hedging | 1 | -1 | ? | Underconfident (imposter-like) |
| Admits uncertainty | 0 | 1 | 1 | Appropriate uncertainty (Socratic) |
| "I don't know" when wrong | -1 | 1 | ? | Partial awareness of limits |

**Testbed Proposal:**

Using decoupled confidence elicitation (analogous to AFCE-style protocols):

1. **Query LLM for answer** -> compute $K_0$ (against ground truth)
2. **Query LLM for confidence** -> record $C$ (0-100%)
3. **Query LLM: "Do you know this?"** -> elicit $\text{Claim}_1$
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

**Layer-wise Operationalization for LLMs:**

| Layer | Human Operationalization | LLM Operationalization |
|:------|:------------------------|:-----------------------|
| **$K_0$** | Response vs ground truth | Output vs benchmark answer |
| **$K_1$** | Self-assessment claim | Verbalized confidence / hedging |
| **$K_2$** | Meta-self-assessment | "How reliable is my confidence?" prompt |

#### Connection to Recent Research

*Note: Right-column descriptions are interpretations of these works within the K framework, not claims made by the original authors.*

| Research Area | K Framework Contribution |
|:--------------|:------------------------|
| **Human-AI metacognition** (Fernandes et al., 2024; arXiv:2409.16708) | $K_1$ patterns provide a natural way to describe why the Dunning-Kruger effect disappears with AI assistance; AI "levels" metacognitive accuracy |
| **LLM uncertainty communication** (Steyvers et al., 2025; arXiv:2510.05126) | Fine-tuning improves LLM calibration/discrimination; $K_1$ highlights directional (over/under-confidence) patterns that scalar metrics like ECE cannot fully characterize |
| **Latent knowledge probing** (Burns et al., 2022; arXiv:2212.03827, ICLR 2023) | Probing internal activations reveals what LLMs "know" vs "say"; potential alternative to verbalized $g_0$ |
| **LLM metacognitive capacity** (Li et al., 2025; arXiv:2505.13763) | Neurofeedback paradigm quantifies LLM self-monitoring; suggests "metacognitive space" is low-dimensional |
| **VLM uncertainty estimation** (Lin et al., 2025; arXiv:2511.22019) | Post-hoc probabilistic embeddings for error detection; one concrete operational choice for $g_n/\hat{K}$ in vision-language settings |
| **Probabilistic VLM embeddings** (Venkataramanan et al., 2025; arXiv:2505.05163, UAI 2025) | GPLVM-based uncertainty calibration; aligns with Option B's probabilistic $K_n$ estimation |
| **Two-level metacognitive architecture** (Li et al., 2025; arXiv:2511.23262) | Meta-level/object-level separation mirrors $K_0$/$K_1$ layer structure; can serve as a testbed for probing whether meta-reasoning improves $K_1$-type behaviour without necessarily improving $K_0$ |
| **Human-AI teaming** | Match human $K_n$ patterns with AI $K_n$ for improved collaboration |

**Scope Boundary:** Detailed LLM operationalization and experiments are marked for future work.

### Novel Contributions

This study is novel in:

1. **Recursive Formalization**: Extending metacognition to arbitrary depths ($K_0 \to K_1 \to K_2 \to ...$)
2. **Socratic Wisdom as Achievement**: Explicitly modeling "knowing ignorance" as $K_0(x)=0, K_1(x)=1$
3. **Layered Observation Model**: Justifying recursive structure via indexed observations with anchor constraints
4. **Orthogonal Dimensions**: Separating epistemic state ($K$) from phenomenological confidence ($C$)
5. **Per-Item Granularity**: Measuring metacognition at the individual item level, not just aggregate statistics



## Conclusion and Future Challenges

This study constructed a recursive epistemic model based on the hierarchical structure of knowledge. Using a single core function $K$ applied recursively---$K(x)$, $K(K(x))$, $K(K(K(x)))$---we provide a mathematically rigorous yet philosophically grounded framework that captures:

1. The **recursive nature of self-awareness**: The same epistemic question applies at every level of reflection.
2. The **hierarchical structure of metacognition**: Distinguishing "knowing ignorance" (Socratic wisdom) from "unknowing ignorance" (Dunning-Kruger effect).
3. The **continuous gradation of knowledge**: Knowledge states exist on a continuum from misconception ($-1$) through ignorance ($0$) to accurate knowledge ($1$).

### Main Results

1. We proposed a **layered observation model $\{K_n\}$** with formal anchor constraints (preservation, monotonicity, boundedness), demonstrating that recursive metacognition is a well-founded observational structure. The symbolic notation $K(K(x))$ is retained for conceptual communication, while all formal work uses $K_n$ exclusively.
2. We adopted a stance of **methodological relativism**, treating the proposition $x$ itself as the implicit reference point and leaving the designation of "correct" to the experimental context.
3. We provided the **Four Quadrants of Metacognition**, clearly distinguishing "Knowing Ignorance" (Socratic wisdom, $K_0(x)=0, K_1(x)=1$) from "Unknowing Ignorance" (Dunning-Kruger effect, $K_0(x)=0, K_1(x)=-1$).
4. We separated **epistemic state** ($K$) from **phenomenological confidence** ($C$), recognizing them as orthogonal dimensions.
5. We proposed the **Metacognitive Alignment Test (MAT)** as an experimental protocol to validate the model, with specific predictions about the benefits of Socratic wisdom.

### Theoretical Contributions

- **Recursive Formalization**: Extending metacognition to arbitrary depths while maintaining mathematical consistency
- **Layered Observation Model**: Justifying recursive structure via indexed observations ($K_n$) with formal anchor constraints
- **Socratic Wisdom as Achievement**: Explicitly modeling "knowing ignorance" as a high metacognitive state
- **Per-Item Granularity**: Measuring metacognition at the individual item level, complementing aggregate statistical measures

### Limitations

This framework is a **conceptual scaffold** for organizing metacognitive phenomena, not a complete predictive model. We acknowledge the following limitations:

1. **Formal Model:** We adopt an observational family interpretation to resolve the recursion/observation tension. This is a modeling choice, not the only possibility.

2. **Single Dimension (Scope Boundary):** 
   - The $[-1,1]$ scale assumes a **single axis of correctness** with one "opposite" direction.
   - **What this captures:** Directional errors (overconfidence vs underconfidence, correct vs incorrect).
   - **What this does NOT capture:** Multiple, qualitatively different misconceptions (e.g., "thinks A" vs "thinks B" when truth is C).
   
   **Formal Clarification:**
   
   The current model assumes a binary opposition: $\text{Reference} \leftrightarrow \text{Anti-Reference}$
   
   $$K_0 = \begin{cases}
   1 & \text{if Response} = \text{Reference} \\
   0 & \text{if Response} = \text{Absent} \\
   -1 & \text{if Response} \neq \text{Reference}
   \end{cases}$$
   
   This collapses all incorrect responses to $-1$, regardless of *which* error was made.
   
   **When This is Appropriate:**
   - Binary propositions (true/false)
   - Single-answer factual questions
   - Ordinal scales with clear direction
   
   **When This is Limiting:**
   - Conceptual errors with multiple wrong paths
   - Skill assessments with qualitatively different failure modes
   - Open-ended responses
   
   **Future Extension (Out of Scope):**
   
   For multi-dimensional misconceptions, consider:
   
   $$K_0: \mathcal{X} \to [-1, 1]^d$$
   
   Where $d$ = number of independent error dimensions. This requires:
   - Multi-dimensional reference space
   - Vector-valued embedding $g_0$
   - Revised axioms for vector order
   
   We leave this extension for future work, noting that the current scalar formulation covers a wide range of practical applications.

3. **Minimal Axiomatic Theory:** We provide basic constraints on $K$ (anchor preservation, monotonicity, boundedness) but do not specify a unique functional form. The specific dynamics of $K$ (e.g., whether it is contractive, has fixed points beyond $\{-1, 0, 1\}$) are empirical questions.

4. **No Generative Model:** We do not provide a noise model or generative account of how states are produced. This is a task for computational cognitive modeling.

5. **Observation Protocol:** The mapping from observable behavior to $K_n$ values requires operational definitions. While we provide guidelines (e.g., alignment between claims and performance), the specific elicitation methods depend on the application domain.

6. **$K_2$ Identifiability:** Higher-order estimates ($K_2$, $K_3$) require more items and may be less reliable.
   - **Guideline:** For reliable $K_2$ estimation, use $N \geq 50$ items with noise $< 0.2$.
   - **Confidence intervals:** Report 95% CI via bootstrap; if CI width $> 0.3$, interpret with caution.

7. **Simulation Validation Pending:** We have not yet provided simulated evidence that different metacognitive profiles (Socratic, Dunning-Kruger, Imposter) are identifiable under realistic noise. This is planned for future work.

8. **Analogical Type Theory:** The type-theoretic justification is analogical rather than formally constructed. A full domain-theoretic or typed lambda-calculus treatment is beyond the current scope.

9. **LLM Operationalization Incomplete:** Applying $K_n$ to LLMs requires addressing question-side shortcuts and model-side signals. Specific methods (conformal coverage, debate protocols) are suggested but not developed here.

### Validation Roadmap

This paper establishes the **conceptual framework**; validation is planned for follow-up work. We present a staged validation program:

#### Phase 1: Reliability

| Type | Method | Target |
|:---|:---|:---|
| **Test-Retest** | 2-week interval, same items | $r > 0.7$ |
| **Internal Consistency** | Cronbach's $\alpha$ across items | $\alpha > 0.8$ |
| **Split-Half** | Odd-even item split | $r > 0.75$ |

#### Phase 2: Convergent Validity

| $K$ Measure | Comparison Metric | Expected Correlation |
|:---|:---|:---|
| $K_1$ | meta-d'/d' | $r > 0.6$ (positive) |
| $K_1$ | Type-2 AUROC | $r > 0.5$ (positive) |
| $K_0$ | IRT ability $\theta$ | $r > 0.8$ (positive) |

#### Phase 3: Discriminant Validity

| $K$ Measure | Comparison | Expected |
|:---|:---|:---|
| $K_1$ | Raw confidence $C$ | $r < 0.3$ (low) |
| $K_0$ | Response time | $r < 0.2$ (low) |

#### Phase 4: Predictive Validity

| Predictor | Outcome | Hypothesis |
|:---|:---|:---|
| $K_1 = 1$ (Socratic) | Help-seeking | Higher |
| $K_2 = 1$ | Intervention responsiveness | Higher |
| $K_1 = -1$ (DK) | Overconfident errors | Higher |

**Acknowledgment**: We recognize that this validation program is **essential** for empirical adoption. The current paper's contribution is the **conceptual and formal foundation** upon which such validation can be built.

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

**Each layer observes a different object.** There is no "subject's report" vs "evaluator's assessment" --- there is only **observation of states**.

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