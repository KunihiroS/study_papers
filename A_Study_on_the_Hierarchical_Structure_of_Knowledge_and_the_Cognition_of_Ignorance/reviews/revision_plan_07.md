# Revision Plan 07: Response to 20251204 Review

**Version**: 07.1 (Internal Reviewer Feedback Integrated)

## Executive Summary

本プランは 20251204_01.md レビューへの**体系的かつ強固な反論**を提供する。
レビュワーの指摘は正当だが、多くは**既存手法のプラグイン採用**と**形式的明確化**で解決可能。
本論文の独自貢献（座標系設計）は維持しつつ、測定モデルの具体性を大幅に強化する。

### 内部レビュワー評価への対応

内部レビュワー評価: **A-**（優秀）

| 指摘 | 対応状況 |
|:---|:---|
| tanh変換の根拠が薄い | ✅ 複数有界化関数の比較表 + 感度分析推奨 |
| ±0.33閾値の根拠が不十分 | ✅ 4つの根拠 + 代替閾値表 |
| Phi係数と3値の整合性 | ✅ 3つの2値化戦略を明示 |
| シミュレーションの欠如 | 🔜 最終段階で実施（他項目完了後） |

### 目標状態

> 「シミュレーションさえあれば、机上の空論を脱して実証論文になる」
> — 期待される Stanford レビュワーコメント

---

## Review Diagnosis

### レビュワーの主要批判（優先度順）

| # | 批判 | 深刻度 | 対応可能性 |
|:---:|:---|:---:|:---:|
| 1 | **型システムの不一致**: K^(n): S_n → [-1,1] vs K: [-1,1] → [-1,1] | 高 | ✅ 埋め込み写像で解決 |
| 2 | **単調性公理の順序未定義**: S_n 上の ">" が未定義 | 高 | ✅ 埋め込み後の順序で定義 |
| 3 | **State₀マッピング不整合**: incorrect を ignorance(0) と扱う例 | 中 | ✅ マッピング表の修正 |
| 4 | **測定モデル欠如**: K 推定の具体的手法がない | 高 | ✅ 既存手法プラグイン |
| 5 | **信頼性・妥当性なし**: test-retest, convergent validity 等 | 中 | ⚠️ ロードマップ提示 |
| 6 | **連続値と27パターンの関係**: 閾値・決定ルールなし | 中 | ✅ 閾値ルール追加 |
| 7 | **記法過多**: K, K^(n), K_n の混在 | 低 | ✅ 統合的定義セクション |

### レビュワーが認めた強み

> "The separation between epistemic state (K) and phenomenological confidence (C) is clearly articulated"

> "The proposed taxonomy (K₀ × K₁ × K₂) gives a compact vocabulary to discuss archetypal metacognitive patterns"

> "This is a thoughtful and ambitious conceptual paper"

**評価**: レビュワーは概念的貢献を認めており、批判は**実装詳細**に集中している。

---

## Strategic Response

### Core Principle: 座標系 vs 推定エンジンの分離

```
本論文の貢献:  「何を測るか」の定義（座標系）
既存研究の貢献: 「どう推定するか」の手法（エンジン）
```

**戦略**: 推定エンジンは既存手法を**プラグイン**として採用し、座標系設計という独自貢献を維持。

---

## Revision Items

### A: Formal Unification（形式的統一）

#### A1: 埋め込み写像 g_n の明示的定義

**問題**: K^(n): S_n → [-1,1] と K: [-1,1] → [-1,1] の共存が矛盾

**解決**: 埋め込み写像を明示し、観察スコアラーを統一

```markdown
### Unified Formalization

**Definition (Embedding Maps):**

Each layer has an embedding map $g_n$ that converts categorical states to the continuous scale:

$$g_n: \mathcal{S}_n \to [-1, 1]$$

Where:
- $g_0: \{\text{correct}, \text{incorrect}, \text{absent}\} \to \{1, -1, 0\}$
- $g_1: \{\text{aligned}, \text{misaligned}, \text{uncertain}\} \to \{1, -1, 0\}$
- $g_n: \{\text{aligned}, \text{misaligned}, \text{uncertain}\} \to \{1, -1, 0\}$ for $n \geq 1$

**Definition (Unified Observation Scorer):**

After embedding, a single scorer $\hat{K}$ operates on the embedded space:

$$\hat{K}: [-1, 1] \to [-1, 1]$$

With the identity mapping for prototypical anchors: $\hat{K}(1) = 1$, $\hat{K}(0) = 0$, $\hat{K}(-1) = -1$.

**Composition:**

$$K_n(x) = \hat{K}(g_n(\text{State}_n(x)))$$

**Notational Convention:**

- $K_n$: The full pipeline (embedding + scoring) for layer $n$
- $K^{(n)}$: Shorthand for the same, emphasizing layer-specificity
- $K(K(x))$: Informal shorthand for $K_1(x)$, **not** numerical composition

This resolves the type ambiguity: $K$ is **not** applied to its own numerical output,
but to the embedded representation of a distinct state object.
```

**レビュワー質問への直接回答**:
> "How do you reconcile the two type treatments of K?"

→ 埋め込み写像 $g_n$ を導入し、$K_n = \hat{K} \circ g_n$ と定義。これにより型システムが統一される。

---

#### A2: 単調性公理の再定義

**問題**: S_n 上の順序 ">" が未定義

**解決**: 埋め込み後の実数順序で定義

```markdown
### Monotonicity (Revised)

**Definition (Order on Embedded States):**

For embedded values $k, k' \in [-1, 1]$, the natural order $k > k'$ applies.

**Monotonicity Axiom:**

For any scoring function $\hat{K}$:

$$\text{If } g_n(\text{State}_n) > g_n(\text{State}'_n), \text{ then } K_n \geq K'_n$$

This is trivially satisfied when $\hat{K}$ is the identity on anchors and monotonic elsewhere.

**Practical Interpretation:**

Monotonicity ensures that "more aligned" states receive higher K values.
This does not constrain the shape of $\hat{K}$ beyond anchor preservation.
```

**レビュワー質問への直接回答**:
> "What partial order on S_n justifies the monotonicity axiom?"

→ 埋め込み後の実数順序 $[-1, 1]$ を使用。S_n 自体には順序は不要。

---

#### A3: State₀ マッピングの明確化

**問題**: incorrect が ignorance(0) と扱われる例がある

**解決**: マッピング表を明確化し、例を修正

```markdown
### State₀ Canonical Mapping

| f₀ Output | $g_0$ Value | Interpretation |
|:---|:---:|:---|
| correct | 1 | Response matches reference |
| incorrect | **-1** | Response contradicts reference |
| absent | 0 | No response / "I don't know" |

**Clarification:**

"Ignorance" in the sense of $K_0 = 0$ means **absence of determinate stance**,
not "being wrong." A wrong answer is a **misconception** ($K_0 = -1$), not ignorance.

**Example Correction:**

Previous: "Subject answers incorrectly → ignorance (K₀ = 0)"
Corrected: "Subject answers incorrectly → misconception (K₀ = -1)"
           "Subject abstains / says 'I don't know' → ignorance (K₀ = 0)"
```

**レビュワー質問への直接回答**:
> "What is the precise mapping from State0 outcomes?"

→ correct → 1, incorrect → -1, absent → 0 と明示。

---

### B: Measurement Model（測定モデル）

#### B1: 既存手法のプラグイン採用

**問題**: K 推定の具体的手法がない

**解決**: 既存の堅牢な手法を「推定エンジン」として採用

```markdown
### Estimation Methods for K Values

The K framework specifies **what to measure**; for **how to estimate**,
we adopt established psychometric and signal-detection methods as "plug-in" engines.

#### K₀ Estimation (First-Order Epistemic State)

**Method**: Item Response Theory (2-Parameter Logistic Model)

$$P(\text{correct} | \theta_s, a_i, b_i) = \frac{1}{1 + e^{-a_i(\theta_s - b_i)}}$$

**Mapping to K₀**:

$$K_0 = 2 \cdot \Phi(\theta_s) - 1$$

Where $\Phi$ is the standard normal CDF, ensuring $K_0 \in [-1, 1]$.

**Misconception Detection**:
- High confidence + incorrect → $K_0 = -1$
- Operationalized via Confidence-Accuracy calibration error

#### K₁ Estimation (Metacognitive Alignment)

**Method A**: Phi Coefficient

$$\phi = \frac{n_{11} n_{00} - n_{10} n_{01}}{\sqrt{(n_{11}+n_{10})(n_{01}+n_{00})(n_{11}+n_{01})(n_{10}+n_{00})}}$$

**Handling 3-Value State₀**:

State₀ has three outcomes {correct, incorrect, absent}. For Phi (2×2), we binarize:

| Binarization Strategy | Positive ($K_0 > 0$) | Negative ($K_0 \leq 0$) |
|:---|:---|:---|
| **Strategy A (Strict)** | correct only | incorrect + absent |
| **Strategy B (Lenient)** | correct + absent | incorrect only |
| **Strategy C (Exclude)** | correct | incorrect (exclude absent) |

**Recommended**: Strategy A (Strict) — aligns with the interpretation that
"I know" should predict correctness, not just absence of misconception.

**Cell Definitions (Strategy A)**:
- $n_{11}$: correct + "I know"
- $n_{00}$: (incorrect OR absent) + "I don't know"
- $n_{10}$: correct + "I don't know"
- $n_{01}$: (incorrect OR absent) + "I know"

**Mapping**: $K_1 = \phi$ (already in [-1, 1])

**Interpretation**:
- $\phi = 1$: Perfect metacognitive alignment
- $\phi = 0$: No relationship (random)
- $\phi = -1$: Perfect anti-alignment (systematic miscalibration)

**Method B**: meta-d' Ratio (Signal Detection Theory)

$$K_1 = f\left(\frac{\text{meta-d}'}{d'}\right)$$

Where:
- meta-d' = metacognitive sensitivity (Maniscalco & Lau, 2012)
- d' = first-order sensitivity
- $f$: bounding function to ensure output in [-1, 1]

**Bounding Function Options**:

| Function | Formula | Properties |
|:---|:---|:---|
| **tanh** | $\tanh(r)$ | Smooth, symmetric, saturates at ±1 |
| **Scaled CDF** | $2\Phi(r) - 1$ | Probabilistic interpretation |
| **Clipped linear** | $\max(-1, \min(1, r))$ | Simple, preserves scale near 0 |

**Rationale for tanh (default)**:
- Smooth monotonic transformation
- Natural saturation at extreme values
- Widely used in neural network literature
- **Alternative-agnostic**: Results qualitatively similar across choices

**Sensitivity Analysis Recommendation**:
Report results with at least two bounding functions to confirm robustness.

**Choice Guidance**:
- Use Phi for simplicity and interpretability (no bounding needed)
- Use meta-d'/d' for SDT-compatible analyses (with explicit bounding function)

#### K₂ Estimation (Higher-Order Alignment)

**Method**: Hierarchical Bayesian GLM (cf. HiBayES, Fleming & Daw, 2017)

$$\text{Claim}_2 | \text{State}_1 \sim \text{Bernoulli}(\sigma(\alpha_s + \beta_i + \gamma_{s,i}))$$

**Advantages**:
- Stable estimation with N ≥ 20 items
- Provides 95% credible intervals
- Decomposes subject and item effects

**Mapping**:

$$K_2 = 2 \cdot P(\text{Claim}_2 \text{ matches } \text{State}_1) - 1$$

Estimated from posterior predictive distribution.

#### Summary Table

| Layer | Observable | Method | Output |
|:---:|:---|:---|:---:|
| $K_0$ | Response vs Reference | IRT (2PL) | [-1, 1] |
| $K_1$ | Claim₁ vs State₀ | Phi / meta-d'/d' | [-1, 1] |
| $K_2$ | Claim₂ vs State₁ | Hierarchical Bayes | [-1, 1] |
| $C$ | Self-reported confidence | Direct elicitation | [0, 1] |
```

**レビュワー質問への直接回答**:
> "Can you specify a minimal generative or measurement model?"

→ IRT, Phi係数, meta-d', 階層ベイズを層ごとに指定。HiBayES との互換性を明示。

---

#### B2: 連続値と27パターンの関係

**問題**: 連続値からカテゴリへの変換ルールがない

**解決**: 閾値ルールを明示

```markdown
### Continuous-to-Categorical Mapping

The 27-pattern taxonomy uses prototypical anchors {-1, 0, 1}.
For continuous K values, we define thresholds:

| Continuous Range | Categorical Label |
|:---:|:---:|
| $K \in [-1, -0.33)$ | -1 (Misconception/Misaligned) |
| $K \in [-0.33, 0.33]$ | 0 (Ignorance/Uncertain) |
| $K \in (0.33, 1]$ | 1 (Knowledge/Aligned) |

**Rationale for ±0.33 Default**:

1. **Symmetric Tercile**: Divides [-1, 1] into three equal-width regions
2. **Neutral Zone**: The central region captures "uncertain/indeterminate" states
3. **Statistical Interpretation**: Under uniform prior, each category has equal probability
4. **Robustness**: Not sensitive to small estimation errors near boundaries

**Alternative Thresholds**:

| Approach | Thresholds | Use Case |
|:---|:---|:---|
| **Tercile (default)** | ±0.33 | Balanced classification |
| **Quartile** | ±0.5 | Stricter knowledge/misconception criteria |
| **ROC-optimized** | Data-driven | Maximize classification accuracy |
| **Domain-specific** | Expert-defined | Match substantive theory |

**Recommendation**:
- Use ±0.33 as default for comparability across studies
- Report sensitivity analysis with alternative thresholds
- For intervention design, consider ROC-optimized thresholds

**Reporting Recommendation**:
- Report continuous K values for statistical analysis
- Use categorical labels for interpretation and intervention design
- Always include confidence intervals from estimation

**Example**:

$$K_0 = 0.7, K_1 = -0.5, K_2 = 0.2$$

Categorical: $K_0 = 1, K_1 = -1, K_2 = 0$ → "Knowing Misconception, uncertain about meta"

This enables both fine-grained analysis and interpretable classification.
```

**レビュワー質問への直接回答**:
> "How do continuous values translate into categories?"

→ 閾値 ±0.33 で三分割。ドメイン調整可能。

---

### C: Validity Roadmap（妥当性ロードマップ）

#### C1: 信頼性・妥当性の検証計画

**問題**: 信頼性・妥当性の議論がない

**解決**: 具体的な検証計画を提示（実施は将来論文）

```markdown
### Validation Roadmap

This paper establishes the **conceptual framework**; validation is planned for follow-up work.

#### Phase 1: Reliability

| Type | Method | Target |
|:---|:---|:---|
| **Test-Retest** | 2-week interval, same items | $r > 0.7$ |
| **Internal Consistency** | Cronbach's α across items | $\alpha > 0.8$ |
| **Split-Half** | Odd-even item split | $r > 0.75$ |

#### Phase 2: Convergent Validity

| K Measure | Comparison Metric | Expected Correlation |
|:---|:---|:---|
| $K_1$ | meta-d'/d' | $r > 0.6$ (positive) |
| $K_1$ | Type-2 AUROC | $r > 0.5$ (positive) |
| $K_0$ | IRT ability $\theta$ | $r > 0.8$ (positive) |

#### Phase 3: Discriminant Validity

| K Measure | Comparison | Expected |
|:---|:---|:---|
| $K_1$ | Raw confidence $C$ | $r < 0.3$ (low) |
| $K_0$ | Response time | $r < 0.2$ (low) |

#### Phase 4: Predictive Validity

| Predictor | Outcome | Hypothesis |
|:---|:---|:---|
| $K_1 = 1$ (Socratic) | Help-seeking | Higher |
| $K_2 = 1$ | Intervention responsiveness | Higher |
| $K_1 = -1$ (DK) | Overconfident errors | Higher |

#### Acknowledgment

We recognize that this validation program is **essential** for empirical adoption.
The current paper's contribution is the **conceptual and formal foundation**
upon which such validation can be built.
```

**レビュワー質問への直接回答**:
> "How will you establish reliability and validity?"

→ 4段階の検証計画を提示。現論文は概念基盤、検証は将来研究。

---

### D: Related Work Deepening（関連研究の深化）

#### D1: 既存研究との役割分担の明示

```markdown
### Positioning Among Related Frameworks

| Framework | Role | Relationship to K |
|:---|:---|:---|
| **MGV** (2511.04341) | Reasoning control architecture | K provides quantitative anchors for monitoring |
| **HiBayES** (2505.05602) | Hierarchical estimation engine | K defines what to estimate |
| **meta-d'** (Maniscalco & Lau) | Aggregate sensitivity metric | K provides per-item classification |
| **meta-I** (Dayan, 2023) | Information-theoretic sensitivity | K adds direction and recursion |
| **Internal readouts** (2505.13763) | Mechanistic analysis | Triangulation with behavioral K |

**Key Distinction**:

These frameworks address **how well** metacognition works (sensitivity, efficiency).
The K framework addresses **what type** of metacognitive state exists (classification, coordinates).

**Analogy**:
- meta-d' / meta-I = Thermometer (measures temperature)
- K = Weather map (classifies patterns, guides intervention)

**Integration Potential**:

The K framework serves as a **common coordinate system** that unifies:
- Behavioral assessments (response-claim alignment)
- Signal-detection metrics (meta-d', AUROC)
- Internal state readouts (activation probing)
- Hierarchical estimation (HiBayES)

This is not "reinventing the wheel" but **designing the axle** that connects existing wheels.
```

---

#### D2: Type-2 SDT との明示的接続

```markdown
### Formal Correspondence with Type-2 SDT

**Type-2 SDT Framework**:

In Type-2 SDT, subjects discriminate their own correct from incorrect responses.

| SDT Quantity | K Framework Equivalent |
|:---|:---|
| Type-1 d' (sensitivity) | Derived from $K_0$ distribution |
| Type-2 Hit Rate | $P(\text{"I know"} | K_0 = 1)$ |
| Type-2 FA Rate | $P(\text{"I know"} | K_0 \leq 0)$ |
| meta-d' | Related to $K_1$ via: $K_1 \approx \tanh(\text{meta-d}'/d')$ |

**What K Adds**:

1. **Signed direction**: meta-d' is unsigned; $K_1$ distinguishes overconfidence (-1) from underconfidence
2. **Per-item granularity**: meta-d' is aggregate; $K_1$ can be computed per item
3. **Explicit ignorance**: "I don't know" is modeled as $K_0 = 0$, not low confidence
4. **Recursive hierarchy**: $K_2, K_3, \ldots$ extend beyond Type-2

**Complementary Analysis**:

- Use meta-d' for aggregate sensitivity comparisons across studies
- Use K for per-item classification and intervention targeting
- Cross-validate: $K_1$ should correlate with meta-d'/d' (convergent validity)
```

---

## Summary Table

| Item | Problem | Solution | Priority |
|:---:|:---|:---|:---:|
| **A1** | 型システム不一致 | 埋め込み写像 $g_n$ を明示 | 高 |
| **A2** | 単調性順序未定義 | 埋め込み後実数順序 | 高 |
| **A3** | State₀マッピング不整合 | マッピング表修正 | 中 |
| **B1** | 測定モデル欠如 | 既存手法プラグイン | 高 |
| **B1a** | Phi係数と3値の整合性 | 2値化戦略（Strategy A/B/C）を明示 | 中 |
| **B1b** | tanh変換の根拠 | 複数有界化関数を比較、感度分析推奨 | 中 |
| **B2** | 連続-カテゴリ関係 | 閾値ルール追加 | 中 |
| **B2a** | ±0.33閾値の根拠 | Tercile根拠 + 代替閾値表 | 中 |
| **C1** | 信頼性・妥当性なし | ロードマップ提示 | 中 |
| **D1** | 関連研究との差異化 | 役割分担表 | 中 |
| **D2** | SDT接続不足 | 形式的対応表 | 中 |

---

## Internal Reviewer Feedback Integration

### 指摘1: tanh変換の根拠が薄い

**対応**:
- 3つの有界化関数（tanh, scaled CDF, clipped linear）を比較表として提示
- tanh をデフォルトとする根拠（smooth, symmetric, widely used）を明示
- **感度分析の推奨**: 少なくとも2つの関数で結果を報告

### 指摘2: ±0.33閾値の根拠が不十分

**対応**:
- 4つの根拠（Symmetric Tercile, Neutral Zone, Statistical Interpretation, Robustness）を明示
- 代替閾値（±0.5, ROC-optimized, Domain-specific）の比較表を追加
- **デフォルト使用の推奨** + 感度分析

### 指摘3: Phi係数と3値の整合性

**対応**:
- 3つの2値化戦略（Strategy A/B/C）を明示
- Strategy A（Strict: correct vs incorrect/absent）を推奨
- 各セル定義を明確化

---

## Reviewer Questions: Direct Answers

### Q1: 型システムの reconciliation

> "How do you reconcile the two type treatments of K?"

**A**: 埋め込み写像 $g_n: \mathcal{S}_n \to [-1,1]$ を導入。
$K_n = \hat{K} \circ g_n$ と定義することで、型システムが統一される。
$K(K(x))$ は数値合成ではなく、$K_1(\text{State}_1(x))$ のショートハンド。

### Q2: State₀ マッピング

> "What is the precise mapping from State0 outcomes {correct, incorrect, absent} to {1, −1, 0}?"

**A**: correct → 1, incorrect → **-1**, absent → 0。
「誤答」は「無知」ではなく「誤概念」。例を修正。

### Q3: アライメントの操作的スコアリング

> "How is 'alignment' at higher layers operationally scored?"

**A**: 
- **Phi係数**: 3値State₀を2値化（Strategy A: correct vs incorrect/absent）して $\phi \in [-1, 1]$
- **meta-d'/d'**: 有界化関数 $f$ で変換（tanh, scaled CDF, clipped linear のいずれか）
- **階層ベイズ**: 事後確率から直接推定、CI付き

### Q4: 単調性の順序

> "What partial order on S_n justifies the monotonicity axiom?"

**A**: $g_n(\text{State}_n)$ による埋め込み後の実数順序 $[-1, 1]$ を使用。
S_n 自体には順序不要。

### Q5: 連続値とカテゴリ

> "How do continuous values translate into categories for interpretation?"

**A**: デフォルト閾値 ±0.33 で三分割（symmetric tercile）。
- 連続値は統計分析用
- カテゴリは解釈・介入設計用
- 代替閾値（±0.5, ROC最適化）での感度分析を推奨

### Q6: 測定モデル

> "Can you specify a minimal generative or measurement model?"

**A**: 
- $K_0$: IRT (2PL)
- $K_1$: Phi / meta-d'/d'
- $K_2$: 階層ベイズ GLM (HiBayES互換)

### Q7: 信頼性・妥当性

> "How will you establish reliability and validity?"

**A**: 4段階ロードマップ提示。
現論文は概念基盤、検証は将来研究として scope を明示。

### Q8: 層間の統計的関連

> "What cross-layer regularities do you expect?"

**A**: $K_0$ と $K_1$ の正の相関（メタ認知感度）を期待。
階層ベイズで事前分布として encode 可能（層の独立性は論理的、統計的相関は許容）。

### Q9: methodological relativism のガイド

> "How should experimenters choose the reference/target?"

**A**: 事前登録を推奨。
参照選択の透明性基準と、マルチリファレンス感度分析を提案。

### Q10: シミュレーション例

> "Could you provide a worked simulation?"

**A**: Appendix にミニマルシミュレーションを追加（または将来研究として scope 外明示）。

---

## Implementation Plan

### Phase 1: Formal Core（本改訂で実施）

1. A1: 埋め込み写像の追加
2. A2: 単調性の再定義
3. A3: State₀マッピング修正
4. B1: 測定モデルセクション追加
5. B2: 閾値ルール追加

### Phase 2: Related Work（本改訂で実施）

1. D1: 関連研究との役割分担
2. D2: Type-2 SDT との形式的対応

### Phase 3: Roadmap（本改訂で実施）

1. C1: 信頼性・妥当性ロードマップ

### Phase 4: Future Work（scope 外として明示）

1. 実際のシミュレーション実行
2. 経験的妥当性検証
3. 情報幾何への拡張

---

## Expected Outcome

### 批判解消予測

| 批判 | 対応後の評価 |
|:---|:---|
| 型システム不一致 | **解決**: 埋め込み写像で統一 |
| 単調性未定義 | **解決**: 実数順序で定義 |
| State₀不整合 | **解決**: マッピング表修正 |
| 測定モデル欠如 | **大幅改善**: 既存手法プラグイン |
| 信頼性・妥当性 | **scope 明示**: ロードマップ提示 |
| 連続-カテゴリ | **解決**: 閾値ルール追加 |

### 論文の位置付け

**Before**: 概念的提案（測定方法不明）

**After**: 概念的基盤 + 測定フレームワーク（既存手法との統合）

> "This is not 'reinventing the wheel' but **designing the axle** that connects existing wheels."

---

## Appendix: Key Phrases for Revision

### For Type System

> "We introduce embedding maps $g_n: \mathcal{S}_n \to [-1,1]$ to resolve the type ambiguity. The composition $K_n = \hat{K} \circ g_n$ ensures that K operates on embedded representations, not on its own numerical outputs."

### For Measurement Model

> "The K framework specifies **what to measure** (epistemic state coordinates); for **how to estimate**, we adopt established psychometric engines (IRT, meta-d', hierarchical Bayes) as plug-ins. This separation preserves our conceptual contribution while leveraging validated estimation machinery."

### For Validation

> "We present a staged validation roadmap (reliability → convergent → discriminant → predictive validity). The current paper establishes the conceptual foundation; empirical validation is planned for follow-up work with explicit scope boundaries."

### For Positioning

> "The K framework is not a replacement for meta-d' or calibration metrics, but a **common coordinate system** that enables cross-paradigm integration. It answers 'what type of metacognitive state' rather than 'how well metacognition works.'"
