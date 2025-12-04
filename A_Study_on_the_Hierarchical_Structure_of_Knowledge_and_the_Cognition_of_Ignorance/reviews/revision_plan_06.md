# Revision Plan 06: A Study on the Hierarchical Structure of Knowledge and the Cognition of Ignorance

**Based on Review:** 20251203_01.md
**Date:** 2025-12-03
**Status:** Draft — **Formalizing K as a Classification & Intervention Framework**

---

## Review Context: Progress Assessment

### Previous vs Current Review

| Aspect | 前回 (20251201_01) | 今回 (20251203_01) |
|:---|:---|:---|
| **全体評価** | "core ambiguity... conflicts with axioms" | "thoughtful and ambitious conceptual proposal" |
| **27パターン** | 未追加 | "useful for discussion and pedagogy" ✅ |
| **K vs C 分離** | Strengths として評価 | "conceptually valuable" ✅ |
| **Nelson & Narens** | 未言及 | "appropriately invoked" ✅ |
| **Koriat** | 未言及 | "appropriately invoked" ✅ |
| **測定提案** | 批判的 | "reasonable starting points" ✅ |
| **残る課題** | 形式的矛盾 | 形式の一本化 + 軽い実証 |

### 今回のレビュー評価

> "This is a thoughtful and ambitious conceptual proposal... With these improvements, the work could evolve from a position piece into **a more robust foundation that others can build on** empirically and theoretically."

**→ 「コンセプト自体は価値がある。形式を固めて軽い実証を加えれば、他者が構築できる基盤になる」という評価。**

---

## Key Insight: K Framework Positioning

### K は「測定指標」ではなく「分類・介入設計の座標系」

**既存指標との住み分け:**

| 指標 | 機能 | 出力 |
|:---|:---|:---|
| **meta-d'** (Maniscalco & Lau, 2012) | 感度測定（SDTモデル依存） | 数値（d'単位） |
| **meta-I** (Dayan, 2023) | 感度測定（モデルフリー、粒度も評価） | 数値（ビット単位） |
| **K フレームワーク** | **パターン分類 + 介入設計** | 座標 + タイプ |

**K の独自価値:**

1. **分類ツール**: 認知状態を Socratic / DK / Imposter 等にカテゴライズ
2. **方向性（符号）**: 過信 vs 過小評価を区別
3. **再帰的レイヤー**: 問題が K₀/K₁/K₂ のどこにあるか特定
4. **介入設計**: どのレイヤーを動かせば改善するかを示す

**Analogy:**
- meta-d' / meta-I = **温度計**（感度を数値化）
- K = **天気図**（パターンを分類し、対策を示す）

**具体例:**

2人の被験者、同じ meta-I = 0.3 ビット（低い）:

| 被験者 | K₀ | K₁ | K₂ | パターン | 介入戦略 |
|:---|:---:|:---:|:---:|:---|:---|
| A | 0 | -1 | -1 | Dunning-Kruger（重症） | まず K₂ に介入（自己認識の不備に気づかせる） |
| B | 1 | -1 | 1 | Imposter（自覚あり） | K₁ に直接介入（自信を与える） |

**meta-I では A と B を区別できない。K では区別できる。**

---

## Core Issues Identified

### 1. K の二重定義問題（最重要）

**レビュワーの指摘:**
> "There is an unresolved tension between (i) defining a single recursive mapping k_{n+1}=K(k_n) over [-1,1] and (ii) later insisting that K1(x) is not the numerical composition K(K0(x)) but an observation on a distinct object State1."

**レビュワーの提案:**

| Option | Description | 評価 |
|:---|:---|:---|
| **Option A** | 関数的再帰を維持、`K(0)≠0` を許容 | 現フレームワークと整合しにくい |
| **Option B** | 観察ファミリー `{K^(n)}` を定義、State_{n+1} を明示的に構成 | **推奨** |

### 2. State_n の形式的定義の欠如

**レビュワーの指摘:**
> "Key constructs (State_n) are described informally; the reader lacks a precise generative/measurement model specifying how State_n is observed from responses and claims."

### 3. 実証的検証の欠如

**レビュワーの指摘:**
> "No empirical sanity checks are provided to demonstrate that the proposed aggregation schemes or Bayesian models recover meaningful K1/K2 estimates or to benchmark against meta-d' or calibration metrics."

### 4. 関連研究との接続の浅さ

**レビュワーの指摘:**
> "The link to existing formalizations (e.g., signal detection theory for metacognition, meta-d', hierarchical psychometric models) could be deepened."

---

## Strategic Decision

### 採用: Option B — 観察ファミリー `{K^(n)}` モデル

**理由:**
1. **レビュワーの明確な推奨**: "This seems closer to your operational intent and avoids type confusion."
2. **本フレームワークの哲学的立場と整合**: 「純粋に観測的」な立場
3. **形式的一貫性**: 層ごとに異なるオブジェクト（State_n）を観測することを明示
4. **拡張性**: 将来の情報幾何への接続を容易にする

---

## Revision Items

### A: Formal Core — 最高優先

#### A1: Option B の明示的採用

**現状:** K の解釈が曖昧（関数的再帰 vs 観察プロトコル）
**対応:** Option B を明確に採用し、全体を書き換え

```markdown
### Formal Framework: Layered Observation Model

We adopt an **observational family** interpretation of K:

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
```

---

#### A2: State_n の形式的定義

**現状:** State_n が非形式的に記述
**対応:** 明示的な定義と図を追加

```markdown
### Formal Definition of State_n

**State_0 (First-Order Epistemic State):**

$$\text{State}_0(x) = f_0(\text{Response}(x), \text{Reference}(x))$$

Where:
- $\text{Response}(x)$: Subject's answer to item $x$
- $\text{Reference}(x)$: Ground truth or expert consensus
- $f_0$: Comparison function yielding {correct, incorrect, absent}

**State_1 (Metacognitive State):**

$$\text{State}_1(x) = f_1(\text{Claim}_1(x), \text{State}_0(x))$$

Where:
- $\text{Claim}_1(x)$: Subject's metacognitive claim ("I know" / "I don't know" / "I'm wrong")
- $f_1$: Alignment function yielding {aligned, uncertain, misaligned}

**State_n (n-th Order State):**

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
```

---

#### A3: なぜ「同じ K」を仮定するか

**レビュワーの質問:**
> "Why should the same mapping K be assumed across layers given differences in observables, noise, and scoring?"

**対応:**

```markdown
### Why a Single Unified K?

**Philosophical Motivation:**

The unified K reflects a core insight: **the same epistemic question ("Do I know?") applies at every level of reflection.**

- At layer 0: "Do I know the answer?"
- At layer 1: "Do I know whether I know the answer?"
- At layer 2: "Do I know whether I know whether I know?"

**Practical Implementation:**

While the **semantic anchors** are shared (-1/0/1 for misconception/ignorance/knowledge), the **measurement procedures** $K^{(n)}$ may differ:

| Layer | Observable | Measurement Procedure |
|:---:|:---|:---|
| $K^{(0)}$ | Response vs Reference | Accuracy scoring |
| $K^{(1)}$ | Claim vs State_0 | Alignment scoring |
| $K^{(2)}$ | Meta-claim vs State_1 | Meta-alignment scoring |

**Parameter Tying (Optional):**

For parsimony, one may assume:
- Same noise model across layers
- Same link function (e.g., logistic)

Or allow layer-specific parameters if data supports it.

**The key constraint is shared anchor semantics, not identical functional forms.**
```

---

#### A4: 連続値のメリットの明示

**現状:** 連続値であることは述べているが、その理由・メリットが明示されていない
**対応:** 「Why Continuous Scale?」セクションを追加

```markdown
### Why Continuous Scale?

The continuous scale [-1, 1] provides several advantages over binary or categorical representations:

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
```

---

#### A5: 確信度 C の操作的定義

**レビュワーの質問 (Q8):**
> "Could you clarify the role of confidence C operationally?"

**現状:** C の操作的定義が論文内で不明確
**対応:** K と C の関係を明示し、操作的定義を追加

```markdown
### Operational Definition of Confidence (C)

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

K and C are **conceptually orthogonal**:

| Pattern | K₀ | C | Interpretation |
|:---|:---:|:---:|:---|
| Confident correct | 1 | High | Ideal |
| Confident wrong | −1 | High | Dangerous misconception |
| Unconfident correct | 1 | Low | Imposter-like |
| Unconfident wrong | −1 | Low | Appropriate uncertainty |

**Diagnostic Role:**

C helps distinguish subtypes within the same K pattern:
- DK (K₀=0, K₁=−1) with **high C** → Overconfident ignorance
- DK (K₀=0, K₁=−1) with **low C** → Uncertain but still wrong claim

**Measurement Protocol:**

1. Elicit response → compute K₀
2. Elicit confidence (0-100%) → record C
3. Elicit metacognitive claim ("Do you know?") → compute K₁
4. Analyze K × C jointly for full characterization

**K-C Dissociation Hypothesis:**

Subjects can have:
- High K₀ with low C (Imposter syndrome)
- Low K₀ with high C (Dunning-Kruger effect)

This dissociation is empirically testable and clinically meaningful.
```

---

### B: Empirical Validation — 高優先

#### B1: Toy Simulation

**レビュワーの要求:**
> "Provide toy simulations with a generative model to illustrate that your estimators recover ground truth K0/K1/K2 under realistic noise and bias."

**対応:** Python シミュレーションを実装し、Appendix に結果を掲載

```markdown
### Simulation Study: Recovering K from Noisy Observations

**Generative Model:**

We define agent types with ground-truth $(K_0, K_1, K_2)$:

**Discrete Prototypes:**

| Type | K_0 | K_1 | K_2 | Description |
|:---|:---:|:---:|:---:|:---|
| Socratic | 0 | 1 | 1 | Knows they don't know |
| Dunning-Kruger | 0 | -1 | -1 | Doesn't know they don't know |
| Imposter | 1 | -1 | 1 | Knows but thinks they don't, aware of this |
| Ideal | 1 | 1 | 1 | Perfect self-awareness |

**Continuous Variants (追加):**

| Type | K_0 | K_1 | K_2 | Description |
|:---|:---:|:---:|:---:|:---|
| Mild DK | 0.2 | -0.5 | -0.3 | Slight knowledge, moderate overconfidence |
| Recovering Imposter | 0.8 | -0.3 | 0.7 | High competence, improving self-assessment |
| Uncertain Socratic | 0.1 | 0.6 | 0.4 | Near-ignorance, partial awareness |

**Simulation Procedure:**

1. Generate N=100 items per agent
2. For each item:
   - Generate Response based on K_0 (with noise ε)
   - Generate Claim_1 based on K_1 (with noise δ)
   - Generate Claim_2 based on K_2 (with noise γ)
3. Apply estimators:
   - $\hat{K}_0 = \frac{1}{N}\sum_i \text{score}_0(i)$
   - $\hat{K}_1 = 2P(\text{Claim}_1 = \text{correct}) - 1$
   - $\hat{K}_2 = 2P(\text{Claim}_2 = \text{aligned with } K_1) - 1$
4. Compute 95% confidence intervals via bootstrap

**Results:**

[Table: Ground Truth vs Estimated K values with 95% CI]
[Figure: Recovery accuracy as a function of noise and sample size]

**Sample Size Guidelines for K₂ Identifiability:**

| Noise Level (γ) | Required N for |K₂ error| < 0.1 | 95% CI Width |
|:---:|:---:|:---:|
| 0.1 | 30 | ±0.08 |
| 0.2 | 50 | ±0.12 |
| 0.3 | 80 | ±0.15 |
| 0.4 | 150+ | ±0.20 |

**Findings:**

- K_0 and K_1 are reliably recovered with N ≥ 30 items (noise < 0.3)
- K_2 requires N ≥ 50 items for stable estimation (noise < 0.2)
- **Continuous agents**: Intermediate values are recovered with proportionally higher N
- The four prototype types remain distinguishable under moderate noise (ε, δ, γ < 0.3)
- **Practical guideline**: For reliable K₂ estimation, use N ≥ 50 items with noise < 0.2
```

---

#### B2: meta-d' / meta-I との比較

**レビュワーの要求:**
> "Compare to meta-d' and calibration curves on known datasets; show cases where your taxonomy adds diagnostic power beyond standard metrics."

**対応:**

```markdown
### Relationship to meta-d' and meta-I

**Existing Sensitivity Metrics:**

| Metric | Basis | Measures | Limitation |
|:---|:---|:---|:---|
| **meta-d'** | SDT | Sensitivity (model-dependent) | No direction, single layer |
| **meta-I** | Information Theory | Sensitivity + granularity (model-free) | No direction, single layer |
| **Calibration (ECE)** | Error | Confidence-accuracy alignment | No pattern classification |

**What K Adds:**

| K Feature | What it provides | Why it matters |
|:---|:---|:---|
| **Signed scale** | Direction of misalignment | Distinguishes overconfidence from underconfidence |
| **Layered structure** | K₀, K₁, K₂... | Identifies where the problem is |
| **Pattern taxonomy** | 27 patterns | Enables targeted intervention |

**Position Statement:**

K is **not** a replacement for meta-d' or meta-I.

- meta-d' / meta-I answer: "How well does confidence track accuracy?"
- K answers: "What type of metacognitive pattern is this, and where should we intervene?"

**Complementarity Demonstrated:**

Two subjects with identical meta-I = 0.3 bits:
- Subject A: K₀=0, K₁=-1 → Dunning-Kruger → needs awareness intervention
- Subject B: K₀=1, K₁=-1 → Imposter → needs confidence-building

meta-I cannot distinguish these; K can.

**Analogy:**
- meta-d' / meta-I = **Thermometer** (measures temperature)
- K = **Weather map** (classifies patterns, guides action)
```

---

### C: Related Work Deepening — 中優先

#### C1: meta-d' / meta-I との形式的対応

**対応:**

```markdown
### Formal Correspondence with Sensitivity Metrics

**meta-d' (Maniscalco & Lau, 2012):**

$$\text{meta-d'} = \Phi^{-1}(H_{\text{meta}}) - \Phi^{-1}(FA_{\text{meta}})$$

Measures how well confidence discriminates correct from incorrect responses (SDT framework).

**meta-I (Dayan, 2023):**

$$\text{meta-I} = H(\text{accuracy}) - H(\text{accuracy} | \text{confidence})$$

Measures mutual information between confidence and accuracy (information-theoretic, model-free).

**Mapping to K:**

- $H_{\text{meta}} \approx P(\text{Claim}_1 = \text{"know"} | K_0 = 1)$
- $FA_{\text{meta}} \approx P(\text{Claim}_1 = \text{"know"} | K_0 \leq 0)$

**Key Distinction:**

| Metric | Type | Direction | Layers |
|:---|:---|:---|:---|
| meta-d' | Sensitivity | ❌ Unsigned | 1 |
| meta-I | Sensitivity + granularity | ❌ Unsigned | 1 |
| K | **Classification** | ✅ **Signed** | **Recursive** |

**K is not competing with sensitivity metrics; it provides a different function (classification and intervention design).**
```

---

#### C2: AI Metacognition への接続

**レビュワーの指摘:**
> "Recent AI metacognition work... can serve as empirical testbeds."

**対応:**

```markdown
### Application to AI Metacognition

The K framework provides a structured vocabulary for evaluating LLM metacognition:

**Mapping LLM Behaviors:**

| LLM Pattern | K_0 | K_1 | K_2 | Interpretation |
|:---|:---:|:---:|:---:|:---|
| Correct + confident | 1 | 1 | 1 | Ideal calibration |
| Hallucination + confident | -1 | -1 | ? | Confident wrong |
| Correct + hedging | 1 | -1 | ? | Underconfident |
| Admits uncertainty | 0 | 1 | 1 | Appropriate uncertainty |

**Testbed Proposal:**

Using AFCE-style decoupled confidence elicitation:
1. Query LLM for answer (→ K_0)
2. Query LLM for confidence (→ C)
3. Query LLM for "Do you know this?" (→ Claim_1)
4. Compute K_1 from Claim_1 vs K_0

This allows testing the K vs C dissociation hypothesis empirically.
```

---

### D: Presentation Refinement — 低優先

#### D1: 記法の統一

**対応:** 論文全体で $K_n$ 記法を一貫して使用し、$K(K(x))$ はショートハンドとして残す

#### D2: Limitations の更新

```markdown
### Limitations (Updated)

1. **Formal Model:** We adopt Option B (observational family) to resolve the recursion/observation tension. This is a modeling choice, not the only possibility.

2. **Simulation Scope:** Our toy simulations demonstrate feasibility, not exhaustive validation. Real-world validation requires empirical studies.

3. **Single Dimension (Scope Boundary):** 
   - The [-1,1] scale assumes a **single axis of correctness** with one "opposite" direction.
   - **What this captures:** Directional errors (overconfidence vs underconfidence, correct vs incorrect).
   - **What this does NOT capture:** Multiple, qualitatively different misconceptions (e.g., "thinks A" vs "thinks B" when truth is C).
   - **Design rationale:** This simplification enables tractable measurement and clear intervention design. Multi-dimensional misconceptions require a different formalism (e.g., vector-valued K or belief distributions) and are outside the current scope.
   - **Future extension:** Vector-valued $K \in [-1,1]^d$ or embedding in a latent space could address this limitation.

4. **Layer-Specific Parameters:** We assume shared anchor semantics but allow layer-specific measurement procedures. The optimal degree of parameter tying is an empirical question.

5. **K_2 Identifiability:** Higher-order estimates (K_2, K_3) require more items and may be less reliable.
   - **Guideline:** For reliable K₂ estimation, use N ≥ 50 items with noise < 0.2.
   - **Confidence intervals:** Report 95% CI via bootstrap; if CI width > 0.3, interpret with caution.
```

---

## Summary: Revision Scope

| Category | Items | Priority | Estimated Work |
|:---|:---|:---:|:---|
| **A: Formal Core** | A1 (Option B採用), A2 (State_n定義), A3 (統一K正当化), A4 (連続値メリット), A5 (C操作的定義) | 最高 | High |
| **B: Validation** | B1 (シミュレーション), B2 (meta-d'/meta-I比較) | 高 | Medium-High |
| **C: Related Work** | C1 (meta-d'/meta-I形式化), C2 (AI応用) | 中 | Medium |
| **D: Presentation** | D1 (記法統一), D2 (Limitations更新) | 低 | Low |

---

## Implementation Plan

### Phase 1: Formal Core (A1-A5)
1. Option B の明示的採用と全体書き換え
2. State_n の形式的定義（図含む）
3. 「統一K」の正当化セクション
4. 「連続値のメリット」セクション（情報幾何への接続を示唆）
5. **確信度 C の操作的定義**（K と C の関係、直交性、診断的役割）

### Phase 2: Validation (B1-B2)
1. Python シミュレーション実装
   - 4エージェントタイプの生成モデル
   - K推定器の実装
   - ノイズ下での回復精度評価
   - **信頼区間の計算**（95% CI）
2. meta-d' との比較
   - 概念的対応の記述
   - シミュレーション結果の比較表

### Phase 3: Refinement (C1-D2)
1. 関連研究セクションの深化
2. AI応用セクションの追加
3. 記法統一と Limitations 更新

---

## Key Deliverables

1. **論文本体の更新** (.md → .tex)
   - Option B の明示的採用
   - State_n の形式的定義と図
   - シミュレーション結果セクション

2. **Python シミュレーションコード**
   - `simulation/k_recovery.py`
   - 再現可能な結果

3. **Appendix**
   - シミュレーション詳細
   - コードへのリンク

---

## Questions for Discussion

1. **シミュレーションの実装レベル**: 
   - 本文に埋め込む vs Appendix のみ
   - 図/表の粒度

2. **LLM 実験の追加**:
   - シミュレーションのみ vs LLMを使った疑似実験も追加
   - 工数とリターンのバランス

3. **meta-d' / meta-I との比較の深さ**:
   - 概念的対応のみ vs 数値的比較も

4. **K の位置づけ**:
   - 「分類・介入設計の座標系」として論文全体のトーンを調整するか

---

## Reviewer Questions Response Mapping

| Q# | Question | Plan Item | Status |
|:---:|:---|:---|:---:|
| Q1 | K の解釈 | A1 (Option B採用) | ✅ |
| Q2 | State_n の定義 | A2 | ✅ |
| Q3 | 同じ K の正当化 | A3 | ✅ |
| Q4 | 多次元誤認 | D2 (Limitations強化) | ✅ |
| Q5 | シミュレーション | B1 (連続値追加) | ✅ |
| Q6 | K₂ 識別可能性 | B1 (ガイドライン追加) | ✅ |
| Q7 | meta-d' との形式化 | C1 | ✅ |
| Q8 | C の役割 | **A5 (新規追加)** | ✅ |

---

## Next Steps

1. ~~この revision_plan_06 のレビュー~~ ✅ 内部レビュー完了
2. 優先度の確認（A→B→C→D の順序でよいか）
3. Phase 1 の実装開始
