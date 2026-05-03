# Numerical-Analysis
# 🔢 Numerical Methods in Python

A collection of 8 classic Numerical Methods implemented in simple Python with user input. Each program is beginner-friendly, minimal, and runs directly from the terminal.

---

## 📋 Methods Included

| # | Method | Type |
|---|--------|------|
| 1 | Bisection Method | Root Finding |
| 2 | Regula Falsi | Root Finding |
| 3 | Newton-Raphson | Root Finding |
| 4 | Jacobi Method | System of Equations |
| 5 | Gauss-Seidel | System of Equations |
| 6 | Newton Forward Interpolation | Interpolation |
| 7 | Gauss Elimination | System of Equations |
| 8 | Newton Backward Interpolation | Interpolation |

---

## 🚀 How to Run

No external libraries needed. Just Python 3.

```bash
python bisection.py
python regula_falsi.py
python newton_raphson.py
python jacobi.py
python gauss_seidel.py
python newton_forward.py
python gauss_elimination.py
python newton_backward.py
```

---

## 📂 File Structure

```
numerical-methods/
│
├── bisection.py
├── regula_falsi.py
├── newton_raphson.py
├── jacobi.py
├── gauss_seidel.py
├── newton_forward.py
├── gauss_elimination.py
├── newton_backward.py
└── README.md
```

---

## 🔍 Method Details & Sample I/O

### 1. Bisection Method
Repeatedly halves the interval `[a, b]` where `f(a)` and `f(b)` have opposite signs.

**Function used:** `f(x) = x³ - x² + 2`

```
Enter a: -2
Enter b: 0
Root: -1.0000
```

> ⚠️ `f(a)` and `f(b)` must have **opposite signs**, otherwise no root exists in that interval.

---

### 2. Regula Falsi (False Position)
Uses a straight line between `(a, f(a))` and `(b, f(b))` to find a better root estimate than Bisection.

**Function used:** `f(x) = x³ - 2x - 5`

```
Enter a: 2
Enter b: 3
Root: 2.0946
```

> ⚠️ Same sign rule applies. For `f(x) = x³ - 2x - 5`, use `a=2, b=3` (not negative values like -200, -100 — both would be negative, causing it to fail).

---

### 3. Newton-Raphson
Uses the formula `x = x - f(x)/f'(x)` iteratively. Fastest convergence among root-finding methods.

**Function used:** `f(x) = x³ - x² + 2`, `f'(x) = 3x² - 2x`

```
Enter initial guess: -1
Root: -1.0000
```

> ⚠️ You must manually provide the **derivative** `f'(x)` in the code. Pick an initial guess close to the root.

---

### 4. Jacobi Method
Solves `Ax = b` iteratively. Each variable uses values from the **previous** iteration only.

```
Enter number of equations: 3
Enter row 1 coefficients: 4 1 -1
Enter b1: 3
Enter row 2 coefficients: 2 7 1
Enter b2: 19
Enter row 3 coefficients: 1 -3 12
Enter b3: 31
x1 = 1.0000
x2 = 2.0000
x3 = 3.0000
```

> ⚠️ Matrix must be **diagonally dominant** (diagonal element largest in each row) for guaranteed convergence.

---

### 5. Gauss-Seidel Method
Like Jacobi, but uses **updated values immediately** within the same iteration — converges faster.

```
Enter number of equations: 3
Enter row 1 coefficients: 4 1 -1
Enter b1: 3
Enter row 2 coefficients: 2 7 1
Enter b2: 19
Enter row 3 coefficients: 1 -3 12
Enter b3: 31
x1 = 1.0000
x2 = 2.0000
x3 = 3.0000
```

> ✅ Same input as Jacobi. Gauss-Seidel typically converges in fewer iterations.

---

### 6. Newton Forward Interpolation
Estimates `y` at a point near the **beginning** of the data table using forward differences.

```
Enter number of points: 4
Enter x0: 0   Enter y0: 1
Enter x1: 1   Enter y1: 2
Enter x2: 2   Enter y2: 9
Enter x3: 3   Enter y3: 28
Enter x to find y: 1.5
Interpolated value: 4.7500
```

> ⚠️ x values must be **equally spaced**. Use this when the target point is near the start of the table.

---

### 7. Gauss Elimination
Converts `Ax = b` to upper triangular form, then solves using back substitution. Gives exact solution.

```
Enter number of equations: 3
Enter row 1 (with b): 2 1 -1 8
Enter row 2 (with b): -3 -1 2 -11
Enter row 3 (with b): -2 1 2 -3
x1 = 2.0000
x2 = 3.0000
x3 = -1.0000
```

> ℹ️ Enter the full augmented matrix row including the `b` value, all space-separated.

---

### 8. Newton Backward Interpolation
Estimates `y` at a point near the **end** of the data table using backward differences.

```
Enter number of points: 4
Enter x0: 0   Enter y0: 1
Enter x1: 1   Enter y1: 2
Enter x2: 2   Enter y2: 9
Enter x3: 3   Enter y3: 28
Enter x to find y: 2.5
Interpolated value: 17.5000
```

> ⚠️ x values must be **equally spaced**. Use this when the target point is near the end of the table.

---

## ⚡ Quick Input Guide

| Method | How to Enter Input |
|--------|-------------------|
| Bisection / Regula Falsi | Two numbers: `a` and `b` with opposite sign f values |
| Newton-Raphson | One initial guess close to the root |
| Jacobi / Gauss-Seidel | Coefficients space-separated per row, then `b` separately |
| Gauss Elimination | Full augmented row `[a1 a2 a3 b]` space-separated |
| Forward / Backward Interpolation | x and y values one by one, then target x |

---

## 🛠️ Requirements

- Python 3.x
- No external libraries required (`math` module is built-in)

---

## 📌 Notes

- All outputs are rounded to **4 decimal places**
- Tolerance used for iterative methods: `0.0001`
- To change the function in root-finding methods, edit the `func(x)` return statement
- For Newton-Raphson, also update the `derivative(x)` function manually

---

## 👨‍💻 Author

Made for Numerical Methods coursework.  
Feel free to fork, use, and modify.
