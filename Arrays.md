# 🧮 Arrays in Java – Beginner-Friendly Detailed Notes

---

## 🔍 What is an Array?

An **array** is a **collection of similar data types** stored in **contiguous memory locations**.

> You can think of an array like a **row of mailboxes**, each one storing a value and each having an address (index).

---

### 📦 Why Use Arrays?

Without arrays:

```java
int a1 = 10;
int a2 = 20;
int a3 = 30;
```

With arrays:

```java
int[] arr = {10, 20, 30};
```

✅ Arrays help you:

* Store multiple items
* Access them easily using an index
* Process data using loops

---

## 📌 Key Characteristics

| Feature          | Description                             |
| ---------------- | --------------------------------------- |
| Fixed Size       | Size is defined at the time of creation |
| Indexed          | Starts from index **0**                 |
| Homogeneous      | Stores **same data type** elements      |
| Memory Efficient | Continuous memory allocation            |

---

## 🔨 Declaration and Initialization

### 1️⃣ Declare an Array (but not initialize)

```java
int[] arr;        // preferred syntax
// OR
int arr[];        // also valid
```

### 2️⃣ Create Array with `new` keyword

```java
arr = new int[5];   // allocates space for 5 integers
```

### 3️⃣ Assign values

```java
arr[0] = 10;
arr[1] = 20;
// and so on...
```

### ✅ Combined Declaration and Initialization

```java
int[] arr = {10, 20, 30, 40, 50};
```

---

## 🧾 Accessing Elements

Use the index to read or write values.

```java
System.out.println(arr[2]);  // Output: 30
arr[4] = 100;                // Update value at index 4
```

⛔️ If you access out of bounds:

```java
System.out.println(arr[10]); // Error: ArrayIndexOutOfBoundsException
```

---

## 🔁 Iterating Through Arrays

### ➤ Using `for` Loop

```java
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

### ➤ Using `for-each` Loop (Enhanced for Loop)

```java
for (int num : arr) {
    System.out.println(num);
}
```

---

## 🔢 Array Length

```java
System.out.println(arr.length);  // gives total size of array
```

---

## 🧪 Example Program

```java
public class ArrayDemo {
    public static void main(String[] args) {
        int[] numbers = {5, 10, 15, 20, 25};
        
        // Print all elements
        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Element at index " + i + ": " + numbers[i]);
        }

        // Find sum of elements
        int sum = 0;
        for (int num : numbers) {
            sum += num;
        }
        System.out.println("Sum = " + sum);
    }
}
```

---

## 🧠 Real-Life Analogy

> Think of an array like a **train** with compartments.
> Each compartment (index) can hold **one passenger (data)** of the **same type**.

---

## 📚 Types of Arrays

### 1️⃣ **One-Dimensional Array**

```java
int[] marks = {50, 60, 70};
```

### 2️⃣ **Two-Dimensional Array (Matrix)**

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6}
};

System.out.println(matrix[1][2]); // Output: 6
```

---

## 🔍 Common Mistakes to Avoid

| Mistake                              | Correct Usage                          |
| ------------------------------------ | -------------------------------------- |
| Accessing beyond array length        | Use `arr.length` to stay within bounds |
| Forgetting `new` when declaring size | `arr = new int[5];`                    |
| Mixing data types                    | All elements must be same data type    |

---

## ✅ Summary

* Arrays are fixed-size, same-type, indexed collections.
* Use `for` or `for-each` loops to iterate.
* `length` property helps prevent index errors.
* Ideal when you want to store and process multiple values efficiently.

---

## 🧪 Want to Try?

1. Create an array of 5 names and print them.
2. Find the **maximum** number from an array of integers.
