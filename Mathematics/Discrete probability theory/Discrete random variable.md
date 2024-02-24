# Discrete random variable

Let $(\Omega, \mathcal{F}, P)$ be a [[Discrete probability space|discrete probability space]].

A discrete random variable $X:\Omega\to\mathbb{R}$ is a function which assigns a real number value to each outcome in the [[Sample space|sample space]] $\Omega$.

## Discrete uniform random variable

A discrete random variable $X:\Omega\to\mathbb{R}$ which can take one of $n$ possible values has uniform distribution if the [[Probability mass function|probability mass function]] $p$ of $X$ is defined as:

$$
p_{X}(x) = 
\begin{cases}
\frac{1}{n} & x\in \{X(\omega)|\omega\in\Omega\}\\
 0          & \text{otherwise}
\end{cases}
$$

The notation for $X$ is $X\sim\text{Uniform}(n)$.

## Discrete geometric random variable

Consider a random experiment with $n \in \mathbb{N}$ independent trials, each with probabilities of success and failure $\rho$ and $1-\rho$ respectively.

A discrete random variable $X:\Omega\to{N}_{\ge0}$ has a geometric distribution if the probability mass function $p$ of $X$ is defined as:

$$
p_{X}(x) =
\begin{cases}
(1-\rho)^{x}\rho & x\in{N}_{\ge0}\\
0                & \text{otherwise}
\end{cases}
$$

The notation for $X$ is $X\sim\text{Geometric}(\rho)$.

## Discrete binomial random variable

Consider a random experiment with $n \in \mathbb{N}$ independent trials, each with probabilities of success and failure $\rho$ and $1-\rho$ respectively.

A discrete random variable $X:\Omega\to{N}_{\ge0}$, representing the number of successful trials in each experiment, has a binomial distribution if the probability mass function $p$ of $X$ is defined as:

$$
p_{X}(x) = 
\begin{cases}
\binom{n}{x}(1-\rho)^{n-x}\rho^{x} & x\in{N}_{\ge0}\\
0           & \text{otherwise}
\end{cases}
$$

The notation for $X$ is $X\sim\text{Binomial}(n,\rho)$.

## Discrete Bernoulli random variable

Consider a random experiment with two outcomes, success or failure, each with probabilities $\rho$ and $1-\rho$ respectively.

A discrete random variable $X:\Omega\to\{0,1\}$, assigning $1$ to successful experiments and $0$ to failed experiments, has a Bernoulli distribution if the probability mass function $p$ of $X$ is defined as:

$$
p_{X}(x) = 
\begin{cases}
\rho   & x = 1\\
1-\rho & x = 0\\
0      & \text{otherwise}
\end{cases}
$$

The notation for $X$ is $X\sim\text{Bernoulli}(\rho)$.

## Discrete Poisson random variable

Consider a random experiment where events occur independently over a continuous interval of time or space, with average rate $\lambda$ of events per unit interval.

A discrete random variable $X:\Omega\to\mathbb{N}_{\ge0}$, representing the number of events occurring in a fixed interval, has a Poisson distribution if the probability mass function $p$ of $X$ is defined as:

$$
p_{X}(x) = 
\begin{cases}
\frac{\lambda^{k}\cdot e^{-\lambda}}{k!} & x\in{N}_{\ge0}\\
0           & \text{otherwise}
\end{cases}
$$

The notation for $X$ is $X\sim\text{Poisson}(\lambda)$.
