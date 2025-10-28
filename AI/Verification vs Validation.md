Here’s a concise, exam-ready summary you can copy straight into your Verification and Validation.md Obsidian note — formatted cleanly, objective in tone, and with key textbook quotes included.

  

  

  

  

Verification and Validation in Simulation

  

  

  

1. Definitions

  

  

Verification – “Did we build the model right?”

Ensures the simulation model has been correctly implemented according to the conceptual design.

  

“Verification allows us to confirm that we have built the model right.” (Bekker, Simulation 442, §2.9)

  

Validation – “Did we build the right model?”

Ensures the model is an adequate representation of the real-world system for its intended purpose.

  

“Validation allows us to confirm that we have built the right model for the particular objectives of the study.” (Bekker, Simulation 442, §2.9)

  

  

  

  

2. Main Differences

  

|   |   |   |
|---|---|---|
|Aspect|Verification|Validation|
|Objective|Check correctness of model logic and code.|Check realism and usefulness of the model.|
|Focus|Internal consistency and technical accuracy.|External consistency and conceptual accuracy.|
|Question answered|“Is the model implemented correctly?”|“Is the model an adequate representation of the real system?”|
|Methods|Debugging, syntax checking, walkthroughs, animation tracing, deterministic test runs.|Face validation, expert review, statistical tests (t-test, Wilcoxon), comparison with real data.|
|Timing|During and after model coding.|During and after model execution.|
|Responsibility|Modeller/analyst.|Analyst, user, and technical evaluator.|

  

  

  

  

3. Relationship and Overlap

  

  

Verification and validation are interrelated and partially overlapping processes.

  

“Verification and validation are interrelated: when verifying, the model is partially validated in terms of correct output.” (Bekker, §2.9)

  

Key idea:

Some verification activities can contribute to validation when they also demonstrate realistic or expected system behaviour.

  

Examples of overlap:

  

- Deterministic runs that produce expected theoretical results.
- Animation walkthroughs that domain experts confirm as realistic.
- Debugging with real-world data that reproduces known performance.

  

  

Verification must occur first, but complete validation cannot occur unless the model has been verified.

  

  

  

  

4. Validity Tests (Law & Kelton, 2000)

  

  

Three main perspectives of validation:

  

1. Conceptual validity – Does the model represent the real-world system adequately?
2. Operational validity – Are the model’s generated outputs statistically consistent with the real system’s data?
3. Credibility – Do decision-makers have confidence in the model’s results?

  

  

  

  

  

4. Properties of a Valid Model

  

  

A valid model should demonstrate:

  

- Continuity: Small input changes → small, appropriate output changes.
- Consistency: Repeated runs produce similar results (within stochastic variation).
- Degeneracy: Removing model elements has logical effects (e.g., reduced capacity → reduced output).
- No absurd conditions: The model must not produce unrealistic values (e.g., negative times).

  

  

  

  

  

6. Summary Diagram

  

[ Verification ] ⊂ [ Validation ]

Verification ensures the model runs right.

Validation ensures the model means right.

Together, they ensure the simulation is both technically correct and conceptually credible.

  

  

  

  

7. Exam Tip

  

  

Verification = building the model correctly.

Validation = building the correct model.

Both are iterative, overlapping, and essential to simulation credibility.

  

Would you like me to include a short “example scenario” (like the parking area or factory queue) at the end so that you can quickly recall the difference during study revision?

https://chatgpt.com/share/69012f42-3bf0-8001-a5ec-75792d3d80b0