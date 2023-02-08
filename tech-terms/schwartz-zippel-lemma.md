# Schwartz-Zippel Lemma

## Definition

**Multi-variate polynomial's degree:** Given any m-variate polynomial $$g(x_1, ..., x_m)$$, where each term can be a product of some variates with any exponents (e.g. $$g(x_1,x_2,x_3)=x_1^2x_2+x_2^3x_3+4x_1x_3$$). Here the degree of each term in this polynomial is the sum of each variate's exponents. And the degree of this polynomial is the maximum of degree of any term in $$g$$.



**Schwartz-Zippel Lemma:** Let $$\mathbb{F}$$ be an field, and let $$g:\mathbb{F}^m\rightarrow\mathbb{F}$$ be a nonzero m-variate polynomial of total degree at most $$d$$ (that is, $$g(x_1, ... x_m)$$, in a function form). Then on any finite set $$S \subseteq \mathbb{F}$$, selecting some compositions of $$x_1, ..., x_n$$, the probability that the composition is a zero of the function is no more than $$\frac{d}{|S|}$$. Formally,&#x20;

$$
\begin{matrix} \mathbf{Pr}_{x \leftarrow S^m} \end{matrix} [g(x) = 0] ≤ \frac{d}{|S|}
$$



## Application

The success probability of randomly picking a value that is the zero of some polynomial is negligible.

In interactive protocols, we usually use a randomized challenge to verify the correctness of some arguments. This lemma gives us a way to introduce polynomials into the protocol.

We can prove that for any two distinct m-variate polynomials $$p$$ and $$q$$ of total degree at most $$d$$,  $$p(x)=q(x)$$ for at most $$\frac{d}{|\mathbb{F}|}$$ of inputs.&#x20;

