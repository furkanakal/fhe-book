# Encryption with Ring-LWE

Ring-LWE extends the foundational concepts of LWE into the context of ring theory, optimizing the efficiency of cryptographic operations. This approach involves the utilization of polynomial rings for key generation, encryption, and decryption, thereby streamlining the cryptographic process. The security of Ring-LWE is predicated on the difficulty of solving the LWE problem within the context of polynomial rings, which, like its predecessor, is believed to be resistant to quantum attacks. The process encompasses the generation of keys through the selection of elements within a specific ring, followed by the encryption and decryption of messages. This methodology effectively encapsulates messages within the complexity of the Ring-LWE problem, ensuring their confidentiality and integrity.

### Public Setup

* A prime \\(p\\) and dimension \\(n\\) and resulting Ring-LWE ring:
    

$$R_p := \mathbb{Z}[x]/(x^n + 1),$$

* A moderately large \\(k \in \mathbb{Z}.\\)
    

### Key-Pair Generation

* Bob selects a small random element \\(s \in R_p\\).
    
* Bob selects a small random element \\(e_1 \in R_p\\).
    
* Bob defines \\((a, b) \in R_p \times R_p,\\) where \\(b = a \cdot s + e_1\\).
    
* Bob keeps \\(s\\) as his private ket and shares \\((a, b)\\) as his public key.
    

### Encryption

* Alice selects a random \\(r \in R_p\\), this is the ephemeral key.
    
* Alice selects small random \\(e_2, e_3 \in R_p\\).
    
* Alice defines
    

$$v = a \cdot r + e_2$$

$$w = b \cdot r + e_3 + k \cdot m.$$

* Alice sends the ciphertext \\((v, w)\\) to Bob.
    

### Decryption

* Bob computes
    

$$x = w - v \cdot s.$$

* Bob rounds \\(x\\) to the nearest multiple of \\(k\\).
    
* Bob divides the result by \\(k,\\) reveals the message.
    

## Verifying the Correctness

$$x = w - vs$$

$$x = br + e_3 + km - (ar + e_2)s$$

$$x = br + e_3 + km - ars - e_2s$$

$$x = ars + e_1r + e_3 + km - ars - e_2s$$

$$x = km + e_1r + e_3 - e_2s$$

As \\(e_1r + e_3 - e_2s\\) is a fairly small element of \\(R_p\\), rounding to the nearest multiple of \\(k\\) (moderately large) gives \\(k \cdot m \\) . Hence, dividing it by \\(k\\) reveals \\(m.\\)
