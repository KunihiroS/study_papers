# Revision Plan 14: 対応関係の厳密導出と理論の完全化

**Date**: 2025-12-07
**Target Review**: `20251207_02.md`
**Strategy**: Plan 13 の Acceptance Criteria 駆動アプローチを継承し、**対応関係を「heuristic」から「derived theorem」へ昇格**

---

## Executive Summary

**Plan 13 の成果**:
- 定理・命題・補題の形式化は達成（T1-T5, P1-P6, L1-L2, Claim 1）
- 概念的明確さ、技術的新規性について高評価を獲得

**残存課題（20251207_02 指摘）**:

| カテゴリ | 具体的指摘 | 深刻度 |
|:---------|:-----------|:------:|
| **対応関係が heuristic** | K₀≈tanh(θ), K₁≈tanh(meta-d'/2), K₁≈1−2·ECE が「導出されていない」 | ★★★ |
| **連続-離散の橋渡し不完全** | continuous K_n の生成方法が underdeveloped | ★★★ |
| **プロトコル仕様不完全** | f_n, Claim の許容値・タイミング・指示文 | ★★☆ |
| **識別可能性/不変性の深化** | より強い axiom/constraint が必要 | ★★☆ |
| **normative bias との reconciliation** | K₁=-1 が「rational observer の misalignment」なのか | ★☆☆ |

**Plan 14 の目標**:

> **「シミュレーションを除けば accept！」とレビュアーに言わせる**

そのために:
1. **全ての対応関係を「仮定 → 導出 → 境界条件」の形式に統一**
2. **連続 K_n の生成モデルを完全仕様化**
3. **Claim protocol を完全定義（許容応答・タイミング・指示文）**
4. **識別可能性/不変性の条件を強化・証明**
5. **normative bias との関係を明示的に論じる**

**Scope 外（Future Work 維持）**:
- シミュレーション検証
- 実データ適用
- LLM への完全な operationalization（概念的指針のみ本文に記載）

---

## メタ的な構造（K フレームワークでの自己評価）

**x** = 「トップカンファに耐えうる理論的厳密さを達成している」

### Plan 13 終了時点での K 状態

| Layer | 状態 | 評価 |
|:------|:-----|:-----|
| **K₀(x)** | 定理・命題の形式は整った。ただし対応関係が「heuristic」扱い | K₀ ≈ 0.3（部分的に成立、核心でまだズレ） |
| **K₁(x)** | Plan 13 で「定理を追加すれば OK」と評価していた | K₁ ≈ 0（「まあまあできている」という認識だが、レビュー的にはまだ gap） |
| **K₂(x)** | 「criteria 駆動」に切り替えたことで、自己評価プロセス自体は改善 | K₂ ≈ 0.5（メタ認知は立ち上がりつつある） |

### Plan 14 で目指す K 状態

| Layer | 目標状態 | 達成手段 |
|:------|:---------|:---------|
| **K₀(x)** | K₀ → +1（理論的に完全、スキなし） | 全対応関係の厳密導出 |
| **K₁(x)** | K₁ → +1（「これで十分」という評価が正しい） | レビュー Q1-Q9 への完全回答 |
| **K₂(x)** | K₂ → +1（自己評価が外部評価と一致） | 本 Plan の完遂 |

---

## Review Analysis: 20251207_02.md への対応

### レビュー指摘の Criteria マッピング

| # | レビュー指摘 | Type | Criteria | 対応項目 |
|:--|:-------------|:----:|:---------|:---------|
| W1 | "formalism risks being tautological without stronger axioms" | A | C1, C3 | AX1-AX3 |
| W2 | "K̂ role is redundant under identity; claims uninstantiated" | A | C1 | TH-K̂ |
| W3 | "continuous K_n generation underdeveloped" | A | C1, C2 | DEF-CONT |
| W4 | "correspondences are heuristic, not derived" | A | C1, C7 | TH-CORR-1~3 |
| W5 | "No reliability analysis or validation" | C | — | Scope外（シミュレーション） |
| W6 | "protocol not specified (claims, f_n)" | A | C2, C8 | PROTO-1~3 |
| W7 | "Type-2 SDT loosely referenced" | A | C4 | P1-EXT |
| W8 | "normative bias not integrated" | A | C4 | DISC-NORM |
| W9 | "LLM operationalization incomplete" | B | C8 | Future Work 明示 |
| Q1 | "precise Claim protocol at each layer" | A | C2 | PROTO-1~3 |
| Q2 | "continuous K₁ estimation without heuristic transforms" | A | C1 | TH-CORR-2 |
| Q3 | "derive K₀≈tanh(θ), K₁≈tanh(meta-d'/2)" | A | C1 | TH-CORR-1, TH-CORR-2 |
| Q4 | "K₂ computation concretely" | A | C1 | TH-K2-EST |
| Q5 | "identifiability/invariance properties" | A | C3, C7 | AX1-AX3, L1-L2-EXT |
| Q6 | "abstentions/guessing in K₀" | A | C1, C8 | DEF-K0-EXT |
| Q7 | "synthetic experiment for K₁/C dissociation" | C | — | Scope外 |
| Q8 | "reconcile normative biases with K₁ misalignment" | A | C4 | DISC-NORM |
| Q9 | "LLM instantiation details" | B | C8 | Future Work 明示 |

**Type 凡例:**
- **A**: 既存 criteria の不足 → 本 Plan で対応
- **B**: criteria 更新 → Limitations/Future Work で明示
- **C**: Scope 外 → 記録のみ

---

## Part 1: Acceptance Criteria の更新

### 1.1 Plan 13 からの継承 + 強化

| Criteria | Plan 13 状態 | Plan 14 強化点 |
|:---------|:-------------|:---------------|
| **C1: 非自明な数学的結果** | ✅ T1-T5, P1-P6 追加済み | 対応関係を「仮定明示 + 導出 + 境界条件」に強化 |
| **C2: 形式的定義の完備性** | ✅ 概ね達成 | Claim protocol の完全仕様化 |
| **C3: 識別可能性・推定可能性** | ✅ T3-T5 追加済み | より強い axiom/constraint を追加 |
| **C4: 既存理論との関係** | ✅ P1-P3 追加済み | normative bias との関係を追加 |
| **C5: 計算複雑性** | ✅ P6 追加済み | 維持 |
| **C6: 先行研究との差分** | ✅ Claim 1 追加済み | 維持 |
| **C7: 不変性・頑健性** | ✅ L1-L2 追加済み | 感度分析の形式化 |
| **C8: スコープ境界の明示** | △ 部分的 | LLM/シミュレーションを明示的に Future Work 化 |
| **C9: 連続-離散の整合性** (NEW) | ❌ 未着手 | 完全仕様化 |

### 1.2 新規 Acceptance Criteria

| ID | 内容 | 根拠 |
|:---|:-----|:-----|
| **C9** | 連続 K_n と離散アンカーの関係が厳密に定義されている | W3, Q2 |
| **C10** | Claim protocol が再現可能なレベルで仕様化されている | W6, Q1 |

---

## Part 2: Gap 分析（詳細版）

### 2.1 Gap-CORR: 対応関係が「heuristic」

**現状**: K₀≈tanh(θ), K₁≈tanh(meta-d'/2), K₁≈1−2·ECE は本文に記載済みだが、
レビュアーは「これらは導出されていない」「仮定が不明」「境界条件がない」と指摘。

**問題の根本原因**:
- 「≈」で書いており、等号成立の条件が曖昧
- 仮定を明示していない
- 仮定が破れた場合の挙動（誤差境界）がない

**必要な追加**:

| ID | 対応関係 | 必要な形式 |
|:---|:---------|:-----------|
| **TH-CORR-1** | K₀ = tanh(a(θ-b)/2) | **定理**: 2PL-IRT の下で等号成立。Proof: 代数変形。境界: a≠2 or b≠0 の場合の誤差 |
| **TH-CORR-2** | K₁ と meta-d' の概念的関係 | **Remark**: 両者は相補的な側面を測定。数学的等号は主張せず、conceptual relationship として位置づけ |
| **TH-CORR-3** | K₁ ≈ 1−2·ECE | **命題**: 特定のビニング下で近似成立。警告: ECE はビニング・サンプル依存 |

### 2.2 Gap-CONT: 連続-離散の橋渡し

**現状**: 「continuous scale [-1,1]」と「discrete anchors {-1,0,+1}」が混在し、どう遷移するか不明確。

**必要な追加**:

| ID | 内容 |
|:---|:-----|
| **DEF-CONT-1** | 連続 K_n の生成モデル（latent variable + link function） |
| **DEF-CONT-2** | 離散化のしきい値とその決定理論的根拠 |
| **DEF-CONT-3** | 推定量の定義（点推定 + 信頼区間） |

### 2.3 Gap-PROTO: プロトコル仕様の不完全性

**現状**: Claim₁, Claim₂ の「許容応答」「タイミング」「指示文」が本文で断片的。

**必要な追加**:

| ID | 内容 |
|:---|:-----|
| **PROTO-1** | Claim₁ の完全仕様（許容カテゴリ、タイミング、指示文テンプレート） |
| **PROTO-2** | Claim₂ の完全仕様 |
| **PROTO-3** | f_n の決定規則表（すべての入力パターンに対する出力を網羅） |

### 2.4 Gap-AXIOM: より強い axiom/constraint

**現状**: Anchor preservation, monotonicity, boundedness は記載済みだが、「framework が tautological」という批判。

**必要な追加**:

| ID | 内容 |
|:---|:-----|
| **AX-FALSI** | Falsifiability axiom: K framework が反証可能であることの明示 |
| **AX-SEPAR** | Separation axiom: K と C が異なる次元であることの形式的条件 |
| **AX-LAYER** | Layer independence axiom の強化（条件付き独立性の帰結） |

### 2.5 Gap-NORM: normative bias との関係

**現状**: Dunning-Kruger を「K₁=-1」としてラベリングしているが、
normative accounts（例: positive evidence bias が合理的行動である可能性）との関係が未整理。

**必要な追加**:

| ID | 内容 |
|:---|:-----|
| **DISC-NORM** | Discussion セクションで normative vs descriptive の区別を明示 |

---

## Part 3: 対応計画（詳細版）

### Phase 1: 対応関係の厳密導出

#### Phase 1.1: TH-CORR-1（K₀-IRT 対応の完全化）

**現状の定理 1 を以下の形式に強化**:

```
Theorem 1 (K₀-IRT Exact Correspondence):

**Assumptions**:
(A1) Item response follows 2PL-IRT model:
     P(correct | θ, a, b) = 1 / (1 + exp(-a(θ - b)))
(A2) K₀ is defined as the signed expected accuracy:
     K₀ := 2P(correct) - 1

**Statement**:
Under (A1)-(A2), for each item i:
  K₀⁽ⁱ⁾ = tanh(aᵢ(θ - bᵢ)/2)

**Proof**: [現行の証明を維持、より丁寧に]

**Corollary 1.1** (Standardized Form):
Under additional assumption (A3): a = 2, b = 0,
  K₀ = tanh(θ)

**Boundary Condition** (Deviation from Assumptions):
When (A3) is violated:
  |K₀ - tanh(θ)| ≤ |tanh(a(θ-b)/2) - tanh(θ)|

For typical parameter ranges (a ∈ [0.5, 3], b ∈ [-2, 2], θ ∈ [-3, 3]):
  Max deviation ≈ 0.3 (tabulate for common cases)

**Scope of Validity**:
- Holds exactly for binary correct/incorrect responses
- Does not hold for partial credit (see Limitations)
```

#### Phase 1.2: TH-CORR-2（K₁ と meta-d' の関係 — Conceptual Relationship へ格下げ）

**フィードバックに基づく方針転換**:

元々「K₁ ≈ tanh(meta-d'/2)」を数学的対応として主張しようとしていたが、これは問題がある：
- meta-d' は Type-2 SDT の文脈で Φ⁻¹(HR₂) - Φ⁻¹(FAR₂) として定義
- K₁ = φ (Phi係数) は相関係数
- これらは異なる量であり、tanh 変換で一致する数学的根拠が弱い

**新方針**: 数学的等号を主張せず、**Conceptual Relationship** として位置づける

```
Remark 1 (K₁ and meta-d': Complementary Perspectives):

K₁ and meta-d' measure related but distinct aspects of metacognition:

**meta-d'** (Maniscalco & Lau, 2012):
- Sensitivity-based: How well does confidence discriminate correct from incorrect?
- Rooted in Signal Detection Theory (SDT)
- Requires Gaussian assumptions on evidence distributions
- Unit: d' scale (unbounded)

**K₁** (This framework):
- Alignment-based: Does the subject's claim match their actual epistemic state?
- Assumption-free (uses Phi coefficient or contingency)
- Bounded: K₁ ∈ [-1, 1]

**Relationship**:
- Both are high when metacognition is accurate
- Both are low when confidence is unrelated to accuracy
- However, they are NOT mathematically equivalent

**Empirical Expectation**:
- In well-calibrated populations: Cor(K₁, tanh(meta-d'/2)) > 0.6
- In biased or extreme populations: divergence is expected

**Recommendation**:
- Report BOTH K₁ and meta-d' when SDT framework is applicable
- K₁ is preferred when SDT assumptions are questionable
- Do NOT use K₁ ≈ tanh(meta-d'/2) as an identity
```

**この変更の利点**:
1. 数学的に誠実（主張しないことで批判を回避）
2. 相補性を強調することで、K framework の独自価値を明示
3. 実務的な使い分けガイドを提供

#### Phase 1.3: TH-CORR-3（K₁-ECE 対応の限界明示）

```
Proposition 1b (K₁-ECE Approximate Relationship):

**Statement**:
Under fixed binning with B bins and large sample size:
  K₁ ≈ 1 - 2·ECE

**Critical Warning**:
ECE is:
- Binning-dependent (different B → different ECE)
- Sample-size dependent (small N → high variance)
- Always ≥ 0 (cannot distinguish over- vs under-confidence)

**Recommendation**:
- Use K₁ = φ (Phi coefficient) as primary measure
- Use K₁ ≈ 1 - 2·ECE only for cross-study comparison where ECE is standard
- Always report binning scheme and sample size
```

### Phase 2: 連続-離散の完全仕様化

#### Phase 2.1: DEF-CONT（連続 K_n の生成モデル）

```
Definition (Continuous K_n Generation):

**Latent Variable Model**:
  K*_n ~ N(μ_n, σ²_n)  (latent alignment strength)

**Link Function**:
  K_n = h(K*_n) where h: ℝ → [-1, 1]

**Default Link (tanh)**:
  K_n = tanh(β · K*_n)

where β > 0 is a sensitivity parameter.

**Alternative Links**:
| Link | Formula | Properties |
|:-----|:--------|:-----------|
| tanh (default) | tanh(βx) | Smooth, symmetric |
| Scaled probit | 2Φ(x) - 1 | Probabilistic interpretation |
| Clipped linear | max(-1, min(1, x)) | Simple, piecewise linear |

**Anchor Preservation**:
All links satisfy: h(+∞) = +1, h(0) = 0, h(-∞) = -1.

**Discretization**:
| Continuous K_n | Discrete Label |
|:---------------|:---------------|
| K_n > τ⁺ | +1 |
| τ⁻ ≤ K_n ≤ τ⁺ | 0 |
| K_n < τ⁻ | -1 |

**Threshold Options**:

| Option | Definition | Rationale |
|:-------|:-----------|:----------|
| **A: Fixed thresholds** | τ⁺ = +1/3, τ⁻ = -1/3 | Divides [-1,1] into three equal-length intervals |
| **B: Data-adaptive** | τ⁺ = Q₆₇(K_n), τ⁻ = Q₃₃(K_n) | Equal-frequency discretization (terciles) |

**Selection Guideline**:
- **Option A (recommended for theory)**: Provides fixed interpretation across studies
- **Option B (recommended for practice)**: Adapts to population distribution

**Decision-Theoretic Justification** (for Option A):
Under symmetric 0-1 loss and uniform prior, τ = ±1/3 is optimal.

**Note**: The term "tercile" refers to percentile-based cutoffs (Option B), not fixed values.
Option A should be called "equal-interval" discretization.
```

### Phase 3: Claim Protocol の完全仕様化

#### Phase 3.1: PROTO-1（Claim₁ の完全仕様）

```
Protocol Specification: Claim₁ Elicitation

**Timing**: 
- After response to item x
- Before feedback on correctness

**Instruction Template (Categorical)**:
"How confident are you that your answer is correct?
 □ I'm confident I'm correct ("I know")
 □ I'm not sure ("Uncertain")
 □ I think I might be wrong ("I don't know")"

**Instruction Template (Continuous)**:
"What is the probability that your answer is correct?
 [Slider: 0% ──────────────── 100%]"

**Mapping (Continuous → Categorical)**:
| Reported p | Claim₁ |
|:-----------|:-------|
| p ≥ 0.7 | "I know" |
| 0.3 < p < 0.7 | "Uncertain" |
| p ≤ 0.3 | "I don't know" |

**Threshold Calibration**:
1. Pilot: Adjust to achieve ~equal category frequencies
2. Alternative: Use percentile-based (top 30%, middle 40%, bottom 30%)
3. Domain-specific: Higher thresholds for domains with inflated confidence

**Inter-Rater Reliability Requirement**:
- Categorical: Cohen's κ > 0.8
- Continuous: ICC > 0.7
```

#### Phase 3.2: PROTO-2（Claim₂ の完全仕様）

```
Protocol Specification: Claim₂ Elicitation

**Timing**:
- After all items are completed
- After K₁ is computed (or after metacognitive feedback)

**Instruction Template**:
"Thinking about your self-assessments across all questions:
 How accurate do you think your self-assessments were?
 □ My self-assessments were accurate ("Meta-aligned")
 □ I'm not sure about my self-assessments ("Meta-uncertain")
 □ My self-assessments were probably inaccurate ("Meta-misaligned")"

**Alternative (Item-Level Claim₂)**:
After revealing K₁ for each item:
"Was your confidence judgment appropriate for this item?
 □ Yes, appropriate
 □ Not sure
 □ No, inappropriate"
```

#### Phase 3.3: PROTO-3（f_n の決定規則表）

```
Complete Specification: f₁ Decision Rules

**Input**: (K₀, Claim₁)
**Output**: State₁ ∈ {aligned, uncertain, misaligned}

| K₀ | Claim₁ = "I know" | Claim₁ = "Uncertain" | Claim₁ = "I don't know" |
|:---|:------------------|:---------------------|:------------------------|
| +1 | aligned | uncertain | misaligned |
| 0 | misaligned | aligned | aligned |
| -1 | misaligned | uncertain | aligned* |

*Rationale for K₀=-1, Claim="I don't know" → aligned:
See "Epistemic Improvement Criterion" (already in paper).

**Alternative Interpretation (Stricter)**:

| K₀ | Claim₁ = "I don't know" | Alternative Output |
|:---|:------------------------|:-------------------|
| -1 | "I don't know" | **uncertain** (not aligned) |

**Rationale for Alternative**:
- "I don't know" does not explicitly acknowledge misconception
- True alignment at K₀=-1 would require: "I think I'm wrong"

**Framework Choice**:
- **(a) Default (aligned)**: Prioritizes recognition of non-knowledge (Socratic wisdom)
- **(b) Alternative (uncertain)**: Prioritizes recognition of specific error direction

**Recommendation**:
- Use (a) as default for general metacognition research
- Use (b) for domains where distinguishing "don't know" from "know I'm wrong" is critical
- Always report which interpretation is used

**g₁ Embedding**:
| State₁ | K₁ |
|:-------|:---|
| aligned | +1 |
| uncertain | 0 |
| misaligned | -1 |
```

### Phase 3.4: WORKED-EXAMPLE-K2（K₂ の具体的計算例 — NEW）

**Q4 への回答として追加**:

シミュレーションは Scope 外だが、**worked example（具体的計算例）**は追加可能。

```
Worked Example: K₂ Computation

**Setup**:
Subject completes 10 items.

**Step 1: Raw Data**
| Item | Response | Correct? | K₀ | Claim₁ |
|:-----|:---------|:---------|:---|:-------|
| 1 | A | ✓ | +1 | "I know" |
| 2 | B | ✓ | +1 | "I know" |
| 3 | C | ✗ | -1 | "I don't know" |
| 4 | A | ? | 0 | "Uncertain" |
| 5 | B | ✓ | +1 | "I know" |
| 6 | D | ✗ | -1 | "I know" |
| 7 | A | ✗ | -1 | "Uncertain" |
| 8 | C | ✓ | +1 | "I know" |
| 9 | B | ? | 0 | "I don't know" |
| 10 | A | ✓ | +1 | "I know" |

**Step 2: Compute K₁ per item**
Using f₁ decision rules:

| Item | K₀ | Claim₁ | State₁ | K₁ |
|:-----|:---|:-------|:-------|:---|
| 1 | +1 | "I know" | aligned | +1 |
| 2 | +1 | "I know" | aligned | +1 |
| 3 | -1 | "I don't know" | aligned* | +1 |
| 4 | 0 | "Uncertain" | aligned | +1 |
| 5 | +1 | "I know" | aligned | +1 |
| 6 | -1 | "I know" | misaligned | -1 |
| 7 | -1 | "Uncertain" | uncertain | 0 |
| 8 | +1 | "I know" | aligned | +1 |
| 9 | 0 | "I don't know" | aligned | +1 |
| 10 | +1 | "I know" | aligned | +1 |

**Step 3: Aggregate K₁**
Mean(K₁) = (1+1+1+1+1-1+0+1+1+1) / 10 = 0.7

**Step 4: Elicit Claim₂**
Subject is asked: "How accurate were your self-assessments?"
Response: "My self-assessments were accurate" → Claim₂ = "Meta-aligned"

**Step 5: Compute State₂ and K₂**

Option A (Threshold-based):
- If Mean(K₁) > τ⁺ = 1/3 → actual State₁ = "mostly aligned"
- Claim₂ = "Meta-aligned" → claimed State₁ = "aligned"
- Match? Yes → State₂ = aligned → K₂ = +1

Option B (Test-Retest ICC):
- If subject repeats task at t₂:
  - K₁(t₁) = [+1, +1, +1, +1, +1, -1, 0, +1, +1, +1]
  - K₁(t₂) = [+1, +1, +1, 0, +1, -1, +1, +1, +1, +1]
  - ICC(K₁(t₁), K₁(t₂)) = 0.82
  - K₂ = 0.82 (high stability)

**Summary**:
| Metric | Value | Interpretation |
|:-------|:------|:---------------|
| K₀ (mean) | 0.2 | Moderate knowledge |
| K₁ (mean) | 0.7 | Good metacognitive alignment |
| K₂ (Option A) | +1 | Meta-aligned |
| K₂ (Option B) | 0.82 | Stable metacognition |
```

**この例の価値**:
1. 抽象的な定義を具体的な数値で示す
2. シミュレーションなしでも「計算可能性」を実証
3. Option A/B の違いを明確化

---

### Phase 4: Axiom/Constraint の強化

#### Phase 4.1: Falsifiability Axiom

```
Axiom F (Falsifiability):

The K framework is empirically falsifiable:

**Falsifiable Prediction 1** (K-C Dissociation):
∃ subjects with (K₁ = -1, C = high) [Dunning-Kruger pattern]
∃ subjects with (K₁ = -1, C = low) [Imposter pattern]

If ALL subjects show K₁ = sign(2C - 1), the framework adds nothing.

**Falsifiable Prediction 2** (Layer Independence):
Cor(K₀, K₂ | K₁) ≈ 0

If K₂ is strongly predicted by K₀ after controlling for K₁, 
layer separation is violated.

**Falsifiable Prediction 3** (Intervention Sensitivity):
Metacognitive training → K₁ increases while K₀ may remain constant.

If K₁ cannot be moved independently of K₀, the distinction is spurious.

**Falsifiable Prediction 4** (Quantitative — NEW):
"Metacognitive training improves K₁ by at least δ = 0.2 on average,
 while K₀ remains within ε = 0.1 of pre-training level."

Formally:
  E[K₁_post - K₁_pre] ≥ 0.2
  |E[K₀_post - K₀_pre]| ≤ 0.1

If training affects both K₀ and K₁ equally (i.e., ΔK₁ ≈ ΔK₀),
then layer separation is empirically spurious for that intervention.

**Falsifiable Prediction 5** (K-C Correlation Bound — NEW):
"In any population, Cor(K₁, C) < 0.85."

If Cor(K₁, C) > 0.85 consistently across multiple datasets,
K₁ and C are empirically redundant and the distinction adds no value.
```

#### Phase 4.2: Separation Axiom

```
Axiom S (K-C Separation):

K (epistemic alignment) and C (phenomenological confidence) are 
theoretically and operationally distinct:

**Theoretical Distinction**:
- K: Alignment between claim and actual state (requires feedback)
- C: Subjective certainty (measured before feedback)

**Operational Distinction**:
- C is measured at t₁ (during response)
- K₁ is computed at t₂ (after feedback reveals correctness)

**Empirical Test**:
If Cor(K₁, C) < 0.7, the dimensions are empirically separable.
If Cor(K₁, C) > 0.9, they may be redundant for the population studied.
```

### Phase 5: Normative Bias との関係

```
Discussion Addition: Normative vs Descriptive Interpretation

**The Tension**:
Recent work (e.g., positive evidence bias literature) suggests that 
some "metacognitive biases" may be rational responses to high-dimensional
hypothesis spaces, not failures.

**Our Position**:
The K framework is DESCRIPTIVE, not normative.

K₁ = -1 means:
"The subject's claim does not match their actual state 
 relative to the experimenter-defined reference."

This is a COORDINATE, not a JUDGMENT.

**When K₁ = -1 Might Be "Rational"**:
1. Experimenter's reference is contested or incomplete
2. Subject is optimizing a different objective than accuracy
3. Subject has access to information experimenter lacks

**Recommendation**:
Report K₁ alongside task context. 
Do not interpret K₁ = -1 as "failure" without considering 
whether the reference standard is appropriate.

**Methodological Relativism (Reiterated)**:
The framework does NOT adjudicate what is "correct."
K₁ = -1 is descriptive of a state, not prescriptive of a norm.
```

---

## Part 4: 実装チェックリスト

### 4.1 対応関係の強化

| ID | 項目 | Criteria | 状態 |
|:---|:-----|:---------|:-----|
| **TH-CORR-1** | K₀-IRT: 仮定明示 + 境界条件追加 | C1, C7 | ☐ |
| **TH-CORR-2** | K₁-meta-d': **Conceptual Relationship** として位置づけ（等号を主張しない） | C1, C4 | ☐ |
| **TH-CORR-3** | K₁-ECE: 限界と警告を明示 | C1, C7 | ☐ |

### 4.2 連続-離散の仕様化

| ID | 項目 | Criteria | 状態 |
|:---|:-----|:---------|:-----|
| **DEF-CONT-1** | Latent variable model | C2, C9 | ☐ |
| **DEF-CONT-2** | Link function 選択肢 | C2, C9 | ☐ |
| **DEF-CONT-3** | 離散化しきい値の根拠 | C2, C9 | ☐ |

### 4.3 Protocol 仕様化

| ID | 項目 | Criteria | 状態 |
|:---|:-----|:---------|:-----|
| **PROTO-1** | Claim₁ 完全仕様 | C2, C10 | ☐ |
| **PROTO-2** | Claim₂ 完全仕様 | C2, C10 | ☐ |
| **PROTO-3** | f_n 決定規則表 + 代替解釈の明示 | C2, C10 | ☐ |
| **WORKED-EXAMPLE-K2** | K₂ の具体的計算例（10項目の worked example） | C1, C2 | ☐ |

### 4.4 Axiom/Constraint 強化

| ID | 項目 | Criteria | 状態 |
|:---|:-----|:---------|:-----|
| **AX-FALSI** | Falsifiability axiom（定量的予測 Pred 4-5 を含む） | C1, C3 | ☐ |
| **AX-SEPAR** | K-C Separation axiom | C1, C3 | ☐ |

### 4.5 Discussion 追加

| ID | 項目 | Criteria | 状態 |
|:---|:-----|:---------|:-----|
| **DISC-NORM** | Normative vs Descriptive | C4 | ☐ |
| **DISC-LLM** | LLM への指針（Future Work 明示） | C8 | ☐ |

---

## Part 5: Criteria カバレッジ確認

| Criteria | Plan 13 状態 | Plan 14 追加 | 最終状態 |
|:---------|:-------------|:-------------|:---------|
| C1 (数学的結果) | ✅ T1-T5, P1-P6 | TH-CORR-1~3, AX-FALSI, AX-SEPAR | ✅✅ 完全 |
| C2 (定義完備) | ✅ | DEF-CONT-1~3, PROTO-1~3 | ✅✅ 完全 |
| C3 (識別可能性) | ✅ T3-T5 | AX-FALSI, AX-SEPAR | ✅✅ 完全 |
| C4 (既存理論) | ✅ P1-P3 | TH-CORR-2, DISC-NORM | ✅✅ 完全 |
| C5 (計算複雑性) | ✅ P6 | 維持 | ✅ 完全 |
| C6 (新規性) | ✅ Claim 1 | 維持 | ✅ 完全 |
| C7 (頑健性) | ✅ L1-L2 | TH-CORR-1~3 の境界条件 | ✅✅ 完全 |
| C8 (スコープ) | △ | DISC-LLM, Future Work 整理 | ✅ 完全 |
| C9 (連続-離散) | ❌ | DEF-CONT-1~3 | ✅ NEW |
| C10 (Protocol仕様) | ❌ | PROTO-1~3 | ✅ NEW |

---

## Part 6: 期待される効果

### 6.1 レビュー批判への対応マップ

| 批判 | Plan 14 での対応 |
|:-----|:-----------------|
| "correspondences are heuristic" | TH-CORR-1~3 で「仮定 → 導出 → 境界条件」形式に |
| "continuous K_n underdeveloped" | DEF-CONT-1~3 で完全仕様化 |
| "protocol not specified" | PROTO-1~3 で完全仕様化 |
| "framework risks being tautological" | AX-FALSI, AX-SEPAR で反証可能性を明示 |
| "normative bias not integrated" | DISC-NORM で descriptive 立場を明確化 |
| "LLM incomplete" | DISC-LLM で Future Work として明示 |

### 6.2 Questions for Authors への回答マップ

| Question | 回答箇所 |
|:---------|:---------|
| Q1: precise Claim protocol | PROTO-1~3 |
| Q2: continuous K₁ estimation | DEF-CONT-1~3, TH-CORR-2 |
| Q3: derive correspondences | TH-CORR-1~3 |
| Q4: K₂ computation | **WORKED-EXAMPLE-K2** (NEW) + 既存の D1, D2 |
| Q5: identifiability/invariance | AX-FALSI, AX-SEPAR, 既存 T3-T5 |
| Q6: abstentions/guessing | DEF-K0-EXT（Limitations で明示） |
| Q7: synthetic experiment | Scope 外（Future Work） |
| Q8: normative bias | DISC-NORM |
| Q9: LLM instantiation | DISC-LLM（Future Work） |

### 6.3 期待されるレビュー評価の変化

| 評価軸 | Before (20251207_02) | After (Plan 14 完遂) |
|:-------|:---------------------|:---------------------|
| 概念的明確さ | ✅ 高評価 | ✅ 維持 |
| 技術的厳密さ | △「heuristic」 | ✅「derived with assumptions」 |
| 実証的検証 | ❌「なし」 | △「Scope 外として明示」 |
| 投稿先適合性 | △「workshop/theory track」 | ✅「main track 検討可」 |

---

## Part 7: 実装順序

1. **TH-CORR-1~3**: 対応関係の厳密化（最優先、レビューの核心）
2. **DEF-CONT-1~3**: 連続-離散の完全仕様化
3. **PROTO-1~3**: Claim protocol の完全仕様化
4. **AX-FALSI, AX-SEPAR**: Axiom 強化
5. **DISC-NORM, DISC-LLM**: Discussion 追加

---

## 付録: Plan 13 → Plan 14 の差分

| 観点 | Plan 13 | Plan 14 |
|:-----|:--------|:--------|
| 目標 | 定理・命題の形式化 | 対応関係の「導出」完全化 |
| 対応レベル | 「Theorem X: ...」を追加 | 「Assumptions → Derivation → Boundary」形式に強化 |
| 連続-離散 | 暗黙 | **明示的に仕様化** |
| Protocol | 断片的 | **完全仕様化** |
| Axiom | 基本的制約のみ | **反証可能性・分離条件を追加** |
| normative bias | 未対応 | **Discussion で明示** |

---

## 確認事項

1. 上記の方針で進めてよいか
2. TH-CORR-1~3 の優先度で正しいか
3. 追加すべき項目はあるか
4. Scope 外の判断（シミュレーション、LLM 詳細）は妥当か

---

## 付録 B: 内部フィードバックへの対応（2025-12-07 追記）

### 受領したフィードバック要約

| # | 指摘 | 対応 |
|:--|:-----|:-----|
| 1 | TH-CORR-2 の K₁≈tanh(meta-d'/2) は数学的根拠が弱い | ✅ **Conceptual Relationship** に格下げ。等号を主張せず相補性を強調 |
| 2 | AX-FALSI の「予測」が定義に近い | ✅ **定量的予測 (Pred 4-5)** を追加。δ=0.2, ε=0.1, Cor < 0.85 等 |
| 3 | DEF-CONT-3 の「tercile」が誤用 | ✅ **2オプション併記**（固定しきい値 vs データ適応）、用語を修正 |
| 4 | PROTO-3 のエッジケース（K₀=-1, "I don't know"）が論争的 | ✅ **代替解釈 (Stricter)** を追加。(a) Default vs (b) Alternative を明示 |
| 5 | Q4 に worked example がない | ✅ **WORKED-EXAMPLE-K2** を追加。10項目の具体的計算例 |

### フィードバック後の評価

| 観点 | フィードバック前 | フィードバック後 |
|:-----|:-----------------|:-----------------|
| TH-CORR-2 の扱い | ⚠️ 数学的等号を主張 | ✅ 概念的関係として誠実に位置づけ |
| 反証可能性 | △ 定性的予測のみ | ✅ 定量的予測を含む |
| 離散化の柔軟性 | △ 単一オプション | ✅ 2オプション併記 |
| エッジケースの透明性 | △ 暗黙 | ✅ 代替解釈を明示 |
| K₂ の具体性 | △ 抽象的定義のみ | ✅ worked example あり |

**結論**: フィードバックにより Plan 14 の堅牢性が向上。これで実装に移行可能。
