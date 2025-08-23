# 1. Probability Space
**Probability Spaces** are used to model random processes or experiments. It is defined as a triple:
$$(\Omega, \mathcal{A}, P)$$

where  
- $$\Omega$$ is the **sample space** (all possible outcomes),  
- $$\mathcal{A}$$ is a **$$\sigma$$-field (sigma-algebra)**,  
- $$P$$ is the **probability measure**. 

## Understanding $$\sigma$$-field $$\mathcal{A}$$
$$\sigma$$ algebra is collection of subsets of **$$\Omega$$** that satifies below three properties.
1. $$\mathcal(A)$$ contains sample space \
   $$\Omega \in \mathcal{A}$$ \
   **Intuition:** The whole set of possible outcomes should be in **$$\mathcal{A}$$** as probability must always be define over entire sample _(and must be equal to 1)_. For example, possible outcomes of a coin toss are $${H, T}$$,  so both $$H$$ and $$T$$ must be included as events.
3. 
