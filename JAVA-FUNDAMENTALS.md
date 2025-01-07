# Java Fundamentals for DSA (Data Structures and Algorithms) Preparation

This document is a **comprehensive guide to Java fundamentals**, specially tailored for mastering **Data Structures and Algorithms (DSA)**. It covers all the essential concepts, syntax, and features of Java, enabling you to build a strong foundation for solving complex DSA problems. Let’s dive into the details!

---

## **Table of Contents**
1. Setting up the Java Environment
    - JDK, JRE, and JVM
    - Installing Java and IDE Setup
    - Configuring Environment Variables
2. Java Basics
    - Identifiers
    - Keywords
    - Data Types
    - Variables
3. Input and Output
    - Scanner
    - BufferedReader
    - PrintWriter for Fast I/O
4. Control Flow Statements
    - If-Else
    - Switch-Case
    - Loops (For, While, Do-While)
5. Operators
    - Arithmetic Operators
    - Relational Operators
    - Logical Operators
    - Assignment Operators
    - Unary Operators
    - Bitwise Operators
6. Methods and Recursion
    - Defining and Calling Methods
    - Static Methods
    - Parameter Passing (Call by Value)
    - Recursion
    - Tail Recursion and Optimization
7. Exception Handling
    - Try-Catch
    - Finally Block
    - Throwing Exceptions
8. Scope of Variables
    - Local Variables
    - Instance Variables
    - Static Variables
9. Advanced Topics (Optional Overview)
    - Object-Oriented Programming Basics
    - Collections Framework Overview
    - Working with Strings

---

## **1. Setting up the Java Environment**

### **JDK, JRE, and JVM**
- **JDK (Java Development Kit):**
  - A software development environment used for developing Java applications.
  - Includes a compiler (`javac`), libraries, and tools required for development.

- **JRE (Java Runtime Environment):**
  - Provides the libraries and JVM required to run Java applications.

- **JVM (Java Virtual Machine):**
  - Responsible for running Java bytecode on different platforms.
  - Java is platform-independent because of the JVM.

### **Installing Java and IDE Setup**
1. Download the JDK from [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html) or [OpenJDK](https://openjdk.org/).
2. Install a preferred IDE for Java development:
   - **IntelliJ IDEA:** Great for advanced development.
   - **Eclipse:** Lightweight and widely used.
   - **Visual Studio Code:** Add the Java Extension Pack for support.

### **Configuring Environment Variables**
1. Add the `bin` directory of your JDK installation to the system PATH.
2. Verify the installation by running:
   ```bash
   java -version
   javac -version
   ```

---

## **2. Java Basics**

### **Identifiers**
- Identifiers are names given to variables, methods, classes, or other program elements.
- **Rules for Identifiers:**
  1. Must begin with a letter (A-Z or a-z), `$`, or `_`.
  2. Cannot start with a digit.
  3. Can contain letters, digits, `$`, and `_`.
  4. Cannot use **keywords** as identifiers.
  5. Case-sensitive (e.g., `myVar` and `MyVar` are different).

**Example:**
```java
int age;       // Valid
int _salary;   // Valid
int $price;    // Valid
int 123num;    // Invalid (starts with a digit)
int class;     // Invalid (keyword)
```

### **Keywords**
- Keywords are reserved words in Java with predefined meanings.
- Examples include:

| Access Modifiers | Control Flow  | Primitive Types | Other Keywords       |
|-------------------|---------------|-----------------|----------------------|
| `public`         | `if`          | `int`           | `class`, `return`   |
| `private`        | `else`        | `boolean`       | `static`, `void`    |
| `protected`      | `switch`      | `char`          | `this`, `new`       |
| `final`          | `while`       | `double`        | `throws`, `try`     |

### **Data Types**
Java has two categories of data types:

#### **1. Primitive Data Types**
- **Numeric Types:**
  - `byte`: 1 byte, values (-128 to 127)
  - `short`: 2 bytes, values (-32,768 to 32,767)
  - `int`: 4 bytes, values (-2^31 to 2^31 - 1)
  - `long`: 8 bytes, values (-2^63 to 2^63 - 1)
  - `float`: 4 bytes, single-precision decimals
  - `double`: 8 bytes, double-precision decimals

- **Character and Boolean Types:**
  - `char`: 2 bytes, stores a single Unicode character.
  - `boolean`: Stores `true` or `false`.

**Example:**
```java
byte b = 100;
int num = 100000;
char grade = 'A';
boolean isJavaFun = true;
```

#### **2. Reference Data Types**
- Refers to objects and arrays.
- Examples:
  - Strings: `String name = "Java";`
  - Arrays: `int[] arr = {1, 2, 3};`

### **Variables**
Variables are containers for storing data values.

**Declaration Syntax:**
```java
data_type variable_name = value;
```

**Example:**
```java
int age = 25;      // Integer variable
double price = 99.99; // Decimal variable
```

#### **Types of Variables**
1. **Local Variables:** Declared inside a method or block, must be initialized.
2. **Instance Variables:** Declared inside a class but outside methods.
3. **Static Variables:** Declared with the `static` keyword, shared across all instances.

---

## **3. Input and Output**

### **Using Scanner**
```java
import java.util.Scanner;

public class ScannerExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your name: ");
        String name = scanner.nextLine();
        System.out.println("Hello, " + name);
    }
}
```

### **Using BufferedReader**
```java
import java.io.*;

public class BufferedReaderExample {
    public static void main(String[] args) throws IOException {
        BufferedReader reader = new BufferedReader(new InputStreamReader(System.in));
        System.out.print("Enter your age: ");
        int age = Integer.parseInt(reader.readLine());
        System.out.println("Your age is: " + age);
    }
}
```

### **Using PrintWriter**
```java
import java.io.*;

public class PrintWriterExample {
    public static void main(String[] args) throws IOException {
        PrintWriter out = new PrintWriter(System.out);
        out.println("Fast Output Example");
        out.flush();
    }
}
```

---

## **4. Control Flow Statements**

### **If-Else**
```java
if (condition) {
    // Code when condition is true
} else {
    // Code when condition is false
}
```

### **Switch-Case**
```java
int day = 3;
switch (day) {
    case 1: System.out.println("Monday"); break;
    case 2: System.out.println("Tuesday"); break;
    default: System.out.println("Other Day");
}
```

### **Loops**

#### **1. For Loop**
```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
```

#### **2. While Loop**
```java
int i = 0;
while (i < 5) {
    System.out.println(i);
    i++;
}
```

#### **3. Do-While Loop**
```java
int i = 0;
do {
    System.out.println(i);
    i++;
} while (i < 5);
```

---

### **Operators**

#### **Arithmetic Operators**
Arithmetic operators are used for mathematical calculations. The following table lists the operators and their usage:

| Operator | Description        | Example           |
|----------|--------------------|-------------------|
| `+`      | Addition           | `a + b`           |
| `-`      | Subtraction        | `a - b`           |
| `*`      | Multiplication     | `a * b`           |
| `/`      | Division           | `a / b`           |
| `%`      | Modulus (Remainder)| `a % b`           |

**Example:**
```java
int a = 10, b = 3;
System.out.println("Addition: " + (a + b)); // 13
System.out.println("Subtraction: " + (a - b)); // 7
System.out.println("Multiplication: " + (a * b)); // 30
System.out.println("Division: " + (a / b)); // 3
System.out.println("Remainder: " + (a % b)); // 1
```

#### **Relational (Comparison) Operators**
Relational operators compare two values and return a boolean result (`true` or `false`).

| Operator | Description                  | Example  |
|----------|------------------------------|----------|
| `==`     | Equal to                     | `a == b` |
| `!=`     | Not equal to                 | `a != b` |
| `>`      | Greater than                 | `a > b`  |
| `<`      | Less than                    | `a < b`  |
| `>=`     | Greater than or equal to     | `a >= b` |
| `<=`     | Less than or equal to        | `a <= b` |

**Example:**
```java
int x = 5, y = 10;
System.out.println(x > y);  // false
System.out.println(x < y);  // true
System.out.println(x == y); // false
System.out.println(x != y); // true
```

#### **Logical Operators**
Logical operators are used to combine conditional statements.

| Operator | Description                 | Example        |
|----------|-----------------------------|----------------|
| `&&`     | Logical AND                 | `(a > b) && (c > d)` |
| `||`     | Logical OR                  | `(a > b) || (c > d)` |
| `!`      | Logical NOT                 | `!(a > b)`     |

**Example:**
```java
int a = 10, b = 20, c = 30;
System.out.println((a > b) && (b < c)); // false
System.out.println((a < b) || (b > c)); // true
System.out.println(!(a < b)); // false
```

#### **Assignment Operators**
Assignment operators are used to assign values to variables.

| Operator | Description            | Example   |
|----------|------------------------|-----------|
| `=`      | Assign                 | `a = b`   |
| `+=`     | Add and assign          | `a += b`  |
| `-=`     | Subtract and assign     | `a -= b`  |
| `*=`     | Multiply and assign     | `a *= b`  |
| `/=`     | Divide and assign       | `a /= b`  |
| `%=`     | Modulus and assign      | `a %= b`  |

**Example:**
```java
int a = 10;
a += 5; // a = a + 5
System.out.println(a); // 15
a *= 2; // a = a * 2
System.out.println(a); // 30
```

#### **Unary Operators**
Unary operators are applied to a single operand.

| Operator | Description         | Example   |
|----------|---------------------|-----------|
| `+`      | Unary plus          | `+a`      |
| `-`      | Unary minus         | `-a`      |
| `++`     | Increment           | `++a` or `a++` |
| `--`     | Decrement           | `--a` or `a--` |
| `!`      | Logical NOT         | `!a`      |

**Example:**
```java
int x = 5;
System.out.println(++x); // Pre-increment: 6
System.out.println(x++); // Post-increment: 6 (then x becomes 7)
System.out.println(--x); // Pre-decrement: 6
System.out.println(x--); // Post-decrement: 6 (then x becomes 5)
```

#### **Bitwise Operators**
Bitwise operators perform operations on the binary representation of numbers.

| Operator | Description      | Example   |
|----------|------------------|-----------|
| `&`      | AND              | `a & b`   |
| `|`      | OR               | `a | b`   |
| `^`      | XOR              | `a ^ b`   |
| `~`      | Complement        | `~a`      |
| `<<`     | Left Shift       | `a << b`  |
| `>>`     | Right Shift      | `a >> b`  |

**Example:**
```java
int a = 5, b = 3; // Binary: a = 0101, b = 0011
System.out.println(a & b); // AND: 0001 (1)
System.out.println(a | b); // OR: 0111 (7)
System.out.println(a ^ b); // XOR: 0110 (6)
System.out.println(~a);    // NOT: 1010 (-6 in 2's complement)
System.out.println(a << 1); // Left Shift: 1010 (10)
System.out.println(a >> 1); // Right Shift: 0010 (2)
```

---

## **6. Methods and Recursion**

### **Defining and Calling Methods**
A method is a block of code that performs a specific task. It is reusable and improves modularity.

**Syntax:**
```java
returnType methodName(parameters) {
    // Method body
    return value; // if returnType is not void
}
```

**Example:**
```java
public class MethodExample {
    public static int addNumbers(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int result = addNumbers(5, 10);
        System.out.println("Sum: " + result);
    }
}
```

### **Static Methods**
Static methods belong to the class rather than instances of the class. They can be called without creating an object.

**Example:**
```java
public class StaticExample {
    public static void printMessage() {
        System.out.println("This is a static method.");
    }

    public static void main(String[] args) {
        printMessage(); // Direct call to static method
    }
}
```

### **Parameter Passing (Call by Value)**
In Java, method arguments are passed by value. Changes made to the parameters inside the method do not affect the original variables.

**Example:**
```java
public class CallByValue {
    public static void modifyValue(int x) {
        x = x + 10; // Change only inside the method
    }

    public static void main(String[] args) {
        int num = 5;
        modifyValue(num);
        System.out.println("Original value: " + num); // Output: 5
    }
}
```

### **Recursion**
Recursion is a technique where a method calls itself to solve a problem.

**Example (Factorial):**
```java
public class RecursionExample {
    public static int factorial(int n) {
        if (n == 0) {
            return 1; // Base case
        }
        return n * factorial(n - 1); // Recursive case
    }

    public static void main(String[] args) {
        int result = factorial(5);
        System.out.println("Factorial: " + result); // Output: 120
    }
}
```

### **Tail Recursion and Optimization**
Tail recursion is when the recursive call is the last statement in the function. It can be optimized by the compiler to reduce stack usage.

**Example:**
```java
public class TailRecursion {
    public static int factorialTail(int n, int accumulator) {
        if (n == 0) {
            return accumulator;
        }
        return factorialTail(n - 1, accumulator * n);
    }

    public static void main(String[] args) {
        int result = factorialTail(5, 1);
        System.out.println("Factorial: " + result); // Output: 120
    }
}
```

---
