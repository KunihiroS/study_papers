# Revision Plan 11: Response to 20251206_01.md Review

**Date**: 2025-12-06
**Target Review**: `20251206_01.md`
**Strategy**: 数学的導出の厳密化 + 推定器の具体化 + コーディング決定の正当化

---

## Executive Summary

レビュアーはフレームワークの概念的価値を認めた上で、以下の技術的詰めを要求：

1. **数学的導出**: $K_0 \approx \tanh(\theta)$ 等のマッピングを導出・正当化
2. **連続値の生成方法**: アンカー間の中間値をどう計算するか
3. **コーディング決定の正当化**: $K_0 = -1$ で "I don't know" が aligned となる理由
4. **推定器の具体化**: $K_1$, $K_2$ の具体的推定方法

**Scope外（Future Work維持）**:
- シミュレーション検証
- Toy dataset実装

---

## 過去の失敗からの教訓（中期的改善事項）

> **Note**: この表は他論文執筆時にも参照可能な汎用Tipsとして設計

### ステータス凡例

| Status | 意味 |
|:-------|:-----|
| ✅ CLOSED | 対策完了・検証済み |
| 🔧 PENDING | 対策中・本Plan内で対応予定 |
| ⚠️ OPEN | 未対応・今後の課題 |

### 具体的失敗と対策

| Status | 過去の問題 | 発生Plan | 具体例 | 対策 |
|:-------|:-----------|:---------|:-------|:-----|
| ✅ CLOSED | **不必要な重複** | Plan 1-9 | Analogy、Framework Provides等の重複 | Plan 10で削除済み |
| ✅ CLOSED | **番号付けの不整合** | Plan 10 | Limitationsの番号ズレ (5,4,5→5,6,7) | Plan 10で修正済み |
| ✅ CLOSED | **重要な表・定義の後方配置** | Plan 1-9 | 27パターン表等が後方に | Plan 10でExecutive Summary追加 |
| 🔧 PENDING | **マッピングの「主張のみ」** | Plan 1-10 | $\tanh(\theta)$等を導出なしに記載 | 本Plan Phase 1.2で対応 |
| 🔧 PENDING | **コーディング決定の根拠不足** | Plan 1-10 | monotonicity理由のみ | 本Plan Phase 2.1で対応 |

### 汎用化した教訓（他論文向けTips）

| カテゴリ | 失敗パターン | 予防策 | チェックタイミング |
|:---------|:-------------|:-------|:-------------------|
| **構造** | 同じ概念の複数箇所での説明 | 追加前に `grep` で既存記述を検索 | 各セクション追加時 |
| **構造** | リスト・番号の不整合 | 挿入後に全体の番号を通し確認 | 編集完了時 |
| **可読性** | 重要な定義・表が後方に埋没 | Executive Summary / Early Previewを冒頭に配置 | 初稿完成時 |
| **厳密性** | 数学的主張の導出不在 | 「なぜ」を1段階深く記述（仮定→導出→結論） | 数式追加時 |
| **厳密性** | 設計決定の根拠不足 | Design Rationale / Justificationセクションを設ける | 設計決定時 |
| **整合性** | 用語の表記揺れ | 用語表（Glossary）を維持・参照 | 全体レビュー時 |
| **参照** | 参考文献の不完全性 | 引用時に即座にBibTeX追加 | 引用追加時 |
| **形式** | LaTeX変換時のUnicode問題 | 特殊文字を事前にLaTeXコマンドに置換 | 変換前 |

### 自己チェックリスト（論文完成前）

```
□ 重複記述がないか（grep検索）
□ 番号・リストが連続しているか
□ 重要な表・定義が早期に登場するか
□ 数学的主張に導出があるか
□ 設計決定に根拠があるか
□ 用語の表記が統一されているか
□ 参考文献が完備しているか
□ LaTeX変換でエラーが出ないか
```

---

## Review Analysis: Questions for Authors への対応

### Q1: 連続 $K_n$ 値の計算方法

> "How do you propose to compute continuous K_n values between the anchors in practice?"

**現状**: Latent Variable Modelで言及あるが、具体的な計算式不足

**対応**: Phase 1.1

---

### Q2: $K_0 \approx \tanh(\theta)$ の導出

> "Can you derive the K0 ≈ tanh(θ) mapping precisely from a 2PL/3PL IRT model?"

**現状**: 主張のみ、導出なし

**対応**: Phase 1.2

---

### Q3: "I don't know" + $K_0 = -1$ → aligned のコーディング

> "Why is 'I don't know' with K0 = −1 coded as fully 'aligned' at K1?"

**現状**: monotonicity理由のみ、不十分

**対応**: Phase 2.1

---

### Q4: $K_2$ の推定方法

> "How should K2 be estimated: test–retest stability, higher-order calibration, or structural model?"

**現状**: 概念的説明のみ、具体的推定器なし

**対応**: Phase 1.3

---

### Q5: Claim$_1$, Claim$_2$ の引き出しプロトコル

> "What is the empirical protocol for eliciting Claim_1 and Claim_2?"

**現状**: 表形式の例示のみ、プロトコル不足

**対応**: Phase 2.2

---

### Q6: Polytomous scoring / Partial credit

> "How would you handle polytomous scoring or partial credit at K0?"

**現状**: Limitations内でScope Boundaryとして言及

**対応**: Phase 2.3（拡張可能性の明示）

---

### Q7: Toy dataset / Worked example

> "Could you add a toy dataset and end-to-end worked example?"

**対応**: **Scope外** - シミュレーション/実証フェーズで対応

---

## Phase 1: 数学的導出の追加

### Phase 1.1: 連続 $K_n$ 値の計算（Proper Scoring Rule ベース）

**Location**: Measurement Theory セクション内

**Content**:
```markdown
### Continuous K Values via Proper Scoring Rules

For discrete elicitation mapped to continuous $K_n$, we define principled estimators based on strictly proper scoring rules.

#### $K_0$ Continuous Estimation

**Option A: Brier-Based Embedding**

Given a response $r$ and reference $t$, with confidence $c \in [0, 1]$:

$$K_0 = \begin{cases}
2c - 1 & \text{if } r = t \text{ (correct)} \\
0 & \text{if } r = \text{abstain} \\
-(2c - 1) & \text{if } r \neq t \text{ (incorrect)}
\end{cases}$$

This maps high-confidence correct to $K_0 \to +1$, high-confidence incorrect to $K_0 \to -1$, and low-confidence or abstention to $K_0 \to 0$.

**Option B: Proper Score Centering**

Using Brier score $B = (c - \mathbb{1}[\text{correct}])^2$:

$$K_0 = 1 - 2B$$

This yields $K_0 = +1$ for perfect calibration on correct, $K_0 = -1$ for perfect miscalibration.

#### $K_1$ Continuous Estimation

**Meta-d' Based**:

$$K_1 = \tanh\left(\frac{\text{meta-d}'}{2}\right)$$

Where meta-d' is the signal-detection sensitivity for type-2 decisions (discriminating correct from incorrect responses).

**Alignment Score Based**:

For item $i$ with actual $K_0^{(i)}$ and claimed state $\tilde{K}_0^{(i)}$:

$$K_1 = \frac{1}{N} \sum_{i=1}^{N} \mathbb{1}[K_0^{(i)} \cdot \tilde{K}_0^{(i)} > 0] \cdot 2 - 1$$

This yields $K_1 = +1$ for perfect alignment, $K_1 = -1$ for systematic misalignment.

#### Properties

| Property | $K_0$ (Brier) | $K_1$ (meta-d') |
|:---------|:--------------|:----------------|
| **Anchor Preservation** | $K_0 \in \{-1, 0, +1\}$ at extremes | $K_1 \in \{-1, 0, +1\}$ at extremes |
| **Monotonicity** | Increases with accuracy × confidence | Increases with metacognitive sensitivity |
| **Properness** | Derived from strictly proper Brier | meta-d' is bias-free under SDT assumptions |
```

---

### Phase 1.2: $K_0 \approx \tanh(\theta)$ の厳密導出

**Location**: Measurement Theory セクション内、IRT対応の後

**Content**:
```markdown
### Formal Derivation: K_0 from IRT

#### 2-Parameter Logistic Model

Under the 2PL IRT model, the probability of correct response is:

$$P(\text{correct} | \theta, a, b) = \frac{1}{1 + e^{-a(\theta - b)}}$$

Where:
- $\theta$: Latent ability
- $a$: Discrimination parameter
- $b$: Difficulty parameter

#### Mapping to K_0

**Step 1**: Convert probability to $[-1, 1]$ scale:

$$K_0^* = 2P - 1 = \frac{1 - e^{-a(\theta - b)}}{1 + e^{-a(\theta - b)}}$$

**Step 2**: Recognize hyperbolic tangent identity:

$$\tanh(x) = \frac{e^{2x} - 1}{e^{2x} + 1} = \frac{1 - e^{-2x}}{1 + e^{-2x}}$$

**Step 3**: Match exponents:

$$K_0^* = \tanh\left(\frac{a(\theta - b)}{2}\right)$$

#### Standardization Assumption

For the simplified form $K_0 \approx \tanh(\theta)$, we assume:
- $a = 2$ (unit discrimination)
- $b = 0$ (centered difficulty)

**Full Form**:
$$K_0 = \tanh\left(\frac{a(\theta - b)}{2}\right)$$

**Simplified Form** (under standardization):
$$K_0 \approx \tanh(\theta)$$

#### Dependency Note

This mapping is **item-parameter dependent**:
- High $a$ (discriminating items) → sharper transition
- High $b$ (difficult items) → shift toward lower $K_0$

For aggregate $K_0$ across items with varying $(a_i, b_i)$, use:

$$\bar{K}_0 = \frac{1}{N} \sum_{i=1}^{N} \tanh\left(\frac{a_i(\theta - b_i)}{2}\right)$$

Or estimate $\theta$ via standard IRT procedures and apply the mapping post-hoc.
```

---

### Phase 1.3: $K_2$ 推定器の具体化

**Location**: Measurement Theory セクション内

**Content**:
```markdown
### K_2 Estimation: Candidate Methods

$K_2$ measures meta-metacognitive alignment: does the subject accurately assess their own metacognitive accuracy ($K_1$)?

#### Method A: Test-Retest Stability

$$K_2^{(\text{stability})} = \text{Cor}(K_1^{(t_1)}, K_1^{(t_2)})$$

Where $K_1$ is measured at two time points. High stability ($K_2 \to +1$) indicates consistent metacognitive self-assessment.

**Interpretation**: This operationalizes $K_2$ as **reliability of $K_1$** rather than accuracy.

#### Method B: Higher-Order Claim Alignment

$$K_2^{(\text{claim})} = \mathbb{1}[\text{Claim}_2 \text{ matches actual } K_1] \cdot 2 - 1$$

Where Claim$_2$ is the subject's belief about their own metacognitive accuracy.

**Implementation**:
1. Compute $K_1$ from (Response, Claim$_1$, Reference)
2. Elicit Claim$_2$: "Is your self-assessment accurate?"
3. Compare Claim$_2$ to actual $K_1$

#### Method C: Hierarchical Bayesian Reliability

Model $K_1^{(i)}$ as noisy observations of a latent true $K_1^*$:

$$K_1^{(i)} | K_1^* \sim \mathcal{N}(K_1^*, \sigma^2)$$

Then:
$$K_2 = 1 - \frac{\text{Var}(K_1^{(i)} | K_1^*)}{\text{Var}(K_1^{(i)})} = \frac{\text{Var}(K_1^*)}{\text{Var}(K_1^{(i)})}$$

This is the **reliability coefficient** (analogous to Cronbach's α).

#### Recommended Default

For practical use, we recommend **Method B** (claim-based) for direct operationalization, with **Method A** (stability) as a validation check.

| Method | Measures | Requires |
|:-------|:---------|:---------|
| A (Stability) | Reliability of $K_1$ | Repeated measurement |
| B (Claim) | Accuracy of meta-metacognition | Explicit Claim$_2$ |
| C (Bayesian) | Signal-to-noise ratio | Multiple items |
```

---

## Phase 2: コーディング決定の正当化

### Phase 2.1: "I don't know" + Misconception → Aligned の正当化

**Location**: State$_1$ 表の後

**Content**:
```markdown
### Rationale: Coding "I don't know" with Misconception as Aligned

**The Contested Case**:

| $K_0$ | Claim$_1$ | Current Coding | Question |
|:------|:----------|:---------------|:---------|
| $-1$ (misconception) | "I don't know" | aligned ($K_1 = +1$) | Why not partial? |

**Justification: Epistemic Improvement Criterion**

We adopt the **epistemic improvement criterion**: a claim is "aligned" if it represents the best available response given the subject's actual state.

**Argument**:

1. A subject with $K_0 = -1$ (misconception) who claims "I know" would be **doubly wrong**: wrong about the content AND wrong about their epistemic state.

2. A subject with $K_0 = -1$ who claims "I don't know" is **partially correct**: wrong about the content but aware of their uncertainty.

3. This awareness ($K_1 = +1$) is **epistemically valuable**: it opens the door to correction.

**Formal Criterion**:

$$K_1 = \begin{cases}
+1 & \text{if Claim}_1 \text{ is the } \textbf{best response} \text{ given } K_0 \\
0 & \text{if Claim}_1 \text{ is } \textbf{uncertain} \\
-1 & \text{if Claim}_1 \text{ is the } \textbf{worst response} \text{ given } K_0
\end{cases}$$

**"Best response" for each $K_0$**:

| $K_0$ | Best Claim$_1$ | Reasoning |
|:------|:---------------|:----------|
| $+1$ | "I know" | Accurate confidence |
| $0$ | "I don't know" | Accurate ignorance |
| $-1$ | "I don't know" | Protective epistemic humility |

**Alternative: Graded Alignment (Out of Scope)**

A graded scheme could assign:
- $K_0 = -1$, Claim = "I don't know" → $K_1 = 0.5$ (partial alignment)
- $K_0 = -1$, Claim = "I know" → $K_1 = -1$ (full misalignment)

This is a valid design choice but complicates anchor semantics. We leave graded alignment for future extension.

**Monotonicity Preservation**:

The current coding preserves the ordering:

$$\text{"I know" when wrong} \prec \text{"I don't know" when wrong} \prec \text{"I don't know" when ignorant} \prec \text{"I know" when right}$$

This is monotonic in epistemic quality.
```

---

### Phase 2.2: Claim 引き出しプロトコルの明示

**Location**: Measurement Theory セクション内、MAT Protocol 付近

**Content**:
```markdown
### Claim Elicitation Protocol

#### Standard Protocol (Categorical)

**Claim$_1$ Elicitation**:

After each response, present:

> "How confident are you in your answer?"
> - [ ] I'm confident I'm correct
> - [ ] I'm not sure
> - [ ] I think I might be wrong

**Claim$_2$ Elicitation**:

After completing all items, present:

> "How accurate do you think your self-assessments were overall?"
> - [ ] My self-assessments were accurate
> - [ ] I'm not sure about my self-assessments
> - [ ] My self-assessments were probably inaccurate

#### Continuous Protocol (Slider)

**Claim$_1$ Elicitation**:

> "How confident are you?" (slider: 0-100)

**Threshold Mapping**:

| Slider Value | Claim$_1$ |
|:-------------|:----------|
| $c \geq 70$ | "I know" |
| $30 < c < 70$ | "Not sure" |
| $c \leq 30$ | "I don't know" |

**Threshold Calibration**:

Thresholds should be validated via:
1. **Pilot calibration**: Adjust thresholds to achieve approximately equal category frequencies
2. **Cross-participant comparison**: Use percentile-based thresholds (e.g., top 30%, middle 40%, bottom 30%)
3. **Domain-specific adjustment**: Higher thresholds for domains with inflated confidence

#### Inter-Rater Reliability

For categorical claims:
- Expected Cohen's $\kappa > 0.8$ for Claim$_1$ coding
- Any ambiguous responses should be coded by 2+ raters

For continuous claims:
- Report ICC (Intraclass Correlation) for slider reliability
- Expected ICC $> 0.7$ for adequate reliability
```

---

### Phase 2.3: Polytomous Scoring 拡張可能性

**Location**: Limitations セクション内、Scope Boundary の後

**Content**:
```markdown
### Extension Path: Polytomous and Partial Credit Scoring

**Current Limitation**: $K_0 \in \{-1, 0, +1\}$ collapses nuanced correctness.

**Extension via Graded Response Model (GRM)**:

For polytomous outcomes (e.g., 0, 1, 2, 3 partial credit):

$$P(Y \geq k | \theta) = \frac{1}{1 + e^{-a(\theta - b_k)}}$$

**Mapping to $K_0$**:

$$K_0^{(\text{graded})} = \frac{2Y - Y_{\max}}{Y_{\max}}$$

Where $Y$ is the observed score and $Y_{\max}$ is the maximum.

**Impact on Higher Layers**:

Graded $K_0$ propagates to $K_1$:
- "I'm 80% confident" matches $K_0 = 0.6$ → partial alignment
- "I'm 80% confident" matches $K_0 = -0.2$ → partial misalignment

**Implementation Status**: Conceptually compatible; formal development deferred to future work.

**When to Use**:

| Scenario | Recommended Approach |
|:---------|:--------------------|
| Factual Q&A (binary) | Trichotomous $K_0$ |
| Essay grading (rubric) | Graded $K_0$ |
| Programming (test cases) | Proportion-based $K_0$ |
| Multiple-choice with partial credit | GRM-based $K_0$ |
```

---

## Phase 3: Related Work 統合強化

### Phase 3.1: Type-2 SDT との厳密な対応

**Location**: Related Work、meta-d' セクション

**Content**:
```markdown
### Formal Correspondence with Type-2 SDT

#### meta-d' Definition

In Type-2 SDT (Maniscalco & Lau, 2012), meta-d' is the d' that would produce the observed Type-2 ROC if the observer had optimal metacognitive access to their Type-1 evidence.

#### Mapping to K Framework

**$K_1$ as Normalized meta-d'**:

$$K_1 = \tanh\left(\frac{\text{meta-d}'}{2}\right)$$

**Derivation**:

1. meta-d' $\in (-\infty, +\infty)$, with 0 = chance, positive = above-chance sensitivity
2. $\tanh$ maps $(-\infty, +\infty) \to (-1, +1)$ monotonically
3. The factor of 2 ensures that meta-d' $= 2$ (good sensitivity) maps to $K_1 \approx 0.76$

**M-Ratio Alternative**:

$$K_1 = \text{M-ratio} - 1 = \frac{\text{meta-d}'}{d'} - 1$$

Where M-ratio = 1 indicates ideal metacognitive efficiency.

**Comparison Table**:

| SDT Quantity | $K$ Framework | Relationship |
|:-------------|:--------------|:-------------|
| d' (Type-1) | Related to $K_0$ | $d' \approx 2 \cdot \text{arctanh}(K_0)$ |
| meta-d' | Related to $K_1$ | $K_1 \approx \tanh(\text{meta-d}'/2)$ |
| M-ratio | Metacognitive efficiency | $K_1 \approx \text{M-ratio} - 1$ (if $d' = 2$) |
| Type-2 AUROC | Discrimination accuracy | $K_1 \approx 2 \cdot \text{AUROC} - 1$ |

**Note**: These are approximate correspondences valid under specific assumptions (symmetric criteria, Gaussian noise). Exact relationships depend on model parameters.
```

---

### Phase 3.2: Monitor-Generate-Verify との対応

**Location**: Related Work、AI Metacognition 付近

**Content**:
```markdown
### Correspondence with Monitor–Generate–Verify Architectures

Recent LLM metacognition research (cf. arXiv:2511.04341) formalizes recursive self-monitoring via Monitor–Generate–Verify (MGV) loops.

**Mapping to $K$ Framework**:

| MGV Component | $K$ Layer | Correspondence |
|:--------------|:----------|:---------------|
| Generate | $K_0$ | First-order response quality |
| Monitor | $K_1$ | Self-assessment of response |
| Verify | $K_2$ | Meta-assessment of monitoring accuracy |

**Iteration Dynamics**:

In MGV, the loop:
1. Generate response → observe $K_0$
2. Monitor quality → compute $K_1$
3. Verify monitoring → compute $K_2$
4. If $K_2 < \tau$, regenerate

**$K$ Framework as Stopping Criterion**:

$$\text{Accept output iff } K_1 \geq \tau_1 \text{ AND } K_2 \geq \tau_2$$

This formalizes the intuition that LLMs should only output when they are confident ($K_1$) and that confidence is justified ($K_2$).

**Complementarity**:

- MGV provides **process** (how to iterate)
- $K$ provides **coordinates** (where the system is in metacognitive space)
```

---

## Implementation Order

```
Phase 1.1 (Continuous K via Proper Scoring)
    ↓
Phase 1.2 (K0 ≈ tanh(θ) Derivation)
    ↓
Phase 1.3 (K2 Estimation Methods)
    ↓
Phase 2.1 ("I don't know" + Misconception Rationale)
    ↓
Phase 2.2 (Claim Elicitation Protocol)
    ↓
Phase 2.3 (Polytomous Extension Path)
    ↓
Phase 3.1 (Type-2 SDT Formal Correspondence)
    ↓
Phase 3.2 (MGV Architecture Mapping)
```

---

## Questions for Authors への回答マッピング

| Question | Response Location |
|:---------|:------------------|
| Q1: Continuous $K_n$ | Phase 1.1 |
| Q2: $K_0 \approx \tanh(\theta)$ derivation | Phase 1.2 |
| Q3: "I don't know" coding rationale | Phase 2.1 |
| Q4: $K_2$ estimation | Phase 1.3 |
| Q5: Claim elicitation protocol | Phase 2.2 |
| Q6: Polytomous scoring | Phase 2.3 |
| Q7: Toy dataset | **Scope外** (Future Work) |

---

## Scope外（Future Work として明示維持）

| 項目 | 理由 |
|:-----|:-----|
| シミュレーション検証 | 堅牢な理論構築完了後に実施 |
| Toy dataset | 同上 |
| 完全なGRM統合 | 概念的互換性は示す、詳細実装は延期 |
| Multi-agent DEL拡張 | 単一エージェント理論が先 |

---

## Expected Outcome

この revision により：

1. **数学的厳密化**: $K_0$, $K_1$ のマッピングが導出付きで正当化
2. **推定器の具体化**: $K_2$ の3つの候補メソッドを明示
3. **コーディング正当化**: "Epistemic Improvement Criterion" による根拠
4. **プロトコル明示**: Claim引き出しの具体的手順

**予想されるレビュー改善**:
- "asserted but not derived" → 解消
- "how intermediate values are produced" → 解消
- "contestable coding decision" → 正当化により緩和
- "no estimation method for K2" → 解消
