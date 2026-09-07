# Design & Analysis of Algorithms (D&AA)

## Types of Algorithms --- Exam Notes

> **Source:** Course slides, *D&AA Day 06: Types of Algorithm*.\
> These notes cover the topics and examples presented in the 69-slide
> deck, using easy exam-friendly English.



# 1. What is an Algorithm?

An **algorithm** is a **step-by-step procedure used to solve a
problem**.

A good algorithm should be optimized in: - **Time** --- how fast it
runs. - **Space** --- how much extra memory it needs.

Different problems need different algorithmic techniques.

## Important Types of Algorithms

1.  **Brute Force**
2.  **Recursion**
3.  **Divide & Conquer**
4.  **Greedy**
5.  **Dynamic Programming (DP)**
6.  **Backtracking**
7.  **Randomized Algorithm**



# 2. Brute Force Algorithm

## Definition

A **Brute Force algorithm** is a simple method that **tries all possible
choices/solutions** until it finds the answer.

### Easy idea

**Try everything → check the answers → choose the required one.**

It is useful when the problem is small, but it becomes slow for large
problems because it may have very high time complexity.

## Key Characteristics

1.  **Methodical listing:** Checks every possible solution in an
    organized way.
2.  **Best for small problems:** Works well when the number of
    possibilities is small.
3.  **No optimization/heuristics:** It does not cleverly remove
    possibilities before checking them.
4.  **Simple and direct:** Easy to understand and implement.

## Applications / Examples

-   Finding a shortest path by checking all possible paths.
-   Arranging books in all possible ways to find the best arrangement.
-   **Linear Search** --- checks elements one by one --- `O(n)`.
-   **Bubble Sort** --- repeatedly swaps adjacent elements --- `O(n²)`.
-   **Selection Sort** --- repeatedly selects the minimum element ---
    `O(n²)`.
-   **Naive String Matching** --- checks the pattern at each possible
    position --- `O(n·m)`.
-   **Closest Pair of Points (Brute Force)** --- checks every pair ---
    `O(n²)`.
-   **Travelling Salesman Problem (Exhaustive Search)** --- checks every
    route permutation --- `O(n!)`.
-   **Knapsack (Brute Force)** --- checks every subset --- `O(2ⁿ)`.
-   **Standard Matrix Multiplication** --- three nested loops ---
    `O(n³)`.

## Advantages

1.  Guaranteed to find the correct solution when all candidates are
    checked.
2.  General-purpose method.
3.  Very simple.
4.  Good for small and simple problems.
5.  Can be used as a benchmark to compare better algorithms.

## Disadvantages

1.  Usually inefficient for large inputs.
2.  Can have very high time complexity.
3.  Depends more on computer power than clever algorithm design.
4.  Usually slow.
5.  Does not use pruning or optimization techniques.

### Exam line

**Brute Force = Try all possible solutions.**



# 3. Recursion

## Definition

**Recursion** is a technique where a function **calls itself**, directly
or indirectly.

A function that calls itself is called a **recursive function**.

## Simple Example

``` c
int function(int value) {
    if(value < 1)
        return;

    function(value - 1);
    printf("%d ", value);
}
```

Here, `function()` calls itself with a smaller value.

## Indirect Recursion

Sometimes:

`function1()` → calls `function2()` → calls `function1()` again.

So recursion can be: - **Direct recursion:** A function calls itself. -
**Indirect recursion:** One function calls another function which
eventually calls the first function.

## Two Important Properties of Recursion

### 1. Base Criteria / Base Case

There must be a condition that **stops the recursive calls**.

Example:

``` text
if (n <= 1)
    return;
```

Without a base case, recursion may continue forever.

### 2. Progressive Approach

Each recursive call must move **closer to the base case**.

Example:

``` text
function(n-1)
```

The value becomes smaller, so it eventually reaches the base case.

### Easy formula to remember

**Recursion = Base Case + Smaller Recursive Call**



## How Recursion Works: Stack

Many programming languages implement recursion using a **stack**.

When a function calls another function or itself:

1.  The caller pauses.
2.  Control goes to the callee.
3.  The caller's information is stored.
4.  When the callee finishes, the caller resumes.

### Activation Record / Stack Frame

An **activation record** (or stack frame) stores information such as:

-   Local variables
-   Formal parameters
-   Return address
-   Other information needed by the function

The caller must resume from exactly where it stopped.



## Why Use Recursion?

### Advantages

-   Makes some programs simpler.
-   Often makes code easier to read.
-   Natural for problems that have a recursive structure.
-   Useful for tree, divide-and-conquer, and backtracking problems.

### Disadvantages

-   May use more memory because of the call stack.
-   Function-call overhead exists.
-   Can cause stack overflow for very deep recursion.
-   It is not always faster than iteration.



## Time Complexity of Recursion

For simple recursion, we can count how many recursive calls are made.

A normal function call is considered `O(1)` when its work is constant.

If there are `n` such calls, the time may be **O(n)**.

However, some recursive algorithms have much higher complexity, such as
Fibonacci `O(2ⁿ)`.

## Space Complexity of Recursion

Recursion usually needs extra stack space because an **activation record
is stored for each call**.

Therefore, recursive solutions can use more memory than iterative
solutions.



## Examples of Recursion

  ---
  Example                 Main Idea                   Complexity from slides
  ----------------------- --------------------------- -----------------------
  Factorial               `n × factorial(n-1)`        `O(n)`

  Fibonacci               Sum of previous two terms   `O(2ⁿ)` naive

  Binary Search           Divide search range in half `O(log n)`

  Tower of Hanoi          Recursively move `n-1`      `O(2ⁿ)`
                          disks                       

  Merge Sort              Divide array recursively    `O(n log n)`
                          and merge                   

  Quick Sort              Recursively partition       Avg `O(n log n)`, worst
                          around pivot                `O(n²)`

  Sum of digits/array     Add one item at a time      `O(n)`

  GCD (Euclidean)         `gcd(a,b)=gcd(b,a mod b)`   `O(log(min(a,b)))`

  Permutations/Subsets    Include/exclude elements    `O(2ⁿ)` or `O(n!)`
  ---

### Exam line

**Recursion = A function solving a problem by calling itself on a
smaller problem.**



# 4. Divide & Conquer

## Definition

**Divide and Conquer** solves a large problem by:

1.  Dividing it into smaller sub-problems.
2.  Solving the smaller sub-problems.
3.  Combining their solutions.

### Easy formula

**Divide → Conquer → Combine**

## Three Main Steps

### 1. Divide / Break

Break the original problem into smaller sub-problems.

This is usually repeated until the sub-problems become very small.

### 2. Conquer / Solve

Solve each small sub-problem.

Very small problems can often be solved directly.

### 3. Merge / Combine

Combine the solutions of the smaller problems to get the solution of the
original problem.



## Diagram Idea

``` text
                 PROBLEM
                /       \
           Subproblem  Subproblem
              |           |
            Solve       Solve
              |           |
           Solution     Solution
                \       /
                 COMBINE
                    |
              FINAL SOLUTION
```

## Advantages

-   Sub-problems can often be solved independently.
-   Supports **parallelism**.
-   Different processors/machines can work on different sub-problems.
-   Often gives efficient algorithms.

## Disadvantage

Many divide-and-conquer algorithms use recursion, so: - Stack memory is
needed. - Memory management can become high.



## Examples

  -----------------------------------------------------------------------
  Algorithm               Main Idea               Complexity
  ----------------------- ----------------------- -----------------------
  Max-Min                 Divide array and find   `O(n)`
                          max/min                 

  Merge Sort              Divide into halves,     `O(n log n)`
                          sort, merge             

  Quick Sort              Partition around pivot  Avg `O(n log n)`, worst
                                                  `O(n²)`

  Binary Search           Repeatedly divide       `O(log n)`
                          search range            

  Strassen Matrix         Divide matrices and     `O(n^2.81)`
  Multiplication          reduce multiplications  

  Karatsuba               Divide large numbers    `O(n^1.585)`
                          and reduce              
                          multiplications         

  Closest Pair of Points  Divide points into      `O(n log n)`
                          halves and check        
                          boundary                
  -----------------------------------------------------------------------

### Exam line

**Divide & Conquer = Divide the problem, solve smaller problems, then
combine the results.**



# 5. Greedy Algorithm

## Definition

A **Greedy algorithm** solves a problem by choosing the **best option
available at the current moment**.

It makes a **local best choice** hoping to obtain a good/global
solution.

### Important point

A greedy algorithm **does not go back and change an earlier decision**.

So:

**Greedy = Choose the best now → Never reconsider**

It does **not always produce the optimal solution**.



## Five Components of Greedy Algorithm

1.  **Candidate Set**\
    Set of possible items from which the solution is created.

2.  **Selection Function**\
    Chooses the best candidate to add.

3.  **Feasibility Function**\
    Checks whether the selected candidate can be used.

4.  **Objective Function**\
    Gives a value to a solution or partial solution.

5.  **Solution Function**\
    Checks whether a complete solution has been reached.



## General Working

1.  Start with an empty solution set.
2.  Select an item.
3.  Check whether the solution remains feasible.
4.  If feasible, keep the item.
5.  If not feasible, reject it.
6.  Continue until a solution is reached.



## Advantages

1.  Simple and easy to implement.
2.  Usually uses little memory.
3.  Often fast.
4.  Useful for real-time situations.
5.  Can provide near-optimal solutions.
6.  Applicable to many problems.

## Limitations

1.  May give a **suboptimal solution**.
2.  Does not backtrack.
3.  Depends strongly on the problem structure.
4.  Not suitable for every optimization problem.



## Important Example: Why Greedy Can Fail

Suppose a tree has:

``` text
             20
            /  \
           2    3
          / \    \
         7  10    1
```

We want the **largest path from root to leaf**.

Greedy chooses the larger child at every step:

-   From `20`, choose `3` because `3 > 2`.
-   From `3`, choose `1`.
-   Total = `20 + 3 + 1 = 24`.

But another path is:

`20 → 2 → 10`

Total:

`20 + 2 + 10 = 32`

So:

**Greedy result = 24**\
**Optimal result = 32**

Therefore, greedy does not always give the optimal solution.



## Examples of Greedy Algorithms

  -----------------------------------------------------------------------
  Algorithm               Idea                    Complexity from slides
  ----------------------- ----------------------- -----------------------
  TSP (Nearest Neighbor)  Choose nearest          `O(n²)`
                          unvisited city          

  Prim's MST              Choose minimum-weight   `O(E log V)`
                          connecting edge         

  Kruskal's MST           Sort edges and add if   `O(E log E)`
                          no cycle                

  Dijkstra                Choose vertex with      `O(E log V)`
                          smallest known distance 

  Graph Map Coloring      Use smallest available  `O(V²)`
                          color                   

  Vertex Cover            Greedily choose         `O(V+E)`
                          endpoints to cover      
                          edges                   

  Fractional Knapsack     Choose highest          `O(n log n)`
                          value/weight ratio      

  Job Sequencing          Choose jobs by profit   `O(n²)` or `O(n log n)`
                          and schedule before     with DSU
                          deadline                

  Optimal Merge Pattern   Merge two smallest      `O(n log n)`
                          files/lists first       
  -----------------------------------------------------------------------

### Important special case

**Fractional Knapsack:** Greedy gives the optimal solution because items
can be divided into fractions.

### Exam line

**Greedy = Best choice now, without changing previous choices.**



# 6. Dynamic Programming (DP)

## Definition

**Dynamic Programming** breaks a problem into smaller sub-problems, but
unlike ordinary divide-and-conquer, it **stores the results of
sub-problems** and reuses them.

### Easy idea

**Solve once → Store → Reuse**

DP focuses on the **overall optimal solution**, not only the local
choice.



## DP vs Divide & Conquer

### Divide & Conquer

-   Breaks into smaller problems.
-   Sub-problems are generally solved independently.
-   Results are combined.

### Dynamic Programming

-   Breaks into smaller problems.
-   Sub-problems may **overlap**.
-   Results are stored and reused.
-   Avoids repeated calculation.



## Two Properties Required for DP

### 1. Overlapping Subproblems

The same smaller sub-problems appear more than once.

Example: In naive Fibonacci, `fib(3)`, `fib(2)`, etc. are calculated
repeatedly.

DP stores these results so they do not need to be calculated again.

### 2. Optimal Substructure

The optimal solution of the whole problem can be constructed from
optimal solutions of smaller sub-problems.

### Easy memory trick

**DP = Overlapping Subproblems + Optimal Substructure**



## Steps to Solve a DP Problem

1.  Define the problem using sub-problems.
2.  Identify the base cases.
3.  Find the recurrence relation.
4.  Store sub-problem results.
5.  Build the final answer from the stored results.



# 7. Fibonacci and Dynamic Programming

## Naive Recursive Fibonacci

``` text
function fib(n) {
    if (n <= 1) return n;
    return fib(n-1) + fib(n-2);
}
```

Time complexity:

**O(2ⁿ)**

### Why is it slow?

Because the same values are calculated repeatedly.

For example, while calculating `fib(5)`, the algorithm calculates
`fib(3)`, `fib(2)`, etc. multiple times.



# 8. Types of Dynamic Programming

There are two main approaches:

1.  **Top-Down --- Memoization**
2.  **Bottom-Up --- Tabulation**



## 8.1 Top-Down Approach (Memoization)

### Idea

Start from the main problem and recursively go down to smaller problems.

Store every computed result.

If the result is already stored, use it instead of calculating again.

### Features

-   Uses recursion.
-   Uses a table/array to store results.
-   Avoids repeated calculations.

### Simple steps

``` text
Create memo array
Call recursive function
If answer is already stored → return it
Otherwise calculate it
Store it
Return it
```

### Fibonacci complexity

**Time = O(n)**

Because each Fibonacci value is computed only once.



## 8.2 Bottom-Up Approach (Tabulation)

### Idea

Start from the smallest sub-problems and build upward to the final
problem.

### Features

-   Uses a table/array.
-   Usually uses iteration.
-   No recursion is required.

### Fibonacci example

``` text
dp[0] = 0
dp[1] = 1

for i = 2 to n:
    dp[i] = dp[i-1] + dp[i-2]

return dp[n]
```

### Time Complexity

**O(n)**

Because there is one linear loop.



## Memoization vs Tabulation

  Feature          Memoization           Tabulation
  ---------------- --------------------- ---------------------
  Direction        Top → Down            Bottom → Up
  Main technique   Recursion             Iteration
  Stores results   Yes                   Yes
  Repeated work    Avoided               Avoided
  Example          Recursive Fibonacci   Iterative Fibonacci

### Easy memory trick

**Memoization = Recursive + Store**

**Tabulation = Table + Iteration**



## Examples of Dynamic Programming

### 1. Matrix Chain Multiplication

Finds the best way to parenthesize matrices to minimize multiplication
cost.

**Time: `O(n³)`**

### 2. Floyd-Warshall Algorithm

Finds shortest paths between **all pairs of vertices**.

It can handle negative edge weights if there is **no negative cycle**.

**Time: `O(V³)`**

### 3. 0-1 Knapsack

For each item, decide whether to: - Include it, or - Exclude it.

Items cannot be divided.

**Time: `O(n·W)`**

### 4. Longest Common Subsequence (LCS)

Finds the longest common ordering between two sequences. The characters
do not have to be next to each other.

**Time: `O(m·n)`**

### 5. TSP using Dynamic Programming

Uses DP with bitmasking to store solutions for subsets of visited
cities.

**Time: `O(n²·2ⁿ)`**

### Exam line

**Dynamic Programming = Break into sub-problems, store their answers,
and reuse them.**



# 9. Backtracking

## Definition

**Backtracking** is a problem-solving technique that builds a solution
**step by step**.

When a choice leads to a dead end, it **undoes the choice and goes
back** to try another choice.

### Easy idea

**Choose → Explore → Check → Backtrack**



## How Backtracking Works

1.  **Choose** a possible option.
2.  **Explore** further using that option.
3.  **Check validity**.
4.  If invalid, **undo/backtrack**.
5.  Try another option.
6.  Continue until a solution is found or all possibilities are checked.

Backtracking saves time by stopping early when a partial solution is
already invalid.



## Example: N-Queens Problem

### Goal

Place `N` queens on an `N × N` chessboard so that **no two queens attack
each other**.

### Steps

1.  Start with the first row.
2.  Try placing a queen in a column.
3.  Move to the next row.
4.  Check whether the new queen is safe.
5.  If two queens are in the same column or diagonal, reject that
    branch.
6.  Backtrack and try another column.
7.  Continue until all queens are placed.

If all queens are placed without conflict, a valid solution is found.



## Backtracking Diagram Colors from Slides

The slide diagram shows: - **Green** = start/accepted state depending on
the diagram - **Blue** = intermediate/check point - **Red** = no
feasible solution / dead end - **Grey** = end solution

The important idea is that when a red/dead-end state is reached, the
algorithm goes backward and tries another branch.



## Backtracking Algorithm

A simplified form from the slides:

``` text
Backtrack(x)

1. If x is not a solution:
       return false

2. If x is a new solution:
       add it to the list of solutions

3. Backtrack(expand x)
```

Another form:

``` text
Backtrack(current_position)

1. If current_position is the goal:
       return success

2. Otherwise:
       If current_position is an end point:
           return failed
       Else:
           explore
           repeat
```



## Why Backtracking Saves Time

Without backtracking/pruning, we may have to test a huge number of
possible arrangements.

With backtracking: - Check validity early. - Stop an invalid branch
immediately. - Do not continue an impossible path.

### Exam line

**Backtracking = Try a choice; if it fails, undo it and try another
choice.**



# 10. Complexity of Backtracking

Generally, the time complexity is **exponential**, often written as:

**O(kⁿ)**

In some problems it can be **factorial**:

**O(n!)**

So backtracking can become expensive for large input sizes.



# 11. When to Use Backtracking

Use backtracking when:

1.  The problem is a **constraint satisfaction problem**.

    -   N-Queens
    -   Sudoku
    -   Rat in a Maze

2.  It is a search problem where invalid branches can be removed early.

3.  You need to find **multiple/all valid solutions**.

4.  The problem involves combinations, permutations, or subsets with
    constraints.



# 12. When NOT to Use Backtracking

Avoid backtracking when:

1.  Greedy or DP can solve the problem more directly.
2.  No pruning is possible.
3.  The input is very large and the search space is huge.
4.  Only one optimal solution is needed and another efficient algorithm
    is available.



# 13. Examples of Backtracking

  -----------------------------------------------------------------------
  Problem                 Main Idea               Worst-case complexity
                                                  from slides
  ----------------------- ----------------------- -----------------------
  N-Queen                 Place queens safely     `O(N!)`

  Sudoku                  Try valid digits and    `O(9^(n²))`
                          backtrack               

  M-Coloring              Color graph without     `O(M^V)`
                          adjacent same colors    

  Rat in a Maze           Explore paths and       `O(2^(n²))`
                          backtrack at dead ends  

  Knight's Tour           Visit every board       `O(8^(N²))`
                          square once             
  -----------------------------------------------------------------------



# 14. Randomized Algorithm

## Definition

A **Randomized Algorithm** uses **random numbers/random choices** while
making decisions during execution.

The random choice can affect the path taken by the algorithm.

### Easy idea

**Input + Random choice → Algorithm → Output**

A random number generator (RNG) is a prerequisite for these algorithms.



## Deterministic vs Randomized Algorithm

### Deterministic Algorithm

For the same input:

-   It follows the same steps.
-   It makes the same decisions.
-   It produces the same output.

### Randomized Algorithm

For the same input:

-   It can make different random decisions.
-   It may follow different steps in different runs.
-   Its behavior can vary between runs.

### Easy comparison

  Deterministic                Randomized
  ---------------------------- --------------------------------
  Same input → same behavior   Same input → behavior may vary
  No random choice             Uses random choice
  Same execution path          Execution path may differ
  Predictable                  Randomized decisions



# 15. Examples of Randomized Algorithms

## 1. Randomized QuickSort

Chooses a **random pivot** instead of always using a fixed pivot.

Purpose: - Reduce the chance of bad pivot choices. - Avoid poor behavior
on already-sorted/adversarial inputs.

Expected time:

**O(n log n)**

## 2. Randomized Selection / Quickselect

Finds the `k`-th smallest element using a randomly selected pivot.

Expected time:

**O(n)**

## 3. Karger's Min-Cut Algorithm

-   Randomly chooses an edge.
-   Contracts the chosen edge.
-   Continues until two vertices remain.
-   Repeats the process to increase the probability of finding the
    minimum cut.

Time per run from slides:

**O(V²)**



# 16. Quick Comparison of All 7 Types

  -----------------------------------------------------------------------
  Type                    Main Idea               Key Word
  ----------------------- ----------------------- -----------------------
  **Brute Force**         Try all possibilities   **Try Everything**

  **Recursion**           Function calls itself   **Call Again**

  **Divide & Conquer**    Divide, solve, combine  **Divide & Combine**

  **Greedy**              Choose best option now  **Best Now**

  **Dynamic Programming** Store and reuse         **Store & Reuse**
                          subproblem results      

  **Backtracking**        Try, fail, undo, try    **Undo & Try**
                          again                   

  **Randomized**          Use random decisions    **Random Choice**
  -----------------------------------------------------------------------



# 17. Important Differences for Exam

## Brute Force vs Greedy

**Brute Force** - Tries all possibilities. - Usually guarantees the
correct/optimal answer if all candidates are evaluated. - Can be very
slow.

**Greedy** - Chooses the best option at each step. - Does not reconsider
earlier choices. - May fail to give the optimal answer.



## Divide & Conquer vs Dynamic Programming

**Divide & Conquer** - Divides the problem. - Sub-problems are generally
independent. - Solves and combines them.

**Dynamic Programming** - Divides the problem. - Sub-problems can
overlap. - Stores answers and reuses them.



## Greedy vs Dynamic Programming

**Greedy** - Local best choice. - Usually does not backtrack. - May not
give optimal result.

**DP** - Considers overall optimization. - Stores subproblem results. -
Can give an optimal solution when DP properties hold.



## Backtracking vs Brute Force

**Brute Force** - Usually checks all possible candidates.

**Backtracking** - Also explores possibilities, but **stops
early/prunes** when a partial solution becomes invalid.

So:

**Backtracking = Brute-force style search + pruning/backtracking.**



## Recursion vs Divide & Conquer

**Recursion** is a programming/problem-solving technique where a
function calls itself.

**Divide & Conquer** is an algorithm design strategy: - Divide
problem. - Solve sub-problems. - Combine results.

Divide & conquer often uses recursion, but recursion itself is broader.



# 18. Very Important Complexity List

Memorize these examples from the slides:

``` text
Linear Search                 O(n)
Bubble Sort                   O(n²)
Selection Sort                O(n²)
Naive String Matching         O(n·m)
Closest Pair (Brute Force)    O(n²)
TSP Brute Force               O(n!)
Knapsack Brute Force          O(2ⁿ)
Matrix Multiplication         O(n³)

Factorial recursion           O(n)
Naive Fibonacci               O(2ⁿ)
Recursive Binary Search       O(log n)
Tower of Hanoi                O(2ⁿ)
Merge Sort                    O(n log n)
Quick Sort                    O(n log n) average, O(n²) worst
GCD                           O(log(min(a,b)))

Binary Search (D&C)           O(log n)
Strassen                      O(n^2.81)
Karatsuba                     O(n^1.585)
Closest Pair (D&C)            O(n log n)

Fractional Knapsack           O(n log n)
Prim                          O(E log V)
Kruskal                       O(E log E)
Dijkstra                      O(E log V)

DP Fibonacci (Memoization)    O(n)
DP Fibonacci (Tabulation)     O(n)
Matrix Chain Multiplication   O(n³)
Floyd-Warshall                O(V³)
0-1 Knapsack                  O(n·W)
LCS                           O(m·n)
TSP DP                        O(n²·2ⁿ)

Backtracking                  Generally O(kⁿ), sometimes O(n!)
N-Queens                      O(N!)
```



# 19. Short Questions --- Ready-to-Write Answers

## Q1. What is Brute Force?

**Answer:**\
Brute Force is a simple algorithmic technique that systematically tries
all possible solutions until the required solution is found. It is
suitable for small problems but can be very slow for large inputs.

## Q2. What is Recursion?

**Answer:**\
Recursion is a technique in which a function calls itself directly or
indirectly to solve a smaller version of a problem.

## Q3. What are the two properties of recursion?

**Answer:** 1. **Base case:** A condition that stops recursion. 2.
**Progressive approach:** Each recursive call must move closer to the
base case.

## Q4. What is Divide & Conquer?

**Answer:**\
Divide & Conquer divides a problem into smaller sub-problems, solves
them, and combines their solutions to obtain the final solution.

## Q5. What are the three steps of Divide & Conquer?

**Answer:** 1. Divide 2. Conquer/Solve 3. Merge/Combine

## Q6. What is a Greedy Algorithm?

**Answer:**\
A Greedy algorithm selects the best available option at each step
without reconsidering previous choices. It may not always produce the
globally optimal solution.

## Q7. What are the five components of a Greedy Algorithm?

**Answer:** 1. Candidate set 2. Selection function 3. Feasibility
function 4. Objective function 5. Solution function

## Q8. What is Dynamic Programming?

**Answer:**\
Dynamic Programming solves a problem by dividing it into smaller
sub-problems, storing their results, and reusing those results to avoid
repeated calculations.

## Q9. What are the two properties of DP?

**Answer:** 1. Overlapping subproblems 2. Optimal substructure

## Q10. What are the two types of DP?

**Answer:** 1. Top-Down / Memoization 2. Bottom-Up / Tabulation

## Q11. What is Backtracking?

**Answer:**\
Backtracking builds a solution step by step. When a choice leads to an
invalid state or dead end, it undoes the choice and tries another
option.

## Q12. What is a Randomized Algorithm?

**Answer:**\
A Randomized Algorithm uses random numbers or random choices during
execution, so the same input may lead to different decisions or
execution paths in different runs.



# 20. Last-Minute Revision

### One-line memory trick

``` text
Brute Force       → Try all
Recursion         → Call itself
Divide & Conquer  → Divide + Solve + Combine
Greedy            → Best now
DP                → Store + Reuse
Backtracking      → Try + Undo
Randomized        → Random choice
```

### Most important points to memorize

-   **Brute Force:** all possibilities.
-   **Recursion:** base case + progressive approach.
-   **Recursion uses:** stack/activation records.
-   **Divide & Conquer:** Divide → Conquer → Combine.
-   **Greedy:** local best choice; may not be globally optimal.
-   **Greedy has 5 components:** candidate, selection, feasibility,
    objective, solution.
-   **DP:** overlapping subproblems + optimal substructure.
-   **Memoization:** top-down + recursion.
-   **Tabulation:** bottom-up + iteration.
-   **Backtracking:** choose → explore → check → undo.
-   **Backtracking:** useful for N-Queens, Sudoku, maze, coloring.
-   **Randomized:** uses random decisions; same input can behave
    differently across runs.



# 21. Important Exam Keywords

Use these keywords in answers:

-   **Brute Force:** exhaustive search, all possibilities, simple,
    inefficient.
-   **Recursion:** self-call, base case, stack, activation record.
-   **Divide & Conquer:** divide, conquer, combine.
-   **Greedy:** local optimum, best current choice, no backtracking.
-   **DP:** overlapping subproblems, optimal substructure, memoization,
    tabulation.
-   **Backtracking:** trial-and-error, pruning, dead end, undo.
-   **Randomized:** random numbers, random decisions, RNG, different
    runs.



## Final Exam Tip

For a **3--5 mark definition question**, write:

**Definition → 2/3 key points → one example → complexity (if
relevant).**

For a **difference question**, use a small table.

For a **long question**, write:

**Definition → Working/Steps → Advantages → Limitations → Examples →
Complexity.**
