# Learning-With-Errors (LWE)

## What is it?

In cryptography, **Learning-With-Errors** (**LWE**) is a mathematical problem that is widely used to create secure encryption algorithms.

Let \\(\mathbb{Z}_q\\) denote the ring of integers modulo \\(q\\) and let \\(\mathbb{Z}_q^n\\) denote the set of \\(n\\)\-vectors over \\(\mathbb{Z}_q\\). There exists a certain unknown linear function \\(f: \mathbb{Z}_q^n \rightarrow \mathbb{Z_q}\\), and the input to the LWE problem is a sample of pairs \\((x, y),\\) where \\(x \in \mathbb{Z}_q^n\\) and \\(y \in \mathbb{Z}_q\\), so that with high probability \\(y = f(x)\\).

It is based on the idea of representing secret information as a set of vector equations with errors. In other words, LWE is a way to hide the value of a secret by introducing noise to it.

The concept of Learning-With-Errors (LWE) introduces a computational problem where solving linear equations becomes infeasible due to the addition of noise. Specifically, LWE is based on the premise that given a set of linear equations defined over a finite field, it is computationally hard to find the solution when each equation is perturbed by a small, random error. This principle leverages the difficulty in distinguishing between random noise and structured data, laying the groundwork for cryptographic schemes that are secure against quantum attacks. The noise component is essential, as it obscures the relationship between the input vectors and their corresponding outputs, making it challenging to reverse-engineer the secret linear function.

## Contents

1. **LWE**: Fundamental definitions, properties, and the concept of noise injection
2. **Ring-LWE**: Applying the LWE setup into polynomial rings