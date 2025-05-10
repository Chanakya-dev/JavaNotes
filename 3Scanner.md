## **Scanner Class in Java**

The **Scanner class** in Java is part of the `java.util` package and is used to obtain the input of primitive types (like `int`, `double`, etc.) and strings. It is primarily used for reading input from the user, files, or other input sources like streams. It provides methods to read different data types from input sources.

---

### **Basic Structure of Scanner Class**:

```java
import java.util.Scanner;

public class ScannerExample {
    public static void main(String[] args) {
        // Create Scanner object
        Scanner scanner = new Scanner(System.in);

        // Using methods to read input
        System.out.print("Enter your name: ");
        String name = scanner.nextLine();

        System.out.println("Hello, " + name + "!");
        
        scanner.close();  // Close the scanner after use
    }
}
```

---

### **Important Methods of Scanner Class**:

Here are some commonly used methods of the `Scanner` class for reading various types of input:

1. **next()**:

   * Reads the next token (word) from the input as a string.
   * It only reads input until it encounters whitespace.

   **Example**:

   ```java
   Scanner sc = new Scanner(System.in);
   System.out.print("Enter your first name: ");
   String firstName = sc.next();  // Reads a single word
   System.out.println("First Name: " + firstName);
   ```

2. **nextLine()**:

   * Reads an entire line of text (including spaces) from the input.

   **Example**:

   ```java
   Scanner sc = new Scanner(System.in);
   System.out.print("Enter your full name: ");
   String fullName = sc.nextLine();  // Reads the full line with spaces
   System.out.println("Full Name: " + fullName);
   ```

3. **nextInt()**:

   * Reads the next integer from the input.
   * If the user does not enter a valid integer, it throws `InputMismatchException`.

   **Example**:

   ```java
   Scanner sc = new Scanner(System.in);
   System.out.print("Enter your age: ");
   int age = sc.nextInt();  // Reads an integer value
   System.out.println("Age: " + age);
   ```

4. **nextDouble()**:

   * Reads the next floating-point number from the input.
   * Throws `InputMismatchException` if the input is not a valid double.

   **Example**:

   ```java
   Scanner sc = new Scanner(System.in);
   System.out.print("Enter your height: ");
   double height = sc.nextDouble();  // Reads a double value
   System.out.println("Height: " + height);
   ```

5. **nextBoolean()**:

   * Reads the next boolean value from the input (`true` or `false`).

   **Example**:

   ```java
   Scanner sc = new Scanner(System.in);
   System.out.print("Are you a student? (true/false): ");
   boolean isStudent = sc.nextBoolean();  // Reads a boolean value
   System.out.println("Is Student: " + isStudent);
   ```

6. **nextLine() (After nextInt() or nextDouble())**:

   * When you use methods like `nextInt()`, `nextDouble()`, they do not consume the newline character `\n` left after reading the input. So if you follow a `nextInt()` with a `nextLine()`, it will read the newline character as the input.
   * To handle this, you can call `nextLine()` after reading integers or floating-point numbers to consume the leftover newline character.

   **Example**:

   ```java
   Scanner sc = new Scanner(System.in);
   System.out.print("Enter your age: ");
   int age = sc.nextInt();  // Reads integer
   sc.nextLine();  // Consumes the newline character

   System.out.print("Enter your full name: ");
   String name = sc.nextLine();  // Reads the full line without issues
   ```

---

### **Commonly Used Methods for Other Input Operations**:

1. **hasNext()**:

   * Returns `true` if the scanner has another token in the input stream.
   * Useful for checking if input is available.

   **Example**:

   ```java
   Scanner sc = new Scanner(System.in);
   while(sc.hasNext()) {
       String word = sc.next();
       System.out.println(word);
   }
   ```

2. **hasNextInt()**:

   * Returns `true` if the next token can be interpreted as an `int`.

   **Example**:

   ```java
   Scanner sc = new Scanner(System.in);
   if(sc.hasNextInt()) {
       int num = sc.nextInt();
       System.out.println("You entered: " + num);
   } else {
       System.out.println("That's not a valid integer.");
   }
   ```

3. **skip()**:

   * Skips over the next input token based on the provided regular expression.

   **Example**:

   ```java
   Scanner sc = new Scanner(System.in);
   System.out.print("Enter some text: ");
   sc.skip("\\s*");  // Skips any leading whitespace
   String text = sc.nextLine();
   System.out.println("You entered: " + text);
   ```

---

### **Scanner Class in File Handling**:

You can also use the `Scanner` class to read input from files. Here’s an example of reading data from a file:

```java
import java.util.Scanner;
import java.io.File;
import java.io.FileNotFoundException;

public class FileScannerExample {
    public static void main(String[] args) {
        try {
            File file = new File("example.txt"); // Open file
            Scanner sc = new Scanner(file); // Create Scanner object for the file

            // Read and print the content of the file line by line
            while (sc.hasNextLine()) {
                String line = sc.nextLine();
                System.out.println(line);
            }

            sc.close();  // Close the scanner after reading the file
        } catch (FileNotFoundException e) {
            System.out.println("File not found.");
        }
    }
}
```

---

### **Advantages of Using Scanner Class**:

* **Simplifies Input**: It simplifies reading input as compared to older methods like `BufferedReader` and `InputStreamReader`.
* **Flexible**: It can read different types of data (strings, integers, booleans, etc.).
* **File Input**: Can be used to read from files easily.
* **Exception Handling**: Provides a good mechanism to handle invalid input with appropriate methods like `hasNext()`, `hasNextInt()`, etc.

---

### **Closing the Scanner Object**:

It is a good practice to close the `Scanner` object after you're done using it. This can be done using the `close()` method:

```java
scanner.close();
```

This ensures that resources associated with the scanner are released, especially when reading from files or streams.

---

### **Summary**:

The **Scanner class** in Java is an essential tool for reading input from various sources like the console, files, or other input streams. It provides an easy way to work with different data types and comes with methods for parsing input data, validating it, and managing file I/O operations efficiently.
