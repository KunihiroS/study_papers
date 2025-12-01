# Revision Plan 04: A Study on the Hierarchical Structure of Knowledge and the Cognition of Ignorance

**Based on Review:** 20251130_03.md
**Date:** 2025-12-01
**Status:** Draft — **Deepening Phase: From Conceptual Framework to Formal Specification**

---

## Review Context: Stateless Evaluation

**Important Note:** Each review is independent (stateless). This reviewer has not seen previous revisions.

### Current Review Assessment

| Aspect | 今回の評価 (20251130_03) |
|:---|:---|
| **概念的フレームワーク** | "conceptually appealing", "clear and timely conceptual framing" |
| **K と C の分離** | Strengths として評価 |
| **T(x) の中立性** | "well-motivated and pragmatically framed" |
| **説明の明確さ** | "narrative and illustrative examples are compelling" |
| **MAT** | "concrete path toward measurement" |
| **Overall** | "contribution has potential but is not yet ready for a top-tier venue" |

### 批判の本質

レビュワーは概念フレームワーク自体を評価しつつ、**形式的な深さ**を要求している：

> "the technical core remains under-specified: without axioms or functional constraints on K, the model lacks predictive power and identifiability"

---

## Strategic Decision: 論文の性格の明確化

### 選択肢

| Option | Description | Pros | Cons |
|:---|:---|:---|:---|
| **A: Full Formalization** | K の完全な公理化、シミュレーション、型理論の厳密化 | レビュワーの要求に完全対応 | 論文の性格が変わる、作業量膨大 |
| **B: Targeted Strengthening** | 核心的な批判への対応 + 限界の明示 | 論文の焦点を維持、現実的 | 一部の批判が残る |
| **C: Position Paper Declaration** | 概念論文としての立場を明確化 | 期待値を調整 | 一部のレビュワーには不十分 |

### 推奨: **Option B — Targeted Strengthening**

理由：
1. 概念フレームワークとしての評価は既に得られている
2. 完全な形式化は別論文の範囲
3. 核心的な批判への対応で論文の質を向上させつつ、限界を正直に認める

---

## Review Criticism Analysis

### レビュワーの 10 Questions への分類

| # | Question | 優先度 | 対応方針 |
|:---|:---|:---:|:---|
| Q1 | K の公理・構造的性質 | **高** | 基本公理を明示（ただし完全な理論は Future Work） |
| Q2 | T(x)=0 と K(x)=0 の区別 | **高** | 明確な区別を追加 |
| Q3 | 主観確率 → [-1,1] マッピング | **中** | オプションを提示（完全な導出は Future Work） |
| Q4 | 連続的 K(K(x)) の推定 | **中** | 2·P(match)−1 の明確化 |
| Q5 | 統計的ベースライン (meta-d', IRT) | **中** | 関係性の明確化（実装は Future Work） |
| Q6 | 回答スタイル・社会的望ましさの制御 | **低** | Limitations として認識 |
| Q7 | LLM での question-side shortcuts | **低** | Future Work として位置づけ |
| Q8 | シミュレーションによる識別可能性 | **低** | Future Work として位置づけ |
| Q9 | 型理論的基盤の厳密化 | **中** | 現行の類推を維持しつつ、限界を認める |
| Q10 | 文化・ドメイン固有の非対称性 | **低** | Future Work として位置づけ |

---

## Revision Items

### A: Technical Foundation — 高優先

#### A1: K の基本公理の明示

**現状:** K の構造的制約が不明確
**批判:** "no axioms... making the model non-falsifiable"

**対応:**

新しいサブセクション「**Axiomatic Constraints on K**」を追加：

```
### Axiomatic Constraints on K

We impose the following minimal constraints on the epistemic function K:

**Definition: Objective Evaluation**
The function $K$ represents an **objective evaluation** of the subject's epistemic state by an external observer (or the system), distinct from the subject's subjective feeling of confidence ($C$).
- $K(x) = 1$: Objectively accurate recognition.
- $K(x) = -1$: Objectively inverted recognition (misconception).

**Anchor Preservation:**
- $K(1) = 1$ (accurate recognition of knowledge)
- $K(0) = 0$ (accurate recognition of ignorance)
- $K(-1) = -1$ (accurate recognition of misconception)

*Rationale for $K(-1)=-1$:* Even if a subject subjectively believes a misconception is true (high confidence), the **objective** relationship between their state and the proposition is inverted. Thus, $K$ must map this state to $-1$.

**Monotonicity:**
- If k₁ > k₂, then K(k₁) ≥ K(k₂)
- More positive epistemic states are not mapped to more negative metacognitive states

**Boundedness:**
- K: [-1, 1] → [-1, 1]
- The function is closed on the epistemic state space

**Note:** We deliberately refrain from specifying stronger constraints (e.g., odd symmetry, Lipschitz constant, contraction mapping) at this stage. The framework is intended to be **descriptive** rather than **predictive** — it provides a vocabulary for classifying observed metacognitive states, not a generative model of metacognitive dynamics. Specifying a particular functional form for K is a task for domain-specific empirical research.
```

**Scope Clarification:**

追加テキスト：
> "This framework is a **conceptual scaffold** for organizing metacognitive phenomena, not a complete predictive model. The specific functional form of K (e.g., whether it is contractive, has fixed points beyond {-1, 0, 1}, or exhibits particular dynamics under iteration) is an **empirical question** to be addressed in domain-specific research."

---

#### A2: Removing T(x) — Proposition as Implicit Reference

**Current Issue:** T(x) is framed as a "Truth Function," leading to confusion about T(x)=0 (undefined truth) vs K(x)=0 (ignorance).
**Critique:** "The treatment of '0' in T(x)... risks conflation"

**Response Strategy:**
We eliminate the T(x) notation entirely. The proposition $x$ itself serves as the implicit reference point.

**1. Remove T(x) Notation**
- We do not use a separate "Truth Function" or "Reference Value" symbol.
- The proposition $x$ itself serves as the reference point.
- What counts as "aligned" ($K(x)=1$) vs "opposed" ($K(x)=-1$) is determined by the **experimental context** (e.g., expert consensus, empirical measurement), not by this model.

**2. Redefine K(x) as Epistemic State**

$K(x)$ represents the subject's **epistemic state** regarding proposition $x$:

| K(x) | State | Interpretation |
|:---:|:---|:---|
| $1$ | Aligned | Subject's belief is consistent with $x$ |
| $0$ | Indeterminate | Subject has no determinate stance on $x$ |
| $-1$ | Opposed | Subject's belief is contrary to $x$ |

**3. Scope Clarification (Methodological Relativism)**

```markdown
### Scope Clarification

This model does not adjudicate what is "correct" or "true." 
It provides a mathematical apparatus for representing and manipulating 
the **structure of epistemic states** relative to a proposition. 

The designation of a proposition as the "target" (such that $K(x)=1$ 
represents success) is a **methodological choice** made by the experimenter, 
not a claim of this framework.
```

**Conclusion:** By removing T(x) and treating the proposition itself as the implicit reference, we eliminate the conflation of "undefined truth" and "ignorance." The model focuses purely on the **structure of epistemic states** — the T(x)=0 case simply does not exist in this framework.

---

### B: Measurement Theory — 中優先

#### B1: 連続的 K(K(x)) 推定の明確化

**現状:** 2·P(match)−1 の言及はあるが詳細が不足
**批判:** "The inference of K(K(x)) from a single categorical self-claim collapses nuance"

**対応:**

「Measurement Theory」セクションに追加：

```
### Continuous Estimation of K(K(x))

The categorical inference of K(K(x)) from a single "Do you know?" claim is a **simplified operationalization**. For more robust measurement, we propose:

**Option 1: Aggregation Across Items**

For a subject responding to multiple items within a domain:

$$K(K)_{aggregate} = 2 \cdot P(\text{meta-claim matches actual state}) - 1$$

where P is estimated across all items. This yields a continuous value in [-1, 1].

**Option 2: Hierarchical Bayesian Estimation**

Model K(K(x)) as a latent variable with:
- Prior distribution over subjects
- Item-level random effects
- Observation model linking latent K(K(x)) to categorical claims

This approach accommodates noise, individual differences, and item difficulty.

**Option 3: Probabilistic Elicitation**

Instead of categorical "Yes/No/Unsure", elicit:
- "How confident are you that your previous answer was correct?" (0-100%)

Map this to K(K(x)) via a proper scoring rule or calibration analysis.

**Relationship to meta-d':**

Our K(K(x)) and meta-d' measure related but distinct constructs:

| Aspect | meta-d' | K(K(x)) |
|:---|:---|:---|
| **Granularity** | Aggregate (across trials) | Per-item or aggregate |
| **Statistical Model** | Type-2 SDT | Recursive epistemic function |
| **Socratic Wisdom** | Not explicitly modeled | K(x)=0, K(K(x))=1 |

An integrated research program could:
1. Use meta-d' for noise-tolerant aggregate metacognitive sensitivity
2. Use K(K(x)) for per-item structural classification
3. Compare both metrics to validate convergent validity
```

---

#### B2: MAT と既存指標の関係の明確化

**現状:** meta-d', ECE, Brier との関係が high-level
**批判:** "no formal mapping or empirical synthesis"

**対応:**

「MAT」セクションに追加：

```
### Relationship to Established Metrics

The MAT is designed to complement, not replace, existing metacognitive measures:

| Metric | What it measures | Relationship to MAT |
|:---|:---|:---|
| **meta-d'** | Metacognitive sensitivity (discrimination) | Can be computed from MAT data; provides aggregate validation |
| **Brier Score** | Probabilistic calibration | Applicable if confidence is elicited as probability |
| **ECE** | Expected calibration error | Measures bias in confidence-accuracy relationship |
| **AUROC** | Discrimination ability | Can be derived from confidence ratings vs. accuracy |
| **IRT** | Item difficulty and discrimination | Can model item-level variance in MAT responses |

**Recommended Analysis Pipeline:**

1. Compute K(x) and K(K(x)) per item using MAT protocol
2. Compute meta-d' across trials as aggregate metacognitive sensitivity
3. Compute calibration metrics (Brier, ECE) from confidence ratings
4. Compare K(K(x)) patterns (Socratic, Dunning-Kruger, etc.) with meta-d' to validate convergent validity
5. Use IRT to account for item-level heterogeneity

**Hypothesis:** High K(K(x)) (accurate metacognition) should correlate with high meta-d'/d' ratio and good calibration, but K(K(x)) provides additional structural information (e.g., distinguishing Socratic wisdom from mere low confidence).
```

---

### C: Related Work — 中優先

#### C1: Graded Epistemic Logic への言及強化

**現状:** S5/KD45 との比較はあるが、graded logic への言及がない
**批判:** "Key literatures in graded/fuzzy epistemic logics... are only partially engaged"

**対応:**

「Related Work」セクションに追加：

```
### Relationship to Graded Epistemic Logics

Recent work in graded epistemic logics (e.g., S5G frameworks) models knowledge with continuous plausibility values in [0, 1]. Our framework differs in key respects:

| Aspect | Graded Epistemic Logics | Our K(K(x)) |
|:---|:---|:---|
| **Scale** | [0, 1] (plausibility) | [-1, 1] (includes misconception) |
| **Misconception** | Typically not modeled | K(x) = -1 |
| **Metacognition** | Introspection axioms | Explicit recursive operator |
| **Focus** | Idealized agents | Psychologically realistic failures |

**Formal Correspondence:**

Our K can be viewed as a **graded, psychologically realistic** extension that:
1. Relaxes positive/negative introspection axioms to accommodate metacognitive failures
2. Extends the scale to include misconception (negative values)
3. Focuses on the **gap** between actual and recognized epistemic states, rather than idealized consistency

Whether K is idempotent (K(K(x)) = K(x) for accurate metacognizers) or contractive (higher-order reflection converges) is an **empirical question** that our framework can accommodate but does not presuppose.
```

---

### D: Scope and Limitations — 新規追加

#### D1: 明示的な Limitations セクションの追加

**対応:**

新しいセクション「**Limitations and Future Work**」を追加：

```
## Limitations and Future Work

### What This Framework Does Not Provide

1. **Complete Axiomatic Theory:** We provide minimal constraints on K (anchor preservation, monotonicity, boundedness) but do not specify a unique functional form. The framework is descriptive, not predictive.

2. **Generative Model:** We do not provide a noise model or generative account of how K values are produced. This is a task for computational cognitive modeling.

3. **Simulation Validation:** We have not yet provided simulated evidence that different metacognitive profiles (Socratic, Dunning-Kruger, Imposter) are identifiable under realistic noise. This is planned for future work.

4. **Domain-Theoretic Type Theory:** The type-theoretic justification is analogical rather than formally constructed. A full domain-theoretic or typed lambda-calculus treatment is beyond the current scope.

5. **LLM Operationalization:** Applying K(K(x)) to LLMs requires addressing question-side shortcuts and model-side signals. Specific methods (conformal coverage, debate protocols) are suggested but not developed here.

### Future Research Directions

1. **Empirical Validation:** Conduct MAT experiments to estimate K and K(K(x)) across domains and compare with meta-d' and calibration metrics.

2. **Simulation Studies:** Simulate agents with known K/C profiles to demonstrate identifiability and estimate required sample sizes.

3. **Formal Type Theory:** Develop a typed calculus or algebraic data type where K's self-application is a well-typed endomorphism.

4. **AI Safety Applications:** Operationalize K(K(x)) for LLMs using abstention behavior, self-consistency, and metamorphic testing.

5. **Cultural and Domain Variation:** Investigate whether the symmetry assumption (misconception vs. knowledge) holds across cultures and domains.
```

---

## Summary: Revision Scope

| Category | Items | Estimated Work |
|:---|:---|:---|
| **A: Technical Foundation** | A1 (K axioms), A2 (T(x)/K(x) distinction) | Medium |
| **B: Measurement Theory** | B1 (K(K(x)) estimation), B2 (MAT vs. metrics) | Medium |
| **C: Related Work** | C1 (Graded epistemic logic) | Low |
| **D: Scope/Limitations** | D1 (Explicit limitations) | Low |

### 対応しない批判（スコープ外）

| 批判 | 理由 |
|:---|:---|
| シミュレーションによる識別可能性の証明 | Future Work として位置づけ |
| 完全な型理論の構築 | 別論文の範囲 |
| LLM 応用の完全な operationalization | Future Work として位置づけ |
| 文化・ドメイン固有の非対称性の検証 | 実証研究の範囲 |

---

## Decision Points for Discussion

1. **Option B (Targeted Strengthening) で良いか？** — 完全な形式化を目指すか、概念フレームワークの深化に留めるか

2. **K の公理の範囲** — 最小限（anchor preservation, monotonicity, boundedness）で十分か、より強い制約を追加するか

3. **Limitations セクションの追加** — 明示的に限界を認めることで、レビュワーの期待値を調整する戦略は適切か

4. **Related Work の深さ** — Graded epistemic logic への言及をどこまで深めるか

---

## Next Steps

1. この revision_plan_04 のレビュー
2. 合意後、.md ファイルへの変更適用
3. .tex ファイルの同期
4. 再コンパイルと確認
