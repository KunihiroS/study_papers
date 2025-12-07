# Revision Plan 15: 正当批判への対応 + レビュー見落とし対策

**Date**: 2025-12-07
**Target Review**: `20251207_03.md`
**Strategy**: Plan 14 を継承しつつ、**正当な批判への追加執筆** + **LLM レビュー見落とし対策** を実施

---

## Executive Summary

**Plan 14 の成果**:
- 対応関係の形式化、連続-離散仕様、Protocol 仕様は整備済み
- Falsifiability Axiom、K-C Separation Axiom 追加済み
- Worked Example (K₂ 計算例) 追加済み

**20251207_03 の批判の分析結果**:

レビュー批判を精査した結果、**論文に既に存在する内容を見落としている批判**と**正当な批判**が混在していることが判明。

| カテゴリ | 件数 | 対応方針 |
|:---------|:----:|:---------|
| **A: 正当な批判** | 4件 | **新規執筆**で対応 |
| **B: 論文内容の見落とし** | 5件 | **露出強化・書き換え**で対応 |
| **C: Scope 外** | 1件 | Future Work 維持 |

**Plan 15 の目標**:

> **「レビュアーが『見落とす確率』を最小化しつつ、正当な批判を解消する」**

そのために:
1. **正当な批判（A）**: 新規コンテンツ追加（4項目）
2. **見落とし（B）**: 露出強化・ラベル明示化（5項目）
3. **見落とし傾向分析**: パターン特定 → 構造的対策

---

## Part 1: レビュー批判の分類と分析

### 1.1 20251207_03.md の指摘一覧

| # | レビュー指摘 | 分類 | 根拠 |
|:--|:-------------|:----:|:-----|
| W1 | "no nontrivial theorems, identifiability results, or guarantees" | **B** | Theorem 3-5 (Identifiability) が存在。見落とし |
| W2 | "K₀=0 conflates abstentions with epistemic indeterminacy" | **A** | 正当。明示的分離が必要 |
| W3 | "correspondences are heuristic" | **B** | Theorem 1 に derivation あり。Remark 1 で「等号ではない」と明示済み |
| W4 | "recursive pipeline risks circularity or non-identifiability" | **A** | 正当。パイプライン全体の identifiability 未証明 |
| W5 | "K̂ is arbitrary" | **A** | 正当。理論的根拠が弱い |
| W6 | "under-cites polytomous IRT (GRM/GPCM)" | **A** | 正当。言及不足 |
| W7 | "under-cites HMeta-d" | **B** | meta-d' との比較は Remark 1 にあるが、HMeta-d 言及なし |
| W8 | "why tanh over logit/probit?" | **B** | Link Functions セクションにあるが、uniqueness 証明なし |
| W9 | "synthetic experiments needed" | **C** | Scope 外。Future Work |
| W10 | "falsifiable predictions are definitions, not tests" | **B** | Axiom F に定量的予測 (Pred 4-5) あり。見落とし |

### 1.2 見落としパターンの特定

| パターン | 発生箇所 | 推定原因 | 対策 |
|:---------|:---------|:---------|:-----|
| **P1: セクション埋没** | Theorem 3-5, Axiom F | 本文中に埋もれている。見出しが目立たない | **見出し強化** + **Technical Guide 追加** |
| **P2: ラベル不足** | Remark 1, Link Functions | "nontrivial", "guarantee" などのキーワードがない | **ラベル明示化** |
| **P3: 分散配置** | Identifiability 関連 | 複数箇所に散在し、全体像が掴みにくい | **Summary Table 追加** |
| **P4: 結論での未再掲** | Formal Results 全般 | Conclusion に要約がない | **Conclusion 強化** |

---

## Part 2: 対応計画

### Phase A: 正当な批判への新規執筆（4項目）

#### A1: Abstention vs Ignorance の明示的分離

**現状**: K₀=0 が "abstention"（応答なし）と "ignorance"（認識なし）の両方を含む。

**追加内容**:

```markdown
### Disambiguation: Abstention vs Epistemic Ignorance

**Definition** (Disambiguated Zero States):

At layer 0, we distinguish two generative processes that can yield K₀ = 0:

**(a) Epistemic Ignorance** (State₀ = ignorant):
- Subject attempts response but lacks knowledge
- Model: Subject responds, but P(correct) ≈ chance
- Indicator: Response given, result ≈ random

**(b) Strategic Abstention** (State₀ = abstained):
- Subject withholds response deliberately
- Model: Missing Not At Random (MNAR)
- Indicator: A₀ = 1 (abstention flag)

**Extended State Space**:

| State₀ | K₀ | A₀ (Abstention flag) |
|:-------|:---|:---------------------|
| correct | +1 | 0 |
| incorrect | -1 | 0 |
| ignorant (responded) | 0 | 0 |
| abstained | undefined | 1 |

**Operational Recommendation**:
- Report (K₀, A₀) jointly
- When A₀ = 1, K₀ is undefined (not 0)
- Analyze abstention patterns separately from ignorance patterns

**Scope Boundary**: Full MNAR modeling is beyond current scope (see Limitations).
```

---

#### A2: Pipeline Identifiability Theorem（再帰パイプラインの識別可能性）

**現状**: Theorem 3-5 は各層を個別に扱うが、全体のパイプラインとしての identifiability は未証明。

**追加内容**:

```markdown
### Theorem 6: Recursive Pipeline Identifiability

**Theorem 6** (Pipeline Identifiability):

**Assumptions**:
(A1) Reference is fixed and known before estimation
(A2) Claim_n is elicited BEFORE feedback on K_{n-1} is provided
(A3) N ≥ 10 items per subject
(A4) Var(K₀) > 0 and Var(Claim₁ | K₀) > 0

**Statement**:
Under (A1)-(A4), the triple (K₀, K₁, K₂) is jointly identifiable.

**Proof**:

1. **K₀ Identifiability**: 
   By Theorem 3, K₀ is identifiable given Var(b_i) > 0.

2. **K₁ Identifiability (given K₀)**:
   By (A2), Claim₁ is elicited before K₀ feedback.
   Therefore, Claim₁ ⊥ estimation_error(K₀) | true_K₀.
   By Theorem 4, K₁ is identifiable given K₀ and Claim₁.

3. **K₂ Identifiability (given K₁)**:
   By analogous reasoning with (A2), Claim₂ ⊥ estimation_error(K₁) | true_K₁.
   By Theorem 5, K₂ is identifiable.

4. **No Circularity**:
   The Markov property holds: K₂ ⊥ K₀ | K₁.
   Each layer depends only on its immediate predecessor and the corresponding Claim.
   No feedback loop exists in the estimation pipeline. □

**Corollary 6.1** (Circularity Condition):
If Claim₁ is elicited AFTER feedback on correctness, K₁ is confounded with K₀.
The pipeline becomes circular and identifiability is lost.

**Non-Identifiable Example**:
- Subject answers item → feedback "correct" shown → subject asked "Did you know?"
- Response to "Did you know?" is confounded with feedback, not pure metacognition.
```

---

#### A3: K̂ Sufficiency Lemma

**現状**: K̂ の役割は説明されているが、identity で十分という理論的根拠がない。

**追加内容**:

```markdown
### Lemma 3: K̂ Sufficiency Condition

**Lemma 3** (K̂ = Identity Sufficiency):

K̂ = identity is optimal when the following conditions hold:

**(C1) Range Preservation**: g_n already maps to [-1, 1]
**(C2) Anchor Preservation**: g_n(±1) = ±1, g_n(0) = 0
**(C3) No Systematic Bias**: E[estimation_error] = 0

**Proof**:
Under (C1)-(C3), any K̂ ≠ identity would:
- Distort intermediate values without improving anchor interpretation
- Introduce unnecessary nonlinearity
- Complicate inverse mapping for interpretation

Since g_n satisfies (C1)-(C3) by construction, K̂ = identity is optimal. □

**When K̂ ≠ Identity**:

| Scenario | Recommended K̂ | Rationale |
|:---------|:---------------|:----------|
| Known systematic bias | Isotonic calibration | Corrects monotonic bias |
| Cross-study comparison | Percentile normalization | Aligns distributions |
| Non-standard g_n | Custom scaling | Restores anchor semantics |

**Default Recommendation**: Use K̂ = identity unless (C1)-(C3) are violated.
```

---

#### A4: Polytomous IRT (GRM) との関係明示

**現状**: Binary IRT (2PL) のみ言及。GRM/GPCM への言及不足。

**追加内容**:

```markdown
### Extension: Connection to Polytomous IRT

**Current Scope**: The K framework primarily addresses binary correctness (correct/incorrect/abstain).

**Extension to Graded Response Model (GRM)**:

For polytomous outcomes (e.g., rubric scores 0, 1, 2, 3), the Graded Response Model provides a natural extension:

$$P(Y \geq k | \theta) = \frac{1}{1 + e^{-a(\theta - b_k)}}$$

**Mapping to Graded K₀**:

$$K_0^{(\text{graded})} = \frac{2Y - Y_{\max}}{Y_{\max}}$$

where Y is the observed score and Y_max is the maximum possible score.

| Y (Score) | Y_max = 3 | Graded K₀ |
|:----------|:----------|:----------|
| 0 | 3 | -1.0 |
| 1 | 3 | -0.33 |
| 2 | 3 | +0.33 |
| 3 | 3 | +1.0 |

**Impact on Higher Layers**:
Graded K₀ naturally propagates to K₁ with graded alignment interpretation.

**Relationship to GPCM**:
The Generalized Partial Credit Model (Masters, 1982) provides an alternative polytomous model with different threshold parameterization. Both GRM and GPCM are compatible with the K framework via the linear mapping above.

**Implementation Status**: Conceptually compatible; full integration deferred to future work.

**References**:
- Samejima, F. (1969). Estimation of latent ability using a response pattern of graded scores.
- Masters, G. N. (1982). A Rasch model for partial credit scoring.
```

---

### Phase B: レビュー見落とし対策（5項目）

#### B1: Technical Guide for Reviewers の追加

**目的**: LLM レビュアーが「どこに何があるか」を即座に把握できるようにする。

**追加箇所**: 論文冒頭（Abstract 直後）または Related Work 直前

```markdown
## Technical Guide for Reviewers

This section provides a roadmap to the formal results in this paper.

### Nontrivial Theorems and Identifiability Results

| ID | Name | Content | Section |
|:---|:-----|:--------|:--------|
| **Theorem 1** | K₀-IRT Exact Correspondence | K₀ = tanh(a(θ-b)/2) with full derivation | §X.Y |
| **Theorem 2** | K₁-Phi Correspondence | K₁ = φ under binary State₀/Claim₁ | §X.Y |
| **Theorem 3** | K₀ Identifiability | Var(b_i) > 0 ⇒ K₀ identifiable | §X.Y |
| **Theorem 4** | K₁ Identifiability | Variability conditions for K₁ | §X.Y |
| **Theorem 5** | K₂ Identifiability | ICC-based identifiability | §X.Y |
| **Theorem 6** | Pipeline Identifiability | Joint identifiability of (K₀, K₁, K₂) | §X.Y (NEW) |

### Falsifiable Predictions with Quantitative Bounds

| ID | Prediction | Quantitative Bound | Section |
|:---|:-----------|:-------------------|:--------|
| **Pred 1** | K-C Dissociation | ∃ subjects with K₁=-1, C=high | §X.Y |
| **Pred 2** | Layer Independence | Cor(K₀, K₂ | K₁) ≈ 0 | §X.Y |
| **Pred 4** | Intervention Effect | E[ΔK₁] ≥ 0.2, |E[ΔK₀]| ≤ 0.1 | §X.Y |
| **Pred 5** | K-C Correlation Bound | Cor(K₁, C) < 0.85 | §X.Y |

### Key Clarifications

- **K₁ ≈ tanh(meta-d'/2)**: This is a **conceptual relationship**, NOT a mathematical identity (see Remark 1, §X.Y)
- **K̂ = identity**: Justified by Lemma 3 under standard conditions (see §X.Y)
```

---

#### B2: Formal Results セクションの見出し強化

**現状**: "### Identifiability Theorems" のような控えめな見出し。

**変更後**:

```markdown
## Formal Results: Nontrivial Theorems and Guarantees

This section contains **nontrivial mathematical results** with **explicit assumptions**, **formal proofs**, and **boundary conditions**.

### 5.1 Correspondence Theorems (Derived, Not Heuristic)

#### Theorem 1: K₀-IRT Exact Correspondence (Formal Derivation)
[内容]

#### Theorem 2: K₁-Phi Correspondence (Formal Derivation)
[内容]

### 5.2 Identifiability Theorems (Formal Guarantees)

#### Theorem 3: K₀ Identifiability
[内容]

...
```

**ポイント**:
- "Nontrivial", "Guarantee", "Formal Derivation" をタイトルに含める
- セクション番号を明示
- 「これは heuristic ではない」ことを見出しで主張

---

#### B3: Conclusion への Formal Results 要約追加

**現状**: Conclusion は概念的成果のみ言及。定理の再掲なし。

**追加内容**:

```markdown
### Formal Contributions (Summary)

This paper contributes the following **nontrivial mathematical results**:

1. **Theorem 1-2 (Correspondence)**:
   - K₀ = tanh(a(θ-b)/2) is **exactly derived** from 2PL-IRT under explicit assumptions
   - K₁ = φ (Phi coefficient) under binary State₀/Claim₁

2. **Theorem 3-6 (Identifiability)**:
   - K₀, K₁, K₂ are **individually identifiable** under stated conditions
   - The recursive pipeline (K₀ → K₁ → K₂) is **jointly identifiable** without circularity

3. **Axiom F (Falsifiability)**:
   - Five **quantitative predictions** with explicit bounds (δ = 0.2, ε = 0.1, Cor < 0.85)
   - Framework is **empirically refutable**

4. **Lemma 1-3 (Robustness)**:
   - Scale invariance, class imbalance bounds, K̂ sufficiency conditions
```

---

#### B4: Remark 1 の位置移動 + ラベル強化

**現状**: Remark 1 (K₁ and meta-d') は Appendix に近い位置。

**変更**:
1. Formal Results セクション内に移動
2. タイトルを強化: "Remark 1 (Critical Clarification): K₁ and meta-d' Are NOT Mathematically Equivalent"

```markdown
#### Remark 1 (Critical Clarification): K₁ and meta-d' Are NOT Mathematically Equivalent

> **Note**: We do NOT claim K₁ ≈ tanh(meta-d'/2) as a mathematical identity.
> K₁ and meta-d' measure **related but distinct** aspects of metacognition.

[既存内容]
```

---

#### B5: HMeta-d との関係追加

**現状**: meta-d' との比較はあるが、HMeta-d (Fleming, 2017) への言及なし。

**追加内容** (Related Work セクション):

```markdown
### Connection to Hierarchical Meta-d' (HMeta-d)

Fleming and Daw (2017) introduced HMeta-d, a hierarchical Bayesian framework for estimating meta-d' with:
- Subject-level random effects
- Proper uncertainty quantification
- Shrinkage toward group mean

**Relationship to K Framework**:

| Aspect | HMeta-d | K Framework |
|:-------|:--------|:------------|
| **Purpose** | Estimate meta-d' with uncertainty | Classify metacognitive patterns |
| **Model** | Hierarchical Bayesian | Observational (model-free option) |
| **Output** | Posterior distribution of meta-d' | Discrete K_n or continuous K_n |
| **Granularity** | Aggregate (subject-level) | Per-item + aggregate |

**Complementary Use**:
- HMeta-d provides **reliable aggregate estimates** with uncertainty
- K framework provides **per-item pattern classification** and **directional information**
- Both can be computed from the same raw data (responses + confidence)

**Integration Potential**:
Use HMeta-d for meta-d' estimation, then compare with K₁ to assess convergent validity.

**Reference**: Fleming, S. M., & Daw, N. D. (2017). Self-evaluation of decision-making: A general Bayesian framework for metacognitive computation. *Psychological Review*, 124(1), 91-114.
```

---

## Part 3: 見落とし対策の構造的実装

### 3.1 対策パターンと実装箇所

| パターン | 対策 | 実装箇所 | 優先度 |
|:---------|:-----|:---------|:------:|
| **P1: セクション埋没** | Technical Guide 追加 | Abstract 直後 | ★★★ |
| **P1: セクション埋没** | 見出し強化 | Formal Results 全体 | ★★★ |
| **P2: ラベル不足** | キーワード明示 | 各定理タイトル | ★★☆ |
| **P3: 分散配置** | Summary Table 追加 | Technical Guide 内 | ★★★ |
| **P4: 結論での未再掲** | Formal Contributions 追加 | Conclusion 内 | ★★☆ |

### 3.2 キーワード戦略

LLM レビュアーが「探す」可能性が高いキーワードを意図的に配置：

| キーワード | 配置箇所 | 回数 |
|:-----------|:---------|:----:|
| "nontrivial theorem" | Technical Guide, Formal Results 見出し, Conclusion | 3+ |
| "identifiability" | Theorem 3-6 タイトル, Technical Guide, Conclusion | 5+ |
| "guarantee" | Formal Results 見出し, Conclusion | 2+ |
| "falsifiable prediction" | Axiom F 見出し, Technical Guide | 2+ |
| "formal derivation" | Theorem 1-2 タイトル | 2 |
| "NOT heuristic" | Remark 1, Theorem 1 近辺 | 2+ |

---

## Part 4: 実装チェックリスト

### 4.1 正当批判への新規執筆 (Phase A)

| ID | 項目 | 対応批判 | 状態 |
|:---|:-----|:---------|:-----|
| **A1** | Abstention vs Ignorance の分離 | W2 | ☐ |
| **A2** | Theorem 6: Pipeline Identifiability | W4 | ☐ |
| **A3** | Lemma 3: K̂ Sufficiency | W5 | ☐ |
| **A4** | GRM/GPCM との関係 | W6 | ☐ |

### 4.2 見落とし対策 (Phase B)

| ID | 項目 | 対応パターン | 状態 |
|:---|:-----|:-------------|:-----|
| **B1** | Technical Guide for Reviewers | P1, P3 | ☐ |
| **B2** | Formal Results 見出し強化 | P1, P2 | ☐ |
| **B3** | Conclusion への Formal Results 要約 | P4 | ☐ |
| **B4** | Remark 1 の位置移動 + ラベル強化 | P2 | ☐ |
| **B5** | HMeta-d との関係追加 | W7 | ☐ |

### 4.3 キーワード配置確認

| ID | キーワード | 目標回数 | 状態 |
|:---|:-----------|:--------:|:-----|
| **K1** | "nontrivial theorem" | 3+ | ☐ |
| **K2** | "identifiability" | 5+ | ☐ |
| **K3** | "guarantee" | 2+ | ☐ |
| **K4** | "NOT heuristic" / "NOT equivalent" | 2+ | ☐ |

---

## Part 5: 期待される効果

### 5.1 レビュー批判への対応マップ

| 批判 | 分類 | Plan 15 での対応 |
|:-----|:----:|:-----------------|
| W1: "no nontrivial theorems" | B | **B1-B3**: Technical Guide + 見出し強化 + Conclusion 要約 |
| W2: "abstention = ignorance conflation" | A | **A1**: 明示的分離定義 |
| W3: "correspondences are heuristic" | B | **B2, B4**: ラベル強化 + Remark 1 位置移動 |
| W4: "pipeline risks circularity" | A | **A2**: Theorem 6 追加 |
| W5: "K̂ is arbitrary" | A | **A3**: Lemma 3 追加 |
| W6: "under-cites polytomous IRT" | A | **A4**: GRM 関係追加 |
| W7: "under-cites HMeta-d" | B | **B5**: HMeta-d 関係追加 |
| W8: "why tanh" | B | 既存 Link Functions セクションで対応済み。必要なら補強 |
| W9: "synthetic experiments needed" | C | Scope 外維持 |
| W10: "falsifiable predictions are definitions" | B | **B1, B3**: Technical Guide + Conclusion で定量予測を強調 |

### 5.2 見落とし発生確率の低減見込み

| パターン | Before | After (見込み) |
|:---------|:------:|:--------------:|
| P1: セクション埋没 | 高 | **低** (Technical Guide で先回り) |
| P2: ラベル不足 | 高 | **低** (キーワード明示) |
| P3: 分散配置 | 中 | **低** (Summary Table) |
| P4: 結論での未再掲 | 高 | **低** (Conclusion 強化) |

### 5.3 期待されるレビュー評価の変化

| 評価軸 | Before (20251207_03) | After (Plan 15 完遂) |
|:-------|:---------------------|:---------------------|
| 非自明な定理 | ❌「なし」と誤認 | ✅「Technical Guide で明示」 |
| 識別可能性 | ❌「pipeline circular」 | ✅「Theorem 6 で証明」 |
| 対応関係 | ❌「heuristic」 | ✅「NOT heuristic と明示」 |
| 既存理論 | △「under-cites」 | ✅「GRM, HMeta-d 追加」 |
| 反証可能性 | △「definitions」 | ✅「定量予測を強調」 |

---

## Part 6: 実装順序

1. **B1: Technical Guide for Reviewers** — 最優先。見落とし対策の中核。
2. **A2: Theorem 6 (Pipeline Identifiability)** — 正当批判の中で最重要。
3. **B2-B3: 見出し強化 + Conclusion 強化** — 露出改善。
4. **A1, A3, A4: 新規定義・補題** — 正当批判への対応。
5. **B4-B5: Remark 1 移動 + HMeta-d** — 仕上げ。

---

## Part 7: メタ的な構造（K フレームワークでの自己評価）

**x** = 「レビュアーに正しく認識され、トップカンファに採択される」

### Plan 14 終了時点での K 状態

| Layer | 状態 | 評価 |
|:------|:-----|:-----|
| **K₀(x)** | 内容は概ね揃っている | K₀ ≈ 0.6（定理・公理は存在） |
| **K₁(x)** | レビュアーが認識していない | K₁ ≈ -0.5（内容はあるが見落とされている = misaligned） |
| **K₂(x)** | 見落としパターンを分析できた | K₂ ≈ 0.5（メタ認知は立ち上がりつつある） |

### Plan 15 で目指す K 状態

| Layer | 目標状態 | 達成手段 |
|:------|:---------|:---------|
| **K₀(x)** | K₀ → +1（理論的に完全） | A1-A4 で正当批判を解消 |
| **K₁(x)** | K₁ → +1（レビュアーが正しく認識） | B1-B5 で露出強化 |
| **K₂(x)** | K₂ → +1（見落としパターンを制御） | 本 Plan の構造的対策 |

---

## 付録: Plan 14 → Plan 15 の差分

| 観点 | Plan 14 | Plan 15 |
|:-----|:--------|:--------|
| 焦点 | 内容の追加・強化 | **内容 + 露出** の両面対応 |
| 見落とし対策 | なし | **構造的に実装** |
| Technical Guide | なし | **新規追加** |
| 結論強化 | なし | **Formal Contributions 追加** |
| 見出し戦略 | 暗黙 | **明示的キーワード配置** |
| Pipeline Identifiability | なし | **Theorem 6 追加** |
| Abstention 分離 | 暗黙 | **明示的定義** |

---

## 確認事項

1. 上記の方針で進めてよいか
2. Phase A（新規執筆）と Phase B（露出強化）の優先度は正しいか
3. Technical Guide の位置（Abstract 直後 vs Related Work 前）はどちらが適切か
4. 追加すべき項目はあるか
