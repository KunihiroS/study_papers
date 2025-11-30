# A Study on the Hierarchical Structure of Knowledge and the Cognition of Ignorance

*Kunihiro Sugiyama*  
kunihiros@gmail.com

## Introduction

Human knowledge possesses a multi-layered structure, and the ability to recognize one's own ignorance (metacognition) is crucial for learning and decision-making. This study proposes a recursive model of knowledge and ignorance based on a single core function: **$K$**, which represents epistemic recognition. By applying this function recursively—$K(x)$, $K(K(x))$, $K(K(K(x)))$, and so on—we formalize the hierarchical structure of self-awareness that distinguishes **Socratic wisdom** ("knowing that one does not know") from the **Dunning-Kruger effect** ("not knowing that one does not know").

This model integrates insights from **metacognition research**, **epistemology**, and **type theory** to address three aspects that have not been sufficiently unified in existing research:

1. The **recursive nature of self-awareness**: The same epistemic question ("Do I know?") can be applied at every level of reflection.
2. The **continuous gradation of knowledge**: Knowledge states exist on a continuum from complete misconception ($-1$) through ignorance ($0$) to accurate knowledge ($1$).
3. The **distinction between epistemic state and phenomenological confidence**: What one knows versus how certain one feels are orthogonal dimensions.

By presenting a mathematically rigorous yet philosophically grounded framework, this study seeks to deepen our understanding of the structure of knowledge and the cognitive mechanisms of ignorance.


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


## The Reference Point: Truth Function $T(x)$

To analyze the discrepancy between what a subject believes and what is considered factual, we introduce a **Truth Function** $T(x)$.

### Definition

* **Symbol:** $T(x)$
* **Definition:** A reference function that maps a proposition $x$ to a continuous value representing its "factual status" as understood within the cognitive context.
* **Domain/Codomain:** $T: \mathcal{X} \to [-1, 1]$
  * $1.0$: The proposition is considered fully accurate within the context.
  * $0.0$: The proposition is undefined or undeterminable within the context.
  * $-1.0$: The proposition is considered completely contrary to the understood facts.

### Ontological Neutrality

This paper deliberately adopts an **ontologically neutral** position regarding $T(x)$. We do not take a stance on whether $T(x)$ represents:

* **Objective reality** (realism): Facts exist independently of observers.
* **Phenomenal facts** (phenomenalism/relativism): Facts are constituted through the subject's cognitive context.

What matters for this methodology is that $T(x)$ serves as a **reference point** against which the subject's state $K(x)$ can be compared. The ontological status of $T(x)$ is a separate philosophical question beyond the scope of this paper.

This design allows users of this framework to adopt their preferred philosophical interpretation while maintaining the mathematical rigor of the model.

### Connection with Epistemological Tradition

This study acknowledges the discussion of **the separation between the subjective and the objective** in epistemology. In his *Critique of Pure Reason*, Kant distinguished between phenomena (subjective experience) and the thing-in-itself (objective reality), and argued that humans cannot directly know the thing-in-itself (Kant, 1781). 

Rather than claiming access to the "thing-in-itself," our model uses $T(x)$ as a practical reference point that can be operationalized in specific contexts (e.g., as expert consensus, empirical measurement, or community agreement). This distinction is an essential premise for considering the **discrepancy between the subjectivity and objectivity of knowledge**.

## The Recursive Structure: $K(K(K(x)))$

The cognitive structure of knowledge is modeled using a **recursive epistemic function** $K$. This model formalizes the intuition that the same question—"Do I know?"—can be applied at every level of self-reflection.

### Formal Definition of $K$

**Definition:**

$$K: \text{Object} \to [-1, 1]$$

Where **Object** can be:
- A proposition (e.g., "The Earth is round")
- A cognitive state (e.g., $K(x) \in [-1, 1]$)
- A metacognitive state (e.g., $K(K(x)) \in [-1, 1]$)

**Output Interpretation:**
- $K(\text{object}) = 1$: The subject accurately recognizes the object.
- $K(\text{object}) = 0$: The subject does not recognize the object (ignorance).
- $K(\text{object}) = -1$: The subject misrecognizes the object (misconception).

**Key Insight:** The function $K$ has **consistent semantics** across all layers: "How accurately does the subject recognize this object?"

### Type-Theoretic Foundation

To address concerns about mathematical rigor, we provide a type-theoretic justification for the recursive structure.

**Type Hierarchy:**

```
type EpistemicObject = Proposition | EpistemicState
type Proposition = String
type EpistemicState = Real[-1, 1]
```

**Function Signature:**

```
K : EpistemicObject -> EpistemicState
K : EpistemicObject -> Real[-1, 1]
```

**Recursive Application:**

Since `EpistemicState` is a subtype of `EpistemicObject`, we can apply $K$ recursively:

```
K(x : Proposition) -> s0 : EpistemicState
K(s0 : EpistemicState) -> s1 : EpistemicState
K(s1 : EpistemicState) -> s2 : EpistemicState
```

**This is not a type error.** This is a **recursive type** with a well-defined structure, analogous to:
- **Lambda Calculus**: Self-application via $\lambda x. (\lambda y. y) x$
- **Fixed-Point Combinators**: $Y = \lambda f. (\lambda x. f(x x))(\lambda x. f(x x))$
- **Recursive Types**: $\mu \alpha. \alpha \to \alpha$

The recursive structure $K(K(x))$ is mathematically well-founded and has precedent in formal systems.

### Recursive Application

**Notation:**

$$K_0(x) = K(x)$$
$$K_1(x) = K(K_0(x)) = K(K(x))$$
$$K_2(x) = K(K_1(x)) = K(K(K(x)))$$

**Interpretation:**

| Layer | Expression | Question |
|:---|:---|:---|
| **Layer 0** | $K(x)$ | "How accurately do I recognize proposition $x$?" |
| **Layer 1** | $K(K(x))$ | "How accurately do I recognize my state $K(x)$?" |
| **Layer 2** | $K(K(K(x)))$ | "How accurately do I recognize my metacognitive state $K(K(x))$?" |

**Same question. Same function. Same semantics.**

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

### Connection with Metacognition Research

Flavell (1979) defined metacognition as "the ability to monitor and control one's own cognitive activities." The recursive structure ($K \to K(K) \to K(K(K))$) formalizes this concept mathematically.

Dunning and Kruger (1999) demonstrated that individuals with low competence tend to overestimate their abilities. In our model, this corresponds to $K(x) = 0$ (ignorance) but $K(K(x)) = -1$ (misrecognition of ignorance).

**Novel Contribution:** While existing metacognition studies focus on statistical measures of metacognitive sensitivity (e.g., meta-d'), our model provides a **structural formalization** of the recursive nature of self-awareness, explicitly distinguishing "Knowing Ignorance" (Socratic wisdom) as a high metacognitive achievement.



## Measurement Theory

This section describes how the theoretical constructs ($K(x)$, $K(K(x))$) can be operationalized and measured empirically.

### The Challenge of Measuring Second-Order States

$K(K(x))$ is a **second-order epistemic state**: it represents the subject's recognition of their own first-order state $K(x)$. We cannot directly observe $K(K(x))$; we must infer it from observable behavior.

### Introducing Confidence: $C$

To fully characterize the phenomenological experience of metacognition, we additionally measure **subjective confidence** $C_k \in [0, 1]$.

**Important Distinction:**
- $K(x)$: Epistemic state (how accurately the subject recognizes $x$)
- $C$: Phenomenological confidence (how certain the subject feels)

These are **orthogonal dimensions**. A subject can have:
- $K(x) = 0$ (ignorance) with $C = 1$ (high confidence) — Dunning-Kruger
- $K(x) = 1$ (knowledge) with $C = 0.5$ (moderate confidence) — Underconfidence

### Measurement Protocol

#### Step 1: Establish Ground Truth $T(x)$

For each proposition $x$, establish a reference truth value via expert consensus, empirical measurement, or community agreement.

#### Step 2: Measure $K(x)$ via Task Performance

**Task:** Subject answers: "Is proposition $x$ true, false, or unknown?"

| Subject's Answer | $T(x)$ | Inferred $K(x)$ |
|:---|:---:|:---:|
| "True" | $1$ | $1$ (correct knowledge) |
| "False" | $-1$ | $1$ (correct knowledge) |
| "I don't know" | any | $0$ (ignorance) |
| "True" | $-1$ | $-1$ (misconception) |
| "False" | $1$ | $-1$ (misconception) |

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

#### Discrepancy between Reference and State

$$D_{TK} = |T(x) - K(x)|$$

Measures how far the subject's recognition deviates from the factual reference.

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
- Present factual questions with established $T(x)$ values
- Subject responds: True / False / I don't know
- Calculate $K(x)$ based on correctness

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



## Related Work

### Metacognitive Sensitivity: meta-d'

Maniscalco and Lau (2012) developed the *meta-d'* framework for measuring metacognitive sensitivity—the ability to discriminate between correct and incorrect responses via confidence ratings.

**Comparison:**

| Aspect | meta-d' | Our $K(K(x))$ |
|:---|:---|:---|
| **Focus** | Discrimination ability (sensitivity) | Structural accuracy (recognition) |
| **Measurement** | Statistical correlation across trials | Per-item metacognitive state |
| **"I don't know"** | Treated as low confidence | $K(x)=0, K(K(x))=1$ (Socratic wisdom) |
| **Theoretical Basis** | Signal Detection Theory | Recursive epistemology |

**Key Difference:** meta-d' measures whether confidence ratings **correlate** with accuracy. Our model measures whether metacognitive claims **match** actual states. Crucially, we recognize that **accurately knowing one's ignorance** ($K(x) = 0, K(K(x)) = 1$) is a **high metacognitive achievement**, not a failure.

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

**Complementary Relationship:** Dempster-Shafer theory could be used to model $T(x)$ when the reference itself is uncertain. Our model specifically targets the **gap between what one knows and what one thinks one knows**.

### Dunning-Kruger Effect (Empirical Psychology)

Dunning and Kruger (1999) empirically demonstrated that low-competence individuals overestimate their abilities.

**Our Contribution:** We provide a **formal mathematical model** of this phenomenon:
- $K(x) = 0$ (low competence)
- $K(K(x)) = -1$ (misrecognition: believes they have competence)
- Often accompanied by $C = 1$ (high confidence)

This formalization enables:
1. Precise measurement protocols
2. Distinction from related phenomena (e.g., imposter syndrome)
3. Extension to arbitrary depths of self-reflection

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

1. We proposed a **recursive epistemic function $K$** with type-theoretic justification, demonstrating that $K(K(x))$ is not a type error but a well-founded recursive structure.
2. We introduced the **Truth Function $T(x)$** with **ontological neutrality**, allowing the framework to be used by researchers with different philosophical commitments.
3. We provided the **Four Quadrants of Metacognition**, clearly distinguishing "Knowing Ignorance" (Socratic wisdom, $K(x)=0, K(K(x))=1$) from "Unknowing Ignorance" (Dunning-Kruger effect, $K(x)=0, K(K(x))=-1$).
4. We separated **epistemic state** ($K$) from **phenomenological confidence** ($C$), recognizing them as orthogonal dimensions.
5. We proposed the **Metacognitive Alignment Test (MAT)** as an experimental protocol to validate the model, with specific predictions about the benefits of Socratic wisdom.

### Theoretical Contributions

- **Recursive Formalization**: Extending metacognition to arbitrary depths while maintaining mathematical consistency
- **Type-Theoretic Foundation**: Justifying self-application via recursive types
- **Socratic Wisdom as Achievement**: Explicitly modeling "knowing ignorance" as a high metacognitive state
- **Per-Item Granularity**: Measuring metacognition at the individual item level, complementing aggregate statistical measures

### Future Challenges

1. **Empirical Validation**: Conduct MAT experiments to validate the model's predictions about Socratic wisdom and Dunning-Kruger effect.
2. **AI Safety Applications**: Apply the framework to detect "hallucinations" in LLMs as instances of Unknowing Ignorance ($K(x)=0, K(K(x))=-1$).
3. **Cultural Factors**: Evaluate how social and cultural contexts influence metacognitive patterns.
4. **Educational Interventions**: Design interventions to cultivate Socratic wisdom (increasing $K(K(x))$ when $K(x)=0$).
5. **Higher-Order Recursion**: Investigate the cognitive and computational limits of $K(K(K(...)))$ recursion.



## References

1. Kant, I. (1781). *Critique of Pure Reason*.
2. Flavell, J. H. (1979). Metacognition and cognitive monitoring: A new area of cognitive-developmental inquiry. *American Psychologist*, *34*(10), 906-911.
3. Dunning, D., & Kruger, J. (1999). Unskilled and unaware of it: How difficulties in recognizing one's own incompetence lead to inflated self-assessments. *Journal of Personality and Social Psychology*, *77*(6), 1121-1134.
4. Maniscalco, B., & Lau, H. (2012). A signal detection theoretic approach for estimating metacognitive sensitivity from confidence ratings. *Consciousness and Cognition*, *21*(1), 422-430.
5. Shafer, G. (1976). *A Mathematical Theory of Evidence*. Princeton University Press.
6. Fleming, S. M., & Daw, N. D. (2017). Self-evaluation of decision-making: A general Bayesian framework for metacognitive computation. *Psychological Review*, *124*(1), 91-114.