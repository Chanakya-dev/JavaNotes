## **Java Basic Notes**

### **1. Features of Java**

#### **1. Simple**

* Java is easy to learn due to its clean and understandable syntax, removing complexities like explicit memory management (as in C/C++).

#### **2. Object-Oriented**

* Java is based on **Object-Oriented Programming** principles:

  * **Encapsulation**: Bundling of data and methods that operate on the data.
  * **Inheritance**: Mechanism where one class inherits the properties and behaviors of another.
  * **Polymorphism**: Ability to process objects differently based on their data type or class.
  * **Abstraction**: Hiding the complexity and showing only the necessary features.

#### **3. Platform-Independent**

* Java follows the **Write Once, Run Anywhere** (WORA) principle, ensuring Java applications can run on any device with a compatible JVM.

#### **4. Secure**

* Java provides security through:

  * **Bytecode Verification**: Ensuring that the bytecode does not violate security rules.
  * **Runtime Security Managers**: Protecting against harmful code.
  * **Sandbox Model**: Restricting the interaction of Java code with the system to prevent malicious behavior.

#### **5. Robust**

* Java's robustness comes from:

  * **Strong Memory Management**: Prevents memory leaks via automatic garbage collection.
  * **Exception Handling**: Java uses try-catch blocks to handle errors effectively.
  * **Type Checking**: Ensures that data types are consistent throughout.

#### **6. Multithreaded**

* Java supports **multithreading**, allowing multiple threads to run simultaneously, optimizing CPU utilization and improving application performance.

#### **7. High Performance**

* Java's performance is optimized with **Just-In-Time (JIT) Compilation**, converting bytecode into machine code during runtime.

#### **8. Distributed Computing**

* Java supports **distributed computing** and makes it easier to develop networked applications.

#### **9. Dynamic**

* Java can dynamically load classes at runtime, enabling flexible and scalable applications.

---

### **2. JDK, JVM, and JRE**

#### **JDK (Java Development Kit)**

* The **JDK** is a software development kit required for developing Java applications. It includes:

  * **JRE** (Java Runtime Environment)
  * **Development Tools**: Compiler, debugger, etc.
  * **Libraries**: Essential packages for application development.

  Developers use the **JDK** to write, compile, and run Java applications.

#### **JVM (Java Virtual Machine)**

* The **JVM** executes **compiled Java bytecode**, ensuring platform independence. Its functions include:

  * Loading bytecode
  * Verifying bytecode integrity
  * Executing bytecode
  * Managing memory (via garbage collection)

#### **JRE (Java Runtime Environment)**

* The **JRE** allows users to run Java applications. It includes:

  * **JVM**: To run bytecode
  * **Libraries**: Provides essential classes and packages.

  The **JRE** does not include development tools like the compiler or debugger.

#### **Relationship Between JDK, JRE, and JVM**

* **JDK** = **JRE + Development Tools**
* **JRE** = **JVM + Libraries**
* **JVM** = Executes bytecode.

---

### **3. Class and Main Method Structure**

#### **Class**

* A class in Java defines properties (fields) and behaviors (methods). It's a blueprint for creating objects.
* Example:

  ```java
  public class HelloWorld {
      public static void main(String[] args) {
          System.out.println("Hello, World!");
      }
  }
  ```
* **Class**: Defined with the `class` keyword.
* **Method**: A function inside the class that defines its behavior.
* **Main Method**: Entry point of a Java program.

#### **Main Method**

* The main method has a specific structure to kick-start the program:

  ```java
  public static void main(String[] args) {
      // Code to be executed
  }
  ```

  * **public**: Access modifier that allows the method to be called from outside the class.
  * **static**: Allows the method to be called without creating an instance of the class.
  * **void**: Specifies no return value.
  * **main**: Name that Java looks for to begin execution.
  * **String\[] args**: Accepts command-line arguments.

---

### **Summary of Java Core Concepts**

* Java is a **simple**, **object-oriented**, **platform-independent**, and **secure** programming language with **robust** features.
* **JDK** is used for development, **JRE** is for running Java applications, and **JVM** executes bytecode, ensuring platform independence.
* The **main method** serves as the entry point for Java applications and follows a specific structure.

---
