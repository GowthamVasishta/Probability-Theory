# 1. Probability Space
**Probability Spaces** are used to model random processes or experiments. It is defined as a triple:
$(\Omega, 𝒜, P)$

where  
- $$\Omega$$ is the **sample space** (all possible outcomes),  
- $$𝒜$$ is a **$$\sigma$$-field (sigma-algebra)**,  
- $$P$$ is the **probability measure**. 

## Understanding $$\sigma$$-field 𝒜
**$$\sigma$$ algebra** is collection of subsets of **$$\Omega$$** that satifies below three properties.
1. **It contains sample space** \
   $$\Omega \in 𝒜$$ 

   Possible outcomes of a coin toss are {H, T},  so both $$H$$ and $$T$$ must be included as events.
   
   **Intuition:** The whole set of possible outcomes should be in 𝒜 as probability must always be defined over the entire sample _(and must be equal to 1)_.
   
3. **It’s closed under complements:**  
   If $$\(A \in 𝒜\)$$, then its complement $$\(A^c \in 𝒜\)$$.
   
   If there is an event in the $$\sigma$$-field, then its opposite should also be in the $$\sigma$$-field. For example, if “rain” is an event, then “no rain” must also be an event.
      
   **Intuition:** Probability deals with something happening and not happening. If we only allowed one side, we couldn't assign consistent probabilities.

5. **It’s closed under countable unions (and intersections):**  
   If $$\(A_1, A_2, A_3, \dots \in 𝒜\)$$, then  
   $$\(\bigcup_{i=1}^\infty A_i \in 𝒜\)$$.
   
   If “rain on Monday,” “rain on Tuesday,” “rain on Wednesday,” … are events, then “rain on some day” must also be an event.
    
   **Intuition:** Probability should not only apply to the single events, but also to combined events.

In short, $$\sigma$$-field always includes "everything happens", the  "opposite" of any event and combination of events to assign probabilities consistently without missing cases.

### Example on construction of $$\sigma$$-field 𝒜
Let's consider our sample space to be $\Omega = ${1, 2, 3}. The power set of $$\Omega$$ is all subsets of {1 ,2 ,3} i.e. $$2^3 = 8$$ subsets.  
𝒫(Ω)={ ∅, {1}, {2}, {3}, {1,2}, {1,3}, {2,3}, {1,2,3} }

This is the largest possible σ-field on {1,2,3}. But a $\sigma$-field doesn't always need the entire power set; we can construct it with a few subsets of the power set and still satisfy the three rules (contains Ω, closed under complements, closed under countable unions).  
   a. **A trivial $\sigma$-field** $A_1​=${ ∅,{1,2,3} } only "nothing" and "something" happen. Always valid but not quite useful.  
   b. **A non-trivial $\sigma$-field** Lets say we include {1}, then its complement is {2, 3}. Then a valid $\sigma$-field is as follows.  
      A2​={ ∅, {1}, {2,3}, {1,2,3} }

