# Object Oriented Programming | Java Operator

An **operator** is a symbol used to perform an operation on values or variables.

**Example:** `+`, `-`, `*`, `/`, `==`

## Types of Operators in Java

### 1. Arithmetic Operators

Used to perform **mathematical calculations**.

**Example:** `+`, `-`, `*`, `/`, `%`

### 2. Relational Operators

Used to **compare two values**.

**Example:** `>`, `<`, `==`, `!=`, `>=`, `<=`

### 3. Bitwise Operators

Used to perform operations on **individual bits** of values.

**Example:** `&`, `|`, `^`, `~`

### 4. Boolean Logical Operators

Used to perform **logical operations** on boolean values.

**Example:** `&&`, `||`, `!`

### 5. Conditional Operator (`?:`)

Used to make a **simple decision between two values**.

**Example:**
```java
age >= 18 ? "Adult" : "Minor"
```

## Conditional Operator (`?:`)

The **conditional operator** is a ternary operator used to choose **one of two values based on a condition**.

### Syntax

```java
condition ? value1 : value2;
```

- If the condition is **true**, `value1` is selected.
- If the condition is **false**, `value2` is selected.

### Example

```java
int age = 20;

String result = age >= 18 ? "Adult" : "Minor";

System.out.println(result);
```

### Output

```text
Adult
```

### Explanation

Here, `age >= 18` is **true**, so `"Adult"` is selected.

---

## Question

**Write a Java program to demonstrate the use of the Conditional Operator (`?:`).**

### Answer

```java
public class Test {

    public static void main(String args[]) {

        int a, b;

        a = 10;

        b = (a == 1) ? 20 : 30;

        System.out.println("Value of b is : " + b);

        b = (a == 10) ? 20 : 30;

        System.out.println("Value of b is : " + b);
    }
}
```

### Output

```text
Value of b is : 30
Value of b is : 20
```

### Explanation

```java
b = (a == 1) ? 20 : 30;
```

`a == 1` is **false**, so `b = 30`.

```java
b = (a == 10) ? 20 : 30;
```

`a == 10` is **true**, so `b = 20`.

### Conditional Operator Format

```java
condition ? value_if_true : value_if_false;
```

# Control Statements in Java

Control statements are used to **control the flow of execution** of a Java program.

## 1. Selection Statements

Selection statements are used to **make decisions** in a program.

- **if** — Executes a block of code when a condition is true.
- **switch** — Selects one block of code from multiple choices.

## 2. Iteration Statements

Iteration statements are used to **repeat a block of code**.

- **for loop** — Repeats code for a specific number of times.
- **while loop** — Repeats code while a condition is true.
- **do-while loop** — Executes the code at least once, then repeats while the condition is true.

## 3. Jump Statements

Jump statements are used to **change the normal flow of execution**.

- **break** — Stops the loop or switch statement.
- **continue** — Skips the current iteration and moves to the next iteration.
- **return** — Exits from a method and can return a value.

## 1. Check Whether a Number is Even or Odd

### Question

**Write a Java program to check whether a number is even or odd.**

### Answer

```java
public class EvenOdd {

    public static void main(String[] args) {

        int num = 10;

        if (num % 2 == 0)
            System.out.println("Even");
        else
            System.out.println("Odd");
    }
}
```

### Output

```text
Even
```

## 2. Check Whether a Number is Positive or Negative

### Question

**Write a Java program to check whether a number is positive or negative.**

### Answer

```java
public class PositiveNegative {

    public static void main(String[] args) {

        int num = 10;

        if (num >= 0)
            System.out.println("Positive");
        else
            System.out.println("Negative");
    }
}
```

### Output

```text
Positive
```

## 3. Check Whether a Year is a Leap Year or Not

### Question

**Write a Java program to check whether a year is a leap year or not.**

### Answer

```java
public class LeapYear {

    public static void main(String[] args) {

        int year = 2024;

        if (year % 4 == 0)
            System.out.println("Leap Year");
        else
            System.out.println("Not a Leap Year");
    }
}
```

### Output

```text
Leap Year
```

## 4. Find the Maximum Value of Three Numbers

### Question

**Write a Java program to find the maximum value among three numbers.**

### Answer

```java
public class Maximum {

    public static void main(String[] args) {

        int a = 10;
        int b = 20;
        int c = 15;

        if (a > b && a > c)
            System.out.println(a + " is maximum");
        else if (b > c)
            System.out.println(b + " is maximum");
        else
            System.out.println(c + " is maximum");
    }
}
```

### Output

```text
20 is maximum
```
