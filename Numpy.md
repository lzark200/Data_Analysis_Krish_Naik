# 🔢 NumPy Comprehensive Guide

<div align="center">

[![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

**The Ultimate NumPy Reference for Data Scientists & Analysts**

*From fundamentals to advanced mathematical operations*

[Quick Start](#-quick-start) • [Documentation](#-table-of-contents) • [Examples](#-examples) • [Contributing](#-contributing)

</div>

---

## 🚀 Quick Start

```bash
pip install numpy
```

```python
import numpy as np

# Create your first NumPy array
arr = np.array([1, 2, 3, 4, 5])
print(f"Array: {arr}")
print(f"Mean: {np.mean(arr)}")
print(f"Shape: {arr.shape}")
```

---

## 📋 Table of Contents

- [🎯 What is NumPy?](#-what-is-numpy)
- [🏗️ Core Data Structure: ndarray](#️-core-data-structure-ndarray)
- [🧮 Mathematical Functions](#-mathematical-functions)
  - [Basic Arithmetic](#-basic-arithmetic-operations)
  - [Statistical Functions](#-statistical-functions)
  - [Exponential & Logarithmic](#-exponential--logarithmic-functions)
  - [Trigonometric Functions](#-trigonometric-functions)
  - [Linear Algebra](#-linear-algebra-functions)
  - [Random Operations](#-random-functions)
  - [Utility Functions](#-utility-functions)
- [❓ Common Issues & Solutions](#-common-issues--solutions)
- [📖 Examples](#-examples)
- [🤝 Contributing](#-contributing)

---

## 🎯 What is NumPy?

**NumPy** (Numerical Python) is the fundamental package for scientific computing in Python. It provides:

| Feature | Description |
|---------|-------------|
| 🏎️ **Performance** | Up to 100x faster than pure Python for numerical operations |
| 📊 **N-dimensional Arrays** | Powerful ndarray object for multi-dimensional data |
| 🔢 **Mathematical Functions** | Comprehensive library of mathematical operations |
| 🔗 **Ecosystem Integration** | Foundation for Pandas, SciPy, Scikit-learn, TensorFlow |

### Why NumPy over Python Lists?

```python
# ❌ Python Lists (Slow)
python_list = [1, 2, 3, 4, 5]
result = [x * 2 for x in python_list]  # Loop overhead

# ✅ NumPy Arrays (Fast)
numpy_array = np.array([1, 2, 3, 4, 5])
result = numpy_array * 2  # Vectorized operation
```

---

## 🏗️ Core Data Structure: ndarray

The **ndarray** (N-dimensional array) is NumPy's main data structure:

### Key Properties

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])

print(f"Shape: {arr.shape}")     # (2, 3) - 2 rows, 3 columns
print(f"Dimensions: {arr.ndim}") # 2 - 2D array
print(f"Data type: {arr.dtype}") # int64
print(f"Size: {arr.size}")       # 6 - total elements
```

### Array Creation Methods

| Method | Example | Description |
|--------|---------|-------------|
| `np.array()` | `np.array([1,2,3])` | From Python list |
| `np.zeros()` | `np.zeros((3,4))` | Array of zeros |
| `np.ones()` | `np.ones(5)` | Array of ones |
| `np.arange()` | `np.arange(0,10,2)` | Range of values |
| `np.linspace()` | `np.linspace(0,1,5)` | Evenly spaced values |
| `np.random.rand()` | `np.random.rand(3,3)` | Random values |

---

## 🧮 Mathematical Functions

### ➕ Basic Arithmetic Operations

```python
arr = np.array([1, 2, 3, 4, 5])

# Element-wise operations
print(arr + 5)    # [6 7 8 9 10]
print(arr * 2)    # [2 4 6 8 10]
print(arr ** 2)   # [1 4 9 16 25]
print(arr / 2)    # [0.5 1. 1.5 2. 2.5]
```

### 📊 Statistical Functions

Essential for data analysis:

| Function | Usage | Description |
|----------|-------|-------------|
| `np.mean()` | `np.mean(arr)` | Average value |
| `np.median()` | `np.median(arr)` | Middle value |
| `np.std()` | `np.std(arr)` | Standard deviation |
| `np.var()` | `np.var(arr)` | Variance |
| `np.min()` | `np.min(arr)` | Minimum value |
| `np.max()` | `np.max(arr)` | Maximum value |
| `np.percentile()` | `np.percentile(arr, 75)` | Percentile value |

#### Multi-dimensional Statistics

```python
arr2d = np.array([[1, 2, 3], [4, 5, 6]])

# Axis operations
np.sum(arr2d, axis=0)    # [5 7 9]  - Column-wise
np.sum(arr2d, axis=1)    # [6 15]   - Row-wise
np.sum(arr2d)            # 21       - All elements
```

### 📈 Exponential & Logarithmic Functions

Critical for machine learning and data transformation:

```python
# Exponential
np.exp([1, 2, 3])           # [2.718, 7.389, 20.086]

# Logarithmic
np.log([1, np.e, np.e**2])  # [0., 1., 2.]
np.log10([1, 10, 100])      # [0., 1., 2.]
np.log2([1, 2, 4, 8])       # [0., 1., 2., 3.]
```

### 📐 Trigonometric Functions

Useful for signal processing and transformations:

```python
angles = np.array([0, np.pi/4, np.pi/2, np.pi])

np.sin(angles)      # [0., 0.707, 1., 0.]
np.cos(angles)      # [1., 0.707, 0., -1.]
np.tan(angles)      # [0., 1., inf, 0.]

# Conversions
np.degrees(np.pi)   # 180.0
np.radians(180)     # 3.14159...
```

### 🔢 Linear Algebra Functions

Essential for machine learning and data science:

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[2, 0], [1, 2]])

# Matrix operations
np.dot(A, B)           # Matrix multiplication
np.matmul(A, B)        # Alternative matrix multiplication
A @ B                  # Python 3.5+ matrix multiplication

# Matrix properties
np.linalg.det(A)       # Determinant
np.linalg.inv(A)       # Inverse matrix
np.linalg.eig(A)       # Eigenvalues and eigenvectors
np.linalg.norm(A)      # Matrix norm
```

### 🎲 Random Functions

For data simulation and sampling:

```python
# Set seed for reproducibility
np.random.seed(42)

# Basic random generation
np.random.rand(3)              # [0,1) uniform distribution
np.random.randn(3)             # Standard normal distribution
np.random.randint(1, 10, 5)    # Random integers

# Advanced sampling
np.random.choice([1,2,3,4], size=10, replace=True)
np.random.choice(['A','B','C'], size=5, p=[0.5, 0.3, 0.2])  # Weighted
```

### 🔧 Utility Functions

```python
arr = np.array([1.2, 2.7, 3.1, -4.5])

# Rounding
np.round(arr)      # [1. 3. 3. -4.]
np.floor(arr)      # [1. 2. 3. -5.]
np.ceil(arr)       # [2. 3. 4. -4.]

# Absolute values
np.abs(arr)        # [1.2 2.7 3.1 4.5]

# Comparison operations
arr > 2            # [False True True False]
np.where(arr > 2, "High", "Low")  # ['Low' 'High' 'High' 'Low']
```

---

## ❓ Common Issues & Solutions

### 🔍 1. Array vs List Confusion

| Aspect | Python List | NumPy Array |
|--------|-------------|-------------|
| **Data Types** | Mixed types allowed | Homogeneous (same type) |
| **Performance** | Slower (Python loops) | Faster (C optimized) |
| **Memory** | More overhead | Contiguous memory |
| **Operations** | Limited math operations | Rich mathematical functions |

### 🔍 2. Shape, Size, and Dimensions

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])

print(f"Shape: {arr.shape}")    # (2, 3) - dimensions
print(f"Size: {arr.size}")      # 6 - total elements  
print(f"ndim: {arr.ndim}")      # 2 - number of axes
```

### 🔍 3. Matrix vs Element-wise Operations

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[2, 1], [1, 2]])

# ❌ Element-wise multiplication
A * B              # [[2, 2], [3, 8]]

# ✅ Matrix multiplication
np.dot(A, B)       # [[4, 5], [10, 11]]
A @ B              # Same as np.dot(A, B)
```

### 🔍 4. Axis Parameter Confusion

> **Rule of thumb**: The axis parameter specifies which dimension gets "collapsed"

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])

np.sum(arr, axis=0)    # [5, 7, 9]  - Sum along rows (collapse rows)
np.sum(arr, axis=1)    # [6, 15]    - Sum along columns (collapse columns)
```

### 🔍 5. NaN Handling

```python
arr = np.array([1, 2, np.nan, 4, 5])

# ❌ Regular functions propagate NaN
np.mean(arr)           # nan

# ✅ NaN-aware functions
np.nanmean(arr)        # 3.0
np.nansum(arr)         # 12.0
np.nanstd(arr)         # 1.58
```

### 🔍 6. Copy vs View

```python
original = np.array([1, 2, 3, 4, 5])

# View (shares memory)
view = original[1:4]
view[0] = 999          # Changes original!

# Copy (independent)
copy = original.copy()
copy[0] = 999          # Doesn't affect original
```

---

## 📖 Examples

### Example 1: Data Analysis Pipeline

```python
# Generate sample data
data = np.random.normal(100, 15, 1000)  # Mean=100, Std=15

# Statistical analysis
print(f"Mean: {np.mean(data):.2f}")
print(f"Median: {np.median(data):.2f}")
print(f"Std Dev: {np.std(data):.2f}")
print(f"Min: {np.min(data):.2f}")
print(f"Max: {np.max(data):.2f}")

# Percentiles
percentiles = np.percentile(data, [25, 50, 75])
print(f"Q1, Q2, Q3: {percentiles}")
```

### Example 2: Image Processing Basics

```python
# Simulate a grayscale image (2D array)
image = np.random.randint(0, 256, (100, 100), dtype=np.uint8)

# Basic operations
print(f"Image shape: {image.shape}")
print(f"Pixel value range: {image.min()} - {image.max()}")

# Image transformations
brighter = np.clip(image + 50, 0, 255)  # Increase brightness
darker = np.clip(image - 50, 0, 255)    # Decrease brightness
inverted = 255 - image                   # Invert colors
```

### Example 3: Linear Algebra in Machine Learning

```python
# Feature matrix (samples x features)
X = np.random.rand(100, 5)
# Target vector
y = np.random.rand(100)

# Compute correlation matrix
correlation_matrix = np.corrcoef(X.T)

# Normal equation for linear regression (simplified)
# θ = (X^T X)^(-1) X^T y
XtX = X.T @ X
XtX_inv = np.linalg.inv(XtX)
Xty = X.T @ y
theta = XtX_inv @ Xty

print(f"Regression coefficients: {theta}")
```

---

## 🔗 Additional Resources

- 📚 [Official NumPy Documentation](https://numpy.org/doc/)
- 🎓 [NumPy Tutorials](https://numpy.org/learn/)
- 📝 [NumPy Cheat Sheet](https://numpy.org/devdocs/user/quickstart.html)
- 🎥 [Video Tutorials](https://www.youtube.com/results?search_query=numpy+tutorial)

---

## 🤝 Contributing

Contributions are welcome! Please feel free to:

1. 🐛 Report bugs
2. 💡 Suggest improvements  
3. 📖 Add examples
4. 🔧 Fix documentation

### How to Contribute

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## ⭐ Show Your Support

If this guide helped you, please consider:

- ⭐ Starring this repository
- 🍴 Forking for your own reference
- 📢 Sharing with fellow data scientists

---

<div align="center">

**Happy Computing with NumPy! 🎉**

*Made with ❤️ for the Data Science Community*

</div>
