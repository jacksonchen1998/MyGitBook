# Linear Algebra

> Page 35

The **span** of a set of vectors is the set of all points obtainable by linear combination of the original vectors.

Determining whether **Ax = b has a solution** thus amounts to testing whether b is in the span of the columns of A. This particular span is known as the **column space** or the **range** of A.

> Page 37

Sometimes we need to measure the size of a vector. In machine learning, we usually measure the size of vectors using a function called a **norm.**

$$
||x||p=(\sum_{i}|x_{i}|^p)^{\frac{1}{p}} \ \ \ ,for \  p  ∈ R, p ≥ 1
$$

A norm is any function f that satisfies the following properties:

* The norm/size of a vector is zero if and only if the vector is the zero vector.

$$
f(x)=0 \Rightarrow x = 0
$$

* The norm/size of the sum of two vectors should be no greater than the sum of the sizes of the two vectors. More specifically, the equality holds when the two vectors are parallel. Also known as the triangle inequality, where the length of any side of a triangle cannot be greater than the sum of the lengths of the other two sides.

$$
f(x+y) \le \ f(x) + f(y)
$$

* Scaling a vector scales its norm/size by the same positive amount since size must be more than or equal to zero. The size of a doubled vector is twice the size of the original vector.

$$
\forall  \alpha \in \R, f(\alpha \bold{x})=|\alpha|f(\bold{x})
$$

> Page 38

Sometimes we may also wish to measure the size of a matrix. In the context of deep learning, the most common way to do this is with the otherwise obscure **Frobenius norm,** which is analogous to the L2 norm of a vector.

$$
||A||_{F}= \sqrt{\sum_{i,j}}A^{2}_{i,j}
$$
