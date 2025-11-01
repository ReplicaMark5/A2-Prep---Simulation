_Source: Sim442 / Output Data Analysis notes + textbook Chapter 5_
_Context: All examinable content for Output Data Analysis (Sim442)_

---

## 🎯 Purpose of Output Data Analysis
To decide **whether simulation scenarios differ statistically** — determining if differences in means are due to **random variation** or **real performance differences**.

---

## 1️⃣ Key Statistical Tools

| Test | Use Case | Core Idea |
|------|-----------|-----------|
| **t-test (Welch’s)** | Compare **two** independent scenarios | Tests if their mean difference = 0 |
| **ANOVA (Analysis of Variance)** | Compare **three or more** scenarios | Tests if at least one mean differs |
| **K-N (Kim–Nelson)** | Sequential selection | Finds best scenario with confidence (1−α) |

---

## 2️⃣ The Welch Two-Sample t-test

> [!learn] When to use  
> - Comparing **two sets of results** (e.g., Scenario 1 vs Scenario 2)  
> - Variances are **unknown and unequal**  
> - Observations are **independent** and **normally distributed**

### Hypotheses
$$H_0: \mu_1 - \mu_2 = 0$$  
$$H_1: \mu_1 - \mu_2 \neq 0$$

### Formula
$$t = \frac{(\bar{x}_1 - \bar{x}_2)}{\sqrt{(s_1^2/n_1)+(s_2^2/n_2)}}$$

### Degrees of Freedom
$$v = \frac{(\frac{s_1^2}{n_1}+\frac{s_2^2}{n_2})^2}{\frac{(\frac{s_1^2}{n_1})^2}{n_1-1} + \frac{(\frac{s_2^2}{n_2})^2}{n_2-1}}$$

---

## 3️⃣ Decision Process

> [!danger] LEARN  
> 1. **Calculate or read** t, v, and p-value.  
> 2. **Find critical t-value** for α=0.05 (two-tailed):  
>    $$t_{critical} = t_{0.975, v}$$  
> 3. **Decision rule**  
>    - If |t| > t₍critical₎ or p < 0.05 → Reject H₀  
>    - Else → Fail to reject H₀

> [!tip] Exam focus  
> You don’t need to calculate everything by hand — but must **recognise**, **apply**, and **interpret** results correctly.

---

## 4️⃣ Example Pattern

| Output | Value |
|--------|-------|
| Mean V1 | 0.5189 |
| Mean V2 | 0.4396 |
| t-stat | 0.9386 |
| df | 39 |
| p-value | 0.3537 |
| α | 0.05 |
| Decision | Fail to reject H₀ |

🧠 **Interpretation:** The two scenarios do **not differ significantly** — any observed difference is likely random.

---

## 5️⃣ ANOVA (Analysis of Variance)

> [!learn] When to use  
> Compare **three or more** scenario means (e.g., S1, S2, S3).  
> Tests if all means are equal using an **F-test**.

### Hypotheses
$$H_0: \mu_1 = \mu_2 = \mu_3 = \dots = \mu_k$$  
$$H_1: \text{At least one } \mu_i \text{ differs}$$

If ANOVA finds a difference, perform **post-hoc tests** (Tukey, Scheffé, or Bonferroni-adjusted t-tests).

> [!example] Textbook Context  
> The “Example of t-test” in the ANOVA section shows **pairwise Welch t-tests** (S1 vs S2, S1 vs S3, etc.) — a **simplified ANOVA implementation** that mirrors how Tecnomatix outputs pairwise comparisons.

---

## 6️⃣ Relationship Between F-test and t-test

> [!summary] Key Takeaway  
> The **F-test** and **t-test** are related but not always paired — they serve different roles in hypothesis testing.

### When Each Test Is Used
| Scenario | Appropriate Test | Purpose |
|-----------|------------------|----------|
| Two groups | **t-test** | Checks if their means differ significantly |
| Three or more groups | **ANOVA (F-test)** | Checks if *any* group means differ |

> [!learn]  
> The **t-test** is a *special case of ANOVA* when only two groups exist — the F-test and t-test yield identical results.

### Workflow Logic
1. **Run ANOVA (F-test)** → checks if any difference exists.  
2. **If F is not significant:** stop — all means are statistically similar.  
3. **If F is significant:** perform **pairwise t-tests** (or Tukey/Scheffé) to locate specific differences.

> [!tip] Exam Simplification  
> In Sim442, Tecnomatix automates the F-test internally and outputs the **pairwise Welch t-test results**.  
> When you perform t-tests manually, you are **replicating exactly what Tecnomatix shows**, not an extra step after it.

---

## 7️⃣ Multiple Comparisons and Bonferroni Correction

> [!danger] LEARN  
> Running many t-tests increases the **Type I error** (false positives).  
> Use the **Bonferroni correction**:  
> \[
\alpha' = \frac{\alpha}{k}
\]
> where \(k\) = number of pairwise comparisons.

---

## 8️⃣ Key Interpretation Skills for Exam

| Concept | You must be able to… |
|----------|----------------------|
| Hypotheses | Write H₀ and H₁ clearly |
| Test type | Identify correct test (t-test vs ANOVA) |
| Assumptions | Recall independence, normality, unequal variances |
| P-value logic | Interpret correctly |
| Decision | Use critical values or p-value rule |
| Output interpretation | Read provided Excel or table results |

---

## 9️⃣ Exam Guidance (from lecturer)

> - Formula sheet + statistical tables **will be provided**.  
> - Focus on **concepts, test selection, and interpretation**.  
> - Expect **summarised data** (means, variances, etc.), not raw data.  
> - ANOVA questions may ask you to perform **pairwise t-tests manually**.

---

### ✅ Quick Recap
- **Two samples → Welch t-test**  
- **Three or more → ANOVA (F-test)**  
- ANOVA uses F-test internally, but you interpret pairwise results via **t-tests**.  
- Know how to **state hypotheses**, **select the correct test**, and **interpret p-values**.

---

## 🧩 Terminating vs Non-Terminating Systems (TS vs NTS)

**Terminating System (TS):**
- Has a clear end (finite run time).  
- Estimate mean + CI using independent replications.  
- Determine required replications \(n^*\) using CI half-width formula.

**Non-Terminating System (NTS):**
- Continuous system (no natural end).  
- Remove **transient period** → find truncation point \(t_0\).  
- Two main analysis methods:  
  1. **Replication/Deletion:** multiple long runs, discard warm-up.  
  2. **Batch Means:** divide one long run into \(k\) independent batches after \(t_0\).

**Correlation & Batch Size:**
- Adjacent data correlated → use correlogram to find lag ≈ 0.  
- Batch size must be large enough for batch means to be independent.

---

📚 *End of Output Data Analysis Summary*

---
https://chatgpt.com/share/6904b716-78d4-8013-aaf1-1bcbcc202fe4