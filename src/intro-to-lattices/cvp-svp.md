# SVP & CVP

## The Shortest Vector Problem (SVP)

### Definition
Given a lattice \\( L \\), the length of the shortest non-zero vector in \\( L \\), which is also the minimum distance between any two lattice vectors, is defined as:

\\[
\lambda_1(L) = \min_{v \in L \setminus \{0\}} \| v \|,
\\]

where the norm is defined as:

\\[
\| v \| = \sqrt{v_1^2 + v_2^2 + \dots + v_n^2}.
\\]

The difficulty of SVP arises from the fact that as the dimension increases, finding the shortest vector in a lattice becomes exponentially more challenging.

## The Closest Vector Problem (CVP)

### Definition
Given a basis \\( B \\) and a target vector \\( t \\) that is not in the lattice \\( L(B) \\), the goal is to find a vector in \\( L(B) \\) that is closest to \\( t \\). That is, find a vector \\( v \in L(B) \\) such that for all \\( w \in L(B) \\), it satisfies:

\\[
\| v - t \| \leq \| w - t \|.
\\]

Similar to the SVP, the closest vector problem also becomes extremely difficult as the number of dimensions increases.

