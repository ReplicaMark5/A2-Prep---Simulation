Here is a complete extraction of what you must **learn and prepare** for your **Simulation 442 A2 & A3 exam**, based directly on the official guide you uploaded . taken from [[A2 Guide - Official.pdf]]

---

## 1. **General Exam Principles**

- Be able to do **all tutorial questions** and **class examples**.
    
- Study **theory** thoroughly (concepts, not memorization only).
    
- Use the **Survival Kits** at the end of each chapter.
    
- Review the **Table of Contents** in the eBook — you must recognize **every topic**.
    
- Don’t “spot” study — **everything is examinable** unless stated otherwise.
    
- **Old papers** can help but the lecturer has “moved on.”
    
- **Do not rely** on previous students’ notes — some model answers are **incorrect**.
    

---

## 2. **Exam Format & Marks Allocation**

|**Section**|**Focus**|**Marks**|
|---|---|---|
|Q1|**Theory** – Define, Explain, List, Why?, How?, etc.|33|
|Q2|**Input Data Analysis** – χ² test, inverse transform, etc.|36|
|Q3–9|**Models** – Explain, Why, How, Apply; entity states; calculate ( n^* )|103|
|Q10|**Output Analysis** – h, ( n^* ), MOO, etc.|8|
|**Total**|Duration 3 hours, **180 marks**|—|

### A2 vs A3

- **A2:** No Multiple Choice, **no NTS or K-S**.
    
- **A3:** Same format, no M-C or NTS.
    
- Both require **insight and deep understanding**.
    

---

## 3. **General Exam Guidelines**

- You **don’t need** to know **SimTalk syntax**.
    
- You **don’t need** to memorize **TPS objects**, but you must:
    
    - Interpret **Experiment Manager (EM)** results.
        
    - Link results to **theory** (e.g., p-table interpretation).
        
- Logic questions may require **pseudo-code explanations**.
    
- **Statistical tables** will be provided.
    
- A **formula sheet** similar to A1 will be included.
    
- **Do not calculate** ( t ) or ( \nu ) manually (p.77 in eBook).
    

---

## 4. **Algorithms & Procedures**

### Genetic Algorithm (GA)

Know conceptually:

- **Cross-over**
    
- **Mutation**
    
- **Population size**
    
- **Number of generations**
    
- **Termination condition**
    

### Kim–Nelson (K–N) Procedure

- Understand **its properties**.
    
- You must **explain what it does and why** to a third-year.
    
- No need to know formulas or detailed steps.
    

---

## 5. **Models — Deep Understanding Required**

You must know **all models** in detail, including **Model 0**.

### What to Understand

- Model dynamics and their theoretical underpinnings.
    
- The relationship between models and real-world systems.
    

### Example Guidance

- **McDonalds Model** = effectively a **BAP** (Batch Arrival Process).
    
- **TUM (Trauma Unit Model)**:
    
    - Identify **entities** and **attributes**.
        
    - Apply **Shannon’s worldview** (information theory perspective).
        
    - Understand why the **trauma unit** is a **production line**.
        
- **Buffer Sizes:**
    
    - What happens if **BAP buffers → ∞**?
        
    - Why do models have **upper throughput limits**?
        

---

## 6. **Validation and Modelling Insight**

You must be able to answer:

- How do I **simplify** a model while keeping it realistic?
    
- Which real-world features are **non-negotiable** to include?
    
- What **validation tests** were performed?
    

### Examples

- In the **TUP (Trauma Unit Process)**:
    
    - Why is the model **invalid** if _“Worker stays here after completing job”_ is checked?
        
- In the **(r, Q)** model:
    
    - Why is **total inventory cost still high** when both _r_ and _Q_ are low?
        

---

## 7. **Formulas Provided**

These are on your **formula sheet** — you don’t need to derive them but must know **where and how** to apply them.

### Core Equations

[  
\chi^2 = \sum_{i=1}^k \frac{(E_i - O_i)^2}{E_i}  
]  
[  
h = t_{n-1;1-\alpha/2} \cdot \frac{S_x}{\sqrt{n}}  
]  
[  
C_{ij} = \frac{\sum_{i=1}^{n-j} (X_i - \bar{X})(X_{i+j} - \bar{X})}{n-j}  
]  
[  
n^* = \left\lceil n \left(\frac{h}{h^*}\right)^2 \right\rceil  
]  
[  
P(X \in E) = \sum_{\omega \in A} p(\omega)\delta_\omega(E)  
]

### Distributions

- **Exponential:** ( f(x) = \frac{1}{\beta}e^{-x/\beta}, ; x > 0 )
    
- **Poisson:** ( f(x) = \frac{e^{-\lambda}\lambda^x}{x!}, ; x = 0, 1, 2, \dots )
    

### Correlation

[  
\rho_j = \frac{C_{ij}}{S_X^2}, \quad S^2 = \frac{\sum_{i=1}^n (X_i - \bar{X})^2}{n - 1}  
]  
[  
k = \lfloor 1 + 3.322 \log_{10} n \rfloor  
]

### K–S Test (conceptual only)

[  
D_n = \max {D_n^+, D_n^-}  
]

---

## 8. **Exam Expectations**

- Expect to **apply**, **explain**, and **interpret**, not only calculate.
    
- Understand **links between theory and model output**.
    
- Be ready to interpret **confidence intervals, p-values, h, and n***.
    
- Insight > memorization.
    

---

### ✅ Final Checklist

-  Tutorials mastered (all models, questions).
    
-  Understand GA and K–N procedure conceptually.
    
-  Know Model 0 and model interrelations (BAP, TUM, (r, Q), etc.).
    
-  Understand validation and simplification logic.
    
-  Be able to interpret Experiment Manager output and link it to theory.
    
-  Be comfortable with statistical reasoning (p-tables, CI, χ², etc.).
    
-  Review the Survival Kits from each chapter.
    
-  Study deeply — the exam tests **insight** and **understanding**, not memorization.
    

---

Would you like me to turn this into an **Obsidian-formatted revision note** (with collapsible callouts and tags like > [!learn] and > [!example])?