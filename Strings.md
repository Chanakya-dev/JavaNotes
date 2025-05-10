# **Strings in Java – Beginner-Friendly Detailed Notes**

---

## 🔍 What is a String in Java?

A **String** is a sequence of characters that represents textual data. In Java, **Strings are objects** that are part of the `java.lang` package, and they are widely used to handle text-based data.

### Key Points about Strings:

* **Immutable**: Once a String is created, it cannot be changed.
* **Sequence of Characters**: It can store any sequence of characters, including letters, numbers, symbols, and even spaces.

---

## 📌 Declaring Strings

### 1️⃣ Using String Literal (Preferred)

```java
String greeting = "Hello, Java!";
```

In this example, `"Hello, Java!"` is a **String literal**. Java automatically creates a String object for you.

### 2️⃣ Using the `new` Keyword

```java
String greeting = new String("Hello, Java!");
```

This creates a **new String object** in memory, but it behaves the same as the first method.

---

## 🔑 Important String Properties

* **Length of String**: You can get the number of characters in a string using `.length()`:

  ```java
  String name = "Alice";
  System.out.println(name.length());  // Output: 5
  ```

* **String Indexing**: You can access individual characters using an index (starts from 0).

  ```java
  System.out.println(name.charAt(0));  // Output: A
  ```

---

## 🚀 Common String Methods

### 1️⃣ **Concatenation** – Combine two or more strings

```java
String firstName = "John";
String lastName = "Doe";
String fullName = firstName + " " + lastName;  // Using + operator
System.out.println(fullName);  // Output: John Doe
```

You can also use the `concat()` method:

```java
String fullName = firstName.concat(" ").concat(lastName);
```

### 2️⃣ **Substring** – Extract a portion of the string

```java
String str = "Hello, Java!";
String subStr = str.substring(7);    // Output: Java!
String subStr2 = str.substring(0, 5); // Output: Hello
```

### 3️⃣ **Convert to Uppercase or Lowercase**

```java
String text = "hello";
System.out.println(text.toUpperCase());  // Output: HELLO
System.out.println(text.toLowerCase());  // Output: hello
```

### 4️⃣ **Trim** – Remove leading and trailing spaces

```java
String message = "  Hello World!  ";
System.out.println(message.trim());  // Output: "Hello World!"
```

### 5️⃣ **Replace** – Replace characters or substrings

```java
String sentence = "Java is fun!";
String newSentence = sentence.replace("fun", "awesome");
System.out.println(newSentence);  // Output: Java is awesome!
```

### 6️⃣ **Equals** – Compare two strings

```java
String str1 = "apple";
String str2 = "apple";
String str3 = "orange";

System.out.println(str1.equals(str2));  // Output: true
System.out.println(str1.equals(str3));  // Output: false
```

**Note**: `equals()` compares the actual content of the string, not their memory addresses.

### 7️⃣ **Contains** – Check if a string contains a substring

```java
String phrase = "I love Java programming!";
System.out.println(phrase.contains("Java"));  // Output: true
System.out.println(phrase.contains("Python"));  // Output: false
```

### 8️⃣ **IndexOf** – Find the position of a character or substring

```java
String text = "Hello, World!";
System.out.println(text.indexOf("World"));  // Output: 7
```

### 9️⃣ **Split** – Split a string into an array of substrings

```java
String sentence = "Java is fun";
String[] words = sentence.split(" ");
for (String word : words) {
    System.out.println(word);  // Output: Java, is, fun
}
```

---

## 🌐 StringBuilder vs String

### **String**:

* Immutable: Once a string object is created, its value cannot be modified.
* Example:

  ```java
  String str = "Hello";
  str = str + " World";  // Creates a new String object
  ```

### **StringBuilder**:

* Mutable: You can modify the value of a StringBuilder object without creating new objects each time.
* Ideal for performance when doing string concatenation in loops.

```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World");
System.out.println(sb);  // Output: Hello World
```

---

## 🧠 Real-Life Analogy

> A String is like a **book title** that you can **read** but can't change once it's printed on the cover.

> A StringBuilder, on the other hand, is like a **notebook** where you can keep adding pages, erasing words, and modifying content.

---

## 💡 String Pool in Java (String Interning)

Java maintains a **String Pool** to optimize memory usage. When you create a string literal (e.g., `"Hello"`), Java checks if the string already exists in the pool. If it does, it uses the existing reference; otherwise, it adds the string to the pool.

```java
String str1 = "hello";
String str2 = "hello";
System.out.println(str1 == str2);  // Output: true
```

Both `str1` and `str2` refer to the same object in memory.

---

## ⚠️ Common Mistakes to Avoid

| Mistake                                     | Solution                                                 |
| ------------------------------------------- | -------------------------------------------------------- |
| Trying to modify a String directly          | Use **StringBuilder** or **StringBuffer** for mutability |
| Forgetting `equals()` for string comparison | Always use `.equals()` for comparing string content      |
| Misunderstanding indexing (starts from 0)   | Remember the first index is always 0!                    |

---

## 🧪 Practice Exercises

1. **Count Vowels**: Write a program to count the number of vowels in a string.
2. **Palindrome Check**: Check if a string is a palindrome.
3. **Reverse a String**: Write a program that reverses a string.

---

## 📚 Summary

* **Strings** are immutable objects that represent a sequence of characters.
* You can use methods like `substring()`, `toUpperCase()`, and `replace()` to manipulate strings.
* **StringBuilder** is used for mutable strings when performance matters.
* Java uses a **String Pool** to save memory by reusing string literals.
