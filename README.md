# Spatial Solution Using a Power Series

## Description

This project computes and plots the spatial solution $\phi(x)$ of a differential equation using a **power series expansion**.

The solution is approximated using a finite number of terms, while the parameters $T_0$ and $\lambda\$ are varied to analyze their effect on the spatial behavior of the solution.

The resulting solutions are plotted on the same graph for comparison.

---

## Mathematical Approach

The spatial solution is represented as a power series:


$\phi(x) = \sum_{n=0}^{N} a_n x^n$


where $\(a_n\)$ are the coefficients of the series.

The recurrence relation used to calculate the coefficients is:


$a_{n+3}=-\frac{k\,a_n}{(n+3)(n+2)}$

with

$$
k = \frac{\lambda^2+1}{T_0}
$$

The initial coefficients are defined as:

$a_0=1,\qquad a_1=0$


The remaining coefficients are obtained recursively from the recurrence relation.

For the numerical approximation, the series is truncated after \(N\) terms.

---

## Parameters

The code considers the following values:

### Eigenvalue-like parameter

$$
\lambda = 1,\ 50,\ 100
$$

### Parameter $\(T_0\)$

$$
T_0 = 1,\ 10
$$

### Spatial domain

$$
0 \leq x \leq 1
$$

The domain is discretized using 500 points.

### Number of terms

The series is approximated using:

$$
N=5
$$

---

## Numerical Implementation

The main function is:

```python
phi_series(x, lam, T0, N)
```

This function:

1. Calculates

    $k=\frac{\lambda^2+1}{T_0}$

2. Initializes the coefficients $\(a_0,\ldots,a_N\)$.

3. Sets the initial conditions

   ```python
   a[0] = 1
   a[1] = 0
   ```

4. Computes the remaining coefficients using the recurrence relation.

5. Evaluates the power series at every point in the spatial domain.

6. Returns the numerical approximation of $\(\phi(x)\)$.

---

## Visualization

The code generates a single plot containing all combinations of $\(T_0\)$ and $\(\lambda\)$:

* $\(T_0 = 1\), \(\lambda = 1,50,100\)$
* $\(T_0 = 10\), \(\lambda = 1,50,100\)$

Each curve is labeled according to its corresponding parameter values.

The plot uses:

* **x-axis:** $\(x\)$
* **y-axis:** $\(\phi(x)\)$
* **Title:** Spatial solution for different values of $\(T_0\)$ and $\(\lambda\)$

This allows the effect of the parameters on the spatial solution to be compared directly.

---

## Requirements

The code requires Python 3 and the following libraries:

```text
NumPy
Matplotlib
```

They can be installed with:

```bash
pip install numpy matplotlib
```

---

## How to Run

Run the Python script or execute the cells in a Jupyter Notebook:

```bash
python script_name.py
```

The program will generate the comparison plot automatically.

---

## Results

The plot illustrates how the spatial solution changes as $\(T_0\)$ and $\(\lambda\)$ vary.

Since

$k=\frac{\lambda^2+1}{T_0},$


larger values of $\(\lambda\)$ produce significantly larger values of $\(k\)$,   while increasing $\(T_0\)$ reduces $\(k\)$. Therefore, both parameters influence the magnitude and shape of the power-series approximation.

The comparison of the six curves provides a qualitative view of the sensitivity of the spatial solution to these parameters.
