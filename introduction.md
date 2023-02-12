---
description: >-
  An introdcution to verifiable computing, zero knowledge proof and other
  important terms...
layout: landing
---

# Introduction

Introduced in 1980s, Verifiable Computing (VC) refers to the cryptographic primitive called Interactice Proofs (IPs) and arguments, which allows a prover $$\mathcal{P}$$ to convince a verifier $$\mathcal{V}$$ that a delegated computation is correctly performed.

In general, VC can be defined as a process where the verifier as a party, checks the output of a computation performed by the prover. This is achieved by using cryptographic techniques, such as homomorphic encryption or other subtle protocols, even with their composition, to allow the verifier to validate the result of the computation without revealing any confidential information (or, to say privacy). The goal of verifiable computing is to provide a way to ensure the correctness and integrity of the computation, while still preserving privacy and security.

For example, in the training procedure of Machine Learning (ML), it's common now to outsource the computation to a trusted third party (TTP), e.g. a cloud service provider. The corresponding question is that how to assure that the result of the training or computation is correct or without pollution (that is, the integrity of the computing result)? The situation may truely happened is that the TTP may be compromised or the computing is exceuted with some error that cannot be ignored.

Generally speaking, we can view verifiable computing as a collection of protocols, that allows the verifier believing in a computation result without cumbersome calculation. 

## Interactive Proofs

We can say IPs are the most important schemes to implement VC.

An interactive proof can be defined as a system that allows the prover $$\mathcal{P}$$ to convince the verifier $$\mathcal{V}$$ that the execution of some computation is correct through many rounds of interaction.

Formally, an interactive proof system can be defined as follow: 

Given a prescribed function $$f$$ and some common inputs $$x \in \{0,1\}^n$$, $$\mathcal{P}$$ claimed it holds that the  $$f(x)=y$$. An interactive proof system consists of the prover and verifier (namely, $$\mathcal{P}$$ and $$\mathcal{V}$$) and a collection of algorithms $$\Pi$$ running by them. $$\mathcal{P}$$ and $$\mathcal{V}$$ will exchange a sequence of messages $$m_1...m_k$$ which are outputs of algorithms inside $$\Pi$$. The entire sequence of k messages $$t := (m_1, ... ,m_k)$$  exchanged by $$\mathcal{P}$$ and $$\mathcal{V}$$, along with the claimed answer $$y$$, are called a transcript. At the end of the protocol, $$\mathcal{V}$$ should output $$1$$ for accepting the claim, or $$0$$ for rejecting it.

See the [article](https://dl.acm.org/doi/abs/10.1145/3335741.3335750) of Goldwasser, Micali, and Rackoff for more details. 

An interactive proof should have the following two properties: *completeness* and *soundness.*

- **Completeness**: For every $$x \in \{0,1\}^n$$ and correct claim $$y$$, it holds that:

$$
\mathbf{Pr}[\mathbf{out}(x,t)=1]=1
$$

- $\epsilon$-**Soundness**: For any $$x \in \{0,1\}^n$$ and a incorrect claim $$f(x) \neq y$$, it holds that:

$$
\mathbf{Pr}[\mathbf{out}(x,t)=1]=\epsilon (\epsilon \approx 0)
$$

These property promises that the system will convince $$\mathcal{V}$$ the computation result for every correct claim and accept a wrong claim with only a negligible probability $$\epsilon$$.
