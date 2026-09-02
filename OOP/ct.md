# OBJECT ORIENTED PROGRAMMING-II | CT

## 1. Explain the following statement by considering Java - "Write Once, run everywhere." (CSE-15th)

### Or Why is Java called a platform-independent language? (CT-CSE-19th) *****

**Write Once, Run Everywhere” (WORA)** is a key feature of Java. It means that a Java program needs to be **written and compiled only once**, and the same program can run on different operating systems without changing the source code.

When a Java program is compiled, the Java compiler converts the source code into **bytecode**. This bytecode runs on the **Java Virtual Machine (JVM)**. Since JVM is available for different operating systems such as **Windows, Linux, and macOS**, the same Java bytecode can run on all of them.

**Process:**

**Java Source Code (.java) → Compiler → Bytecode (.class) → JVM → Different Operating Systems**

Thus, Java achieves **platform independence through the JVM**, which is why Java is known for **“Write Once, Run Everywhere.”**

---

## 2. Explain JVM, JRE and JDK?

### 1. JVM (Java Virtual Machine):

JVM is a virtual machine that **executes Java bytecode**. It converts bytecode into machine-level instructions and helps Java achieve **platform independence**.

### 2. JRE (Java Runtime Environment):

JRE provides the environment needed to **run Java programs**. It contains **JVM and Java class libraries**.

### 3. JDK (Java Development Kit):

JDK is a complete package used to **develop and run Java programs**. It contains **JRE and development tools**, such as the Java compiler (`javac`).

### Relationship:

**JDK = JRE + Development Tools**

**JRE = JVM + Java Libraries**

---

## 3. Explain class and object in java with proper diagram.

### Class

A **class** is a blueprint or template used to create objects. It defines the **properties (variables)** and **behaviors (methods)** of objects.

### Object

An **object** is an instance of a class. It has its own **state (data)** and can perform **behaviors (methods)**.

### Proper Diagram

```text
                 CLASS
          ┌─────────────────┐
          │     Student     │
          ├─────────────────┤
          │ name            │
          │ age             │
          ├─────────────────┤
          │ study()         │
          │ display()       │
          └─────────────────┘
                  │
               creates
                  ↓
        ┌─────────────────┐
        │     Object      │
        │    student1     │
        ├─────────────────┤
        │ name = "Rahim"  │
        │ age = 20        │
        └─────────────────┘
```

### In simple words:

**Class = Blueprint**

**Object = Real thing created from the blueprint**

---

## 4. Why Java is NOT a Pure Object-Oriented Programming Language

Java is not considered a pure object-oriented programming language because it supports **primitive data types** such as `int`, `char`, `float`, `double`, and `boolean`, which are not objects.

For example:

```java
int age = 20;
```

Here, `age` is a primitive variable, not an object.

---

## 5. Method to Find Maximum of Two Integers

The following program takes two integers from the user and uses a method to return the maximum value.

```java
import java.util.Scanner;

public class Maximum {

    // Method to find maximum
    static int max(int num1, int num2) {
        if (num1 > num2) {
            return num1;
        } else {
            return num2;
        }
    }

    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        // Taking input from user
        System.out.print("Enter first number: ");
        int num1 = input.nextInt();

        System.out.print("Enter second number: ");
        int num2 = input.nextInt();

        // Calling method
        int result = max(num1, num2);

        // Printing result
        System.out.println("Maximum = " + result);
    }
}
```

### Example Output

```text
Enter first number: 25
Enter second number: 40
Maximum = 40
```

---

## 6. UML Diagram of Car Class in Java

A simple UML diagram for a `Car` class can be:

```text
┌─────────────────────────────┐
│            Car              │
├─────────────────────────────┤
│ - brand : String            │
│ - model : String            │
│ - year : int                │
├─────────────────────────────┤
│ + start() : void            │
│ + stop() : void             │
│ + displayInfo() : void      │
└─────────────────────────────┘
```

### UML Symbols

- `-` → **Private**
- `+` → **Public**
- Top section → **Class name**
- Middle section → **Attributes/variables**
- Bottom section → **Methods/behaviors**
