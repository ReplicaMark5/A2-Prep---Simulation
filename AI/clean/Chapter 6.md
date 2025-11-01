**Chapter 6 – Optimisation with Simulation (Simulation-Optimisation & GA)**
_Source: Lecture 6 (pp. 85–103) + Transcript (A2 Prep Lecture) + Tut 08 Q1–Q6 + Memo_

---

## 🎒 Survival Kit — Chapter 6 Requirements

> [!abstract] What You Must Know for Assessment
> **Optimise your SO skills** and ensure you have the following in your assessment pack:

### Core Requirements

1. **Combinatorial Nature**
   - Understand the combinatorial nature of optimisation problems

2. **Simulation-Optimisation (SO)**
   - Understand the principles of simulation-optimisation (SO) and define it

3. **Meta-Heuristics**
   - Understand meta-heuristics, and that they provide good, but not necessarily optimal solution(s), in relatively short time
   - ⭐ **It is important to understand Figure 6.1**

4. **Genetic Algorithm (GA)** ⭐
   - You must know the basic working of the GA
   - Know its parameters:
     - Population size
     - Number of generations
     - Termination conditions
     - Mutation and selection
     - Cross-over

5. **Multi-Objective Optimisation (MOO)**
   - You must define the MOO problem
   - Understand the concept of dominance
   - Understand the Pareto set

6. **MOSO (Multi-Objective Simulation-Optimisation)**
   - Understand and define MOSO

7. **Computational Burden & Approximate Solutions** ⭐
   - Always keep in mind that in SO, we can only estimate an **approximate Pareto set**
   - Understand that a **computational burden** is associated with SO
   - ⭐ **The concepts illustrated in Figure 6.11 are very important to understand**

8. **Pareto Ranking**
   - You must be able to do Pareto ranking of solutions

⭐ = Explicitly emphasized in survival kit

---

## 🧩 Overview

> [!summary] What "Optimisation with Simulation" Means
> **Simulation-Optimisation (SO)** uses a *simulation model* to **evaluate performance** and a *meta-heuristic optimiser* (like a **Genetic Algorithm**) to **search for good input settings**.
> The simulation provides estimates; the optimiser adjusts the inputs until no major improvement occurs.

> [!info] Exam Context
> **Q10 Coverage**: Output Analysis – $h$, $n*$, MOO, etc. (**8 marks total**)
> **Lecturer emphasis**: "GA must be known... conceptually" - no coding, no detailed calculations
>
> _Source: A2 Exam Study Summary + Lecture Transcript_

---

## 1 | Combinatorial Nature of Optimisation Problems

> [!info] Survival Kit Requirement #1
> "Understand the combinatorial nature of optimisation problems."
> **Depth needed**: Conceptual understanding only

> [!note] Concept
> In realistic systems (e.g., number of doctors, nurses, or buffer sizes), each input can take several discrete values.
> Combining them creates an **enormous search space** → manual enumeration becomes impossible.

**Example:**
If three inputs each have 5 options → $5^3 = 125$ possible combinations.
- With 10 variables and 5 options each → $5^{10} = 9,765,625$ possibilities!

---

## 2 | Principles & Definition of Simulation-Optimisation (SO)

> [!info] Survival Kit Requirement #2
> "Understand the principles of simulation-optimisation (SO) and define it."
> **What you need**: Clear definition + understand the feedback loop (Fig. 6.1)

> [!note] Definition
> **Simulation-Optimisation** = the use of *simulation* to evaluate performance for each candidate design, combined with an *optimisation algorithm* to find the best or near-best settings.

**Workflow (see Fig. 6.1):**
1. Choose decision variables (inputs).
2. The optimiser proposes a set of values.
3. Simulation runs n* replications → returns mean performance + CI.
4. Optimiser uses the result to pick the next set.
5. Stop when termination criteria are met.

![[figure 6.1.png]]
*Figure 6.1: Simulation-Optimisation feedback loop with meta-heuristic*

**Purpose:**  
Find an **approximate best** solution when analytical models are too complex or stochastic.

---

## 3 | Meta-Heuristics — Why They Matter

> [!info] Survival Kit Requirement #3
> "Understand meta-heuristics, and that they provide good, but not necessarily optimal solution(s), in relatively short time. It is important to understand **Figure 6.1**."
> **Focus**: Why they're needed, what they do (not how to code them)

> [!note] Definition
> A **meta-heuristic** is a high-level search procedure that guides lower-level heuristics to explore large solution spaces.
> They **don't guarantee global optima**, but give **good solutions fast**.

**Examples:** Genetic Algorithm (GA), Simulated Annealing, Tabu Search, Particle Swarm Optimisation (PSO).

**Why Essential for Simulation-Optimisation:**
- Each simulation run is computationally expensive
- The objective function $f(x,\xi)$ is **not explicit** — it only exists as simulation output
- No closed-form expression → **can't take derivatives**
- No analytical constraints → **can't use gradient-based methods**
- Must treat the simulation model as a **black box** that returns performance estimates
- Meta-heuristics search by **comparing results**, not by mathematical optimization

---

## 4 | Genetic Algorithm (GA) — Core Mechanics

> [!info] Survival Kit Requirement #4
> "You must know the basic working of the GA, its parameters (population size, number of generations, termination conditions, mutation and selection and cross-over)."
> **Exam scope**: Conceptual only - no manual iterations, no coding

> [!quote] Lecturer's Exact Words (from transcript)
> "Then the **GA must be known**, the genetic algorithm. You must know what **crossover is notation**, the choice of **population size and number of generations**. Those two are **very important**. It's about **exploration and exploitation**...
>
> **Explore is how wide you look** and **exploit is about how do you utilize the information** so explore is about the **population size** of exploit is about a **number of generations**. How many times you allow that algorithm to learn at the cost of computational effort?"
>
> _— Lecturer, A2 Prep Lecture_

### 🔹 Basic Working
1. **Encoding** – represent each solution as a string (chromosome).  
2. **Initial Population** – random set of candidate solutions.  
3. **Evaluation** – run simulation for each; record objective values.  
4. **Selection** – choose better individuals for reproduction.  
5. **Crossover** – exchange segments between parents to create offspring.  
6. **Mutation** – randomly flip bits or adjust parameters to preserve diversity.  
7. **Replacement** – form the new generation.  
8. **Termination** – stop after N generations or when improvement < threshold.

### 🔹 Key Parameters
| Parameter | Meaning | Role |
|------------|----------|------|
| **Population size** | Number of solutions per generation | Controls **exploration** |
| **Number of generations** | Iterations of learning | Controls **exploitation** |
| **Mutation rate** | Random changes | Prevents premature convergence |
| **Crossover rate** | Parent recombination probability | Drives information exchange |
| **Termination condition** | Max generations or no improvement | Ends search |

> [!tip] Tecnomatix GA Wizard  
> You set these values (population size, generations, reps per individual).  
> Simulation results become fitness scores.  
> GA adjusts inputs to improve the response variable.

---

## 5 | Multi-Objective Optimisation (MOO)

> [!info] Survival Kit Requirement #5
> "You must define the MOO problem, and understand the concept of dominance and the Pareto set."
> **Exam scope**: Q10 mentions MOO briefly (part of 8 marks) - conceptual understanding needed

> [!tip] Study Depth Indicator
> This section provides **foundation for MOSO** (Requirement #6).
> Know: definition, dominance concept, Pareto set/front.
> You won't do computational MOO problems - just explain the concepts.

> [!note] Definition
> **MOO** involves optimising **two or more conflicting objectives** (e.g., cost ↓ vs throughput ↑).
> There's no single best answer; instead, we find a set of trade-offs called the **Pareto set**.

### 🔹 Dominance Concept
A solution A **dominates** B if:
- A is no worse than B in all objectives, **and**  
- A is strictly better in at least one.

The set of non-dominated solutions = the **Pareto Front**.

> [!example] Interpretation  
> Points on the front = efficient trade-offs.  
> Moving along the front improves one goal but worsens another.

---

## 6 | MOSO – Multi-Objective Simulation-Optimisation

> [!info] Survival Kit Requirement #6
> "Understand and define MOSO."
> **What you need**: Know what makes MOSO different from MOO (stochastic outputs, approximate Pareto front)

> [!note] Definition
> **MOSO** = *Multi-Objective Optimisation + Simulation*
> A process that **optimises multiple conflicting objectives** using a **simulation model** to estimate performance values.

**Formal Definition:**
$$\min f(x, \xi) = [f_1(x,\xi), f_2(x,\xi), \dots, f_k(x,\xi)]^T$$
$$= [E(Y_1(x,\xi)), E(Y_2(x,\xi)), \dots, E(Y_k(x,\xi))]^T$$

subject to $x \in S_F$ (feasible region)

**Where:**
- **$x$** = decision variables (inputs you control) — e.g., number of doctors, buffer sizes
- **$\xi$** = random elements (simulation uncertainty) — e.g., arrival times, service times, breakdowns
- **$Y_i(x,\xi)$** = random variable for the i-th simulation output
- **$E()$** = expected value estimated over multiple replications
- **$f_i(x,\xi)$** = each performance measure (e.g., cost, waiting time, throughput)

> [!danger] Critical Distinction
> **GA changes $x$ only** (decision variables), NOT $\xi$ (random variables).
> $\xi$ remains fixed in distribution; GA observes performance changes in response to different $x$ values.

---

### Key Differences from Deterministic MOO

|Aspect|MOO (Deterministic)|MOSO (Stochastic)|
|---|---|---|
|**Output type**|Deterministic functions $f_i(x)$|Random variables $Y_i(x,\xi)$|
|**Objective values**|Exact|Estimated (via simulation averages)|
|**Pareto front**|Exact curve|Approximate curve (subject to sampling error)|
|**Computation**|Direct evaluation|Repeated simulation runs per solution|
|**Typical methods**|MILP, ε-constraint, NSGA-II|GA/NSGA-II combined with simulation|

---

### Example: Hospital Simulation

- **Objective 1 ($f_1$)**: Minimise patient waiting time
- **Objective 2 ($f_2$)**: Minimise staff cost
- **Decision variables ($x$)**: Number of doctors, nurses, consultation rooms
- **Random variables ($\xi$)**: Patient arrival times, consultation durations
- **Result**: Pareto front shows efficient trade-offs between cost and waiting time

---

## 7 | Computational Burden & Approximate Pareto Set

> [!info] Survival Kit Requirement #7
> "Always keep in mind that in SO, we can only estimate an approximate Pareto set, and that a computational burden is associated with SO. **The concepts illustrated in Figure 6.11 are very important to understand.**"

> [!danger] Key Insight
> In SO and MOSO, every simulation run costs time.
> The optimiser must balance solution quality with runtime.
> Larger population × more generations × more replications → heavier computation.

### Why the Pareto Set is Only Approximate

Deterministic: $f(x)$ gives **exact values**.
Simulation: $f(x,\xi)$ = stochastic output depending on random $\xi$.

To estimate true mean: $\hat{f}(x) = \frac{1}{n} \sum_{i=1}^n f(x,\xi_i)$

This estimate is **noisy and uncertain** → Pareto front is **approximate**.

**Computational burden**: Total runs = Population Size × Generations × Replications
*Example*: $50 \times 100 \times 10 = 50,000$ simulation runs!

---

### Figure 6.11 — What It Actually Shows

> [!warning] HIGH PRIORITY
> **Survival Kit**: "The concepts illustrated in Figure 6.11 are **very important to understand**."
> This is explicitly emphasized - make sure you can explain what this figure shows!

**Critical Understanding:** Figure 6.11 illustrates that **each decision point $x$ in the decision space has its own output distribution** in objective space.

**Visual Explanation:**
1. **Left side (Decision Space)**: Different green dots represent different $x$ settings (input combinations)
2. **Simulation Process**: Each $x$ is sent through simulation (red arrows)
3. **Right side (Objective Space)**: Each simulation result produces a **distribution** (bell curve), not a single point:
   - Each colored bell curve = **output distribution** for that decision $x$
   - Red dot = **sample mean** (estimated objective value)
   - Curve width = **variance** (uncertainty in the estimate)
   - Confidence interval width = reliability of that estimate

**Key Concepts from Figure 6.11:**

|Concept|Meaning|
|---|---|
|**Simulation adds randomness**|Each $x$ produces variable outcomes, not one deterministic value|
|**Mean vs. variance**|Mean determines where the solution plots; variance determines confidence|
|**Approximate Pareto set**|Because every point has variance, the "true" front is uncertain|
|**Computational burden**|To narrow distributions (reduce variance), you must run more replications → increases cost|

**Trade-off Illustrated:**
- Increasing replications → narrower distributions → better accuracy → higher computational cost
- Increasing generations → better solutions explored → higher cost
- The aim is an **acceptable balance** between accuracy and time

![[figure 6.11.png]]
*Figure 6.11: Each decision point x in decision space produces its own output distribution in objective space*

> [!example] Exam Insight
> Figure 6.11 shows that in MOSO, you're not comparing exact points — you're comparing **distributions with uncertainty**. This is why dominance relationships are approximate, not definitive.

---

## 8 | Pareto Ranking of Solutions

> [!info] Survival Kit Requirement #8
> "You must be able to do Pareto ranking of solutions (although it is not strictly correct in the case of MOSO)."
> **What you need**: Know the procedure (step-by-step) AND why it's approximate in MOSO

> [!note] Purpose
> A practical way to **rank** candidate solutions when multiple objectives exist.
> **Pareto ranking** assigns ranks to solutions based on **dominance relationships**.
> Used in GA/NSGA-II to guide selection pressure toward better solutions.

---
---
### ⚙️ Step-by-Step: Efficient Manual Pareto Ranking Method

**Example:** Five solutions with two objectives $f_1$ and $f_2$, both to be **minimised**.

| Solution | $f_1$ (Waiting Time) | $f_2$ (Cost) |
|-----------|----------------------|---------------|
| A | 8 | 250 |
| B | 9 | 200 |
| C | 7 | 300 |
| D | 10 | 260 |
| E | 7 | 220 |

---

#### 🔹 Step 1: Sort by One Objective

To reduce comparisons, **sort by $f_1$** (smallest to largest).  
Dominance can only occur *downward* in this order.

| Solution | $f_1$ | $f_2$ |
|-----------|-------|-------|
| C | 7 | 300 |
| E | 7 | 220 |
| A | 8 | 250 |
| B | 9 | 200 |
| D | 10 | 260 |

---

#### 🔹 Step 2: Apply the Dominance Rule

> **A solution is on the Pareto front if no other solution is better in both objectives.**
> 
> It can still be worse in one objective, as long as it’s better in the other — that trade-off keeps it non-dominated.
> 
> A solution is dominated (and not on the Pareto front) if there exists another solution that is strictly better in both objectives (for minimisation: lower $f_1$ and lower $f_2$).

---

#### 🔹 Step 3: Scan–Compare–Eliminate

Compare each new solution only with the **current non-dominated** ones above it.

| Step | Candidate | Compare With | Result | Keep / Remove |
|------|------------|---------------|---------|----------------|
| 1 | C | — | First entry | Keep |
| 2 | E | C | E dominates C ($7=7$, $220<300$) | Remove C |
| 3 | A | E | E dominates A ($7<8$, $220<250$) | Remove A |
| 4 | B | E | No dominance ($7<9$, $220>200$) | Keep both |
| 5 | D | E, B | D dominated by both ($10>7$, $260>220$) | Remove D |

✅ **Rank 1 (Pareto Front)** = $\{E, B\}$

---

#### 🔹 Step 4: Remove Rank 1 and Repeat

Remaining: $\{A, C, D\}$

| Step | Candidate | Compare With | Result | Keep / Remove |
|------|------------|---------------|---------|----------------|
| 1 | A | — | Keep |
| 2 | C | A | No dominance ($7<8$, $300>250$) | Keep both |
| 3 | D | A, C | D dominated by both | Remove D |

✅ **Rank 2** = $\{A, C\}$  
✅ **Rank 3** = $\{D\}$

---

### 🧾 Final Ranking

| Solution | Rank | Reason |
|-----------|------|--------|
| E, B | 1 | Pareto-optimal (non-dominated) |
| A, C | 2 | Dominated only by Rank 1 |
| D | 3 | Dominated by higher ranks |

---

> [!tip] Memory Shortcut: **Sort–Scan–Strip**  
> 1. **Sort** by one objective (usually $f_1$).  
> 2. **Scan** each new solution against current non-dominated ones.  
> 3. **Strip** out any dominated solutions immediately.  
>   
> This produces Pareto fronts quickly and cleanly for exam-style problems.

---
---

### Why It's "Not Strictly Correct" in MOSO

> [!warning] Statistical Limitation
> In **MOSO**, objective values $f_i(x,\xi)$ are **stochastic estimates**, not exact values.

**Key Points:**
- Each solution's performance has **variance** and **confidence intervals**
- You can't be 100% sure one solution dominates another
- Differences might be due to **simulation noise**, not true performance
- With more replications, dominance relationships might change

**Implication:**
Pareto ranking is still **useful for visualising trade-offs** in MOSO, but it's **statistically approximate**, not definitive.

> The "true" dominance relationship is uncertain due to stochastic outputs.

---

### Exam Takeaway

|Concept|What to Know|
|---|---|
|**Pareto ranking**|Sort solutions by dominance into fronts (Rank 1 = non-dominated, Rank 2 = dominated only by Rank 1, etc.)|
|**Process**|Iteratively identify non-dominated sets, remove them, repeat|
|**Purpose**|Used in GA/NSGA-II to guide selection toward better trade-offs|
|**In MOSO**|Approximate only — dominance may be uncertain because simulation outputs have randomness and variance|

---

## 🧭 Summary Table

| Topic | Must Know | Depth | Survival Kit # |
|--------|------------|-------|----------------|
| Combinatorial nature | Yes | Concept | #1 |
| SO definition | Yes | Concept + loop | #2 |
| Meta-heuristics | Yes | Definition + purpose | #3 |
| GA basics | Yes | **Crossover + population size + generations** | #4 ⭐ |
| MOO definition | Yes | Dominance + Pareto front | #5 |
| MOSO | Yes | Concept + approximation | #6 |
| Computational burden + Fig 6.11 | Yes | Qualitative | #7 ⭐ |
| Pareto ranking | Yes | Procedural + limitation | #8 |

⭐ = Explicitly emphasized by lecturer or survival kit

---

> [!danger] Exam Focus (Q10: 8 marks)
> - Conceptual GA understanding (no manual iteration)
> - **Exploration vs exploitation** (lecturer's exact emphasis)
> - Define SO, MOO, MOSO
> - Interpret dominance and Pareto set ideas
> - Explain why simulation adds computational cost
> - Understand **Figure 6.11** (called "very important")
> - No coding, equations, or detailed GA math

> [!quote] Lecturer Guidance (from transcript)
> "You don't need to know instant talk syntax, not about coding... But the experiment manager (EM), the output. You must know very well. You must be able to interpret it."
>
> **Translation for Chapter 6**: Understand GA conceptually (what parameters do), not computationally (how to code it).

---

## 🎯 Quick Self-Test Before Exam

Can you explain in your own words:

1. ✓ Why meta-heuristics are needed for simulation-based optimization (vs mathematical optimizers)?
2. ✓ What **population size** controls in GA (exploration - how wide you search)
3. ✓ What **number of generations** controls in GA (exploitation - how deep you learn)
4. ✓ What crossover and mutation do in GA
5. ✓ The difference between MOO and MOSO (deterministic vs stochastic)
6. ✓ What Figure 6.11 illustrates (each decision point has its own output distribution)
7. ✓ How to perform Pareto ranking step-by-step
8. ✓ Why Pareto ranking is "not strictly correct" in MOSO (variance and uncertainty)

**If YES to all → You're ready for Q10** ✅

