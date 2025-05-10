# 🔁 Loops in Java – Detailed Notes for Beginners

---

## 🧠 Why Loops?

Imagine you're a teacher and you want to say “Good Morning” to **50 students**.

Without loops:

```java
System.out.println("Good Morning");
System.out.println("Good Morning");
// ...repeat 50 times!
```

This is **repetitive and inefficient**.
✅ **Loops solve this** by repeating the same block of code **automatically**.

---

## 🎯 Purpose of Loops

* Run code **multiple times** without repeating yourself
* Handle **repetitive tasks** like printing numbers, processing arrays, or waiting for user input
* Make programs **shorter, cleaner, and smarter**

---

## 📌 Types of Loops in Java

Java provides 3 main types of loops:

| Loop Type  | When to Use                                   |
| ---------- | --------------------------------------------- |
| `for`      | When you **know** how many times to run       |
| `while`    | When you **don’t know** how many times to run |
| `do-while` | When you want to **run at least once**        |

---

## 🔹 1. `for` Loop

### ✅ Structure:

```java
for (initialization; condition; update) {
    // repeated code
}
```

### 📖 Parts:

* **Initialization** → set the starting point (e.g., `int i = 1`)
* **Condition** → checked before every loop (e.g., `i <= 5`)
* **Update** → modify the variable after each loop (e.g., `i++`)

### ✅ Example: Print numbers from 1 to 5

```java
for (int i = 1; i <= 5; i++) {
    System.out.println("Count: " + i);
}
```

**Output:**

```
Count: 1
Count: 2
Count: 3
Count: 4
Count: 5
```

### 🎓 Real-life Analogy:

> Think of climbing stairs. You know there are 5 steps. You climb each step (`i++`) until you reach the top (`i <= 5`).

---

## 🔹 2. `while` Loop

### ✅ Structure:

```java
while (condition) {
    // repeated code
}
```

### 📖 Usage:

Use `while` when you **don’t know** how many times the loop will run ahead of time.

### ✅ Example: Print 1 to 5

```java
int i = 1;
while (i <= 5) {
    System.out.println("Number: " + i);
    i++;
}
```

### 🎓 Real-life Analogy:

> You’re waiting for your phone to charge. You keep checking **while** battery < 100%.
> You don’t know how many times you’ll check.

---

## 🔹 3. `do-while` Loop

### ✅ Structure:

```java
do {
    // code runs at least once
} while (condition);
```

### 📖 Key Feature:

Runs **at least once**, even if the condition is false on the first check.

### ✅ Example:

```java
int i = 6;
do {
    System.out.println("Value: " + i);
    i++;
} while (i <= 5);
```

**Output:**

```
Value: 6
```

### 🎓 Real-life Analogy:

> Imagine going to a shop. You’ll **enter** the shop at least once, even if you don’t buy anything.

---

## 🛠 Control Statements with Loops

### 🔸 `break` – Exit the loop early

```java
for (int i = 1; i <= 10; i++) {
    if (i == 5) break;
    System.out.println(i);
}
// Output: 1 2 3 4
```

### 🔸 `continue` – Skip one loop iteration

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) continue;
    System.out.println(i);
}
// Output: 1 2 4 5
```

---

## 🧪 Practice Examples

### 🔸 1. Print even numbers between 1 and 10

```java
for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) {
        System.out.println(i);
    }
}
```

### 🔸 2. Sum of numbers from 1 to N

```java
int sum = 0;
int n = 10;
for (int i = 1; i <= n; i++) {
    sum += i;
}
System.out.println("Sum: " + sum);
```

### 🔸 3. Multiplication Table (e.g., 7)

```java
int num = 7;
for (int i = 1; i <= 10; i++) {
    System.out.println(num + " x " + i + " = " + (num * i));
}
```

---

## 🧠 Summary Table

| Loop Type  | Condition First? | Runs At Least Once? | Use Case                             |
| ---------- | ---------------- | ------------------- | ------------------------------------ |
| `for`      | ✅ Yes            | ❌ Only if true      | Known range (e.g., 1 to 10)          |
| `while`    | ✅ Yes            | ❌ Only if true      | Unknown count (e.g., wait for input) |
| `do-while` | ❌ No (runs once) | ✅ Always runs once  | Must run once (e.g., menu display)   |

---

## 📚 Real-Life Examples

| Scenario                        | Suitable Loop |
| ------------------------------- | ------------- |
| Printing a receipt 10 times     | `for` loop    |
| Waiting until user types "exit" | `while` loop  |
| Showing a menu at least once    | `do-while`    |
