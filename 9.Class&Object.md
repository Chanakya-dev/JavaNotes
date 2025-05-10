# Classes and Objects

## **1. What is a Class in Java?**

A **class** in Java is a blueprint or template for creating objects. It defines the properties (fields) and behaviors (methods) that the objects created from it will have.

* **Properties**: Also known as fields or attributes, these define the state of an object.
* **Methods**: These define the actions or behaviors that objects can perform.

### **Syntax to Define a Class**:

```java
class ClassName {
    // Fields (Attributes)
    dataType fieldName;

    // Constructor
    public ClassName() {
        // Initialization code
    }

    // Methods (Behaviors)
    returnType methodName() {
        // Code for method
    }
}
```

### **Example**:

```java
class Car {
    String model;
    int year;

    // Method to start the car
    void start() {
        System.out.println("The car is starting.");
    }
}
```

---

## **2. What is an Object in Java?**

An **object** is an instance of a class. It represents a real-world entity with both **state (attributes)** and **behavior (methods)**. When you create an object of a class, you essentially instantiate that class.

### **Creating an Object**:

To create an object, you use the `new` keyword followed by the constructor of the class.

#### **Syntax**:

```java
ClassName objectName = new ClassName();
```

### **Example**:

```java
public class Main {
    public static void main(String[] args) {
        Car myCar = new Car();  // Object creation
        myCar.start();  // Calling method on the object
    }
}
```

### **Explanation**:

* `Car myCar = new Car();`: This creates an object `myCar` of class `Car` using the constructor.
* `myCar.start();`: This calls the `start()` method of the `myCar` object.

---

## **3. Constructor in Java**

A **constructor** is a special method in a class that is used to initialize objects. It is called when an object is created. The constructor has the same name as the class and does not have a return type.

### **Types of Constructors**:

1. **Default Constructor**:
   If no constructor is explicitly defined, Java provides a default constructor, which initializes the object with default values.

2. **Parameterized Constructor**:
   A constructor that takes parameters to initialize an object with specific values.

#### **Example**:

```java
class Car {
    String model;
    int year;

    // Default Constructor
    public Car() {
        model = "Unknown";
        year = 2020;
    }

    // Parameterized Constructor
    public Car(String model, int year) {
        this.model = model;
        this.year = year;
    }

    // Method
    void display() {
        System.out.println("Model: " + model);
        System.out.println("Year: " + year);
    }
}

public class Main {
    public static void main(String[] args) {
        // Using Default Constructor
        Car car1 = new Car();
        car1.display();

        // Using Parameterized Constructor
        Car car2 = new Car("Tesla", 2022);
        car2.display();
    }
}
```

### **Output**:

```
Model: Unknown
Year: 2020
Model: Tesla
Year: 2022
```

---

## **4. Methods in Java**

Methods define the behaviors of a class. They are used to perform operations on the object's attributes or perform some actions.

* A **method** is called on an object to perform an action.
* A method can either return a value or be **void** (without a return type).

### **Method Syntax**:

```java
returnType methodName(parameters) {
    // Method body
}
```

#### **Example**:

```java
class Car {
    String model;
    int year;

    void start() {
        System.out.println("The car is starting.");
    }

    void stop() {
        System.out.println("The car is stopping.");
    }
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car();
        myCar.start();
        myCar.stop();
    }
}
```

---

## **5. Access Modifiers in Java**

Access modifiers are used to define the scope and visibility of class members (fields and methods). Java provides four access modifiers:

1. **public**: Accessible from anywhere.
2. **private**: Accessible only within the same class.
3. **protected**: Accessible within the same package and subclasses.
4. **default** (no modifier): Accessible only within the same package.

#### **Example**:

```java
class Person {
    private String name;  // private field

    public void setName(String name) {  // public method
        this.name = name;
    }

    public String getName() {  // public method
        return name;
    }
}

public class Main {
    public static void main(String[] args) {
        Person person = new Person();
        person.setName("John");  // Accessing public method
        System.out.println(person.getName());  // Accessing public method
    }
}
```

---

## **6. Flow of Execution in Java**

The flow of execution starts when the program starts, and the following happens:

1. **Object Creation**:

   * The `new` keyword creates a new object and calls the constructor to initialize it.

2. **Constructor Call**:

   * The constructor initializes the object's attributes.

3. **Method Call**:

   * After the object is created, methods are invoked on the object. These methods perform actions on the object's data or produce outputs.

#### **Example**:

```java
class Calculator {
    // Method to add two numbers
    int add(int a, int b) {
        return a + b;
    }

    // Method to display a message
    void displayMessage() {
        System.out.println("This is a calculator.");
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();  // Step 1: Create object
        int result = calc.add(5, 10);  // Step 2: Call method to add numbers
        System.out.println("Result: " + result);  // Output the result
        calc.displayMessage();  // Call another method
    }
}
```

### **Flow Breakdown**:

1. **Object Creation**: `Calculator calc = new Calculator();`

   * The `Calculator` constructor is called.
2. **Method Call**: `calc.add(5, 10);`

   * The `add()` method is executed and returns the sum of 5 and 10.
3. **Method Call**: `calc.displayMessage();`

   * The `displayMessage()` method prints a message.

---

## **7. Relationship between Classes and Objects**

* A **class** defines the structure and behavior of objects.
* An **object** is an instance of a class. It has state (attributes) and behavior (methods).
* When an object is created, it is initialized via the **constructor** and then used to call methods.

#### **Class vs Object**:

* **Class**: Template or blueprint.
* **Object**: Real-world instance of a class.

---

## **Summary:**

* **Class**: A blueprint for creating objects. It defines the properties (fields) and behaviors (methods) of the objects.
* **Object**: An instance of a class. Objects represent real-world entities and have both state and behavior.
* **Constructor**: A special method to initialize an object when it is created.
* **Methods**: Functions that define the actions or behaviors of the object.
* **Access Modifiers**: Determine the visibility of class members.
* **Flow**: The execution starts with creating an object, calling the constructor, and then invoking methods on the object to perform actions.

