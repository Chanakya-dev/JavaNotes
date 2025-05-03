

### 1 **Features of Java**

#### **1. Simple**

* Java is simple to learn because it has a clean and easy-to-understand syntax. It removes complexity, such as explicit memory management (unlike C/C++).

#### **2. Object-Oriented**

* Java follows Object-Oriented Programming principles, such as **Encapsulation**, **Inheritance**, **Polymorphism**, and **Abstraction**.

#### **3. Platform-Independent**

* The "Write Once, Run Anywhere" (WORA) concept ensures that Java code can be executed on any device with a compatible JVM.

#### **4. Secure**

* Java provides a secure environment for developing applications by ensuring safe code execution through features like bytecode verification, runtime security managers, and the sandbox model.

#### **5. Robust**

* Java is a robust language due to its strong memory management, exception handling, and type-checking mechanisms.
* **Automatic Garbage Collection**: Java automatically handles memory allocation and deallocation to avoid memory leaks.

#### **6. Multithreaded**

* Java supports multithreading, allowing multiple threads to run simultaneously, improving the efficiency of applications.

#### **7. High Performance**

* Java offers high performance through the use of Just-In-Time (JIT) compilation, which compiles bytecode into machine code at runtime.

#### **8. Distributed Computing**

* Java has built-in support for distributed computing, making it easier to develop networked applications.

#### **9. Dynamic**

* Java supports dynamic class loading, which means that it can load classes during runtime.
* This flexibility helps with networked applications and user-based behavior modifications.


---

### 2 **JDK, JVM, and JRE**

#### **JDK (Java Development Kit)**

* The **JDK** is a software development kit used to develop Java applications.
* It includes:

  * **JRE** (Java Runtime Environment)
  * Development tools (compiler, debugger, etc.)
  * Libraries and documentation
* The **JDK** is used by developers to write, compile, and run Java applications.

#### **JVM (Java Virtual Machine)**

* The **JVM** is responsible for running Java bytecode (compiled Java code).
* It is platform-independent, which allows Java to be a **Write Once, Run Anywhere** language.
* The JVM performs several tasks, including:

  * Loading bytecode
  * Verifying bytecode
  * Executing bytecode
  * Providing memory management (Garbage Collection)

#### **JRE (Java Runtime Environment)**

* The **JRE** provides the libraries, Java Virtual Machine, and other components to run Java applications.
* It **does not** include development tools like the compiler and debugger.
* The JRE is used by end-users to run Java programs on their machines.

#### **Relationship Between JDK, JRE, and JVM**

* **JDK** = **JRE + Development Tools (compiler, debugger, etc.)**
* **JRE** = **JVM + Libraries**
* **JVM** = Executes bytecode on the machine.

---

### 3 **Class and Main Method Structure**

#### **Class**

* A class is a **blueprint** for creating objects in Java. It defines the properties (fields) and behaviors (methods) that objects of the class can have.
* Example:

  ```java
  public class HelloWorld {
      public static void main(String[] args) {
          System.out.println("Hello, World!");
      }
  }
  ```
* **Class**: The keyword used to define a class in Java. A class can contain variables, methods, constructors, etc.
* **Methods**: Functions defined within a class.
* **Main Method**: This is the entry point of any Java program. It's where the execution of the program starts.

#### **Main Method**

* The main method has a specific structure and syntax in Java:

  ```java
  public static void main(String[] args) {
      // Code to be executed
  }
  ```
* **public**: Access modifier that allows the method to be called from outside the class.
* **static**: Means the method can be called without creating an instance of the class.
* **void**: Specifies that the method doesn't return any value.
* **main**: Name of the method that Java looks for to begin execution.
* **String\[] args**: Parameter to accept command-line arguments.

---
