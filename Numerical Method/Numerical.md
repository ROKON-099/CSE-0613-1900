# Numerical Method | Curve Fitting

## 1. Curve Fitting

**Definition:** Curve fitting is a numerical method used to find a mathematical equation (curve) that best represents a given set of data points.

**Example:**

Given data points \((x,y)\), we may find an equation like:

$$
y = a + bx
$$

that best fits those points.


## 2. Interpolation

**Definition:** Interpolation is a numerical method used to find or estimate an unknown value within a given set of known data values.

**Example:**

| \(X\) | \(Y\) |
|---:|---:|
| 0 | 1 |
| 2 | 9 |
| 4 | ? |
| 6 | 64 |

Here, the value of \(Y\) at \(X=4\) is missing, while the values at \(X=0,2,6\) are known.

Using interpolation, we can estimate the missing value of \(Y\) at \(X=4\).


## 3. Extrapolation

**Definition:** Extrapolation is a numerical method used to estimate an unknown value outside the range of the given or known data values.

**Example:**

| \(X\) | \(Y\) |
|---:|---:|
| 0 | 1 |
| 2 | 9 |
| 4 | 25 |
| 6 | 49 |

If we want to estimate the value of \(Y\) at \(X=8\), it is outside the given range \(0\) to \(6\). Therefore, we use extrapolation.

### In short

- **Interpolation** → finding a value within the given range.
- **Extrapolation** → finding a value outside the given range.

### Difference Between Interpolation and Extrapolation

| Interpolation | Extrapolation |
|---|---|
| It estimates an unknown value within the range of known data. | It estimates an unknown value outside the range of known data. |
| It is generally more accurate. | It is generally less accurate. |
| It uses data points on both sides of the unknown value. | It uses data points from one side to predict beyond the known range. |
| Example: Known \(X\), find \(Y\) at a value within the range. | Example: Known \(X\), find \(Y\) at a value outside the range. |


## 4. Finite Difference

Finite difference is a numerical method used to find the difference between successive function values.

### Forward Difference

Forward difference is a finite difference method in which the difference is calculated between a function value and the next successive function value.

### Backward Difference

Backward difference is a finite difference method in which the difference is calculated between the current function value and the previous function value.

### Central Difference

Central difference is a finite difference method in which the difference is calculated using function values on both sides of a given point.

**Central Difference = Difference using values before and after the given point**


## 5. Numerical Analysis

Numerical analysis is the study of methods used to find approximate solutions to mathematical problems using numerical calculations.


## 6. Difference between Bisection and Newton-Raphson Methods

| Bisection Method | Newton-Raphson Method |
|---|---|
| 1. It is a bracketing method. | 1. It is an open method. |
| 2. Requires two initial values \(a\) and \(b\). | 2. Requires only one initial guess \(x_0\). |
| 3. \(f(a)\) and \(f(b)\) must have opposite signs. | 3. No sign-change condition is required. |
| 4. Does not require the derivative of \(f(x)\). | 4. Requires the derivative \(f'(x)\). |
| 5. Convergence is slow (linear). | 5. Convergence is generally very fast (quadratic). |
| 6. It is more reliable/stable if the initial interval brackets a root. | 6. It may fail or diverge if the initial guess is poor. |
| 7. The root remains within the bracket \([a,b]\). | 7. The iterations are not necessarily confined to an interval. |
| 8. More iterations are usually required. | 8. Usually needs fewer iterations. |
| 9. Formula: Bisection uses the midpoint of the interval. | 9. Formula: Newton-Raphson uses the tangent-based iteration given below. |


## 7. Newton-Raphson Method

The Newton-Raphson method is an iterative numerical method used to find an approximate real root of a nonlinear equation.

### Newton-Raphson Method — Easy Derivation

To find the root of:

$$
f(x)=0
$$

Suppose \(x_n\) is the present approximation.

The tangent line at \(x_n\) is:

$$
y-f(x_n)=f'(x_n)(x-x_n)
$$

At the root, the tangent touches the \(x\)-axis, so:

$$
y=0
$$

Therefore,

$$
0-f(x_n)=f'(x_n)(x_{n+1}-x_n)
$$

So,

$$
-f(x_n)=f'(x_n)(x_{n+1}-x_n)
$$

Divide by \(f'(x_n)\):

$$
-\frac{f(x_n)}{f'(x_n)}=x_{n+1}-x_n
$$

Therefore,

$$
\boxed{x_{n+1}=x_n-\frac{f(x_n)}{f'(x_n)}}
$$


## 8. How We Overcome the Derivative Problem

The derivative problem of the Newton-Raphson method can be overcome by using the **Secant method**, which approximates the derivative using two successive values of the function.

Newton-Raphson uses:

$$
x_{n+1}=x_n-\frac{f(x_n)}{f'(x_n)}
$$

So, we need to calculate the derivative \(f'(x)\).

The Secant method does not require \(f'(x)\). Its formula is:

$$
\boxed{x_{i+1}=
\frac{x_{i-1}f_i-x_i f_{i-1}}
{f_i-f_{i-1}}}
$$

Therefore:

- **Newton-Raphson** → needs \(f'(x)\)
- **Secant** → does not need \(f'(x)\)


## 9. Why Newton-Raphson is Faster

Newton-Raphson method is faster than Bisection and Regula Falsi mainly because it has **quadratic (second-order) convergence**.

### 1. Quadratic Convergence

Near the root, the error decreases very rapidly:

$$
e_{n+1}\approx C e_n^2
$$

So, if the error becomes small, the next error becomes much smaller.

### 2. No Interval Halving

Bisection method reduces the interval step-by-step:

$$
[a,b]\rightarrow
\left[\frac{a+b}{2},b\right]
$$

Therefore, it usually needs more iterations.

### 3. Uses the Derivative

Newton-Raphson uses:

$$
x_{n+1}=x_n-\frac{f(x_n)}{f'(x_n)}
$$

The derivative gives the slope of the curve, so it can move directly toward the root.

### 4. Fewer Iterations

Therefore, Newton-Raphson generally reaches the required accuracy in fewer iterations than Bisection and Regula Falsi.


## 10. Why Numerical Methods are Preferred in Engineering

Numerical methods are often preferred over analytical methods because they can solve complex engineering problems that are difficult or impossible to solve exactly using mathematical formulas.

### Main Reasons

1. **Solve complex equations** — Useful for nonlinear and complicated equations.
2. **Handle real-world problems** — Engineering problems often involve complex conditions and many variables.
3. **Approximate solutions** — They provide sufficiently accurate answers when exact solutions are difficult.
4. **Suitable for computers** — Numerical calculations can be easily performed using computers/software.
5. **Save time and effort** — Large and complicated calculations can be solved quickly.
6. **Useful for experimental data** — They can work with measured or approximate data.

### Mathematical Advantage

Numerical methods can solve equations such as:

$$
f(x)=0
$$

even when an exact analytical solution is difficult or does not exist.

### Exam Answer

> Numerical methods are preferred in engineering because they provide accurate approximate solutions to complex mathematical problems that are difficult or impossible to solve analytically, and they can be efficiently implemented using computers.
