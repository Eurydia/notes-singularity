# Sample space

Let $(\Omega, \mathcal{F}, P)$ be a [[Discrete probability space|discrete probability space]].

A sample space, denoted by $\Omega$, is the finite non-empty set of all possible outcomes of a random experiment. 

To be considered a valid sample space, a set of outcomes must satisfy three requirements:

**Mutually exclusive outcomes** 

Outcomes of a random experiment must be mutually exclusive, meaning that only one outcome can occur at a time. 

Consider a random experiment of tossing a coin once, the outcomes "heads" and "tails" are mutually exclusive since the coin can land on only one side.

**Collectively exhaustive outcomes** 

A sample space must include every possible outcome of the experiment. 
In other words, it should cover all potential results without omission. 

Consider a random experiment of rolling a six-sided dice once, a sample space such as $\Omega_{1}=\{1, 2, 3, 4, 5\}$ is incomplete because it fails to include the outcome of rolling a six.

**Fine-grained representation** 

A sample space should provide a detailed and relevant description of outcomes without unnecessary complexity. 
It should include all pertinent information without redundancy. 

Consider a random experiment of tossing a coin once, a sample space like $\Omega_2 =\{H, T\}$, where $H$ is the outcome where the coin lands on heads and $T$ is for tails, preferable over $\Omega_3 = \{(H, R), (H, NR), (T, R), (T, NR)\}$ where $(H, R)$ is the outcome where the coin lands on heads while it is raining, $(H, NR)$ is for heads while it is not raining, and so on, because it succinctly represents the essential outcomes without irrelevant details.
