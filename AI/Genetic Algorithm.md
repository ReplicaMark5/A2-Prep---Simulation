
---
Here are concise, exam-aligned notes for the **Genetic Algorithm (GA)** section [[ebook.pdf#page=90&selection=9,0,9,21&color=note|p.90]], built strictly from the lecturer’s transcript and the official A2 guide.

---

## 🧬 Genetic Algorithm (GA) — A2 Exam Notes

### 1. Core Concept

- GA is a **meta-heuristic optimisation method** inspired by natural selection.
    
- Used to **search large decision spaces** efficiently when analytical optimisation is impractical.
    
- Produces _good_, not guaranteed optimal, solutions within reasonable time.
    

---

### 2. Key Terms to Know

|Term|Meaning|
|---|---|
|**Population**|Set of possible solutions in one generation. Controls how widely the search explores the solution space.|
|**Generation**|Each iteration of evolution. Controls how long the algorithm “learns” — exploitation.|
|**Chromosome / Individual**|One candidate solution (a vector of decision variables).|
|**Fitness Function**|Objective value(s) evaluated for each individual — corresponds to simulation outputs (Zᵢ).|
|**Crossover**|Combines parts of two parent solutions to create offspring — main exploration mechanism.|
|**Mutation**|Randomly alters some solution elements — prevents premature convergence and adds diversity.|
|**Selection**|Chooses which individuals become parents based on fitness. Drives exploitation.|

<p align="center">
Population<br>
↓<br>
Fitness Evaluation<br>
↓<br>
Selection<br>
↓<br>
Crossover<br>
↓<br>
Mutation<br>
↓<br>
New Population<br>
↓<br>
Fitness Evaluation<br>
↓<br>
(Repeat until termination)
</p>

---

### 3. Exploration vs. Exploitation (Exam Focus)

> **Explore** = how wide you look.  
> **Exploit** = how well you use information gathered.

|Concept|Controlled By|Description|
|---|---|---|
|**Exploration**|**Population size**|Larger population → more diverse search, broader coverage of decision space.|
|**Exploitation**|**Number of generations**|More generations → deeper learning, but higher computational cost.|
|**Trade-off**|Must balance search diversity vs. computation time.||

Refer to [[Exploration vs Exploitation]] for a more in depth guide

---

### 4. Lecturer’s Emphasis

- “You must know **crossover**, **mutation**, **population size**, **number of generations**.”
    
- Understand their roles in **exploration and exploitation** — _not memorisation of code or equations_.
    
- “Know **how** and **why**, not syntax.”
    
- GA is part of **simulation-optimisation (SO)** — applied to find near-optimal system settings when simulation output is stochastic.
    

---

### 5. In the Exam

Expect conceptual or short applied questions like:

- _“Explain the difference between exploration and exploitation in a GA.”_
    
- _“Which parameters affect each?”_
    
- _“What does crossover achieve?”_
    
- _“How does population size affect computational cost and diversity?”_
    

---

### 6. Practical Insight

- Increasing population size increases exploration but slows runtime.
    
- Increasing generations increases convergence precision but raises computation cost.
    
- Mutation keeps diversity high; without it, the algorithm may converge prematurely.
    
- Always link GA terms to **decision variables (xᵢ)** and **response outputs (Zᵢ)** from your simulation.
    

---

### 7. Related Topics (linked in Section 6 of eBook)

- **Simulation-optimisation (SO)**: GA as a search engine around a simulation model.
    
- **Multi-objective optimisation (MOO)**: GAs can generate Pareto fronts (e.g., NSGA-II).
    
- **MOSO** (multi-objective simulation-optimisation): adds replication (n*) for stochastic evaluation.
    

---

### ✅ Summary Table

|Know for A2|Don’t Need|
|---|---|
|Crossover, mutation, population size, number of generations|SimTalk syntax|
|Exploration vs. exploitation concepts|Detailed formulas|
|Link to simulation-optimisation|GA code structure|

---

Would you like me to make a **1-page printable cheat-sheet** version (with diagrams showing exploration vs. exploitation and GA flow)? It would summarise everything visually for quick revision.

[chat gpt](https://chatgpt.com/share/69010009-cd78-8013-aa92-15842a3f8e14)
