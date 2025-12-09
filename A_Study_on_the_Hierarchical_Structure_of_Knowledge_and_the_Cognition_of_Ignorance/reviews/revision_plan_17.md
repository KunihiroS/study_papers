# Revision Plan 17: K の純化（Pure Sensitivity）と定義的矛盾の解消

**Date**: 2025-12-09
**Target Review**: `review_by_stanford_paperreview_ai_20251207.md`
**Strategy**: 「Conceptual Framework」路線を維持しつつ、K₁ の定義から「較正（Calibration/Bias）」の要素を **再解釈**し、「純粋な識別感度（Pure Sensitivity）」として明確化することで数学的矛盾を解消する。

---

## Executive Summary

### なぜ Plan 17 が必要か

**Stanford Review (20251207) の核心的指摘**:

> "The claim that a single K1 can simultaneously correspond to both calibration (ECE) and discrimination/sensitivity (meta-d'/d') is conceptually problematic; these are orthogonal properties."

**診断**: 論文が K₁ を「万能な指標」として見せようとするあまり、数学的に対立する性質（Sensitivity と Calibration）を一つの指標定義に混在させてしまった。

**著者の本来の意図**:
> 「観測者の立場で、主体の自信度（Bias）には興味がない。事実として知っているかどうかのグラデーションを再帰的にマップしたい」

### 解決策の選択

| 選択肢 | 内容 | 評価 |
|:-------|:-----|:-----|
| (a) レビュアー案 | K₁ → K₁_sens + K₁_cal に分割 | ❌ K の再帰的統一性が損なわれる |
| **(b) Plan 17** | K から Calibration を**完全削除**し、Sensitivity に純化 | ✅ 矛盾解消＋統一性維持 |

---

## Part 1: メタ的な構造（K フレームワークでの自己評価）

**x** = 「この論文の K₁ 定義は数学的に整合している」

### Plan 16 終了時点での K 状態

| Layer | 状態 | 評価 |
|:------|:-----|:-----|
| **K₀(x)** | 「概念枠組み」への移行は成功 | K₀ ≈ 0.8 |
| **K₁(x)** | 感度（Phi）と較正（ECE）を混同していると指摘された | K₁ ≈ -0.5（定義的矛盾） |
| **K₂(x)** | Bias を排除したいという著者の意図と、レビューの指摘が合致 | K₂ ≈ 0.9（修正方向は明確） |

### Plan 17 で目指す K 状態

| Layer | 目標状態 | 達成手段 |
|:------|:---------|:---------|
| **K₀(x)** | 「概念枠組み」としての完成度維持 | Plan 16 のスコープ宣言を維持 |
| **K₁(x)** | 「Pure Sensitivity」としての定義的一貫性 | ECE 対応の**完全削除**、定義の明確化 |
| **K₂(x)** | 数学的矛盾のないクリーンな理論体系 | 観測者視点の徹底 |

---

## Part 2: 批判の分類と対応方針

### 2.1 核心的批判への対応

| 批判 | 対応方針 |
|:-----|:---------|
| **Conflating Calibration & Sensitivity** | **再解釈**: K₁ 単体は Sensitivity のみ。Calibration は K×C の joint で説明 |
| **Split K₁?** | **代替解法**: 分割せず、Bias を C 次元に委譲 |

### 2.2 対応マトリクス

| # | 批判内容 | Plan 17 での対応 |
|:--|:---------|:-----------------|
| W1 | K₁ が ECE と meta-d' の両方に対応（矛盾） | **完全削除**: ECE 対応数式を削除。Calibration は K×C joint で説明 |
| W2 | Informal Proofs | Plan 16 継続（Proposition/Result 格下げ済み） |
| W3 | Ternary Scale Limitations | **補強**: [-1,1] は連続、{-1,0,+1} は anchor |
| W4 | No Simulations | Scope 外（Future Work） |
| W5 | Table Artifacts | LaTeX 修正 |

---

## Part 3: 具体的変更内容

### Phase A: K 定義の明確化（純化）

#### A1: 定義文の修正

**変更前**:
> K は「正解率」や「較正」とも関係する複合指標

**変更後**:
```markdown
> **Definition (K as Pure Sensitivity)**:
> 
> K measures **structural alignment** and **discriminability** between epistemic states 
> and claims. K is designed to be **independent of the subject's confidence bias**.
> 
> A subject with severe overconfidence (Bias) but perfect discrimination 
> (always higher confidence when correct) will have K₁ = +1.
> 
> Calibration (whether confidence values are probabilistically accurate) is NOT 
> captured by K alone. Calibration is a property of the **joint (K, C) distribution**.
```

#### A3: 用語統一（Alignment = Sensitivity）

> ⚠️ **Internal Reviewer Advice**: レビュアーは "Sensitivity" を好むが、論文では "Alignment" を使用。リンクが必要。

```markdown
> **Terminology Note**:
> 
> In this framework, **Metacognitive Alignment (K₁)** is formally equivalent to 
> **Metacognitive Sensitivity** (discrimination ability), as it measures the 
> correlation between subjective claims and objective reality, independent of 
> the absolute magnitude of confidence (Bias).
> 
> | Term in this paper | Equivalent in SDT literature |
> |:-------------------|:-----------------------------|
> | K₀ (First-order alignment) | Accuracy / d' |
> | K₁ (Metacognitive alignment) | Metacognitive sensitivity / meta-d' |
> | K₂ (Higher-order alignment) | Meta-metacognitive sensitivity |
```

#### A2: ECE 対応の再解釈（削除ではなく再フレーム）

**変更前**:
```markdown
K₁ ≈ 1 - 2·ECE
```

**変更後**:
```markdown
> **Note on K₁ and Calibration**:
> 
> K₁ alone does NOT measure calibration (ECE). These are related but distinct constructs:
> 
> | Construct | What it measures | K framework representation |
> |:----------|:-----------------|:---------------------------|
> | **Sensitivity** | Can distinguish correct from incorrect | K₁ (Phi, meta-d') |
> | **Calibration** | Is confidence numerically accurate | Joint (K, C) distribution |
> 
> A subject with K₁ = +1 (perfect discrimination) may still be miscalibrated 
> if their C distribution is systematically biased (e.g., always underconfident).
> 
> ECE is related to **K₁-C alignment**, not to K₁ in isolation.
```

### Phase B: K と C の直交性の強調

#### B1: 新しいパラグラフの追加

```markdown
### Orthogonality of K and C

The K framework maintains strict separation between:

- **K (Epistemic State)**: Structural alignment with ground truth. Bias-free.
- **C (Confidence)**: Phenomenological certainty. May contain bias.

This separation is the key to avoiding the conceptual conflation that plagues 
single-metric approaches. Phenomena like overconfidence are NOT captured by 
K₁ = -1 alone, but by the **combination** of K and C values.
```

#### B2: Dunning-Kruger の再定義

**変更前**:
> K₁ = -1 は過信（Overconfidence）を示す

**変更後**:
```markdown
> **Dunning-Kruger Effect (Reformulated)**:
> 
> - **K₀ = 0 or -1**: Subject lacks knowledge or has misconception
> - **K₁ = -1**: Subject's claims are **anti-correlated** with their actual state 
>   (claims "I know" when wrong, or "I don't know" when right — **structural misalignment**)
> - **C = High**: Subject reports high confidence
> 
> The Dunning-Kruger effect emerges from the **intersection** of:
> - A specific K-pattern (K₀ ≤ 0, K₁ = -1) — structural ignorance + misalignment
> - A specific C-pattern (C = High) — subjective overconfidence
> 
> K₁ = -1 alone means "reverse discrimination" (anti-correlation), 
> NOT "overconfidence". Overconfidence is a C property.
```

### Phase C: 27-Pattern Taxonomy の位置づけ

```markdown
> **Taxonomy Scope**:
> 
> The 27-pattern taxonomy classifies **structural epistemic states** (K₀, K₁, K₂).
> The phenomenological dimension C is **orthogonal** to this taxonomy.
> 
> - The 27 patterns describe "what kind of knower is this person structurally?"
> - C describes "how does this person feel about their knowledge?"
> 
> Complex phenomena (Dunning-Kruger, Imposter Syndrome) require BOTH 
> a K-pattern AND a C-pattern for full characterization.
```

### Phase D: Phi 係数の operationalization 明確化

```markdown
> **Operationalization of K₁ via Phi**:
> 
> With ternary Claim vocabulary {"I know", "Not sure", "I don't know"}, 
> binarization is required for Phi computation:
> 
> | Claim | Binary mapping |
> |:------|:---------------|
> | "I know" | Positive (1) |
> | "Not sure", "I don't know" | Negative (0) |
> 
> Alternative: Ordinal correlation (Kendall's τ or Spearman's ρ) 
> for graded claim responses.
```

---

## Part 4: 実装チェックリスト

### 4.1 定義の明確化

| ID | 項目 | 状態 |
|:---|:-----|:-----|
| **A1** | K の定義に「Bias-independent」「Pure Sensitivity」を明記 | ☐ |
| **A2** | ECE 対応数式を**完全削除**（「K₁ ≈ 1 - 2·ECE」を削除） | ☐ |
| **A3** | Alignment = Sensitivity の用語リンクを追加 | ☐ |
| **A4** | K₁ の説明から「Calibration」単独対応の記述を削除 | ☐ |

### 4.2 K-C 直交性の強調

| ID | 項目 | 状態 |
|:---|:-----|:-----|
| **B1** | 「Orthogonality of K and C」セクション追加 | ☐ |
| **B2** | Dunning-Kruger の定義を (K pattern + C pattern) に修正 | ☐ |
| **B3** | Imposter Syndrome の定義を (K₀=+1, K₁=-1, C=Low) と明記 | ☐ |

### 4.3 Taxonomy の明確化

| ID | 項目 | 状態 |
|:---|:-----|:-----|
| **C1** | 27-pattern は「structural K-space」であり C は別次元と明記 | ☐ |
| **C2** | 複合現象は「K-pattern × C-pattern」の intersection と説明 | ☐ |

### 4.4 Operationalization

| ID | 項目 | 状態 |
|:---|:-----|:-----|
| **D1** | Phi 係数と ternary Claim の binarization ルールを明記 | ☐ |
| **D2** | meta-d' との対応で SDT 仮定を明示 | ☐ |

### 4.5 Plan 16 からの継承

| ID | 項目 | 状態 |
|:---|:-----|:-----|
| **E1** | "Conceptual framework paper" 宣言維持 | ✅ (Plan 16) |
| **E2** | Theorem → Proposition/Result 格下げ維持 | ✅ (Plan 16) |
| **E3** | Future Work セクション維持 | ✅ (Plan 16) |

---

## Part 5: 期待される効果

### 5.1 批判への対応マップ

| レビュー指摘 | Plan 17 での回答 | 期待される評価 |
|:------------|:-----------------|:---------------|
| **Conflating Sens/Cal** | Resolved: K = pure sensitivity, Calibration = K×C joint | Accept |
| **Split K₁?** | Alternative: C handles Bias; K is unified | Accept |
| **No Experiments** | Out of Scope (Plan 16 継続) | Neutral |

### 5.2 最終的な論文の主張

> 「既存の研究は『何を知っているか（State）』と『どう感じているか（Bias）』を混同しがちだった。本フレームワークは、K によって**『純粋な構造的・識別的状態（Sensitivity）』**を抽出し、それを C（Bias）と明確に直交させることで、メタ認知の病理（DK効果など）をよりクリアに記述する座標系を提供する。」

---

## Part 6: 実装順序

1. **A1-A3**: K 定義の明確化（ECE 再解釈を含む）
2. **B1-B3**: K-C 直交性の追加・Dunning-Kruger 再定義
3. **C1-C2**: Taxonomy の位置づけ明確化
4. **D1-D2**: Operationalization の明確化
5. **E1-E3**: Plan 16 継承の確認

---

## 付録: Plan 16 → Plan 17 の差分

| 観点 | Plan 16 | Plan 17 |
|:-----|:--------|:--------|
| **焦点** | ポジショニング変更 | **K の定義的純化** |
| **ECE 対応** | 維持（問題発生源） | **再解釈**（K×C joint） |
| **Bias の扱い** | 明示せず | **C に委譲を明示** |
| **Dunning-Kruger** | K₁=-1 で説明 | **K pattern + C pattern** |
| **Taxonomy** | そのまま | **C との直交性を明示** |

---

## 確認事項

1. ~~ECE 対応を「削除」ではなく「再解釈」（K×C joint）とする方針で良いか~~ → **完全削除に決定**
2. Dunning-Kruger を (K pattern + C pattern) の組み合わせで説明することに同意いただけるか → **承認済み**
3. 27-pattern taxonomy は K-space のみとし、C は別次元とする設計で良いか → **承認済み**

---

## 付録 B: 実装時の重要チェックポイント（5項目）

> ⚠️ **Internal Reviewer Advice**: 今回の更新は「K という温度計の仕様変更」。古い仕様書（ECE 記述）を完全にシュレッダーにかけることが全て。

### ✅ CP1: ECE への言及を「物理削除」する

**削除対象（必須）**:

| 箇所 | 内容 |
|:-----|:-----|
| Executive Summary 表 | `K₁ ≈ 1 - 2·ECE` |
| Correspondence 表 | `K₁ - Calibration - ECE` の行 |
| **Proposition 1b 全体** | K₁-ECE Approximate Relationship |

> ❌ 1行でも残っていると即リジェクト

### ✅ CP2: Alignment = Sensitivity の接続文を追加

**追加場所**: Introduction または Definition セクション

```markdown
> In this framework, **Metacognitive Alignment (K₁)** is formally equivalent to 
> **Metacognitive Sensitivity** (e.g., meta-d'). This represents pure discrimination 
> ability, independent of the subject's confidence magnitude (Bias).
```

### ✅ CP3: Dunning-Kruger の定義を「組み合わせ」に修正

| 修正前 | 修正後 |
|:-------|:-------|
| K₁ = -1 → "Dunning-Kruger" | K₁ = -1 → **"Misalignment"** |
| N/A | K₁ = -1 **AND** C = High → **"Dunning-Kruger Effect"** |

**Taxonomy 表での確認**: #5, #18 の DK パターンに「C = High」条件を明記

### ✅ CP4: Phi 係数が「感度」である理由を補足

**追加すべき論理** (Result 2 付近):

```markdown
> Phi coefficient is a correlation measure. Correlation captures 
> **distributional shape** (co-variation), NOT **absolute value bias**.
> 
> A subject with systematic overconfidence (Bias) but perfect discrimination 
> (higher confidence when correct) will have K₁ = +1.
> 
> This property proves that K₁ is **Pure Sensitivity**.
```

### ✅ CP5: 「なぜ分割しないか」の正当化

**追加場所**: Discussion または Measurement Theory

```markdown
> Existing approaches treat Sensitivity (meta-d') and Calibration (ECE) 
> as separate metrics. This framework **unifies** them differently:
> 
> - **K dimension**: Sensitivity (discrimination ability)
> - **C dimension**: Bias (confidence magnitude)
> - **Joint Model (K × C)**: Captures phenomena like Dunning-Kruger
> 
> This preserves the recursive unity of the K operator while maintaining 
> orthogonal dimensions for state (K) and feeling (C).
```

---

## 付録 C: 作業のアナロジー

**Before (現行ドラフト)**:
> 「この温度計（K）は、気温（Sensitivity）も測れるし、体感温度の不快指数（Calibration/Bias）もこれ一本で分かります！」
> 
> *レビュアー: 「気温と不快指数は別物だろ。混ぜるな危険。」*

**After (Plan 17)**:
> 「この温度計（K）は、**純粋に物理的な気温（Sensitivity）だけ**を測ります。あなたが『暑いと感じるか（Bias）』は、別のメーター（C）で測ってください。Dunning-Kruger現象とは、『気温が低いのに、暑いと感じている状態（K低・C高）』のことです。」

