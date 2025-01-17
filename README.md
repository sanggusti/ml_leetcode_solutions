# Leetcode-like of ML Problems from deep-ml.com Solutions

A Solution to Leetcode-like problems of ML Algorithms on <https://www.deep-ml.com/>. In this repository I notes my takeaway and the summary of the math concept behind each problem in readme. The scripts is in the root of this file.

## Matrix Times Vector

Consider matrix $A$ and a vector $v$, where Matrix $A$:

$$
A_{2,2} =
    \begin{pmatrix}
    a_{1,1} & a_{1,2}  \\
    a_{2,1} & a_{2,2}
    \end{pmatrix}
$$

Vector $v$:

$$
v =
    \begin{pmatrix}
    v_{1} \\
    v_{2}
    \end{pmatrix}
$$

The dot product of $A$ and $v$ results in a new vector:

$$
A \dot v =
    \begin{pmatrix}
    a_{1,1}v_{1} & a_{1,2}v_{2} \\
    a_{2,1}v_{1} & a_{2,2}v_{2}
    \end{pmatrix}
$$

Things to note, an $n \times m$ matrix will need to be multiplied by a vector size of m or else this will not work.

## Calculate Covariance Matrix

The covariance matrix is a fundamental concept in statistics, illustrating how much two random variables change together. It's essential for understanding the relationships between variables in a dataset. For a dataset with $n$ features, the covariance matrix is an $n \times n$ square matrix where each element (i, j) represents the covariance between the $i^th$ and $j^th$ features. Covariance is defined by the formula:

$$
cov(X,Y) = \frac{\sum_{i=1}^{n} (x_{i} - \bar{a}) (y_{i} - \bar{y})}{n - 1}
$$

Where:

- $X$ and $Y$ are two random variables (features)
- $x_{i}$ and $y_{i} are individual observations of $X$ and $Y$
- $\bar{x}$ and $\bar{y}$ are the means of $X$ and $Y$
- $n$ is the number of observations in the covariance matrix
- the diagonal elements (where $i=j$) indicates the variance of each feature
- the off-diagonal elements show the covariance between different features.

The matrix is symmetric as the covariance between $X$ and $Y$ is equal to the covariance between $Y$ and $X$, denoted as $cov(X,Y) = cov(Y,X)$.

## Jacobi Method

The Jacobi method is an iterative algorithm used for solving a system of linear equations $Ax = b$. This method is particularly useful for large systems where direct methods like Gaussian elimination are computationally expensive.

For a system of equations represented by $Ax=b$, where $A$ is a matrix and $x$ and $b$ are vectors, the Jacobi method involves the following steps:

1. Initializations, start with an initial guess of x.
2. Iteration, for each equation $i$ update $x[i]$ using:

$$
x[i] = \frac{1}{a_{ii}} (b[i] - \sum_{j \neq i}a_{ij}x[j])
$$

where $a_{ii}$ are the diagonal elements of $A$ and $a_{ij}$ are the off-diagonal elements.
3. Convergence, repeat the iteration until the changes in $x$ are below a certain tolerance or until a maximum number of iterations is reached.

The method may not converge for all matrices. Choosing a good initial guess can improve convergence. Diagonal dominance of $A$ ensures convergence of the Jacobi method.

## References

- The main site of [deep-ml.com](deep-ml.com)
- [Math notations for Markdowns and LaTex](https://en.wikibooks.org/wiki/LaTeX/Mathematics)
