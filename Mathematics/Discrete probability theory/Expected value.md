# Expected value

Let $(\Omega, \mathcal{F}, P)$ be a [[Discrete probability space|discrete probability space]].

An expected value of a [[Discrete random variable|discrete random variable]] $X:\Omega\to\mathbb{R}$, denoted by $E[X]$, is a weighted average of every value that $X$ can take.
Symbolically,

$$
E[X] = \sum\limits_{x} x\cdot p_{X}(x)
$$

for all $x\in\{X(\omega) | \omega\in\Omega\}$.

## Expected value of discrete uniform random variable

For a discrete random variable $X:\Omega\to\mathbb{R}$ with a [[Discrete random variable#Discrete uniform random variable|uniform distribution]] which can take one of $n$ possible values, the expected value $E[X]$ is expressed as:

$$
E[X] = \frac{1}{n}\sum\limits_{x} x
$$

for all $x\in\{X(\omega)|\omega\in\Omega\}$.

## Expected value of discrete geometric random variable

For a discrete random variable $X:\Omega\to\mathbb{R}$ with a [[Discrete random variable#Discrete geometric random variable|geometric distribution]] where $\rho$ is the probability of success, the expected value $E[X]$ can be expressed as:

$$
E[X] = \frac{1}{\rho}
$$

## Expected value of discrete binomial random variable

For a discrete random variable $X:\Omega\to\mathbb{R}$ with a [[Discrete random variable#Discrete binomial random variable|binomial distribution]] and where $n$ is the number of trials and $\rho$ is possibility of success for each trial, the expected value $E[X]$ is expressed as:

$$
E[X] = n\rho
$$

## Expected value of discrete Bernoulli random variable

For a discrete random variable $X:\Omega\to\mathbb{R}$ with a [[Discrete random variable#Discrete Bernoulli random variable|Bernoulli distribution]] and $\rho$ is the probability of success, the expected value $E[X]$ is expressed as:

$$
E[X] = \rho
$$

## Expected value of discrete Poisson random variable

For a discrete random variable $X:\Omega\to\mathbb{R}$ with a [[Discrete random variable#Discrete Poisson random variable|Poisson distribution]] where $\lambda$ is the number of events occurring in a fixed interval, the expected value $E[X]$ is expressed as:

$$
E[X] = \lambda
$$