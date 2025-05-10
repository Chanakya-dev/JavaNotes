# 🔧 Functions (Methods) in Java – Beginner-Friendly Detailed Notes

---

## 🧠 What is a Function in Java?

In Java, a **function** (or method) is a block of code that performs a **specific task**.
You can **call** the function whenever you need it, instead of writing the same code again and again.

---

## 📌 Why Use Functions?

✅ Benefits:

* Code **reusability**
* Code **modularity** (break programs into smaller parts)
* Makes code **easier to read and maintain**
* Helps in **debugging** and **testing**

---

## 🧱 Basic Structure of a Function

```java
returnType functionName(parameters) {
    // body of the function
    // optional return statement
}
```

---

## ✅ Example: Basic Function

```java
public class HelloWorld {

    // function to print Hello
    static void sayHello() {
        System.out.println("Hello, Java!");
    }

    public static void main(String[] args) {
        sayHello();  // function call
    }
}
```

🟢 Output:

```
Hello, Java!
```

---

## ✨ Function with Parameters

```java
static void greetUser(String name) {
    System.out.println("Hello, " + name + "!");
}

public static void main(String[] args) {
    greetUser("Alice");
    greetUser("Bob");
}
```

🟢 Output:

```
Hello, Alice!
Hello, Bob!
```

---

## 🧮 Function with Return Type

```java
static int add(int a, int b) {
    return a + b;
}

public static void main(String[] args) {
    int result = add(5, 3);
    System.out.println("Sum = " + result);
}
```

🟢 Output:

```
Sum = 8
```

---

## 📚 Types of Functions

| Function Type             | Example                   |
| ------------------------- | ------------------------- |
| No return, No parameter   | `void sayHello()`         |
| No return, With parameter | `void greet(String name)` |
| Return, No parameter      | `int getNumber()`         |
| Return, With parameter    | `int add(int a, int b)`   |

---

## ⚙️ The `main()` Method

```java
public static void main(String[] args) {
    // Program starts here
}
```

📝 It's the **entry point** of any Java program.

* `public` → accessible to JVM
* `static` → doesn’t need an object to run
* `void` → does not return anything

---

## 🔁 Calling a Function

```java
functionName(arguments);
```

📌 Example:

```java
int sum = add(4, 7);
```

---

## 🧠 Real-Life Analogy

> Think of a function like a **vending machine**:
> You give it **input** (money and selection), it performs a **task**, and gives **output** (your snack).

---

## 🔍 Understanding `return`

* `return` sends a value back from the function.
* It also **ends** the function immediately.

```java
return value;
```

Example:

```java
return a + b;
```

---

## 👀 Function Overloading (Bonus Concept)

> Function overloading means having **multiple functions with the same name but different parameters**.

```java
static int multiply(int a, int b) {
    return a * b;
}

static double multiply(double a, double b) {
    return a * b;
}
```

---

## 🧪 Practice Examples

### 1. Function to find maximum of two numbers:

```java
static int max(int a, int b) {
    return (a > b) ? a : b;
}
```

### 2. Function to check even or odd:

```java
static void checkEvenOdd(int num) {
    if (num % 2 == 0)
        System.out.println("Even");
    else
        System.out.println("Odd");
}
```

### 3. Function to calculate factorial:

```java
static int factorial(int n) {
    int result = 1;
    for (int i = 1; i <= n; i++) {
        result *= i;
    }
    return result;
}
```

---

## ⚠️ Common Mistakes to Avoid

| Mistake                                    | Solution                                    |
| ------------------------------------------ | ------------------------------------------- |
| Forgetting `return` for non-void           | Always return a value in non-void functions |
| Wrong parameter types                      | Match exact types and order                 |
| Calling method without parentheses         | Always use `()` when calling a method       |
| Using non-static methods in static context | Learn about objects and classes (OOP)       |

---

## 🧵 Summary

* Java functions are called **methods**
* You define them with a **return type**, name, and parameters
* Use them to **reuse** and **organize** your code
* Java has built-in methods, and you can create your own
* Practice helps master the syntax and structure

