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
- **Largest $\sigma$-field (the power set - all subsets)**
  
$$
𝒫(Ω)=\lbrace ∅, \lbrace1\rbrace, \lbrace2\rbrace, \lbrace3\rbrace, \lbrace1,2\rbrace, \lbrace1,3\rbrace, \lbrace2,3\rbrace, \lbrace1,2,3\rbrace \rbrace
$$

- **Smallest $\sigma$-field (trivial)**

$$
A_1 ​= \lbrace ∅,\lbrace1,2,3\rbrace \rbrace
$$

-  **Intermediate example** If $\lbrace 1 \rbrace \in 𝒜$, then its complement  $\lbrace 2, 3 \rbrace$ must also be in **𝒜**. A valid $\sigma$-field is

$$
A_2​ = \lbrace ∅, \lbrace 1 \rbrace, \lbrace 2,3 \rbrace, \lbrace 1,2,3 \rbrace \rbrace
$$

The σ-field can be very small or as large as the power set, but it must always obey the three rules.

### Why Not Always Use All Subsets?
For **finite sample spaces** (such as coin tosses or dice rolls), we can safely take all subsets as events.

However, for **infinite or continuous sample spaces** (e.g., choosing a real number between 0 and 1), some subsets are too irregular to assign probabilities consistently. Such sets are called **non-measurable sets** (e.g., the Vitali set, constructed using the Axiom of Choice).

**The Fix: The Borel $\sigma$-field**
To avoid inconsistencies, we restrict ourselves to carefully chosen $\ sigma$-fields, such as the **Borel $\sigma$-field** on the real line.

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
1. **Non-negativity:** For every event `A ∈ 𝒜`: $P(A) \geq 0$
2. **Normalization:** The probability of the whole sample space is 1:$P(\Omega) = 1$

3. **Countable Additivity** For any countable collection of disjoint events `A₁, A₂, … ∈ 𝒜`:

$$
P\left( \bigcup_{i=1}^{\infty} A_i \right) 
= \sum_{i=1}^{\infty} P(A_i)
$$


**Intuition:** Imagine you need to assign weights across all possible outcomes. The total weight you assign is 1 (100%). Each outcome gets a portion of that weight. Outcomes with a higher likelihood of occurrence are assigned with larger weight as compared to outcomes with a lower likelihood of occurrence. 


### Properties of Probability Measure P

#### 

In conclusion, a probability measure is a way of **spreading unit weight (1) across possible outcomes**, so that we can talk about how likely events are, in a way that’s logical, consistent, and scalable.

---

### Example

Let's develop a probability space for a coin toss experiment. The sample space is

$$
\Omega = \lbrace H, T \rbrace
$$

One possible σ-field is the power set:  

$$
𝒜 = \lbrace \emptyset, \lbrace H \rbrace, \lbrace T \rbrace, \lbrace H,T \rbrace \rbrace
$$

A valid probability measure could be:  

$$
P( \lbrace H \rbrace) = 0.5, \quad P( \lbrace T \rbrace) = 0.5
$$

Here, every subset of $\Omega$ is an event, and \(P\) assigns probabilities to them.

---

## Summary

A probability space (Ω,𝒜,P) is a framework that defines all possible outcomes, the events of interest, and a consistent rule assigning probabilities to them.
