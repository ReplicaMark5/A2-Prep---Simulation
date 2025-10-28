The exam duration is **three hours** and it counts out of **180 marks** for both A2 and A3.

---

## I. General Preparation Principles

When preparing for A2, you should adhere to the following principles:

*   **Practice Questions:** Make sure you can **do all the tutorial questions**. You must be able to do them "with eyes closed".
*   **Class Examples:** Make sure you can do the **examples done in class**.
*   **Theory:** **Study the theory**.
*   **Survival Kits:** **Use the Survival kits** at the end of each chapter. The kits summarize what the lecturer would study.
*   **Topic Recognition:** Refer to the **TOC (Table of Contents) of the eBook** and see if you can recognize every topic. If you can recognize the topics, you will be fine.
*   **Do Not "Spot":** Do not "spot" certain topics; **all work is covered** except where indicated otherwise.
*   **Old Materials Warning:** Old papers might help, but the content has "moved on". Notes from previous years are in circulation, but be aware that **some of their model answers are wrong**.

---

## II. What You Do Not Need to Memorize (Exclusions/Provisions)

| Requirements/Exclusions                                                                                                                                                                                             | A2 Status           | A3 Status           |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :------------------ | :------------------ |
| Tables with statistical values **will be provided**.                                                                                                                                                                | Provided            | Provided            |
| A **formula sheet** similar to the one in A1 will be provided.                                                                                                                                                      | Provided            | Provided            |
| No need to calculate **$t$ or $\nu$** (p. 77 in eBook).                                                                                                                                                             | Excluded            | Excluded            |
| **SimTalk syntax** is **not required**. Logic can be explained using **pseudo-code**, if asked.                                                                                                                     | Excluded            | Excluded            |
| You do **not need to know the TPS objects** (like buffer or prompt definitions).                                                                                                                                    | Excluded            | Excluded            |
| **Procedure Kim-Nelson (KN):** Know the **properties**, but **not the formulas or detailed steps**. You must be able to explain what it does and why. [[ebook.pdf#page=81&selection=157,0,157,24&color=note\|p.81]] | Properties Required | Properties Required |
| **Monte Carlo (M-C)** and **Contaminating System (NTS)**.                                                                                                                                                           | Excluded            | Excluded            |
| **Kolmogorov–Smirnov (K-S) test**.                                                                                                                                                                                  | Excluded            | Included            |

---

## III. Core Study Content Areas

### A. Models (Questions 3–9, 103 Marks)

**All models** are covered, including the elusive **Model 0** (the drive-through/McDonald's/McD model).

You need to know the models very well and be prepared to **Explain, Why, How, Apply, and Calculate $n^*$**.

| Concept | Required Understanding | Source |
| :--- | :--- | :--- |
| **Theory Application** | Work through the models and think what **theory might be applicable**. | |
| **Dynamics** | **Understand the dynamics** (e.g., McDonald’s is effectively also a **Buffer Allocation Problem (BAP)**). | |
| **Throughput Upper Bounds** | Understand why **all the models have upper bounds for their throughput** (limited by the source/tap). | |
| **Buffer Sizing (BAP)** | Know what would happen if the **BAP buffer sizes are all increased to $\infty$**. | |
| **Trauma Unit Model (TUM)** | Identify the **entity/entities** and **attributes**. Explain why the trauma unit can be considered a **production line**. | |
| **Shannon’s World View** | Know how to **apply Shannon’s world view to the TUM**. | |
| **Events** | An event is something that occurs at a **point in time** (e.g., Patient arrives/leaves, Doctor starts/finishes seeing patient, Customer joins/exits Q). It is *not* a process like "prepare the food". | |
| **System State Variables** | Know how to describe the system state, such as throughput or machine utilization at time T. This relates to the input/output table used in tutorials. | |

### B. Input Data Analysis (Question 2, 36 Marks)

Question 2 covers: $\chi^2$ (chi-squared test) and **inverse transform**.

| Concept                                   | Required Understanding                                                                                                                                                                                                                                                 | Source |
| :---------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----- |
| **Inverse Transform**                     | Ask yourself: Do I know what continuous or discrete inverse transform is about? Can I write something down?.                                                                                                                                                           |        |
| **Processing Count-based Failures (ODF)** | Know what ODF is (failure dictated by number of product cycles) and what type of variable it is (a **discrete random variable**).                                                                                                                                      |        |
| **Simulation-Optimization**               | Know what $\xi$ refers to (the stochastic elements of the problem, e.g., processing times, failure rates, repair times in BAP).                                                                                                                                        |        |
| **Decision Variables ($x$ and $\Omega$)** | Referencing Section 6.6: Know that **$\Omega$** is the **set of possible input values/combination of buffer sizes** (the decision space boundary/range). **$x$** is any **specific combination of decision variables** (e.g., a single row in the Experiment Manager). |        |

### C. Algorithms and Procedures

| Algorithm/Procedure        | Required Knowledge                                                                                                                                                                                                                                              | Source |
| :------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----- |
| **Genetic Algorithm (GA)** | Must be known in terms of: **cross-over**, **mutation**, **choice of population size** (related to **exploration**), and **choice of number of generations** (related to **exploitation**).                                                                     |        |
| **Kim-Nelson (KN)**        | Know the **properties** and be able to explain **what it does and why**. Note that KN only does enough replications to separate scenarios, unlike ANOVA which has a fixed number of replications. [[ebook.pdf#page=81&selection=157,0,157,24&color=note\|p.81]] |        |

### D. Output Analysis (Question 10, 8 Marks)

Question 10 covers: **$h$ (half-width)**, **$n^*$ (required sample size calculation)**, and **MOO (Multi-Objective Optimization)**.

*   **Experiment Manager (EM) Results:** The results of the EM are important, specifically their **interpretation, links to theory, and the $p$-table**. 
*   **P-table Interpretation:** You will receive a P-table question (e.g., five scenarios) and must select the best scenario based on $p$-values (e.g., selecting experiments that are statistically similar to the best performer if $p > 0.05$). [[ebook.pdf#page=78&selection=161,0,162,1&color=important|p.78]]
*   **Pareto-Optimality:** Be able to determine a **Pareto-optimal set of solutions** for bi-objective optimization (e.g., minimizing total WIP and maximizing Throughput).

### E. Validation and Conceptual Questions

*   **Validation Aim:** Understand how to make the model simpler but **still represent the real world adequately**. The goal is **adequate representation**, not "accurate" representation.
*   **Validation Tests:** Be able to explain validation considerations, such as **changing buffer sizes and explaining the throughput observed** (e.g., identifying minimum and maximum throughput bounds). When giving validation considerations, **do not list the theoretical points** as in the notes, but discuss specifics as done in the tutorials. [[Validation]]
*   **Non-Negotiable Features:** Know which real-world features **MUST be included** in the model.

#### Key Validation Catches to Study:

1.  **Trauma Unit Problem (TUP):** Why was the model invalid if the option "Worker stays here after completing the job" was checked? (Because the doctor/nurse must go scrub/restroom afterward).
2.  **(r, Q) Model:** Why was the total inventory cost still high when $r$ and $Q$ both had low values? (Because reordering frequently is expensive, even if inventory levels are low).

---

## IV. Paper Layout Overview (180 Marks Total)

The format for both A2 and A3 is similar.

| Question  | Content Focus           | Marks [A2/A3] | Required Actions (Keywords)                              | Source |
| :-------- | :---------------------- | :------------ | :------------------------------------------------------- | :----- |
| **Q1**    | **Theory**              |               | Define, Explain, List, Why?, How did you...?             |        |
| **Q2**    | **Input Data Analysis** |               | $\chi^2$, inverse transform, ODF, $x$ and $\Omega$       |        |
| **Q3–Q9** | **ALL Models**          |               | Explain, Why, How, Apply. Entity states. Calculate $n^*$ |        |
| **Q10**   | **Output Analysis**     |               | $h$, $n^*$, MOO                                          |        |

---
-[chat gpt](https://chatgpt.com/share/68ff69c5-1bd0-8013-b1d9-fcb5841bfc3a)