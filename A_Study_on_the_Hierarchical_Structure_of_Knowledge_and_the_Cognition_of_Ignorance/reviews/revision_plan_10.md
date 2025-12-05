# Revision Plan 10: Response to 20251205_02.md Review

**Date**: 2025-12-06
**Target Review**: `20251205_02.md`
**Strategy**: 構造改善（可視性向上）+ 軽微な追加 + 新規セクション

---

## Executive Summary

レビューシステムが繰り返し見落とす内容（27パターン表、Latent Variable Model、Correspondence Table）は**既に論文に存在**している。主な対応は：

1. **構造改善**: 重要な表・定義を論文冒頭に移動し、システムの認識率を向上
2. **軽微な追加**: State$_2$表の完全化、Aggregation Rules、Epistemic Logic比較
3. **Future Work明示**: シミュレーション/実証は明確にFuture Workとして維持

---

## Review Analysis: 指摘の分類

### 🔴 誤検出（既に対応済み）

| Line | 指摘内容 | 実際の論文状況 | 対応 |
|:-----|:---------|:--------------|:-----|
| 25 | "27 patterns not enumerated" | Line 748-818 に完全な27行テーブル | **配置移動** |
| 20 | "intermediate values not specified" | Line 1351-1391 Latent Variable Model | **配置移動** |
| 30 | "omits meta-d', calibration, IRT" | Line 1687-1739 Correspondence Table | **配置移動** |
| 22 | "identifiability not analyzed" | Line 1211-1230 Identifiability Section | **配置移動** |

### 🟡 軽微な追加が必要

| Line | 指摘内容 | 現状 | 対応 |
|:-----|:---------|:-----|:-----|
| 28 | State_2 table incomplete | 表はあるが詳細度不足 | Phase 2.1 |
| 50 | "meta-aligned/uncertain/misaligned" 定義不明確 | 定義はあるが散在 | Phase 2.2 |
| 51 | aggregation rules | 部分的に記述 | Phase 2.3 |
| 56 | confidence intervals | 言及あるが具体的手順なし | Phase 2.4 |

### 🟢 新規追加が有益

| Line | 指摘内容 | 対応 |
|:-----|:---------|:-----|
| 42 | S5 introspection axioms との関係 | Phase 3.1 |
| 57 | partial credit, multi-label | Phase 3.2 (Scope Boundary) |
| 62 | trivial regress防止 | Phase 3.3 |

### ⚪ Future Work維持

| Line | 指摘内容 | 方針 |
|:-----|:---------|:-----|
| 24, 38, 39, 63 | Simulation/Empirical | Future Work として明示的に記載 |

---

## Phase 1: 構造改善（可視性向上）

### Phase 1.1: Executive Summary の追加

**Location**: Introduction 直後（現在の Line ~95 付近）

**Content**:
```markdown
## Executive Summary: Framework at a Glance

This section provides a concise overview of the framework's core components for readers seeking quick orientation.

### Core Apparatus

| Component | Definition | Purpose |
|:----------|:-----------|:--------|
| **$K_n$** | Observation function at layer $n$ | Maps State$_n$ to $[-1, 1]$ |
| **State$_n$** | Epistemic state object at layer $n$ | Target of observation |
| **$f_n$** | State function | Computes State$_n$ from inputs |
| **$g_n$** | Embedding map | Maps categorical State$_n$ to $K_n \in [-1, 1]$ |

### Anchor Semantics (All Layers)

| Value | Meaning |
|:------|:--------|
| $K_n = +1$ | Knowledge / Alignment |
| $K_n = 0$ | Ignorance / Indeterminacy |
| $K_n = -1$ | Misconception / Misalignment |

### 27-Pattern Taxonomy (Preview)

The framework generates $3 \times 3 \times 3 = 27$ metacognitive patterns from combinations of $(K_0, K_1, K_2) \in \{-1, 0, +1\}^3$. The complete enumeration appears in Section [X]. Key patterns include:

| Pattern | $(K_0, K_1, K_2)$ | Name |
|:--------|:------------------|:-----|
| #14 | $(0, +1, +1)$ | **Socratic Wisdom** |
| #5 | $(-1, -1, -1)$ | **Dunning-Kruger (Deep)** |
| #22 | $(+1, -1, +1)$ | **Imposter Syndrome (Aware)** |

*See Complete Taxonomy section for full 27-pattern table.*
```

**Rationale**: レビューシステムは論文冒頭を重視する傾向がある。27パターンの存在を早い段階で明示することで誤検出を防ぐ。

---

### Phase 1.2: Correspondence Table の Related Work 統合

**Current Location**: Line 1687-1739 (後半)
**New Location**: Related Work セクション内（Line ~1800付近）

**Action**: 
1. Related Work セクション内に「Correspondence with Established Metrics」を移動
2. 元の位置には参照リンクを残す

**New Structure**:
```markdown
### Related Work

#### Signal Detection Theory and Metacognitive Sensitivity
[既存の meta-d' 議論]

**Correspondence with K Framework:**

| Layer | Our Metric | Established Metric | Relationship |
|:------|:-----------|:-------------------|:-------------|
| $K_0$ | First-order accuracy | IRT ability $\theta$ | $K_0 \approx \tanh(\theta)$ |
| $K_1$ | Metacognitive alignment | meta-d'/d' | $K_1 \approx \tanh(\text{meta-d}'/2)$ |
| $K_1$ | Calibration | ECE | $K_1 \approx 1 - 2 \cdot \text{ECE}$ |
| $K_2$ | Meta-metacognitive stability | Test-retest $K_1$ | Novel contribution |

[残りの Related Work]
```

---

### Phase 1.3: Latent Variable Model の Measurement Theory 冒頭移動

**Current Location**: Line 1351-1391 (後半)
**New Location**: Measurement Theory セクション冒頭

**Rationale**: 「continuous values are not specified」という指摘への直接対応。Measurement Theory を開く際に最初に目に入る位置に配置。

---

## Phase 2: 軽微な追加・明確化

### Phase 2.1: State$_2$ 表の完全化

**Issue**: Line 28 "Several tables have minor transcription artifacts and incomplete rows (e.g., State_2 table)"

**Current**: State$_2$ 表が不完全

**Action**: State$_2$ の9パターンすべてを明示的に列挙

```markdown
#### State$_2$: Third-Order Meta-Metacognitive State

| $K_1$ (actual) | Claim$_2$ | State$_2$ | $K_2$ |
|:---------------|:----------|:----------|:------|
| $+1$ (aligned) | "My self-assessment is accurate" | meta-aligned | $+1$ |
| $+1$ (aligned) | "I'm not sure about my self-assessment" | meta-uncertain | $0$ |
| $+1$ (aligned) | "My self-assessment is inaccurate" | meta-misaligned | $-1$ |
| $0$ (uncertain) | "My self-assessment is accurate" | meta-misaligned | $-1$ |
| $0$ (uncertain) | "I'm not sure about my self-assessment" | meta-aligned | $+1$ |
| $0$ (uncertain) | "My self-assessment is inaccurate" | meta-misaligned | $-1$ |
| $-1$ (misaligned) | "My self-assessment is accurate" | meta-misaligned | $-1$ |
| $-1$ (misaligned) | "I'm not sure about my self-assessment" | meta-uncertain | $0$ |
| $-1$ (misaligned) | "My self-assessment is inaccurate" | meta-aligned | $+1$ |

**Interpretation**: 
- **meta-aligned** ($K_2 = +1$): Subject's belief about their self-assessment accuracy matches reality
- **meta-uncertain** ($K_2 = 0$): Subject expresses uncertainty when actual $K_1$ is uncertain, OR expresses uncertainty when actual $K_1$ is certain (partial alignment)
- **meta-misaligned** ($K_2 = -1$): Subject's belief about their self-assessment accuracy contradicts reality
```

---

### Phase 2.2: meta-aligned/uncertain/misaligned の明示的定義

**Issue**: Line 50 "define 'meta-aligned/uncertain/misaligned' with unambiguous conditions"

**Action**: Boxed definition を追加

```markdown
> **DEFINITION (Higher-Order Alignment States):**
>
> For layer $n \geq 1$, the alignment state is determined by comparing actual $K_{n-1}$ with Claim$_n$:
>
> | Term | Condition | $K_n$ |
> |:-----|:----------|:------|
> | **Aligned** | Claim$_n$ correctly describes $K_{n-1}$ | $+1$ |
> | **Uncertain** | Claim$_n$ = "I'm not sure" | $0$ (if $K_{n-1} = 0$) or context-dependent |
> | **Misaligned** | Claim$_n$ contradicts $K_{n-1}$ | $-1$ |
>
> **Formal Rule**: $K_n = \text{sign}(\text{agreement}(\text{Claim}_n, K_{n-1}))$
```

---

### Phase 2.3: Aggregation Rules セクション追加

**Issue**: Line 51 "Provide aggregation rules across items (e.g., mean K_n, distributional summaries)"

**Location**: Measurement Theory セクション内

```markdown
### Aggregation Rules Across Items

For a subject responding to $N$ items, we obtain item-level scores $(K_0^{(i)}, K_1^{(i)}, K_2^{(i)})$ for $i = 1, \ldots, N$.

#### Point Estimates

| Aggregate | Formula | Interpretation |
|:----------|:--------|:---------------|
| **Mean $K_n$** | $\bar{K}_n = \frac{1}{N} \sum_{i=1}^N K_n^{(i)}$ | Overall epistemic/metacognitive level |
| **Weighted Mean** | $\bar{K}_n^w = \frac{\sum_i w_i K_n^{(i)}}{\sum_i w_i}$ | Item-difficulty adjusted |
| **Distribution** | $P(K_n = k)$ for $k \in \{-1, 0, +1\}$ | Pattern frequencies |

#### Uncertainty Quantification

**Bootstrap Confidence Intervals:**
1. Resample $N$ items with replacement, $B = 1000$ times
2. Compute $\bar{K}_n^{(b)}$ for each bootstrap sample
3. Report 95% CI as $[\bar{K}_n^{(0.025)}, \bar{K}_n^{(0.975)}]$

**Reliability Threshold:** If CI width $> 0.3$, interpret aggregate $K_n$ with caution.

#### Statistical Properties

| Property | Condition | Guarantee |
|:---------|:----------|:----------|
| **Consistency** | $N \to \infty$ | $\bar{K}_n \to \mathbb{E}[K_n]$ |
| **Anchor Preservation** | All $K_n^{(i)} = +1$ | $\bar{K}_n = +1$ |
| **Boundedness** | Always | $\bar{K}_n \in [-1, +1]$ |
```

---

### Phase 2.4: Bootstrap CI 手順の明確化

**Issue**: Line 56 "what statistical guarantees (e.g., confidence intervals, reliability) can be obtained?"

**Action**: Phase 2.3 の Aggregation Rules 内に含める（上記参照）

---

## Phase 3: 新規セクション追加

### Phase 3.1: Brief Comparison with Epistemic Logic

**Issue**: Line 42 "how K_1/K_2 align or diverge from S5 introspection axioms"

**Location**: Related Work セクション内

```markdown
### Relationship to Formal Epistemic Logic

Classical epistemic logic (modal logic S5) assumes **idealized agents** with perfect introspection:

| Axiom | Name | Statement | Our Framework |
|:------|:-----|:----------|:--------------|
| **4** | Positive Introspection | $K\phi \to KK\phi$ | **Violated**: $K_0 = +1$ does not imply $K_1 = +1$ |
| **5** | Negative Introspection | $\neg K\phi \to K\neg K\phi$ | **Violated**: $K_0 = 0$ does not imply $K_1 = +1$ |

**Key Departure**: 

Epistemic logics model **what agents should know** under idealized conditions. Our framework models **what agents actually exhibit** under empirical observation, including systematic failures of introspection.

| Aspect | Epistemic Logic (S5) | Our Framework |
|:-------|:---------------------|:--------------|
| **Agents** | Idealized, consistent | Empirical, fallible |
| **Introspection** | Perfect (axioms 4, 5) | Imperfect (DK, Imposter) |
| **Semantics** | Modal (possible worlds) | Observational (state-based) |
| **Purpose** | Normative reasoning | Descriptive measurement |

**Complementary Use**: Epistemic logic provides normative benchmarks; our framework measures deviations from those benchmarks in real agents.
```

---

### Phase 3.2: Scope Boundary 明確化（Partial Credit, Multi-label）

**Issue**: Line 57 "How would you handle partial credit or graded correctness at K_0, multi-label truths?"

**Location**: Limitations セクション内

```markdown
### Scope Boundary: Binary vs. Graded Truth

**Current Scope**: This framework assumes **binary correctness** at $K_0$:
- Correct ($K_0 = +1$)
- Absent ($K_0 = 0$)
- Incorrect ($K_0 = -1$)

**Out of Scope (Future Work)**:

| Extension | Challenge | Potential Approach |
|:----------|:----------|:-------------------|
| **Partial Credit** | $K_0 \in (0, 1)$ requires graded reference | Probabilistic $f_0$ with continuous output |
| **Multi-label** | Multiple correct answers | Set-valued $K_0$ or soft-max embedding |
| **Graded Truth** | Degrees of correctness | Fuzzy reference with $K_0 = \text{similarity}(\text{Response}, \text{Reference})$ |

**Why Binary for Now**: Binary correctness enables clean anchor semantics and unambiguous $K_1$/$K_2$ computation. Graded extensions require principled definitions of "partial alignment" that preserve interpretability.
```

---

### Phase 3.3: Informativeness Constraint（Trivial Regress 防止）

**Issue**: Line 62 "what prevents trivial satisfaction or regress (e.g., always claiming 'not sure')?"

**Location**: Measurement Theory セクション内

```markdown
### Informativeness Constraint

**Problem**: A subject could trivially achieve $K_n = 0$ for all $n$ by always claiming "I'm not sure." This would satisfy the framework's consistency requirements without providing useful information.

**Solution**: We distinguish between **legitimate uncertainty** and **uninformative hedging** via:

1. **Response Distribution Analysis**:
   - If $P(\text{Claim}_n = \text{"not sure"}) > 0.8$ across items, flag as potentially uninformative
   - Legitimate uncertainty should correlate with item difficulty

2. **Coherence Check**:
   - Subjects with genuine uncertainty should show:
     - $K_0$ variance (some correct, some incorrect)
     - $K_1$ near 0 when $K_0$ is variable
   - Subjects gaming the system show:
     - Uniform "not sure" regardless of $K_0$ distribution

3. **Incentive Design** (Experimental):
   - Proper scoring rules that penalize uninformative claims
   - Reward calibration: higher payoff for confident-and-correct vs. uncertain-and-correct

**Formal Constraint**:
$$\text{Informativeness}(K_n) = 1 - \frac{H(K_n)}{H_{\max}} \cdot \mathbb{1}[\text{no correlation with } K_{n-1}]$$

Where $H(K_n)$ is the entropy of $K_n$ distribution. Low informativeness triggers a warning.
```

---

## Phase 4: プレゼンテーション改善

### Phase 4.1: Worked Example 追加

**Issue**: Line 55 "provide at least one worked example per pattern class"

**Location**: 27-Pattern Taxonomy セクション直後

```markdown
### Worked Examples: Representative Patterns

#### Example 1: Socratic Wisdom (Pattern #14: $K_0 = 0, K_1 = +1, K_2 = +1$)

**Scenario**: History exam, question about the date of the Treaty of Westphalia.

| Step | Observable | Value |
|:-----|:-----------|:------|
| Response | "I don't know" | — |
| Reference | 1648 | — |
| $K_0$ | Response = Absent | $0$ |
| Claim$_1$ | "I correctly identified that I don't know" | — |
| $K_1$ | Claim$_1$ aligns with $K_0 = 0$ | $+1$ |
| Claim$_2$ | "My self-assessment is accurate" | — |
| $K_2$ | Claim$_2$ aligns with $K_1 = +1$ | $+1$ |

**Interpretation**: Subject demonstrates Socratic wisdom—accurate recognition of their own ignorance.

#### Example 2: Dunning-Kruger Deep (Pattern #5: $K_0 = -1, K_1 = -1, K_2 = -1$)

**Scenario**: Math test, question "What is $\sqrt{16}$?"

| Step | Observable | Value |
|:-----|:-----------|:------|
| Response | "5" | — |
| Reference | 4 | — |
| $K_0$ | Response ≠ Reference | $-1$ |
| Claim$_1$ | "I'm confident I'm correct" | — |
| $K_1$ | Claim$_1$ contradicts $K_0 = -1$ | $-1$ |
| Claim$_2$ | "My self-assessment is reliable" | — |
| $K_2$ | Claim$_2$ contradicts $K_1 = -1$ | $-1$ |

**Interpretation**: Triple misalignment—wrong, overconfident, and unaware of overconfidence.

#### Example 3: Imposter Syndrome Aware (Pattern #22: $K_0 = +1, K_1 = -1, K_2 = +1$)

**Scenario**: Programming task, correct solution submitted.

| Step | Observable | Value |
|:-----|:-----------|:------|
| Response | Correct code | — |
| Reference | Expected output | — |
| $K_0$ | Response = Reference | $+1$ |
| Claim$_1$ | "I probably got it wrong" | — |
| $K_1$ | Claim$_1$ contradicts $K_0 = +1$ | $-1$ |
| Claim$_2$ | "I know I tend to underestimate myself" | — |
| $K_2$ | Claim$_2$ correctly identifies $K_1 = -1$ | $+1$ |

**Interpretation**: Imposter syndrome with self-awareness—knows they underestimate themselves.
```

---

### Phase 4.2: 冗長な哲学的フレーミングの削減

**Issue**: Line 27 "substantial space to rhetorical/philosophical framing; some redundancy could be reduced"

**Action**: 
1. 重複する Analogy セクションを統合
2. 重複する「What the Framework Provides/Does NOT Provide」構造を統合
3. Related Work 内の比較表の冗長な説明を圧縮

---

#### 4.2.1: 重複 Analogy の統合（4箇所→2箇所）

| 行番号 | 内容 | 対応 |
|:-------|:-----|:-----|
| L540-550 | Thermometer Calibration Analogy（詳細説明） | **維持** |
| L582-584 | Thermometer/Temperature enabling intervention | **削除**（L540と重複） |
| L1758-1761 | meta-d'/meta-I = Thermometer, $K$ = Weather map | **維持**（Related Work固有） |
| L1846-1848 | 同上（ほぼ同文） | **削除**（L1758と重複） |

**削除対象1** (Line 582-584):
```markdown
**Analogy:**

A thermometer (observation) does not itself heat or cool a room (intervention). But knowing the temperature enables targeted decisions about heating/cooling. Similarly, $K_n$ observes metacognitive states, enabling (but not specifying) targeted interventions.
```
→ 削除理由: L540-550 の詳細な Thermometer Calibration Analogy で十分にカバー

**削除対象2** (Line 1846-1848):
```markdown
**Analogy:**
- meta-d' / meta-I = **Thermometer** (measures metacognitive temperature)
- $K$ = **Weather map** (classifies metacognitive patterns, guides intervention)
```
→ 削除理由: L1758-1761 とほぼ同文（同セクション内での重複）

---

#### 4.2.2: 重複「Framework Provides/Does NOT Provide」構造の統合

| 行番号 | セクション | 内容 | 対応 |
|:-------|:-----------|:-----|:-----|
| L123-129 | Introduction 内 | 「What Provides」のみ | **維持**（前方配置で可視性高） |
| L570-582 | Observation vs Intervention 内 | 「What Provides」+「Does NOT Provide」 | **圧縮** |

**注**: L123-129 には「What the Framework **Provides**」のみ存在。「What the Framework **Does NOT Provide**」は L576-580 にのみ存在するため、完全な重複ではないが、L570-582 は冗長であり圧縮可能。

**変更対象** (Line 570-582):
```markdown
**What the Framework Provides:**

- **Coordinates** for locating epistemic states
- **Taxonomy** for classifying metacognitive patterns
- **Outcome measures** for evaluating interventions

**What the Framework Does NOT Provide:**

- **Causal model** of how interventions change $K_n$
- **Mechanism** by which metacognition operates
- **Prescriptions** for which interventions to use
```
→ **変更後**:
```markdown
**Framework Scope** (see Introduction for full list):

The framework provides **coordinates, taxonomy, and outcome measures** for epistemic states. It does **not** provide causal models, mechanisms, or intervention prescriptions.
```

---

#### 4.2.3: Related Work 比較セクションの圧縮

Line 1794-1876 に4つの **Comparison** テーブルと3つの **Complementary Relationship** パラグラフが存在。

**現状の問題**:
- 各比較で「$K$ adds beyond...」「$K$ specifically targets...」の類似主張が繰り返される
- 冗長なテーブル構造

**統合案**:

**削除対象** (各 Comparison 後の説明文の圧縮):

1. Line 1807-1812 (meta-d' Complementary Relationship):
   - 「These approaches are **not mutually exclusive**...」から始まる段落
   - → 1文に圧縮: 「meta-d' and $K$ are complementary: use meta-d' for aggregate sensitivity, $K$ for per-item classification.」

2. Line 1862 (Calibration Complementary Relationship):
   - → 削除（meta-d'との関係説明で既にカバー）

3. Line 1876 (Dempster-Shafer Complementary Relationship):
   - → 1文に圧縮: 「Dempster-Shafer addresses uncertainty quantification; $K$ addresses metacognitive discrepancy.」

---

#### 4.2.4: 削減見積もり

| カテゴリ | 現状行数 | 削減行数 | 残存行数 |
|:---------|:--------:|:--------:|:--------:|
| 重複 Analogy | 12行 | 6行 | 6行 |
| 重複 Framework 構造 | 20行 | 15行 | 5行 |
| 比較セクション冗長 | 30行 | 15行 | 15行 |
| **合計** | **62行** | **36行** | **26行** |

**推定削減**: 約36行（2142行 → ~2106行）

---

#### 4.2.5: 実装ガイドライン

1. **安全優先**: 削除前に各パターンの前後文脈を確認し、情報損失がないことを検証
2. **統合優先**: 単純削除より「1箇所に統合して他を参照」を優先
3. **内容保持**: 独自の情報（例: 具体的数式）がある場合は削除せず凝縮
4. **順序**: 他の Phase 完了後に実施（追加内容との整合性確認のため）

---

## Implementation Order

```
Phase 1.1 (Executive Summary)
    ↓
Phase 1.2 (Correspondence Table 移動)
    ↓
Phase 1.3 (Latent Variable Model 移動)
    ↓
Phase 2.1 (State_2 表完全化)
    ↓
Phase 2.2 (Alignment 定義)
    ↓
Phase 2.3 (Aggregation Rules)
    ↓
Phase 3.1 (Epistemic Logic)
    ↓
Phase 3.2 (Scope Boundary)
    ↓
Phase 3.3 (Informativeness)
    ↓
Phase 4.1 (Worked Examples)
    ↓
Phase 4.2 (冗長削減)
```

---

## Reviewer Question Response Mapping

| Question | Response Location |
|:---------|:------------------|
| Q1: intermediate values | Phase 1.3 (Latent Variable Model 移動) |
| Q2: 27 patterns enumeration | Phase 1.1 (Executive Summary) + 既存表 |
| Q3: aggregation procedure | Phase 2.3 (Aggregation Rules) |
| Q4: partial credit | Phase 3.2 (Scope Boundary) |
| Q5: K_1 from predicted K_0 | 既存 Identifiability セクション |
| Q6: meta-d' relation | Phase 1.2 (Correspondence Table 移動) |
| Q7: formal properties | 既存 Axioms セクション |
| Q8: reference uncertainty | 既存 Handling Reference Uncertainty |
| Q9: trivial regress | Phase 3.3 (Informativeness) |
| Q10: simulation | Future Work として明示維持 |
| Q11: cross-study comparability | 既存 Cross-Study Comparability |
| Q12: multi-agent, DEL | Phase 3.1 (Epistemic Logic) 末尾で言及 |

---

## Expected Outcome

この revision により：

1. **誤検出の解消**: 重要な表・定義が冒頭に配置され、システムが認識可能に
2. **軽微な追加**: State$_2$表完全化、Aggregation Rules、Epistemic Logic比較
3. **明確なScope**: シミュレーション/実証は Future Work として維持
4. **可読性向上**: Worked examples、冗長削減

**予想されるレビュー改善**:
- "27 patterns not enumerated" → 解消
- "intermediate values not specified" → 解消
- "omits meta-d', IRT" → 解消
- "aggregation rules missing" → 解消
- "trivial regress" → 解消
