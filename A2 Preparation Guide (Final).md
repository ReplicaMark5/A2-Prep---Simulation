**Exam Duration:** 3 hours  
**Total Marks:** 180

---

## I. General Preparation Principles

- Do all **tutorial questions** until you can perform them without notes.
    
- Revise all **class examples**.
    
- Study the **theory** supporting each practical question.
    
- Use the **Survival Kits** at the end of chapters.
    
- Check the **Table of Contents** in the eBook and ensure topic recognition.
    
- Do **not “spot”** topics. Everything is examinable unless stated otherwise.
    
- Treat **old notes cautiously**. Some legacy model answers are wrong or outdated.
    

---

## II. What You Do Not Need to Memorize

| **Item**                                                                                     | **A2**                                                       | **A3**                                                       |
| :------------------------------------------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| Statistical tables                                                                           | <span style="color:rgb(0, 112, 192)">Provided</span>         | <span style="color:rgb(0, 112, 192)">Provided</span>         |
| Formula sheet (as in A1)                                                                     | <span style="color:rgb(0, 112, 192)">Provided</span>         | <span style="color:rgb(0, 112, 192)">Provided</span>         |
| $t$ or $\nu$ calculations [[ebook.pdf#page=77&selection=202,0,203,1&color=red\|ebook, p.77]] | Excluded                                                     | Excluded                                                     |
| SimTalk syntax                                                                               | Excluded                                                     | Excluded                                                     |
| TPS object definitions                                                                       | Excluded                                                     | Excluded                                                     |
| Monte Carlo & Contaminating System (NTS)                                                     | Excluded                                                     | Excluded                                                     |
| Kolmogorov–Smirnov (K–S) test                                                                | Excluded                                                     | <span style="color:rgb(0, 176, 80)">Included</span>          |
| Procedure Kim–Nelson (KN)                                                                    | <span style="color:rgb(112, 48, 160)">Properties only</span> | <span style="color:rgb(112, 48, 160)">Properties only</span> |

---

## III. Core Study Areas

### 1. Theory — Q1 (33 Marks)

- Keywords: _Define, Explain, List, Why?, How did you … ?_
    
- Covers simulation fundamentals, conceptual reasoning, and model understanding.
    
- Expect questions linking **theory to model logic** (e.g., why throughput behaves a certain way).
    

---

### 2. Input Data Analysis: χ², Inverse Transform — Q2 (36 Marks)

Focus on:

- **Chi-squared test (χ²)** for testing distributional fit. [[ebook.pdf#page=50&selection=131,0,131,20&color=note|p.50]]
    
- **Inverse transform sampling** for generating random variables (continuous and discrete).[[ebook.pdf#page=37&selection=88,0,88,26&color=note|p.37]]
    

> [!abstract] Supporting notes
>  *context only, not necessarily direct questions*:
> - **ODF** — discrete variable based on failure counts.
>     
> - **Decision variables and space:** [[ebook.pdf#page=97&selection=154,0,154,48&color=note|p.97]]
>     
>     - $x$ = specific decision variable combination. <span style="color:rgb(0, 176, 80)">(a single solutions combination of decision variables)</span>
>         
>     - $\Omega$ = decision space (all possible $x$). <span style="color:rgb(255, 0, 0)">(set of all feasible combinations of decision variables)</span>
>         
> - **ξ** — stochastic components such as service or failure times.
>     

> [!missing] Excluded
> Monte Carlo, K-S test.

---

### 3. Models — Q3–Q9 (103 Marks)

Know **Model 0 (Drive-through / McD)** and all other models.
[[Model 0 Transcript]]

| Concept                             | Focus                                                                                        |
| :---------------------------------- | :------------------------------------------------------------------------------------------- |
| **Throughput limits**               | All models capped by source (tap) rate.                                                      |
| **Buffer Allocation Problem (BAP)** | Behaviour as buffers → ∞.                                                                    |
| **Trauma Unit Model (TUM)**         | Identify entities and apply Shannon’s world view. [[DES (Shannon & Entity States)\|DES]]<br> |
| **Events**                          | Instantaneous occurrences (arrive, start, finish, leave).                                    |
| **System State Variables**          | Throughput, WIP, utilization over time.                                                      |
| **Validation inside models**        | Recognise throughput effects when configuration changes.                                     |

---

### 4. Validation and Conceptual Questions

Goal: _Adequate_ representation, not “accurate.” 
Discuss real tests, not theory lists.
Reference notes: [[Validation]]

| Model                         | Validation Focus                                                          |
| :---------------------------- | :------------------------------------------------------------------------ |
| **TUP (Trauma Unit Problem)** | “Stay here after job” invalidates model logic — must leave to scrub/rest. |
| **(r, Q) Inventory Model**    | Low r and Q can still cause high total cost (frequent ordering).          |
| **Buffer sizing**             | Observe upper/lower throughput bounds when changing buffers.              |

---

### 5. Output Analysis — Q10 (8 Marks)

- **Half-width ($h$)** and **required sample size ($n^*$)** interpretation.
    
- **Multi-Objective Optimization (MOO):** identify Pareto-optimal trade-offs.
    
- **p-Table:** [[ebook.pdf#page=78&selection=161,0,162,1&color=important|p.78]] and [[P-table and Anova | notes]]
    
    - A **pairwise comparison** table, _not_ ANOVA.
        
    - Interpret p-values:
        
        - `p > 0.05` → no significant difference.
            
        - `p ≤ 0.05` → significant difference.
            
    - Used to identify statistically similar or superior systems.
        
- **Experiment Manager (EM):** outputs and interpretation are examinable.
    

---

### 6. Algorithms and Procedures

| Procedure                                                                                   | Required Knowledge                                                                                                                                             |
| :------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Genetic Algorithm (GA)** [[Genetic Algorithm \| GA]]                                      | Crossover / mutation / population size ↔ exploration; generations ↔ exploitation.                                                                              |
| **Procedure Kim–Nelson (KN)** [[ebook.pdf#page=81&selection=157,0,157,24&color=note\|p.81]] | A _procedure_ performing _just enough replications_ to separate systems statistically — contrasts with ANOVA’s fixed replications. Know properties, not steps. |

---

## IV. Paper Layout

|Q|Content|Marks|Focus|
|:-:|:--|:-:|:--|
|**1**|Theory|33|Define, Explain, List, Why?, How …|
|**2**|Input Data Analysis|36|χ², Inverse Transform|
|**3–9**|Models|103|Model 0, TUM, BAP, (r,Q), Events, Validation|
|**10**|Output Analysis|8|h, n*, MOO, p-table interpretation|

---
### Final Advice

- Understand _why_ systems behave as they do.
    
- Link observations to throughput, variability, and adequacy of representation.
    
- Apply reasoning, not recall.