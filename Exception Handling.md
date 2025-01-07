## **Exception Handling**

In Java, **exceptions** are unexpected events or errors that occur during program execution, disrupting the normal flow of the program. Java provides a robust framework for handling such exceptions, ensuring the program can recover gracefully or terminate in a controlled manner.

### **Key Concepts in Exception Handling**

1. **Exception Hierarchy**  
   Exceptions in Java are part of a hierarchy of classes:
   - **Throwable**: The superclass of all errors and exceptions.
     - **Error**: Represents serious issues (e.g., `OutOfMemoryError`). These are not meant to be handled by the application.
     - **Exception**: Represents conditions that can be handled.
       - **Checked Exceptions**: Exceptions that must be declared or handled (e.g., `IOException`, `SQLException`).
       - **Unchecked Exceptions**: Runtime exceptions (e.g., `NullPointerException`, `ArithmeticException`) that do not need to be explicitly handled.

2. **Keywords in Exception Handling**  
   Java provides five keywords for exception handling:
   - `try`: Defines a block of code to monitor for exceptions.
   - `catch`: Defines a block of code to handle the exception.
   - `finally`: A block that always executes, whether or not an exception occurs.
   - `throw`: Used to explicitly throw an exception.
   - `throws`: Declares exceptions that a method might throw.

---

### **Basic Syntax for Exception Handling**

The basic structure involves `try`, `catch`, and `finally` blocks:

```java
try {
    // Code that may throw an exception
} catch (ExceptionType e) {
    // Code to handle the exception
} finally {
    // Code that will execute regardless of exception
}
```

---

### **Examples of Exception Handling**

#### **1. Try-Catch Block**
The `try` block contains code that might throw an exception, and the `catch` block handles it.

**Example:**
```java
public class TryCatchExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // Division by zero throws ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero: " + e.getMessage());
        }
    }
}
```

**Output:**
```
Cannot divide by zero: / by zero
```

#### **2. Multiple Catch Blocks**
You can use multiple `catch` blocks to handle different types of exceptions.

**Example:**
```java
public class MultipleCatchExample {
    public static void main(String[] args) {
        try {
            int[] arr = {1, 2, 3};
            System.out.println(arr[5]); // ArrayIndexOutOfBoundsException
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic Exception occurred");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array Index Out of Bounds: " + e.getMessage());
        } catch (Exception e) {
            System.out.println("Some other exception occurred");
        }
    }
}
```

**Output:**
```
Array Index Out of Bounds: Index 5 out of bounds for length 3
```

#### **3. Finally Block**
The `finally` block is executed no matter what happens in the `try` block, even if an exception is thrown or caught.

**Example:**
```java
public class FinallyExample {
    public static void main(String[] args) {
        try {
            int data = 50 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Exception caught");
        } finally {
            System.out.println("Finally block executed");
        }
    }
}
```

**Output:**
```
Exception caught  
Finally block executed
```

#### **4. Throwing Exceptions with `throw`**
The `throw` keyword is used to explicitly throw an exception.

**Example:**
```java
public class ThrowExample {
    public static void validateAge(int age) {
        if (age < 18) {
            throw new IllegalArgumentException("Age must be at least 18");
        }
    }

    public static void main(String[] args) {
        try {
            validateAge(16);
        } catch (IllegalArgumentException e) {
            System.out.println("Exception: " + e.getMessage());
        }
    }
}
```

**Output:**
```
Exception: Age must be at least 18
```

#### **5. Declaring Exceptions with `throws`**
The `throws` keyword is used in the method signature to indicate that a method might throw an exception.

**Example:**
```java
import java.io.*;

public class ThrowsExample {
    public static void readFile(String fileName) throws IOException {
        FileReader file = new FileReader(fileName);
        BufferedReader reader = new BufferedReader(file);
        System.out.println(reader.readLine());
    }

    public static void main(String[] args) {
        try {
            readFile("test.txt");
        } catch (IOException e) {
            System.out.println("File not found: " + e.getMessage());
        }
    }
}
```

---

### **Custom Exceptions**
You can define your own exception by extending the `Exception` class or `RuntimeException`.

**Example:**
```java
class CustomException extends Exception {
    public CustomException(String message) {
        super(message);
    }
}

public class CustomExceptionExample {
    public static void main(String[] args) {
        try {
            throw new CustomException("This is a custom exception");
        } catch (CustomException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**Output:**
```
This is a custom exception
```

---

### **Common Exceptions in Java**

Here are some frequently encountered exceptions:
1. **ArithmeticException**: Thrown when dividing by zero.
2. **NullPointerException**: Thrown when an object reference is null.
3. **ArrayIndexOutOfBoundsException**: Thrown when accessing an array index out of bounds.
4. **IOException**: Thrown when an I/O operation fails.
5. **ClassNotFoundException**: Thrown when a class is not found at runtime.
6. **NumberFormatException**: Thrown when converting a string into a number and the format is invalid.

---

### **Best Practices for Exception Handling**

1. Use exceptions to handle **unexpected errors**, not regular program flow.
2. Avoid using generic `Exception` in `catch` blocks; use specific exceptions.
3. Use `finally` for cleanup operations like closing files or releasing resources.
4. Log exceptions for debugging instead of just printing stack traces.
5. Avoid swallowing exceptions (e.g., an empty `catch` block).
6. Use custom exceptions for application-specific errors.

---
