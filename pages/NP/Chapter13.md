Linear Algebra
NumPy provides a robust set of linear algebra functions that are essential for numerical computing. This chapter covers some of the most commonly used linear algebra operations: dot product, matrix multiplication, determinant, inverse, and eigenvalues and eigenvectors.

Dot Product
The dot product is a scalar product of two vectors, calculated as the sum of the products of corresponding elements.

Example
python
Copy code
import numpy as np

# Creating two 1D arrays (vectors)
vector1 = np.array([1, 2, 3])
vector2 = np.array([4, 5, 6])

# Dot product
dot_product = np.dot(vector1, vector2)
print("Dot product:", dot_product)
Matrix Multiplication
Matrix multiplication is the multiplication of two matrices to produce a third matrix. NumPy provides the matmul and dot functions for this purpose.

Example using matmul
python
Copy code
# Creating two 2D arrays (matrices)
matrix1 = np.array([[1, 2], [3, 4]])
matrix2 = np.array([[5, 6], [7, 8]])

# Matrix multiplication using matmul
matrix_product_matmul = np.matmul(matrix1, matrix2)
print("Matrix multiplication (matmul):\n", matrix_product_matmul)
Example using dot
python
Copy code
# Matrix multiplication using dot
matrix_product_dot = np.dot(matrix1, matrix2)
print("Matrix multiplication (dot):\n", matrix_product_dot)
Determinant
The determinant of a matrix is a scalar value that can be computed from its elements and provides important properties about the matrix. NumPy provides the linalg.det function to compute the determinant.

Example
python
Copy code
# Creating a 2D array (matrix)
matrix = np.array([[1, 2], [3, 4]])

# Determinant
determinant = np.linalg.det(matrix)
print("Determinant:", determinant)
Inverse
The inverse of a matrix is a matrix that, when multiplied with the original matrix, yields the identity matrix. NumPy provides the linalg.inv function to compute the inverse of a matrix.

Example
python
Copy code
# Inverse
inverse_matrix = np.linalg.inv(matrix)
print("Inverse matrix:\n", inverse_matrix)
Eigenvalues and Eigenvectors
Eigenvalues and eigenvectors are properties of a matrix that provide insights into its characteristics. NumPy provides the linalg.eig function to compute eigenvalues and eigenvectors.

Example
python
Copy code
# Eigenvalues and eigenvectors
eigenvalues, eigenvectors = np.linalg.eig(matrix)
print("Eigenvalues:", eigenvalues)
print("Eigenvectors:\n", eigenvectors)
Example Code
Here are comprehensive examples demonstrating the use of linear algebra functions:

python
Copy code
import numpy as np

# Creating two 1D arrays (vectors)
vector1 = np.array([1, 2, 3])
vector2 = np.array([4, 5, 6])

# Dot product
dot_product = np.dot(vector1, vector2)
print("Dot product:", dot_product)

# Creating two 2D arrays (matrices)
matrix1 = np.array([[1, 2], [3, 4]])
matrix2 = np.array([[5, 6], [7, 8]])

# Matrix multiplication using matmul
matrix_product_matmul = np.matmul(matrix1, matrix2)
print("Matrix multiplication (matmul):\n", matrix_product_matmul)

# Matrix multiplication using dot
matrix_product_dot = np.dot(matrix1, matrix2)
print("Matrix multiplication (dot):\n", matrix_product_dot)

# Creating a 2D array (matrix)
matrix = np.array([[1, 2], [3, 4]])

# Determinant
determinant = np.linalg.det(matrix)
print("Determinant:", determinant)

# Inverse
inverse_matrix = np.linalg.inv(matrix)
print("Inverse matrix:\n", inverse_matrix)

# Eigenvalues and eigenvectors
eigenvalues, eigenvectors = np.linalg.eig(matrix)
print("Eigenvalues:", eigenvalues)
print("Eigenvectors:\n", eigenvectors)
By using these linear algebra functions, you can perform a wide range of numerical computations, enabling deeper analysis and understanding of your data. These operations are fundamental in many areas of scientific computing, machine learning, and data analysis.
