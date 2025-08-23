# 1. Probability Space
**Probability Spaces** are used to model random processes or experiments. It is defined as a triple:
$$(\Omega, \mathcal{A}, P)$$

where  
- $$\Omega$$ is the **sample space** (all possible outcomes),  
- $$\mathcal{A}$$ is a **$$\sigma$$-field (sigma-algebra)**,  
- $$P$$ is the **probability measure**. 

## Understanding $$\sigma$$-field $$\mathcal{A}$$
$$\sigma$$ algebra is collection of subsets of **$$\Omega$$** that satifies below three properties.
1. **It contains sample space** \
   $$\Omega \in \mathcal{A}$$ 

   Possible outcomes of a coin toss are $${H, T}$$,  so both $$H$$ and $$T$$ must be included as events.
   
   **Intuition:** The whole set of possible outcomes should be in **$$\mathcal{A}$$** as probability must always be defined over the entire sample _(and must be equal to 1)_.
   
3. **It’s closed under complements:**  
   If $$\(A \in \mathcal{A}\)$$, then its complement $$\(A^c \in \mathcal{A}\)$$.
   
   If there is an event in the $$\sigma$$-field, then its opposite should also be in the $$\sigma$$-field. For example, if “rain” is an event, then “no rain” must also be an event.
      
   **Intuition:** Probability deals with something happening and not happening. If we only allowed one side, we couldn't assign consistent probabilities.

5. **It’s closed under countable unions (and intersections):**  
   If $$\(A_1, A_2, A_3, \dots \in \mathcal{A}\)$$, then  
   $$\(\bigcup_{i=1}^\infty A_i \in \mathcal{A}\)$$.
   
   If “rain on Monday,” “rain on Tuesday,” “rain on Wednesday,” … are events, then “rain on some day” must also be an event.
    
   **Intuition:** Probability should not only apply to the single events, but also to combined events.
