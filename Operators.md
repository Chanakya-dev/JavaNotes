# 🧠 Java Operators – Complete Detailed Guide for Beginners

---

## ✅ What are Operators?

**Operators** are special symbols used to perform operations on variables and values. For example:

```java
int sum = 10 + 20;
```

Here `+` is an **arithmetic operator** that adds two numbers.

---

## 📚 Types of Operators in Java

Java provides the following categories of operators:

```
1. Arithmetic Operators
2. Relational (Comparison) Operators
3. Logical Operators
4. Assignment Operators
5. Unary Operators
6. Bitwise Operators
7. Ternary Operator
8. instanceof Operator
```

---

## 1️⃣ Arithmetic Operators

Used to perform basic mathematical operations.

| Operator | Description         | Example  | Result |
| -------- | ------------------- | -------- | ------ |
| `+`      | Addition            | `10 + 5` | 15     |
| `-`      | Subtraction         | `10 - 5` | 5      |
| `*`      | Multiplication      | `10 * 5` | 50     |
| `/`      | Division            | `10 / 2` | 5      |
| `%`      | Modulus (remainder) | `10 % 3` | 1      |

### Example:

```java
int a = 10, b = 3;
System.out.println("Add: " + (a + b));
System.out.println("Divide: " + (a / b)); // Result: 3
System.out.println("Modulus: " + (a % b)); // Result: 1
```

---

## 2️⃣ Relational (Comparison) Operators

Used to compare two values. Returns a boolean result (`true` or `false`).

| Operator | Description              | Example  |
| -------- | ------------------------ | -------- |
| `==`     | Equal to                 | `a == b` |
| `!=`     | Not equal to             | `a != b` |
| `>`      | Greater than             | `a > b`  |
| `<`      | Less than                | `a < b`  |
| `>=`     | Greater than or equal to | `a >= b` |
| `<=`     | Less than or equal to    | `a <= b` |

### Example:

```java
int x = 10, y = 20;
System.out.println(x == y); // false
System.out.println(x < y);  // true
```

---

## 3️⃣ Logical Operators

Used to combine multiple conditions (mostly with boolean values).

| Operator | Description | Example         | Result     |        |   |         |      |
| -------- | ----------- | --------------- | ---------- | ------ | - | ------- | ---- |
| `&&`     | Logical AND | `true && false` | false      |        |   |         |      |
| \`       |             | \`              | Logical OR | \`true |   | false\` | true |
| `!`      | Logical NOT | `!true`         | false      |        |   |         |      |

### Example:

```java
int age = 25;
boolean isStudent = true;
System.out.println(age > 18 && isStudent); // true
System.out.println(!(age > 30)); // true
```

---

## 4️⃣ Assignment Operators

Used to assign values to variables.

| Operator | Example  | Equivalent To |
| -------- | -------- | ------------- |
| `=`      | `x = 10` | assign 10     |
| `+=`     | `x += 5` | `x = x + 5`   |
| `-=`     | `x -= 5` | `x = x - 5`   |
| `*=`     | `x *= 5` | `x = x * 5`   |
| `/=`     | `x /= 5` | `x = x / 5`   |
| `%=`     | `x %= 5` | `x = x % 5`   |

### Example:

```java
int a = 10;
a += 5; // a = 15
System.out.println(a);
```

---

## 5️⃣ Unary Operators

Operate on a single operand.

| Operator | Description          | Example      |
| -------- | -------------------- | ------------ |
| `+`      | Unary plus           | `+a`         |
| `-`      | Unary minus          | `-a`         |
| `++`     | Increment (pre/post) | `++a`, `a++` |
| `--`     | Decrement (pre/post) | `--a`, `a--` |
| `!`      | Logical NOT          | `!true`      |

### Example:

```java
int x = 5;
System.out.println(++x); // 6 (pre-increment)
System.out.println(x--); // 6 (post-decrement, x becomes 5 next)
```

---

## 6️⃣ Bitwise Operators (Advanced, for binary operations)

| Operator | Description        | Example    |     |     |
| -------- | ------------------ | ---------- | --- | --- |
| `&`      | Bitwise AND        | `a & b`    |     |     |
| "|"      | Bitwise OR         | \`a | b\` |
| `^`      | Bitwise XOR        | `a ^ b`    |     |     |
| `~`      | Bitwise Complement | `~a`       |     |     |
| `<<`     | Left shift         | `a << 2`   |     |     |
| `>>`     | Right shift        | `a >> 2`   |     |     |

### Example:

```java
int a = 5;   // 0101
int b = 3;   // 0011
System.out.println(a & b); // 1 (0001)
```

---

## 7️⃣ Ternary Operator (Shorthand `if-else`)

Syntax:

```java
variable = (condition) ? expression1 : expression2;
```

### Example:

```java
int age = 18;
String result = (age >= 18) ? "Adult" : "Minor";
System.out.println(result); // Adult
```

---

## 8️⃣ `instanceof` Operator

Checks whether an object is an instance of a specific class or subclass.

### Example:

```java
String name = "Java";
System.out.println(name instanceof String); // true
```

---

## 📝 Summary Table

| Category     | Common Operators                  |                           |         |
| ------------ | --------------------------------- | ------------------------- | ------- |
| Arithmetic   | `+`, `-`, `*`, `/`, `%`           |                           |         |
| Relational   | `==`, `!=`, `<`, `>`, `<=`, `>=`  |                           |         |
| Logical      | `&&`, \`                          |                           | `, `!\` |
| Assignment   | `=`, `+=`, `-=`, `*=`, `/=`, `%=` |                           |         |
| Unary        | `++`, `--`, `+`, `-`, `!`         |                           |         |
| Bitwise      | `&`, \`                           | `, `^`, `\~`, `<<`, `>>\` |         |
| Ternary      | `? :`                             |                           |         |
| Object Check | `instanceof`                      |                           |         |

---

## 🧠 Best Practices

* Avoid chaining too many operators in a single line.
* Use parentheses `()` to make operator precedence explicit.
* Use ternary operator for **simple** conditions only.
* Know the difference between `==` (comparison) and `=` (assignment).
* For comparing objects (like strings), always use `.equals()` instead of `==`.
