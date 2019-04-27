---
title:  "Probability"
layout: default

---

# probability density function

Pdf of sum of two random variables:
<https://en.wikipedia.org/wiki/Probability_density_function#Sums_of_independent_random_variables>
<https://www.statlect.com/fundamentals-of-probability/sums-of-independent-random-variables>
$$f_{U+V}(x)=\int _{-\infty }^{\infty }f_{U}(y)f_{V}(x-y)\,dy=\left(f_{U}*f_{V}\right)(x)$$

# Distributions

## Binomial

<https://en.wikipedia.org/wiki/Binomial_distribution>

Distribution of sum of two independent binomial variables: $X \sim \def\Bin{\mathord{\rm Bin}}\Bin(n,p)$, $Y \sim \def\Bin{\mathord{\rm Bin}}\Bin(m,p)$, $X+Y \sim \Bin(n+m,p)$
<https://math.stackexchange.com/questions/1176385/sum-of-two-independent-binomial-variables>

# Random walk

There are $2^n$ paths of length $n$.
A path from the origin to an arbitrary point $(n, x)$ exists $\iff \ n = p+q, \quad x = p - q$.
There are $N_{n,x} = \binom{p+q}{p} = \binom{p+q}{q}$ valid paths.

Lemma. (Reflection principle) The number of paths from A to B which touch or cross the x-axis equals the number of all paths from A' to B.

Ballot theorem. In an election where candidate A receives p votes and candidate B receives q votes with p > q, what is the probability that A will be strictly ahead of B throughout the count?

$$P(A) = {\frac {p-q}{p+q}}$$

$$p_{n,r} = P(\{ S_n = r \}) = \binom{n}{\frac{n+r}{2}} 2^{-n}$$

# superlearn

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- probability -- pdf and cdf">
    <p>Your browser does not support iframes.</p>
</iframe>

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- probability -- random walk">
    <p>Your browser does not support iframes.</p>
</iframe>

