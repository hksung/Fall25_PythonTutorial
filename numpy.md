---
layout: page
title: Numpy
---

### Numpy

- NumPy is an optimized library designed for matrix and vector computation in Python. NLP often involves representing words and sentences as vectors (e.g., word embeddings) and performing matrix operations for neural networks. Libraries like *scikit-learn*, *PyTorch*, and *spaCy* all depend on NumPy under the hood.

- [Documentation](https://numpy.org/doc/stable/)

### Core data type

- `np.ndarray`: Main data type used for representing arrays (vectors/matrices).
- Use the constructor function `np.array()` to create arrays.

```python
import numpy as np
a = np.array([1, 2, 3])  # 1D array (vector)
b = np.array([[1, 2], [3, 4]])  # 2D array (matrix)

print(a.shape) # → (3,)
print(b.shape) # → (2,2)
```

### Element-wise arithmetic

You can perform element-wise operations using both Python operators (`+`, `-`, `*`, `/`) and NumPy functions (`np.add()`, `np.subtract()`, `np.multiply()`, `np.divide()`).


```python
import numpy as np

x = np.array([1, 2, 3])
y = np.array([4, 5, 6])

# Addition (x + y)
result = x + y            # Same as np.add(x, y)
print(result)             # [5 7 9]

# Subtraction (x - y)
result = x - y            # np.subtract(x, y)
print(result)             # [-3 -3 -3]

# Multiplication (element-wise)
result = result * x       # np.multiply(result, x)
print(result)             # Output: [-3 -6 -9]

# Division (element-wise)
result = result / x       # np.divide(result, x)
print(result)             # Output: [-3. -3. -3.]
```

The `*` operator performs element-wise multiplication. For matrix multiplication, use `np.dot()`

```python
mat1 = np.array([[1, 2],
                 [3, 4]])
mat2 = np.array([[5, 6],
                 [7, 8]])

mat3 = np.dot(mat1, mat2)
print(mat3)
# Output:
# [[19 22]
#  [43 50]]
```

### Indexing

NumPy offers flexible indexing methods to extract and manipulate data from arrays.

```python
import numpy as np

x = np.random.random((3, 4))  # Random matrix of shape (3, 4)
```

```python
x[:]           # Selects all elements in x
```
- Equivalent to copying the whole array.

```python
x[np.array([0, 2]), :]
```

* Selects the **0th and 2nd rows** from `x`.
* `:` selects all columns.

```python
x[1, 1:3]
```

* Selects from the **1st row**, elements at columns **1 and 2**.
* Returns a 1D array.

```python
x[x > 0.5]
```

* Returns all elements in `x` that are **greater than 0.5**.
* This is called **boolean masking**.
* Output is a 1D array containing only the values that satisfy the condition.

### Excercise


#### 1. How do you create a 2D array with all zeros and shape (3, 4)?

A. `np.zeros([3, 4])`  
B. `np.empty([3, 4])`  
C. `np.ones([3, 4])`  
D. `np.array([[0]*4]*3)`


#### 2. What does `x.shape` return if `x = np.array([[1, 2, 3], [4, 5, 6]])`?

A. `(3, 2)`  
B. `(6,)`  
C. `(2, 3)`  
D. `(1, 6)`

#### 3. Which of the following returns the mean of a NumPy array `x`?**

A. `mean(x)`  
B. `x.mean()`  
C. `np.avg(x)`  
D. `x.mean(axis=None)`


#### 4. What is the result of `np.array([1, 2, 3]) * 2`?**

A. `[2, 4, 6]`  
B. `[1, 2, 3, 1, 2, 3]`  
C. `[[1, 2, 3], [1, 2, 3]]`  
D. Error


#### 5. Which of the following creates a 3x1 column vector?**

A. `np.array([[1], [2], [3]])`  
B. `np.array([1, 2, 3])`  
C. `np.ones((3,))`  
D. `np.zeros((1, 3))`


#### 6. What does `np.dot(a, b)` compute when `a` and `b` are 1D vectors?**

A. Element-wise product  
B. Outer product  
C. Dot (inner) product  
D. Matrix multiplication

#### 7. What is the shape of the result of `np.random.random((2, 3, 4))`?**

A. `(3, 4)`  
B. `(2, 3, 4)`  
C. `(4, 3, 2)`  
D. `(2, 12)`

<details>
<summary style="color:Gray"><strong>Check answers!</strong></summary>

1. A  
2. C  
3. B and D  
4. A  
5. A  
6. C  
7. B

</details>


