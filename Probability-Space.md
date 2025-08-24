# 1. Probability Space
A **Probability Space** is a mathematical framework used to model random experiments or processes. It is defined as a triple

$$
(\Omega, 𝒜, P)
$$

where  
- **$\Omega$** is the **sample space** (the set of all possible outcomes),  
- **$𝒜$** is a **$$\sigma$$-field (sigma-algebra)**, a structured collection of subset of **$\Omega$**,  
- **$P$** is the **probability measure**, which assigns probabilites to the events in **𝒜**. 

---
## Sample Space ($\Omega$)
The sample space is the set of all possible outcomes of an experiment. Subsets of the sample space (**$$\Omega$$**) are called Events.

**Example**
For a die roll,

$$
\Omega = \lbrace 1, 2, 3, 4, 5, 6 \rbrace
$$

**Intuition**  
Think of Ω as the "universe" of everything that could possibly happen in your experiment.

---

## $$\sigma$$-field (𝒜) of Events
A **$\sigma$-field 𝒜** is a collection of subsets of **$\Omega$** that is closed under certain properties.

#### Properties
1. **Contains sample space** $$\Omega \in 𝒜$$
3. **Closed under complements:** If $$\(A \in 𝒜\)$$, then its complement $$\(A^c \in 𝒜\)$$.
   

4. **Closed under countable unions (and intersections):** If $$\(A_1, A_2, A_3, \dots \in 𝒜\)$$, then

$$
(\bigcup_{i=1}^\infty A_i \in 𝒜)
$$  

#### Intuition and Examples
- Rule (1): We must always include the "everything happens" event.
- Rule (2): If "rain" is an event, then "no rain" must also be an event.
- Rule (3): If "rain on Monday", "rain on Tuesday" ... are events, then "rain on some day" must also be an event.

Thus, a $\sigma$-field ensures we can talk about events, their opposites, and combinations consistently. 

### Constructing $$\sigma$$-fields
Consider $\Omega = ${1, 2, 3}. 
- **Largest $\sigma$-field (the power set - all subsets):**
  
$$
𝒫(Ω)=\lbrace ∅, \lbrace1\rbrace, \lbrace2\rbrace, \lbrace3\rbrace, \lbrace1,2\rbrace, \lbrace1,3\rbrace, \lbrace2,3\rbrace, \lbrace1,2,3\rbrace \rbrace
$$

- **Smallest $\sigma$-field (trivial):**

$$
A_1 ​= \lbrace ∅,\lbrace1,2,3\rbrace \rbrace
$$

-  **Intermediate example:** If $\lbrace 1 \rbrace \in 𝒜$, then its complement  $\lbrace 2, 3 \rbrace$ must also be in **𝒜**. A valid $\sigma$-field is

$$
A_2​ = \lbrace ∅, \lbrace 1 \rbrace, \lbrace 2,3 \rbrace, \lbrace 1,2,3 \rbrace \rbrace
$$

The σ-field can be very small or as large as the power set, but it must always obey the three rules.

### Why Not Always Use All Subsets?
For **finite sample spaces** (such as coin tosses or dice rolls), we can safely take all subsets as events.

However, for **infinite or continuous sample spaces** (e.g., choosing a real number between 0 and 1), some subsets are too irregular to assign probabilities consistently. Such sets are called **non-measurable sets** (e.g., the Vitali set, constructed using the Axiom of Choice).

**The Fix: The Borel $\sigma$-field**
To avoid inconsistencies, we restrict ourselves to carefully chosen $\sigma$-fields, such as the **Borel $\sigma$-field** on the real line.

- It starts with all the open intervals (e.g., (0.2, 0.5)).
- By applying $\sigma$-field rules (unions, intersections, complements), it generates a vast collection of sets, including open sets, closed sets, intervals, rays, and countable unions of such sets.
   
The Borel σ-field is large enough for all practical purposes in probability, yet avoids pathological non-measurable sets.

---

## Probability Measure 𝑃
A **probability measure** is a function assigning a probability to each event in **𝒜**.

**Definition**

$$
P: 𝒜 \to [0,1]
$$

such that:
1. **Non-negativity:** **$P(A) \geq 0$** For every event **A ∈ 𝒜**.
2. **Normalization:** **$P(\Omega) = 1$**
3. **Countable Additivity** For disjoing **A₁, A₂, … ∈ 𝒜**,

$$
P\left( \bigcup_{i=1}^{\infty} A_i \right) 
= \sum_{i=1}^{\infty} P(A_i)
$$


**Intuition:** Think of **P** as distributing a total weight of 1 (100%) across all possible outcomes. More likely outcomes get more weight.

---

### Example: Coin Toss

Let's develop a probability space for a coin toss experiment. 

- **sample space** $\Omega = \lbrace H, T \rbrace$
- **σ-field** The power set,
  
$$
𝒜 = \lbrace \emptyset, \lbrace H \rbrace, \lbrace T \rbrace, \lbrace H,T \rbrace \rbrace
$$

- **Probability measure:**  

$$
P( \lbrace H \rbrace) = 0.5, \quad P( \lbrace T \rbrace) = 0.5
$$

Here, every possible subset of $\Omega$ is an event, and \(P\) assigns consistent probabilities to each.

---

## Summary

A probability space **$(\Omega, 𝒜, P)$** provides a rigorous framework to study randomness
- **$\Omega$** defines all possible outcomes,  
- **$𝒜$** specifies which subsets are valid events,  
- **$P$** assigns consistent probabilities to those events.

This structure ensures probability theory is mathematically sound, scalable to infinite cases, and forms the foundation for modern statistics, stochastic processes and application in fields such a finance, physics and machine learning.
