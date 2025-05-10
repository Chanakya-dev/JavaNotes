# 🧠 Java Variables and Data Types – Complete Beginner's Guide

---

## 📌 1. What is a Variable?

A **variable** in Java is a name assigned to a **memory location** that stores a value. Think of it as a container to hold data that can be used and modified during program execution.

### ✅ Example:

```java
int age = 25;
String name = "John";
```

Here:

* `int` and `String` are **data types**.
* `age` and `name` are **variables**.
* `25` and `"John"` are **values**.

---

## 📌 2. Types of Variables in Java

Java supports **three main types** of variables based on where and how they are declared:

### A. **Local Variables**

* Declared inside a method or block.
* Not accessible outside that method/block.
* Must be initialized before use.

```java
void display() {
    int count = 10; // local variable
    System.out.println(count);
}
```

---

### B. **Instance Variables (Non-static Fields)**

* Declared inside a class but **outside** any method.
* Belong to an object of the class.
* Each object has its own copy.

```java
class Person {
    String name; // instance variable

    void sayName() {
        System.out.println(name);
    }
}
```

---

### C. **Static Variables (Class Variables)**

* Declared using the `static` keyword.
* Shared among all instances of the class.

```java
class Student {
    static String school = "ABC High School"; // static variable
}
```

---

## 📌 3. Java Data Types

Java is a **strongly typed** language, meaning each variable must have a declared data type.

### Java Data Types are Categorized into:

```
                Java Data Types
              /                \
      Primitive             Non-Primitive
     (8 types)             (Reference types)
```

---

## 📌 4. Primitive Data Types (Built-in)

Java has **8 primitive** data types:

| Data Type | Description                              | Default Value | Size    | Example                  |
| --------- | ---------------------------------------- | ------------- | ------- | ------------------------ |
| `byte`    | Small integers (-128 to 127)             | 0             | 1 byte  | `byte b = 100;`          |
| `short`   | Larger range of byte (-32,768 to 32,767) | 0             | 2 bytes | `short s = 20000;`       |
| `int`     | Common for whole numbers                 | 0             | 4 bytes | `int x = 100000;`        |
| `long`    | Very large integers                      | 0L            | 8 bytes | `long l = 10000000000L;` |
| `float`   | Decimal numbers (single-precision)       | 0.0f          | 4 bytes | `float f = 3.14f;`       |
| `double`  | Decimal numbers (double-precision)       | 0.0d          | 8 bytes | `double d = 99.99;`      |
| `char`    | Single character (Unicode)               | '\u0000'      | 2 bytes | `char c = 'A';`          |
| `boolean` | True or False                            | false         | 1 bit   | `boolean flag = true;`   |

### ✅ Notes:

* Use `L` or `l` for `long` literals.
* Use `f` or `F` for `float` literals.
* `char` uses single quotes, e.g., `'A'`.

---

## 📌 5. Non-Primitive (Reference) Data Types

* Can be **user-defined** (like classes, interfaces) or **built-in** (like `String`, arrays).
* Store **references** (memory address) to the actual object.

### Examples:

```java
String greeting = "Hello World"; // String object
int[] marks = {90, 85, 88};      // Array object
```

---

## 📌 6. Declaration and Initialization

### ✅ Declaration:

```java
int number;
```

### ✅ Initialization:

```java
number = 50;
```

### ✅ Declaration & Initialization Together:

```java
int number = 50;
```

---

## 📌 7. Naming Rules for Variables

* Must start with a letter, `_` or `$`.
* Cannot start with a number.
* Can contain letters, digits, `_`, `$`.
* Cannot be a Java **keyword** (like `int`, `class`, etc.)
* **Case-sensitive** (`Age` and `age` are different).

### ✅ Examples:

```java
int age;
double totalAmount;
String firstName;
```

---

## 📌 8. Type Casting (Conversion between types)

### A. **Widening (Implicit) Casting** – Safe

Automatically converts a smaller type to a larger type.

```java
int a = 10;
double b = a;  // OK
```

### B. **Narrowing (Explicit) Casting** – Risky

Must be done manually; might lose data.

```java
double x = 9.78;
int y = (int) x;  // y becomes 9 (decimal lost)
```

---

## 📌 9. Constants (`final` keyword)

To declare a constant (value that cannot be changed):

```java
final int MAX_USERS = 100;
```

### ✅ Notes:

* Use all UPPERCASE letters by convention.
* Once assigned, the value cannot change.

---

## 📌 10. Default Values for Instance Variables

If you declare instance variables and don’t initialize them, they get **default values**:

| Data Type              | Default Value             |
| ---------------------- | ------------------------- |
| byte, short, int, long | 0                         |
| float, double          | 0.0                       |
| char                   | '\u0000' (null character) |
| boolean                | false                     |
| Objects (like String)  | null                      |

---

## 📌 11. Java Keywords (Not usable as variable names)

Java reserves words for its own use:

```text
abstract, boolean, byte, class, final, if, else, return, static, void, etc.
```

---

## 📌 12. Best Practices

* ✅ Use **camelCase** for variable names (`studentName`, `totalMarks`)
* ✅ Initialize variables before using.
* ✅ Use `final` for constants.
* ❌ Avoid using single-letter variable names in meaningful code (`x`, `y`, `z`).
* ✅ Add comments to explain purpose of variables when needed.

---

## 📌 13. Sample Code Putting It All Together

```java
public class DataTypeExample {
    // Instance variable
    String name = "Alice";

    // Static variable
    static String language = "Java";

    public static void main(String[] args) {
        // Local variables
        int age = 25;
        float height = 5.9f;
        boolean isStudent = true;
        char grade = 'A';

        System.out.println("Name: Alice");
        System.out.println("Age: " + age);
        System.out.println("Height: " + height);
        System.out.println("Grade: " + grade);
        System.out.println("Student: " + isStudent);
        System.out.println("Language: " + language);
    }
}
```
