# Object Oriented Programming | Keywords, Data Types, Identifiers

## Two Main Types of Data in Java

### 1. Primitive Data Types

Primitive data types are the **basic data types** in Java. They store **simple values** directly.

**Examples:** `int`, `float`, `char`, `boolean`

### 2. Classes

A class is a **user-defined data type** that contains **data and methods**. Objects are created from classes.

**Example:** `Student`, `Employee`

## Short Difference

| Primitive Data Types | Classes |
|---|---|
| Store simple values. | Define objects. |
| Built into Java. | Created by the programmer. |
| Example: `int`, `char` | Example: `Student`, `Employee` |

## Differences Between `7`, `'7'` and `"7"`

| Constant | Type | Meaning |
|---|---|---|
| `7` | Integer (`int`) | Represents the number **7** |
| `'7'` | Character (`char`) | Represents the **single character** 7 |
| `"7"` | String (`String`) | Represents the **text/string** "7" |

### Example

```java
int a = 7;
char b = '7';
String c = "7";
```

## Identifiers in Java

**Identifiers** are the **names given to classes, variables, and methods** in Java.

### Rules of Identifiers

- An identifier can contain **letters (A–Z, a–z), digits (0–9), `$`, and `_`**.
- An identifier **must begin with a letter, `$`, or `_`**.
- An identifier **cannot start with a digit**.
- A **Java keyword** cannot be used as an identifier.
- Identifiers are **case-sensitive**.

### Example of Case Sensitivity

```java
area
Area
AREA
```

### Legal Identifiers

```java
age
$salary
_value
__1_value
```

### Illegal Identifiers

```java
123abc     // Cannot start with a digit
-salary    // '-' is not allowed
student name // Space is not allowed
class      // 'class' is a keyword
```

### Easy Way to Remember

An identifier is simply a name used for a class, variable, or method.

## Find Out the Legal Identifiers

### Legal Identifiers ✅

- `$2`
- `area`
- `Min_number`
- `aaa`
- `sales_tax`
- `_circleArea`
- `a2b`
- `Box100width`
- `ab1234$$`
- `ComputeArea`

### Illegal Identifiers ❌

- `2A` → Cannot start with a digit.
- `d+4` → `+` is not allowed.
- `Max-Number` → `-` is not allowed.
- `/$directory` → `/` is not allowed.

### Final Answer

**Legal:** `$2`, `area`, `Min_number`, `aaa`, `sales_tax`, `_circleArea`, `a2b`, `Box100width`, `ab1234$$`, `ComputeArea`

**Illegal:** `2A`, `d+4`, `Max-Number`, `/$directory`
