# ✅ Java Conditional Statements and `switch` – For Beginners

---

## 🧠 What are Conditional Statements?

Conditional statements help Java programs **make decisions**.
They allow you to run certain code **only when a specific condition is true**.

Example:
If it's raining → Take an umbrella
If it's not raining → Don't take an umbrella

---

## 🔹 1. `if` Statement

Use this to check if **one condition is true**.

### 📌 Syntax:

```java
if (condition) {
    // code runs if condition is true
}
```

### ✅ Example:

```java
int age = 18;
if (age >= 18) {
    System.out.println("You can vote!");
}
```

---

## 🔹 2. `if-else` Statement

Use this when you have **two options**: true or false.

### 📌 Syntax:

```java
if (condition) {
    // code if true
} else {
    // code if false
}
```

### ✅ Example:

```java
int marks = 45;
if (marks >= 50) {
    System.out.println("You passed!");
} else {
    System.out.println("You failed.");
}
```

---

## 🔹 3. `if-else if-else` Ladder

Use this when you have **many conditions**.

### 📌 Syntax:

```java
if (condition1) {
    // code
} else if (condition2) {
    // code
} else {
    // default code
}
```

### ✅ Example:

```java
int marks = 75;

if (marks >= 90) {
    System.out.println("Grade A");
} else if (marks >= 75) {
    System.out.println("Grade B");
} else if (marks >= 60) {
    System.out.println("Grade C");
} else {
    System.out.println("Fail");
}
```

---

## 🔹 4. Nested `if`

You can write an `if` inside another `if`.

### ✅ Example:

```java
int age = 20;
boolean hasID = true;

if (age >= 18) {
    if (hasID) {
        System.out.println("Allowed to vote.");
    } else {
        System.out.println("ID required.");
    }
} else {
    System.out.println("You are too young.");
}
```

---

## 🔸 5. `switch` Statement

Use `switch` when you want to compare **one value** with **many cases** (like a menu).

### 📌 Syntax:

```java
switch (value) {
    case value1:
        // code
        break;
    case value2:
        // code
        break;
    default:
        // code if no case matches
}
```

### ✅ Example:

```java
int day = 3;

switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    case 3:
        System.out.println("Wednesday");
        break;
    default:
        System.out.println("Another day");
}
```

---

### ✅ Example with `String`:

```java
String color = "Red";

switch (color) {
    case "Red":
        System.out.println("Stop");
        break;
    case "Green":
        System.out.println("Go");
        break;
    default:
        System.out.println("Unknown signal");
}
```

---

## 🧠 Tips

| Situation                          | Use this     |
| ---------------------------------- | ------------ |
| Comparing values like 1, 2, 3, ... | `switch`     |
| Checking range or conditions       | `if-else`    |
| Multiple steps and options         | `if-else if` |

---

## 🧪 Mini Practice

👉 Write a program to print whether a number is:

* Positive
* Negative
* Zero

👉 Write a program that takes number 1-7 and prints the day using `switch`.
