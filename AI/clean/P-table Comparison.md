# 🧾 Tutorial 7 — Question 4: Throughput Maximisation (p-Value Interpretation)

_Source: Sim442 / Tutorial 7 — Question 4 (“Model 0” Simulation Output Analysis)_ [[Sim442_Tut07_2025_Questions.pdf#page=2&selection=27,0,28,1&color=note|Sim442_Tut07_2025_Questions, p.2]]

---

## 🧩 Question 4 

> Refer to the output of the **Model 0 simulation** below.  
> In this example, Experiment 1 has one cook, Experiment 2 has two cooks, and so forth.  
> You want to **maximise the throughput**.  
> What is the **best number of cooks** to use if the arrival rate is **0.5 arrivals/minute**?  
> Explain your answer.

---

## 📊 Simulation Results Summary

| Experiment | Mean Throughput | Std. Deviation | 95% CI Lower | 95% CI Upper |
|-------------|-----------------|----------------|---------------|--------------|
| Exp 1 | 27.7 | 4.79 | 25.46 | 29.94 |
| Exp 2 | 53.5 | 8.98 | 49.30 | 57.70 |
| Exp 3 | 70.55 | 9.93 | 65.90 | 75.20 |
| Exp 4 | 77.15 | 10.50 | 72.24 | 82.06 |
| Exp 5 | 78.2 | 11.20 | 72.96 | 83.44 |
| Exp 6 | 74.05 | 11.15 | 68.83 | 79.27 |

---

## 🧮 Pairwise t-Test p-Value Table

| Comparison | Exp 2 | Exp 3 | Exp 4 | Exp 5 | Exp 6 |
|-------------|--------|--------|--------|--------|--------|
| **Exp 1** | 0 | 0 | 0 | 0 | 0 |
| **Exp 2** | — | 0 | 0 | 0 | 0 |
| **Exp 3** | — | — | 0.048 | 0.028 | 0.301 |
| **Exp 4** | — | — | — | 0.761 | 0.371 |
| **Exp 5** | — | — | — | — | 0.248 |

\* Significance level α = 0.05

---

## ⚖️ Decision Rule

> - **p < 0.05 → Significant difference** (reject H₀)  *`Based on statistical evidence collected`*
> - **p ≥ 0.05 → Not significant** (means statistically similar)

---

## 🧠 Step-Down Reasoning — *Top-Down p-Value Interpretation*

> The analysis begins from the configuration with the **highest mean throughput** and moves downward, interpreting p-values until a significant difference is found.
> This saves time and avoids unnecessary pairwise comparisons.
> Note: You're **interpreting** the p-values from Welch t-tests that Tecnomatix already computed, not performing the tests yourself.

### Step 1 – Rank Configurations by Mean Throughput

| Rank | Experiment | Mean Throughput |
|------|-------------|-----------------|
| 1 | Exp 5 | 78.2 |
| 2 | Exp 4 | 77.15 |
| 3 | Exp 6 | 74.05 |
| 4 | Exp 3 | 70.55 |
| 5 | Exp 2 | 53.5 |
| 6 | Exp 1 | 27.7 |

---

### Step 2 – Sequential Comparison (α = 0.05)

#### **Exp 5 vs Exp 4**
- p = 0.761 → **Not significant**  
- Means statistically similar.  
- Exp 4 has slightly lower mean (similar throughput, fewer resources).  
→ **Exp 4 preferred**.

#### **Exp 4 vs Exp 6**
- p = 0.371 → **Not significant**  
- Similar performance → Exp 4 remains preferred.

#### **Exp 4 vs Exp 3**
- p = 0.048 → **Significant difference**  
- Exp 4 is statistically superior.

✅ At this point, Exp 4 is **not significantly different from higher configurations** but **significantly better** than all lower ones — so it is the **best choice**.

---

## 🏁 Conclusion

- **Top group (not significantly different):** Exp 4 ≈ Exp 5 ≈ Exp 6
  - **Evidence:** p(5,4)=0.761, p(4,6)=0.371 → all p ≥ 0.05
  - These three configurations are **statistically indistinguishable** in performance
- **Lower group (significantly worse):** Exp 1 – Exp 3
  - **Evidence:** p(4,3)=0.048 < 0.05 → significantly different
- Throughput rises rapidly up to **4 cooks (Exp 4)**, then **plateaus**
- Adding more cooks (5 or 6) gives **no significant improvement**

> ✅ **Best number of cooks = 4 (Experiment 4)**
> – Maximises throughput efficiently with **fewer resources** than Exp 5 or 6
> – Part of top-performing group {4,5,6} but uses minimal resources

---

## 🧩 Learning Note — *Top-Down p-Value Interpretation Method*

> [!learn] Quick Manual Procedure
> 1. Rank all configurations by mean performance.
> 2. Start with the highest mean.
> 3. Interpret p-values sequentially downward.
> 4. Stop when a significant difference is found (p < 0.05) — the previous configuration is optimal.
> 5. No need to examine all lower pairs.

> [!tip] What This Method Actually Is
> - **"Top-down"** describes your **comparison sequence** (highest to lowest).
> - **"p-value interpretation"** describes what you're doing (reading pre-computed results).
> - **Tecnomatix already performed** the pairwise Welch t-tests — you're just interpreting the p-value matrix.
> - Tecnomatix does **not** perform full ANOVA F-tests; it directly provides pairwise two-sample t-test p-values.
> - This sequential interpretation approach is approved in simulation output evaluation (Rossetti, 2020; Kelton et al., 2019; textbook Ch. 5).

---

📘 **Exam Takeaway:**
Use the **top-down p-value interpretation method** to efficiently find the best configuration.

**Exam Writing Strategy:**
1. **Identify the top group** by showing 2-3 key p-values (e.g., p(5,4)=0.761, p(4,6)=0.371)
2. **State "not significantly different"** for the top group (all p ≥ 0.05)
3. **Show the break point** where significance appears (e.g., p(4,3)=0.048 < 0.05)
4. **Justify with "fewer resources"** — choose minimal resources within the top group

**Efficiency:** This method requires checking only **3-5 p-values** instead of all pairwise comparisons (e.g., **3 checks vs 15 pairs** in a 6-experiment table = **80% time saved**).

| Step | What's Happening | Who Does It |
|------|------------------|-------------|
| 1 | Multiple replications per experiment | Tecnomatix runs simulations |
| 2 | Pairwise Welch t-tests computed | Tecnomatix computes p-values |
| 3 | p-value interpretation | **You interpret the matrix** |
| 4 | Top-down sequential comparison | **You apply this strategy** |
