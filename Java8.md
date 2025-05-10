# Java8 Features
---

### 1. **Lambda Expressions**

Lambda expressions are one of the most prominent features of Java 8. They allow you to express instances of single-method interfaces (functional interfaces) in a much more concise, readable, and flexible way.

#### **What are Lambda Expressions?**

A **lambda expression** is essentially a function that can be passed as an argument to a method. It enables you to treat behavior as a method argument, or to create a short function without having to write a full-blown method.

**Syntax**:

```java
(parameters) -> expression
```

* **parameters**: The input parameters to the function.
* **expression**: The body of the function.

**Example**:

```java
List<String> names = Arrays.asList("John", "Jane", "Doe");

names.forEach(name -> System.out.println(name));
```

Here, the `forEach()` method takes a **lambda expression** that prints each name in the list. This is a more concise and functional approach compared to traditional loops.

#### **Advantages**:

* Simplifies code by removing boilerplate code.
* Makes the code more readable.
* Enhances code flexibility and reusability.

---

### 2. **Functional Interfaces**

A **functional interface** is an interface with just one abstract method. Java 8 introduces functional interfaces to support lambda expressions, enabling functional programming.

#### **What is a Functional Interface?**

A functional interface can have multiple default and static methods, but it must have exactly one abstract method. These interfaces serve as the types for lambda expressions and method references.

**Example**:

```java
@FunctionalInterface
interface MyFunction {
    void apply();
}
```

In this example, `MyFunction` is a functional interface with a single abstract method `apply()`.

Common built-in functional interfaces in Java:

* `Runnable` – Represents a task that can be executed by a thread.
* `Callable` – Represents a task that returns a result and may throw an exception.
* `Comparator` – Used for comparing objects.
* `Predicate` – Represents a boolean-valued function of one argument.
* `Function` – Represents a function that takes an argument and returns a result.

#### **Why are they important?**

Functional interfaces allow you to use lambda expressions and method references. They form the foundation for Java’s functional programming capabilities.

---

### 3. **Streams API**

The **Streams API** introduced in Java 8 allows you to process collections of objects in a functional style. It allows for efficient data processing and makes it easier to work with sequences of data.

#### **What is a Stream?**

A **Stream** is a sequence of elements that can be processed in parallel or sequentially. The Streams API supports **filtering**, **mapping**, **sorting**, **reducing**, and other operations on data.

**Key Operations**:

1. **Intermediate operations**: These operations return a new stream and are lazy (they are only executed when needed).

   * `map()`, `filter()`, `sorted()`, `distinct()`
2. **Terminal operations**: These operations return a result or side-effect (e.g., collecting data or printing values).

   * `collect()`, `forEach()`, `reduce()`, `count()`

**Example**:

```java
List<String> names = Arrays.asList("John", "Jane", "Doe");

names.stream()
     .filter(name -> name.startsWith("J"))
     .forEach(System.out::println);
```

In this example, the `stream()` method converts the list into a stream, the `filter()` method filters names starting with "J", and `forEach()` prints them.

#### **Advantages**:

* Simplifies the handling of collections.
* Provides operations to process large data sets efficiently.
* Allows both sequential and parallel processing with minimal effort.

---

### 4. **Default Methods**

Java 8 introduced **default methods** in interfaces, which allow you to add new methods to interfaces with an implementation, without breaking existing implementations of those interfaces.

#### **What is a Default Method?**

A **default method** is a method in an interface that has a body. It is marked with the `default` keyword, and you can provide a default implementation of the method in the interface.

**Example**:

```java
interface MyInterface {
    default void defaultMethod() {
        System.out.println("This is a default method.");
    }
}
```

In this example, the `defaultMethod()` has an implementation within the interface.

#### **Why is it useful?**

* Allows backward compatibility: You can add new methods to interfaces without breaking existing classes that implement the interface.
* Helps evolve libraries and APIs without breaking the existing codebase.

---

### 5. **Method References**

Method references provide a shorthand for lambda expressions that invoke methods directly. Instead of writing a lambda expression like `(x) -> System.out.println(x)`, you can simply reference the method using `System.out::println`.

#### **What is a Method Reference?**

A **method reference** is a compact, more readable alternative to writing lambda expressions for calling methods.

**Syntax**:

```java
ClassName::methodName
```

**Example**:

```java
List<String> names = Arrays.asList("John", "Jane", "Doe");
names.forEach(System.out::println);  // Using method reference
```

In this example, instead of using a lambda expression `(name) -> System.out.println(name)`, we directly reference the `println()` method.

#### **Types of Method References**:

1. **Reference to a static method**: `ClassName::staticMethod`
2. **Reference to an instance method of a particular object**: `object::instanceMethod`
3. **Reference to an instance method of an arbitrary object**: `ClassName::instanceMethod`
4. **Reference to a constructor**: `ClassName::new`

---

### 6. **Optional Class**

Java 8 introduced the `Optional` class to help developers handle **null values** gracefully and avoid `NullPointerException`. It provides a container for an object that may or may not be `null`.

#### **What is an Optional?**

An `Optional` object contains either a non-null value or `null`. It is used to represent the presence or absence of a value and allows more functional-style handling of `null`.

**Example**:

```java
Optional<String> name = Optional.ofNullable(getName());

if (name.isPresent()) {
    System.out.println(name.get());
} else {
    System.out.println("Name is not available");
}
```

In this example, the `Optional.ofNullable()` method creates an `Optional` that either contains the value returned by `getName()` or is empty if the value is `null`.

#### **Why Use Optional?**

* Reduces the risk of `NullPointerException`.
* Provides better readability and intent when handling potentially null values.
* Supports methods like `ifPresent()`, `orElse()`, and `map()` for more functional-style programming.

---

### 7. **New Date and Time API (`java.time`)**

Java 8 introduced a new, more powerful and flexible **Date and Time API** located in the `java.time` package. This API replaces the older `java.util.Date` and `java.util.Calendar` classes and is more intuitive, thread-safe, and immutable.

#### **What is the java.time API?**

The `java.time` package provides classes for handling dates, times, durations, and time zones. It is much more flexible and easier to work with than the old classes, which were mutable and prone to errors.

Key Classes:

* `LocalDate`: Represents a date without time (e.g., 2023-05-12).
* `LocalTime`: Represents a time without a date (e.g., 10:15 AM).
* `LocalDateTime`: Combines both date and time (e.g., 2023-05-12 10:15 AM).
* `ZonedDateTime`: Represents a date and time with a time zone.
* `Duration`: Represents a duration between two `LocalDateTime` objects.
* `Period`: Represents a period between two `LocalDate` objects.

**Example**:

```java
LocalDate today = LocalDate.now();
System.out.println(today);  // Prints today's date (e.g., 2023-05-12)

LocalDateTime now = LocalDateTime.now();
System.out.println(now);  // Prints date and time (e.g., 2023-05-12T10:15:30)
```

#### **Why is it better?**

* **Immutable** and **thread-safe**.
* Simplifies operations like adding days or calculating the difference between two dates.
* Handles time zones and daylight savings easily with `ZonedDateTime`.
