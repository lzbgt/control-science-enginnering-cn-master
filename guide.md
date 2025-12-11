# Comprehensive Study Guide for Control Science and Engineering Exam

This guide is designed to assist candidates in preparing for the National Unified Examination for Master's Degree in Control Science and Engineering. It is based on the official syllabus and real exam questions.

## Table of Contents
1.  [Part 1: Matrix Theory](#part-1-matrix-theory)
2.  [Part 2: Control Theory](#part-2-control-theory)
3.  [Part 3: Microcomputer System Principles and Applications](#part-3-microcomputer-system-principles-and-applications)
4.  [Part 4: Computer Software Technology](#part-4-computer-software-technology)

---

## Part 1: Matrix Theory

### Chapter 1: Linear Space

#### 1. Detailed Explanation of Fundamental Concepts
*   **Linear Space (Vector Space)**: A set $V$ combined with two operations (addition and scalar multiplication) that satisfy 8 axioms (commutativity, associativity, zero element, inverse, distributivity, identity, etc.).
*   **Linear Dependence/Independence**: A set of vectors is linearly independent if the only linear combination resulting in the zero vector is the trivial one (all scalars are zero).
*   **Basis and Dimension**: A basis is a linearly independent set that spans $V$. The number of vectors in a basis is the dimension of the space, denoted as $\dim(V)$.
*   **Coordinates**: For a basis $\alpha_1, \dots, \alpha_n$, any vector $\beta$ can be uniquely expressed as $\beta = \sum x_i \alpha_i$. The tuple $(x_1, \dots, x_n)$ is the coordinate of $\beta$.
*   **Subspace**: A non-empty subset of $V$ that is closed under addition and scalar multiplication.

#### 2. Representative Exam Question
**Question**: Given $\alpha_{1} =(1, 1, - 1, 0)^{T}, \alpha_{2} =(0, 2, 1, 1)^{T}, \alpha_{3} =(1, 0, 1, 2)^{T}, \alpha_{4} =(1, 1, 1, 2)^{T}$, find the dimension of the subspace $L(\alpha_{1}, \alpha_{2}, \alpha_{3}, \alpha_{4})$.
**Solution**:
1.  Form the matrix with these vectors.
2.  Perform elementary row operations to find the rank.
    $$
    \begin{bmatrix}
    1 & 0 & 1 & 1 \\
    1 & 2 & 0 & 1 \\
    -1 & 1 & 1 & 1 \\
    0 & 1 & 2 & 2
    \end{bmatrix} \rightarrow \dots \rightarrow \text{Rank} = 3
    $$
3.  Answer: 3.

#### 3. Generic Rules & Strategy
*   **Finding Dimension**: The dimension of a subspace spanned by a set of vectors equals the rank of the matrix formed by these vectors.
*   **Checking Independence**: To check if $n$ vectors in $\mathbb{R}^n$ are independent, calculate the determinant. Non-zero determinant $\implies$ Independent.

---

### Chapter 2: Linear Transformation

#### 1. Detailed Explanation of Fundamental Concepts
*   **Linear Transformation**: A mapping $T: V \to W$ such that $T(x+y) = T(x) + T(y)$ and $T(kx) = kT(x)$.
*   **Matrix Representation**: If we choose a basis for $V$ and $W$, $T$ can be represented by a matrix $A$. $Y = AX$.
*   **Eigenvalues and Eigenvectors**: Scalars $\lambda$ and non-zero vectors $x$ such that $Ax = \lambda x$.
*   **Jordan Canonical Form**: Every square matrix is similar to a block diagonal matrix (Jordan form). Crucial for analyzing matrix powers and functions.

#### 2. Representative Exam Question
**Question**: Let $V$ be the space of n-order symmetric matrices. $T(A) = P^T A P$ where $P$ is invertible. Prove $T$ is a linear transformation.
**Solution**:
Check the two conditions:
1.  $T(A+B) = P^T(A+B)P = P^T A P + P^T B P = T(A) + T(B)$.
2.  $T(kA) = P^T(kA)P = k(P^T A P) = kT(A)$.
Since both hold, $T$ is linear.

#### 3. Generic Rules & Strategy
*   **Proving Linearity**: Always strictly verify the two properties: Additivity and Homogeneity.
*   **Finding Matrix of Transformation**: Compute the image of each basis vector under $T$, then express these images as linear combinations of the basis vectors. The coefficients form the columns of the matrix.

---

### Chapter 3: Euclidean Space

#### 1. Detailed Explanation of Fundamental Concepts
*   **Inner Product**: A function $\langle x, y \rangle$ satisfying symmetry, linearity in the first argument, and positive definiteness.
*   **Orthogonality**: Two vectors are orthogonal if $\langle x, y \rangle = 0$.
*   **Gram-Schmidt Process**: An algorithm to convert a basis into an orthonormal basis.
    $$ \beta_k = \alpha_k - \sum_{i=1}^{k-1} \frac{\langle \alpha_k, e_i \rangle}{\langle e_i, e_i \rangle} e_i $$
*   **Orthogonal Matrix**: $A^T A = I$. Preserves inner products and norms.

#### 2. Representative Exam Question
**Question**: Given $\alpha_1=(1,0,-1)^T, \alpha_2=(3,2,2)^T$, find an orthonormal basis for $L(\alpha_1, \alpha_2)$.
**Solution**:
1.  Let $\beta_1 = \alpha_1 = (1, 0, -1)^T$.
2.  $\beta_2 = \alpha_2 - \frac{\langle \alpha_2, \beta_1 \rangle}{\langle \beta_1, \beta_1 \rangle} \beta_1$.
    $\langle \alpha_2, \beta_1 \rangle = 3(1) + 2(0) + 2(-1) = 1$.
    $\langle \beta_1, \beta_1 \rangle = 1^2 + 0 + (-1)^2 = 2$.
    $\beta_2 = (3,2,2)^T - \frac{1}{2}(1,0,-1)^T = (2.5, 2, 2.5)^T$.
3.  Normalize $\beta_1$ and $\beta_2$ to get $e_1, e_2$.

#### 3. Generic Rules & Strategy
*   **Orthogonalization**: Use Gram-Schmidt. Remember to subtract the projection of the new vector onto **all** previously computed orthogonal vectors.
*   **Orthogonal Matrices**: Their rows (and columns) form an orthonormal basis. Determinant is $\pm 1$.

---

### Chapter 4: Bilinear Function and Quadratic Form

#### 1. Detailed Explanation of Fundamental Concepts
*   **Quadratic Form**: A homogeneous polynomial of degree 2, $f(x) = x^T A x$, where $A$ is symmetric.
*   **Standard Form**: A diagonal form $\sum d_i y_i^2$ obtained via coordinate change.
*   **Positive Definiteness**: $f(x) > 0$ for all $x \neq 0$. Equivalent to all eigenvalues of $A$ being positive, or all leading principal minors being positive (Sylvester's Criterion).
*   **Inertia**: The number of positive, negative, and zero eigenvalues (inertia index) is invariant under coordinate changes.

#### 2. Representative Exam Question
**Question**: If $f(x_1, x_2, x_3) = x_1^2 + 3x_2^2 + x_3^2 + 2x_1x_2 + 2x_1x_3 + 2x_2x_3$, find the positive inertia index.
**Solution**:
Write the matrix $A$:
$$
A = \begin{bmatrix}
1 & 1 & 1 \\
1 & 3 & 1 \\
1 & 1 & 1
\end{bmatrix}
$$
Find eigenvalues or diagonalize.
Notice row 1 and row 3 are identical, so $|A|=0$. One eigenvalue is 0.
Sum of rows is constant? No.
Use elementary row operations to diagonalize.
Leading minors: $D_1=1>0$, $D_2=3-1=2>0$, $D_3=0$.
Since $D_1, D_2 > 0$ and rank is 2, the eigenvalues must be positive and zero.
Answer: Positive inertia index is 2.

#### 3. Generic Rules & Strategy
*   **Sylvester's Criterion**: Quickest way to check Positive Definiteness for small matrices.
*   **Standard Form**: Can be found by completing the square (Lagrange's method) or orthogonal diagonalization (finding eigenvalues).

---

### Chapter 5: Matrix Analysis

#### 1. Detailed Explanation of Fundamental Concepts
*   **Matrix Norms**: Measure of the "size" of a matrix. Compatible with vector norms.
*   **Matrix Functions**: defined via power series (e.g., $e^A = \sum A^k/k!$) or via Jordan form.
*   **Differentiation**: Derivative of a matrix with respect to a scalar, or scalar with respect to a matrix.
*   **Differential Equations**: $\dot{x} = Ax$ has solution $x(t) = e^{At}x(0)$.

#### 2. Representative Exam Question
**Question**: Given $A = \alpha \beta^T$ where $\alpha, \beta$ are column vectors. Find $A^3$.
**Solution**:
$A^2 = (\alpha \beta^T)(\alpha \beta^T) = \alpha (\beta^T \alpha) \beta^T = (\beta^T \alpha) A$.
Let $k = \beta^T \alpha$ (a scalar). Then $A^2 = k A$.
$A^3 = k A^2 = k^2 A$.
Answer: $(\beta^T \alpha)^2 A$.

#### 3. Generic Rules & Strategy
*   **Rank-1 Matrices**: Matrices of the form $xy^T$ appear often. Their trace is $y^T x$, and $A^2 = \text{tr}(A) A$.
*   **Computing $e^{At}$**: Use the formula $e^{At} = P e^{Jt} P^{-1}$ or Laplace transform $(sI-A)^{-1}$.

---

## Part 2: Control Theory

### Chapter 1: System Models

#### 1. Detailed Explanation of Fundamental Concepts
*   **Transfer Function**: Laplace transform of impulse response. Ratio of Output/Input in s-domain with zero initial conditions.
*   **State Space**: $\dot{x} = Ax + Bu, y = Cx + Du$.
*   **Block Diagrams**: Graphical representation. Mason's Gain Formula is key for reduction.

#### 2. Representative Exam Question
**Question**: Find the closed-loop transfer function of a feedback system using Mason's Rule.
**Solution**:
1.  Identify forward paths $P_k$.
2.  Identify loops $L_i$.
3.  Calculate determinant $\Delta = 1 - \sum L_i + \sum L_i L_j - \dots$
4.  $T(s) = \frac{1}{\Delta} \sum P_k \Delta_k$.

#### 3. Generic Rules & Strategy
*   **Mason's Rule**: Essential for complex diagrams. Be careful identifying non-touching loops.

### Chapter 2: Stability

#### 1. Detailed Explanation of Fundamental Concepts
*   **Routh-Hurwitz**: Algebraic criterion to check if roots are in LHP.
*   **Nyquist Criterion**: Frequency domain stability test based on encirclements of (-1, j0).
*   **Bode Stability**: Gain Margin (GM) and Phase Margin (PM). Stable if GM > 0 dB and PM > 0 deg (for minimum phase).

#### 2. Representative Exam Question
**Question**: Given open loop $G(s) = \frac{K}{s+1}$, find Phase Margin.
**Solution**:
1.  Gain crossover $\omega_c$: $|G(j\omega_c)| = 1 \implies \frac{K}{\sqrt{\omega_c^2+1}} = 1$.
2.  Phase $\phi = -\arctan(\omega_c)$.
3.  PM $= 180 + \phi$.

#### 3. Generic Rules & Strategy
*   **Routh Array**: If any element in the first column is negative/zero, the system is unstable.
*   **Margins**: PM measures delay tolerance; GM measures gain tolerance.

### Chapter 4: Controllability & Observability

#### 1. Detailed Explanation of Fundamental Concepts
*   **Controllability**: Can we steer the state from $x(0)$ to any $x(t_f)$? Rank condition: $\text{rank}[B, AB, \dots] = n$.
*   **Observability**: Can we determine $x(0)$ from output $y(t)$? Rank condition: $\text{rank}[C^T, A^T C^T, \dots] = n$.
*   **Kalman Decomposition**: Separating state space into controllable/uncontrollable and observable/unobservable parts.

#### 2. Representative Exam Question
**Question**: Check controllability of $\dot{x} = \begin{bmatrix} 1 & 1 \\ 0 & 2 \end{bmatrix} x + \begin{bmatrix} 0 \\ 1 \end{bmatrix} u$.
**Solution**:
1.  $A = \begin{bmatrix} 1 & 1 \\ 0 & 2 \end{bmatrix}, B = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$.
2.  $AB = \begin{bmatrix} 1 \\ 2 \end{bmatrix}$.
3.  $Q_c = [B, AB] = \begin{bmatrix} 0 & 1 \\ 1 & 2 \end{bmatrix}$.
4.  Rank is 2. System is Controllable.

#### 3. Generic Rules & Strategy
*   **PBH Test**: Another way to check. Rank $[sI-A, B] = n$ for all eigenvalues $s$.
*   **Uncontrollable Modes**: Eigenvalues associated with the uncontrollable part cannot be moved by state feedback.

### Chapter 6: Optimal Control

#### 1. Detailed Explanation of Fundamental Concepts
*   **Functional**: A mapping from a function space to scalars (Cost function $J$).
*   **Pontryagin's Minimum Principle**: Necessary condition for optimality. Hamiltonian $H = L + \lambda^T f$.
*   **LQR**: Linear Quadratic Regulator. Min $J = \int (x^T Q x + u^T R u) dt$. Riccati Equation.

#### 2. Representative Exam Question
**Question**: Minimize $J = \int_0^1 u^2 dt$ subject to $\dot{x} = u, x(0)=0, x(1)=1$.
**Solution**:
1.  $H = u^2 + \lambda u$.
2.  $\frac{\partial H}{\partial u} = 2u + \lambda = 0 \implies u = -\lambda/2$.
3.  $\dot{\lambda} = -\frac{\partial H}{\partial x} = 0 \implies \lambda = C$.
4.  $u = -C/2 = \text{const}$.
5.  $\dot{x} = \text{const} \implies x(t) = kt$.
6.  $x(1)=1 \implies k=1$. So $x(t)=t, u(t)=1$.

#### 3. Generic Rules & Strategy
*   **Hamiltonian Approach**: Always the first step for continuous deterministic optimal control.
*   **Boundary Conditions**: Pay attention to fixed vs free end time/state.

---

## Part 3: Microcomputer System Principles and Applications

### Fundamentals & Generic Rules
*   **Data Representation**: Computers work in Binary.
    *   **Rule**: To convert Hex to Binary, replace each Hex digit with 4 bits.
    *   **Rule**: 2's complement of $x$ is $(\sim x) + 1$.
*   **Addressing Modes**:
    *   *Immediate*: `MOV AX, 1234H` (Data is in instruction)
    *   *Direct*: `MOV AX, [1234H]` (Address is in instruction)
    *   *Register Indirect*: `MOV AX, [BX]` (Address is in register)
    *   **Rule**: `[BX]`, `[SI]`, `[DI]` use DS segment by default. `[BP]` uses SS segment.
*   **Interrupts**:
    *   **Rule**: Interrupt Vector Table is at 0000:0000. Each vector is 4 bytes (IP, CS). Vector Address = IntNum * 4.
*   **I/O**:
    *   **Rule**: Memory Mapped I/O vs Isolated I/O (IN/OUT instructions). x86 uses Isolated.

### Representative Exam Question
**Question**: AL=0FFH, CF=1. Write 2 instructions to result in AL=55H, CF=0.
**Solution**:
1.  `AND AL, 55H` (Result 55H, CF cleared).
2.  `XOR AL, 0AAH` (FF xor AA = 55, CF cleared).
**Analysis**: Logical instructions usually clear Carry Flag.

---

## Part 4: Computer Software Technology

### Fundamentals & Generic Rules
*   **Data Structures**:
    *   *Stack*: LIFO. Used for recursion.
    *   *Queue*: FIFO. Used for buffering.
    *   *Tree*: Binary Tree Traversals (Pre, In, Post).
    *   **Rule**: Number of null links in a binary tree of $n$ nodes is $n+1$.
*   **Algorithms**:
    *   *Sorting*: QuickSort ($O(n \log n)$ avg), BubbleSort ($O(n^2)$).
    *   *Search*: Binary Search ($O(\log n)$).
*   **Operating Systems**:
    *   *Process State*: Ready, Running, Blocked.
    *   *Deadlock*: Mutual Exclusion, Hold and Wait, No Preemption, Circular Wait.
*   **Databases**:
    *   *Normalization*: 1NF (Atomic), 2NF (No partial dependency), 3NF (No transitive dependency).
    *   *SQL*: Select-From-Where.

### Representative Exam Question
**Question**: Binary Search max comparisons for 100 elements?
**Solution**: $\lfloor \log_2 100 \rfloor + 1 = 6 + 1 = 7$.
**Rule**: Max comparisons is depth of the binary search tree.
