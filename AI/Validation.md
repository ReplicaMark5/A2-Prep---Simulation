This instruction means you must **apply the validation principles from your textbook (Section 2.9, “Validate the model,” p. 30)** to your **specific simulation model**, not just repeat the textbook’s theory.

---

### 1. Textbook basis

In Section 2.9, the book defines validation as checking **whether the model represents the real-world system adequately**.  
It lists three kinds of validity (Law & Kelton, 2000):

- **Conceptual validity:** the model’s logic reflects the real process.
    
- **Operational validity:** simulated results behave like the real system.
    
- **Credibility:** users trust the model’s output.
    

It also gives **practical tests**: continuity, consistency, degeneracy, and response under absurd conditions. These are theoretical validation _principles_.

---

### 2. What your question expects

The exam prompt asks you not to restate those theoretical points (“continuity… consistency…”).  
Instead, you must show **how you applied those ideas in your own simulation**—that is, _validation considerations_.

---

### 3. Applied example (based on the tutorials)

|Theoretical idea (from textbook)|Practical validation action you describe|
|---|---|
|**Continuity test:** small input change → small output change|You change **buffer size** from 2 to 3 and observe **throughput** rising slightly (not jumping unpredictably).|
|**Operational validity:** model behaviour matches logic|As buffer size increases, you identify the **minimum throughput** (system starved) and **maximum throughput** (system saturated). These bounds confirm the model reacts logically.|
|**Consistency:** repeatability of results|Running the same buffer setting several times yields throughput within the expected confidence interval.|
|**Degeneracy test:** removing a resource reduces performance|You temporarily disable one machine or reduce capacity and confirm throughput drops.|

---

### 4. How to word it in your answer

> “To validate the model, I adjusted buffer sizes and monitored throughput. Throughput increased steadily until a saturation point was reached, confirming logical continuity between input and output. Minimum throughput occurred when buffers were constrained (system starved), and maximum throughput when buffers were large enough to remove blocking. Repeated runs produced consistent results within confidence limits, demonstrating operational validity.”

---

### 5. Summary

In textbook terms:

- Validation = “Did we build the _right_ model?”
    
- But in your report/exam, **show how** you tested that, not **recite why**.  
    Link each observed throughput trend or buffer-size change to the underlying validation principle without naming the principle directly.