# Encryption with LWE

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