# CSE 0613-2203 | Design and Analysis of Algorithms

## Topic: Introduction of Algorithms



## 1. Algorithm

An **algorithm** is a step-by-step procedure that defines a set of instructions to be executed in a certain order to get the desired output.

### Key Points

- Step-by-step procedure
- Produces desired output
- Language independent
- Can be implemented in different programming languages



## 2. Categories of Algorithms

- **Search:** Finding an item in a data structure.
- **Sort:** Arranging items in a particular order.
- **Insert:** Adding an item to a data structure.
- **Update:** Modifying an existing item.
- **Delete:** Removing an item.



## 3. Origin of the Word Algorithm

The word **Algorithm** comes from the name of the Persian mathematician:

**Abu Ja'afar Mohammed Ibn Mousa Al Khwarizmi (825 A.D.)**

He wrote several books on Mathematics and Algebra.



## 4. Characteristics of an Algorithm

### 1. Unambiguous

Every step must be **clear and have only one meaning**.

### 2. Input

An algorithm can have **zero or more well-defined inputs**.

### 3. Output

An algorithm must have **one or more well-defined outputs**.

### 4. Finiteness

An algorithm must **terminate after a finite number of steps**.

### 5. Feasibility

The algorithm must be possible with the available resources.

### 6. Independent

An algorithm should be independent of programming code/language.

### Remember

**U → I → O → F → F → I**



## 5. Ways to Express an Algorithm

### Natural Language

Written using plain English.

- Easy to describe
- May become unclear for complex problems

### Flowchart

A graphical representation of algorithm steps.

- Easy to visualize

### Pseudocode

Text-based, code-like instructions without specific programming-language syntax.

- Easy to understand
- Considered a good way to express an algorithm



## 6. Steps to Design an Algorithm

1. **Problem Definition** – Clearly define the problem.
2. **Constraints** – Identify limitations or rules.
3. **Inputs** – Determine the given data.
4. **Outputs** – Specify the expected result.
5. **Solution Feasibility** – Ensure the solution works within the constraints.

### Shortcut

**Problem → Constraints → Input → Output → Feasibility**



## 7. Algorithm Analysis

### A Priori Analysis

A theoretical analysis performed before implementation.

- Mathematical analysis
- Assumes other factors are constant
- Uses **Ω, O, and θ**

### A Posteriori Analysis

An empirical analysis performed after implementation.

- Algorithm is implemented and executed
- Actual running time and space are measured
- Example: **0.18 seconds, 8 MB**

### Easy Difference

| A Priori | A Posteriori |
|----------|--------------|
| Before implementation | After implementation |
| Theoretical | Empirical |
| Mathematical counting | Run and measure |
| Ω, O, θ | Actual time and space |



## 8. Algorithm Complexity

The two main factors that determine algorithm efficiency are:

### Time Factor

Measures the time/number of key operations required by an algorithm.

**Example:** Number of comparisons in a sorting algorithm.

### Space Factor

Measures the maximum memory space required by an algorithm.

### Complexity Function

If **n** is the size of input data, the complexity **f(n)** represents the running time and/or storage space required by the algorithm in terms of **n**.




