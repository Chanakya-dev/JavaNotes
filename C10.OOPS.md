# OOPS of JAVA

## **1. Inheritance in Java**

**Inheritance** is a mechanism in Java where one class inherits the fields and methods of another class. It allows for code reusability and method overriding.

### **Key Concepts of Inheritance**:

* **Super Class (Parent Class)**: The class whose properties and behaviors are inherited.
* **Sub Class (Child Class)**: The class that inherits the properties and behaviors from the super class.

### **Types of Inheritance in Java**:

1. **Single Inheritance**: A subclass inherits from one superclass.

   * Example:

   ```java
   class Animal {
       void eat() {
           System.out.println("Eating...");
       }
   }

   class Dog extends Animal {
       void bark() {
           System.out.println("Barking...");
       }
   }
   ```

2. **Multilevel Inheritance**: A subclass becomes the superclass for another class.

   * Example:

   ```java
   class Animal {
       void eat() {
           System.out.println("Eating...");
       }
   }

   class Dog extends Animal {
       void bark() {
           System.out.println("Barking...");
       }
   }

   class Puppy extends Dog {
       void play() {
           System.out.println("Playing...");
       }
   }
   ```

3. **Hierarchical Inheritance**: Multiple classes inherit from a single superclass.

   * Example:

   ```java
   class Animal {
       void eat() {
           System.out.println("Eating...");
       }
   }

   class Dog extends Animal {
       void bark() {
           System.out.println("Barking...");
       }
   }

   class Cat extends Animal {
       void meow() {
           System.out.println("Meowing...");
       }
   }
   ```

4. **Interface Inheritance** (via interfaces): A class can inherit behaviors from one or more interfaces.

   * Example:

   ```java
   interface Animal {
       void eat();
   }

   class Dog implements Animal {
       public void eat() {
           System.out.println("Dog is eating...");
       }
   }
   ```

### **Accessing Inherited Members**:

* A subclass can access public and protected members of the superclass but not private members.

### **Constructor in Inheritance**:

* Constructors are not inherited, but a subclass constructor can call the superclass constructor using `super()`.

---

## **2. Polymorphism in Java**

**Polymorphism** allows objects of different classes to be treated as objects of a common superclass. The most common use of polymorphism is when a parent class reference is used to refer to a child class object.

### **Types of Polymorphism**:

1. **Compile-time Polymorphism (Static Polymorphism)**: Occurs when method overloading or operator overloading is used. It is resolved at compile time.

   * **Method Overloading**: Multiple methods in the same class with the same name but different parameters.
   * Example:

   ```java
   class Calculator {
       int add(int a, int b) {
           return a + b;
       }

       double add(double a, double b) {
           return a + b;
       }
   }
   ```

2. **Runtime Polymorphism (Dynamic Polymorphism)**: Occurs when a method in a subclass overrides a method in a superclass. The method call is resolved at runtime.

   * **Method Overriding**: Subclass provides its own implementation for a method defined in the superclass.
   * Example:

   ```java
   class Animal {
       void sound() {
           System.out.println("Animal makes a sound");
       }
   }

   class Dog extends Animal {
       void sound() {
           System.out.println("Dog barks");
       }
   }

   public class Main {
       public static void main(String[] args) {
           Animal myDog = new Dog();  // Parent class reference, child class object
           myDog.sound();  // Output: Dog barks
       }
   }
   ```

### **Method Overloading vs Method Overriding**:

* **Overloading** is when multiple methods with the same name are in the same class, differing in parameter types.
* **Overriding** is when a subclass redefines a method from its superclass.

---

## **3. Abstraction in Java**

**Abstraction** is the concept of hiding the complex implementation details and showing only the necessary features of an object. It helps in reducing complexity by providing a simple interface.

### **Achieving Abstraction**:

1. **Abstract Class**: A class that cannot be instantiated directly but can be subclassed. It can have both abstract methods (without body) and concrete methods (with body).

   * **Syntax**:

     ```java
     abstract class Animal {
         abstract void sound();  // Abstract method

         void sleep() {
             System.out.println("Sleeping...");
         }
     }

     class Dog extends Animal {
         void sound() {
             System.out.println("Barks");
         }
     }
     ```

2. **Interface**: A collection of abstract methods that can be implemented by classes. An interface cannot contain method implementations (until Java 8 where default methods are allowed).

   * **Syntax**:

     ```java
     interface Animal {
         void sound();  // Abstract method
     }

     class Dog implements Animal {
         public void sound() {
             System.out.println("Barks");
         }
     }
     ```

### **Key Points**:

* An **abstract class** can have both abstract and non-abstract methods.
* An **interface** can only have abstract methods (with some exceptions in Java 8+).

---

## **4. Encapsulation in Java**

**Encapsulation** is the technique of bundling data (variables) and methods that operate on the data into a single unit, a class. It also hides the internal object details using access modifiers.

### **Key Concepts of Encapsulation**:

* **Private variables** are hidden from outside access.
* Public **getter** and **setter** methods are used to access and modify private variables.

### **Example**:

```java
class Account {
    private double balance;

    // Getter method to access private variable
    public double getBalance() {
        return balance;
    }

    // Setter method to modify private variable
    public void setBalance(double balance) {
        if(balance >= 0) {
            this.balance = balance;
        } else {
            System.out.println("Invalid balance");
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Account myAccount = new Account();
        myAccount.setBalance(1000.0);  // Using setter method to set balance
        System.out.println("Balance: " + myAccount.getBalance());  // Using getter method to access balance
    }
}
```

### **Benefits of Encapsulation**:

* Protects the integrity of the data by preventing direct access and modification.
* Provides flexibility to change the implementation without affecting other parts of the program.

---

## **Summary of OOP Concepts in Java**

### **Inheritance**:

* **Single Inheritance**: One class inherits from one superclass.
* **Multilevel Inheritance**: A class inherits from a subclass, forming a hierarchy.
* **Hierarchical Inheritance**: Multiple subclasses inherit from a single superclass.
* **Interface Inheritance**: A class can inherit from multiple interfaces.

### **Polymorphism**:

* **Compile-time Polymorphism**: Achieved through method overloading.
* **Runtime Polymorphism**: Achieved through method overriding.

### **Abstraction**:

* **Abstract Class**: Can contain both abstract and non-abstract methods.
* **Interface**: Contains only abstract methods (with some exceptions).

### **Encapsulation**:

* Hides the internal state of an object using private fields and provides public getter and setter methods.
