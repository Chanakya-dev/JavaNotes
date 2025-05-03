
### 1. **Data Types in Java**

Java has two main categories of data types: **Primitive Data Types** and **Reference Data Types**.

#### **Primitive Data Types**

These are the most basic data types that are predefined in Java. They are not objects, and each variable holds a value directly.

1. **byte**

   * Size: 1 byte
   * Range: -128 to 127
   * Example: `byte a = 100;`

2. **short**

   * Size: 2 bytes
   * Range: -32,768 to 32,767
   * Example: `short b = 15000;`

3. **int**

   * Size: 4 bytes
   * Range: -2^31 to 2^31-1 (−2,147,483,648 to 2,147,483,647)
   * Example: `int c = 200000;`

4. **long**

   * Size: 8 bytes
   * Range: -2^63 to 2^63-1
   * Example: `long d = 5000000000L;`
     *Note: Always append `L` to the value for long.*

5. **float**

   * Size: 4 bytes
   * Range: ±3.40282347E+38F (6-7 significant decimal digits)
   * Example: `float e = 5.75f;`
     *Note: Always append `f` to the value for float.*

6. **double**

   * Size: 8 bytes
   * Range: ±1.7976931348623157E+308 (15 significant decimal digits)
   * Example: `double f = 3.14159;`

7. **char**

   * Size: 2 bytes
   * Represents a single 16-bit Unicode character.
   * Example: `char g = 'A';`

8. **boolean**

   * Size: 1 bit
   * Values: `true` or `false`
   * Example: `boolean h = true;`

#### **Reference Data Types**

These refer to objects and arrays in Java. The variable stores the reference (address) to the object, not the actual value.

* **String**: A sequence of characters. It is not a primitive type, but it is widely used.

  * Example: `String name = "Java";`
* **Arrays**: A collection of data elements of the same type.

  * Example: `int[] arr = {1, 2, 3};`

### 2. **Variables in Java**

A **variable** in Java is a container for storing data values. Each variable must be declared with a data type.

#### **Declaration of Variables**

Variables are declared by specifying a data type followed by the variable name.

Example:

```java
int age = 25;
String name = "John";
```

#### **Types of Variables**

1. **Local Variables**: Declared inside a method, constructor, or block. They are not accessible outside.

   * Example:

     ```java
     public void display() {
         int x = 10; // Local variable
     }
     ```

2. **Instance Variables**: Declared inside a class but outside any method. They are used to store the state of an object.

   * Example:

     ```java
     class Car {
         String color; // Instance variable
     }
     ```

3. **Class Variables (Static Variables)**: Declared with the `static` keyword, they are shared by all instances of a class.

   * Example:

     ```java
     class Car {
         static int wheels = 4; // Static variable
     }
     ```

#### **Variable Initialization**

Variables can be initialized at the time of declaration, or they can be assigned a value later in the program. Uninitialized variables in Java cannot be used.

### 3. **Constants**

Java allows you to define **constants** using the `final` keyword. Constants are variables that cannot be reassigned after they are initialized.

Example:

```java
final int MAX_VALUE = 100;
```

### 4. **Type Casting**

Java supports both **implicit** (automatic) and **explicit** (manual) type casting.

* **Implicit Casting (Widening)**: Happens automatically when a smaller type is assigned to a larger type.

  * Example: `int a = 5; double b = a;`

* **Explicit Casting (Narrowing)**: Requires the use of the cast operator to convert a larger type to a smaller type.

  * Example: `double a = 5.5; int b = (int) a;`

### 5. **Type Promotion in Expressions**

In Java, when you perform operations on variables, the result is promoted to the higher data type.

Example:

```java
int a = 5;
float b = 2.0f;
float result = a + b; // result will be a float
```

### 6. **Null and Reference Types**

* **Null** is a special value in Java used to indicate that an object reference does not point to any object. Primitive data types cannot be `null`.
* Example:

  ```java
  String str = null;
  ```
