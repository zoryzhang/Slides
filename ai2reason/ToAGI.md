---
markmap:
  initialExpandLevel: 2
#  initialExpandLevel: -1
  colorFreezeLevel: 3
---

# AI2Reason
## 1. Automated Theorem Prover, ATP
### Description
- Trustworthy: verifiable, explainable, and generalizable.
### Knowledge/Memory
- A mathlib in formal mathematical language with tags: true, false, unexplored, unsure
- E.g. Measure theory and Dominated Convergence Theorem
### Problem of interest
- "Show Fatou's Lemma using DCT"
### Planning
- Goal decomposition
### Analogy
1. Memory Retrieval
    - Based on similarity and catagorization.
2. Mapping Generation
    - E.g. "Measure is like the volume."
3. Analogical Inference
    - Make use of the analogy mapping.
4. Schema Induction.
    - How good is the analogy?
### Simplicity
- The whole point of doing proof: treat proof as explanation of why to gain **insight**.
- We are taking the most sufficient explantion, but no necessarily **good**.

## 2. Scientific Enquiry Machine
### Description
- Explore the world to convince itself.
### Work flow
#### 1. Phenomenon of interest
- E.g. "Sometimes, $\int \lim f_n = \lim \int f_n$"
- Serve as motivation
#### 2. Abductive Explanatory Hypothesis Generation
#### 3. Deduction on Unavoidable Consequences
#### 4. Experimentation
#### 5. Inductive Evaluation
1. If inconsistant, go back to step 2
2. If consistant, serve as a valid hypothesis among candidates
#### 6. Inference to the Best Explanation
- Pick the best among candidates. If good explanation, gain insight.
### Degree of Belief
- Relax the requirement of objective truth.
- E.g. "The Sun will very likely rise tomorrow."

### Levels of Creativity
1. Invent Meaningless yet True Propositions
2. Invent Theorem
3. Invent Definition
    - E.g. Continuity
4. Invent Thoery
5. Invent Concept & Symbol
    - E.g. Integral, gravity

## 3.Artificial Reasoning System
### Efficiency: Dual-Process Thoery
### Knowledge base: Commen Sence, World Model?
### Input: multimodality
- E.g. [Mathvista](https://mathvista.github.io/#leaderboard)
### Agent: Interact with Real World via External Tools
### Planning: How to decompose a complex goal