# RandomizedLinearAlgebra
notes
Sketching is able to compress a large matrix into a smaller matrix

Evaluate the sketching matrix by observing the values of M = $\mathbf S^T\mathbf S$

Let the original matrix be of size mxn and our sketching matrix be size dxn.

Gaussian Sketching
Expectation of the matrix is 1 if i ==j and 0 otherwise. We see our variance is 2/d if i == j and 1/d otherwise. d is the size of the rows or the sketching matrix.
Runtime: O(mnd)

Count Sketch
1. create the matrix C initalizing a dxn to all zeros
2. For j = 1 to n:
    3. uniformaly choose a value i from 1 to d
    4. uniformaly choose a value g from {-1, +1}
    5. C += Aij * g
Expectation of the matrix is 1 if i ==j and 0 otherwise. We see our variance is 0 if i == j and 1/d otherwise. d is the size of the rows or the sketching matrix.
Runtime: O(mn)



Frobeious Norm of a mtrix is the element wise l2 norm of a matrix and so we can use this as a way to get the accuracy of our sketching by using the error formula of 
$$Error (\%) = 100\times\frac{\parallel{}(\mathbf{MA})^T\mathbf{MA} - \mathbf{A}^T\mathbf A \parallel_F}{\parallel{}\mathbf{A}^T\mathbf A \parallel_F}.$$
We define M as the sketching matrix and then A as the actual matrix.


Visualizations
We can see that the accuracy of both the matrices is roughly the same, but the difference is in the runtime as we can see that Gaussian Sketching is not as runtime efficeint as Count Sketching.



Kenneth L. Clarkson and David P. Woodruff. Low rank approximation and regression in input sparsity time. In STOC, 2013.Kenneth L. Clarkson and David P. Woodruff. Low rank approximation and regression in input sparsity time. In STOC, 2013.