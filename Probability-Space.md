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

#### Formal Properties
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
- **Largest $\sigma$-field (the power set)**
  
$$
𝒫(Ω)={ ∅, {1}, {2}, {3}, {1,2}, {1,3}, {2,3}, {1,2,3} }
$$
  
This is the largest possible σ-field on {1,2,3}. But a $\sigma$-field doesn't always need the entire power set; we can construct it with a few subsets of the power set and still satisfy the three rules (contains Ω, closed under complements, closed under countable unions).  

a. **A trivial $\sigma$-field** 
   $A_1​=${ ∅,{1,2,3} } only "nothing" and "something" happen. Always valid but not quite useful. 

b. **A non-trivial $\sigma$-field** 
   Lets say we include {1}, then its complement is {2, 3}. Then a valid $\sigma$-field is as follows.  
   A2​={ ∅, {1}, {2,3}, {1,2,3} }

**Idea:** The biggest σ-field is the power set (all subsets). And, the smallest σ-field is {∅, Ω}.

### Why don't we use all subsets always? Why do we need a $\sigma$-field?
If we’re dealing with something small and finite (like tossing a coin or rolling a die), we can happily include all possible subsets of outcomes as events.
Example: For a coin toss, the subsets are {H}, {T}, {H,T}, and ∅. All of them can have probabilities without any problem.

But when we move to infinite cases (like picking a random number between 0 and 1), things get tricky. Some subsets of [0, 1] are too "wild" to assign a probability to in a consistent way. These unusual sets are referred to as **non-measurable sets**.

**$\sigma$-field as fix:**
To avoid the problem of non-measurable sets, we don't allow all subsets in the infinite case. Instead, we restrict to a carefully chosen collection of subsets called a $\sigma$-field.

For real numbers, the most common choice is the **Borel $\sigma$-field**.

1. It starts with all the open intervals (like (0.2, 0.5)).

2. Then, using the rules of σ-fields (unions, intersections, complements), it builds up a huge family of sets. This family includes:
   a. open sets,
   b. closed sets,
   c. intervals, rays,
   d. finite and countable unions, and more.

The Borel σ-field is big enough to cover every event we care about in practice, but small enough to exclude the problematic non-measurable sets.

In conclusion, imagine a $\sigma$-field as a **safe menu of events** which lets us assign probabilities consistently without running into paradoxes. Although for small cases like coin toss or rolling a die, we can include all subsets in the $\sigma$-field, however, in the infinite or continuous cases, we must be careful due to the existence of non-measurable sets.

---

## Probability Measure 𝑃
In a probability space (Ω, 𝒜, P), the probability measure 𝑃 is a function that assigns a number (probability) to each event in the σ-field 𝒜.

**Intuition:** Imagine you need to assign weights across all possible outcomes. The total weight you assign is 1 (100%). Each outcome gets a portion of that weight. Outcomes with a higher likelihood of occurrence are assigned with larger weight as compared to outcomes with a lower likelihood of occurrence. 

Formally,

$$
P: 𝒜 \to [0,1]
$$

### Properties of Probability Measure P

#### 1. Non-negativity
For every event `A ∈ 𝒜`:

$$
P(A) \geq 0
$$

#### 2. Normalization
The probability of the whole sample space is 1:

$$
P(\Omega) = 1
$$

#### 3. Countable Additivity (σ-additivity)
For any countable collection of disjoint events `A₁, A₂, … ∈ 𝒜`:

$$
P\left( \bigcup_{i=1}^{\infty} A_i \right) 
= \sum_{i=1}^{\infty} P(A_i)
$$

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
