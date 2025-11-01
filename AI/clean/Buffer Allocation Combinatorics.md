That expression


$$c =  
\binom{m + n - 2}{m - 2}  $$

is a **combinatorial formula** — specifically the **“stars and bars”** formula used to count how many ways you can distribute $n$ identical $items$ among $m−1$ $buffers$.

---

### 🔹 What the symbols mean

| Symbol    | Meaning                                                  |
| --------- | -------------------------------------------------------- |
| $( m )$   | Number of machines in the production line                |
| $( n )$   | Total number of buffer “niches” available                |
| $( m-1 )$ | Number of **physical buffers** (spaces between machines) |
| $( c )$   | Number of possible **buffer allocations**                |

---

### 🔹 Why that formula

Each allocation is a non-negative integer solution of:  

$$b_{12} + b_{23} + \dots + b_{(m-1)m} = n $$
 
(where $(b_{ij})$ = number of niches in buffer between machine $i$ and $j$).

The number of such solutions is given by:  

$$c = \binom{(n + (m-1) - 1)}{(m-1) - 1}  
= \binom{m + n - 2}{m - 2}.  $$


This comes directly from **combinations with repetition** (the stars-and-bars theorem).

---

### 🔹 Example (from your question)

- $( m = 3 )$ machines
    
- $( n = 2 )$ niches
    

Then:  

$$c = \binom{3 + 2 - 2}{3 - 2} = \binom{3}{1} = 3 $$

→ 3 possible buffer allocations:

1. $(1, 1)$
    
2. $(2, 0)$
    
3. $(0, 2)$
    

---

**In short:**  

$$c = \binom{m + n - 2}{m - 2}  $$
 
counts all possible **ways to distribute n identical niches among (m−1) buffers**.


---
---
Correct — here’s the concise version for your note:

**Q4 – Total Buffer Spaces**  
Each buffer can have 4 possible space counts, and there are $(m-1 = 2)$ buffers →  
$$
n^{(m-1)} = 4^2 = 16  
$$ 
**Total = 16 possible buffer-space allocations.**

---
---
**Q6 – Total Replications (Computational Burden)**  
The total number of simulation replications in a GA-based optimiser is:  
  
$$N_T = [P(2G - 1)] \times n  $$


- $(P)$: population size
    
- $(G)$: generations
    
- $(n)$: replications per solution
    

The $((2G - 1))$ term accounts for the **initial** and all **offspring populations** that are simulated during evolution.  
This shows how computational cost in SO grows rapidly with larger populations, more generations, or higher replication counts.

---
---
