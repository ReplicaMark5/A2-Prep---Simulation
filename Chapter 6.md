**Chapter 6 – Optimisation with Simulation (Simulation-Optimisation & GA)**
_Source: Lecture 6 (pp. 85–103) + Transcript (A2 Prep Lecture) + Tut 08 Q1–Q6 + Memo_

with a focus on 

> **Survival kit:**
> Optimise your SO skills and ensure you have the following in your assessment pack:
> 1 Understand the combinatorial nature of optimisation problems.
> 2 Understand the principles of simulation-optimisation (SO) and define it.
> 3 Understand meta-heuristics, and that they provide good, but not necessarily optimal
> solution(s), in relatively short time. It is important to understand Figure 6.1.
> 4 You must know the basic working of the GA, its parameters (population size, number of
> generations, termination conditions, mutation and selection and cross-over).
> 5 You must define the MOO problem, and understand the concept of dominance and the
> Pareto set.
> 6 Understand and define MOSO.
> 7 Always keep in mind that in SO, we can only estimate an approximate Pareto set, and that
> a computational burden is associated with SO. The concepts illustrated in Figure 6.11 are
> very important to understand.
> 8 You must be able to do Pareto ranking of solutions (although it is not strictly correct in the
> case of MOSO).

---

## 🧩 Overview

> [!summary] What “Optimisation with Simulation” Means  
> **Simulation-Optimisation (SO)** uses a *simulation model* to **evaluate performance** and a *meta-heuristic optimiser* (like a **Genetic Algorithm**) to **search for good input settings**.  
> The simulation provides estimates; the optimiser adjusts the inputs until no major improvement occurs.

---

## 1 | Combinatorial Nature of Optimisation Problems

> [!learn] Concept  
> In realistic systems (e.g., number of doctors, nurses, or buffer sizes), each input can take several discrete values.  
> Combining them creates an **enormous search space** → manual enumeration becomes impossible.

**Example:**  
If three inputs each have 5 options → \($5^3$ = 125\) possible combinations.

This combinatorial explosion is why we use **heuristics** instead of brute-force enumeration.

---

## 2 | Principles & Definition of Simulation-Optimisation (SO)

> [!definition] Definition  
> **Simulation-Optimisation** = the use of *simulation* to evaluate performance for each candidate design, combined with an *optimisation algorithm* to find the best or near-best settings.

**Workflow (see Fig. 6.1):**
1. Choose decision variables (inputs).  
2. The optimiser proposes a set of values.  
3. Simulation runs n* replications → returns mean performance + CI.  
4. Optimiser uses the result to pick the next set.  
5. Stop when termination criteria are met.

**Purpose:**  
Find an **approximate best** solution when analytical models are too complex or stochastic.

---

## 3 | Meta-Heuristics — Why They Matter

> [!note] Definition  
> A **meta-heuristic** is a high-level search procedure that guides lower-level heuristics to explore large solution spaces.  
> They **don’t guarantee global optima**, but give **good solutions fast**.

**Examples:** Genetic Algorithm (GA), Simulated Annealing, Tabu Search.  
They are essential in SO because each simulation run is computationally expensive.

---

## 4 | Genetic Algorithm (GA) — Core Mechanics

> [!learn] What You Must Know (exam scope confirmed by lecturer)  
> You must know what **crossover** is, and the role of  
> **population size** (exploration) and **number of generations** (exploitation).  
> *Explore = how widely you search; Exploit = how deeply you refine.*

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

> [!definition] Definition  
> **MOO** involves optimising **two or more conflicting objectives** (e.g., cost ↓ vs throughput ↑).  
> There’s no single best answer; instead, we find a set of trade-offs called the **Pareto set**.

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

> [!definition] Definition  
> **MOSO** = *MOO + Simulation* → objectives are stochastic because each evaluation uses simulated outputs.

**Implication:**  
- We can only **estimate** performance → the Pareto front itself is **approximate**.  
- Sampling noise + replications make MOSO **computationally expensive**.

**MOSO** stands for **Multi-Objective Simulation-Optimisation**.

---

### Definition

> A process that **optimises multiple conflicting objectives** using a **simulation model** to estimate performance values.

Formally:  
$$\min f(x, \xi) = (f_1(x,\xi), f_2(x,\xi), \dots, f_k(x,\xi)) $$
where

- $(x)$ = decision variables (inputs you control),
- $(\xi)$ = random elements (simulation uncertainty),
- $(f_i(x,\xi))$ = each performance measure (e.g., cost, waiting time, throughput).

---

### In simple terms

You use **simulation** to measure outcomes and a **meta-heuristic** (like a GA) to find input settings that balance objectives.  
Because simulation outputs are stochastic, MOSO produces **estimates**, not exact optima.

---

### Key ideas

|Concept|Meaning|
|---|---|
|**Multi-objective**|There is more than one performance goal (e.g., minimise cost and waiting time).|
|**Simulation-based**|Each evaluation comes from a simulation run, not an analytical function.|
|**Pareto set**|The group of **non-dominated** solutions representing the best trade-offs.|
|**Approximate front**|Because each simulation is noisy, the Pareto front is only an **estimate**.|
|**Computational cost**|Many replications × generations make MOSO expensive to run.|

---

## 7 | Computational Burden & Approximate Pareto Set

> [!warning] Key Insight  
> In SO and MOSO, every simulation run costs time.  
> The optimiser must balance solution quality with runtime.  
> Larger population × more generations × more replications → heavier computation.

**Figure 6.11 (Conceptual Summary):**
- Increasing replications → better accuracy, higher cost.  
- Increasing generations → better solutions, higher cost.  
- The aim is an **acceptable balance** between accuracy and time.

---

## 8 | Pareto Ranking of Solutions

> [!learn] Purpose  
> A practical way to **rank** candidate solutions when multiple objectives exist.  
> Even though ranking is **not statistically strict** for MOSO, it helps visualise trade-offs.

**Process:**
1. Identify all non-dominated solutions (rank 1).  
2. Remove them from the set.  
3. Identify new non-dominated ones (rank 2).  
4. Continue until all are ranked.

Used to visualise trade-offs in Tecnomatix or Excel scatterplots.

---

## 🧭 Summary Table

| Topic | Must Know | Depth |
|--------|------------|-------|
| Combinatorial nature | Yes | Concept |
| SO definition | Yes | Concept + loop |
| Meta-heuristics | Yes | Definition + purpose |
| GA basics | Yes | Crossover + population size + generations |
| MOO definition | Yes | Dominance + Pareto front |
| MOSO | Yes | Concept + approximation |
| Computational burden | Yes | Qualitative |
| Pareto ranking | Optional | Conceptual only |

---

> [!important] Exam Focus  
> - Conceptual GA understanding (no manual iteration).  
> - Exploration vs exploitation.  
> - Define SO, MOO, MOSO.  
> - Interpret dominance and Pareto set ideas.  
> - Explain why simulation adds computational cost.  
> - No coding, equations, or detailed GA math.

