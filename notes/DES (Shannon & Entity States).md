
---
### **Discrete-Event Simulation (DES)** — the overall framework

a **modelling approach** where the system’s state changes only at discrete points in simulated time (arrivals, departures, service completions, etc.) — those same _events_ defined under Shannon’s framework.

---

### 1. **Shannon’s World View** — the conceptual modelling layer

**Shannon’s world view (1975)** is a **framework** for defining how a real-world system is represented in a computer model.  [[ebook.pdf#page=16&selection=19,0,19,55&color=note|p.16]]

This sits **inside DES** as the **way we describe** the system being simulated.  
It tells us _what_ the system consists of:

- **Entities** (moving objects)
    
- **Attributes** (their properties)
    
- **Resources** (servers, workers, machines)
    
- **Conditions** (rules or logic)
    
- **Events** (points in time that change state)
    
- **System state** (current configuration of entities and resources)
    

This framework provides the _vocabulary and structure_ DES uses to represent reality.

---

### 2. **Entity State Mechanism** — the execution layer

Within DES, this defines _how_ the simulation engine runs the world view in time.  
It uses the entities listed below to manage which entities act next: [[ebook.pdf#page=18&selection=4,11,4,47&color=note|p.18]]

| Entity state          | What happens                                                                    | Event-list structure          |
| --------------------- | ------------------------------------------------------------------------------- | ----------------------------- |
| **Active**            | Entity being processed now                                                      | None                          |
| **Ready**             | Entities waiting to be processed next                                           | **Current Events List (CEL)** |
| **Time-delayed**      | Entities waiting for a scheduled future event (e.g. end of service, transport)  | **Future Events List (FEL)**  |
| **Condition-delayed** | Entities waiting for a logical condition (e.g. queue empty, resource available) | **Delayed List**              |
| **Dormant**           | Special entities controlled manually by analyst logic                           | **User-managed List**         |
