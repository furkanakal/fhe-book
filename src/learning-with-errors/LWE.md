# Learning-With-Errors (LWE)

## What is it?

In cryptography, **Learning-With-Errors** (**LWE**) is a mathematical problem that is widely used to create secure encryption algorithms.

Let \\(\mathbb{Z}_q\\) denote the ring of integers modulo \\(q\\) and let \\(\mathbb{Z}_q^n\\) denote the set of \\(n\\)\-vectors over \\(\mathbb{Z}_q\\). There exists a certain unknown linear function \\(f: \mathbb{Z}_q^n \rightarrow \mathbb{Z_q}\\), and the input to the LWE problem is a sample of pairs \\((x, y),\\) where \\(x \in \mathbb{Z}_q^n\\) and \\(y \in \mathbb{Z}_q\\), so that with high probability \\(y = f(x)\\).

It is based on the idea of representing secret information as a set of vector equations with errors. In other words, LWE is a way to hide the value of a secret by introducing noise to it.

The concept of Learning-With-Errors (LWE) introduces a computational problem where solving linear equations becomes infeasible due to the addition of noise. Specifically, LWE is based on the premise that given a set of linear equations defined over a finite field, it is computationally hard to find the solution when each equation is perturbed by a small, random error. This principle leverages the difficulty in distinguishing between random noise and structured data, laying the groundwork for cryptographic schemes that are secure against quantum attacks. The noise component is essential, as it obscures the relationship between the input vectors and their corresponding outputs, making it challenging to reverse-engineer the secret linear function.

## Encryption with LWE

In the context of LWE-based encryption, the security model revolves around the difficulty of solving the LWE problem. The encryption scheme is constructed around a public and a private key, where the public key is derived from the private key with the addition of noise. This ensures that, while encryption can be performed by anyone possessing the public key, decryption is feasible only with the knowledge of the private key. The essence of this encryption lies in its ability to mask the message with a layer of computational complexity that is impractical to breach without the private key, thus ensuring confidentiality.

**Private Key:**\\(s \leftarrow \mathbb{Z}_q^n\\).

**Public Key:**\\((A, b \in \mathbb{Z}_q^N)\\) where

$$A = (a_1, a_2, ..., a_N) \leftarrow \mathbb{Z}_q^{n \times N}$$

and

$$b = s \cdot A + \epsilon$$

where \\(\epsilon\\) is a randomly chosen \\(N\\)\-vector.

**Encryption:** To encrypt a message \\(m \in \{ 0, 1 \}\\),

$$Enc(0) = (\mathbf{c}_1, c_2) = (\sum_i \mathbf{a}_i, \sum_i b_i)$$

$$Enc(1) = (\mathbf{c}_1, c_2) = (\sum_i \mathbf{a}_i, \lfloor q/2 \rfloor + \sum_i b_i).$$

**Decryption:** To decrypt a given ciphertext \\((\mathbf{c}_1, c_2)\\),

* \\(Dec((\mathbf{c}_1, c_2)) = 0\\) if \\(c_2 - s \cdot \mathbf{c_1}\\) is close to 0,
    
* \\(Dec((\mathbf{c}_1, c_2)) = 1\\) if \\(c_2 - s \cdot \mathbf{c_1}\\) is close to \\(\lfloor q/2 \rfloor\\).