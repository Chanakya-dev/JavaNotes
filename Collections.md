# **Java Collections Framework**

The **Java Collections Framework** is a set of classes and interfaces that implement various types of collections, such as lists, sets, maps, and queues. It provides a way to store and manipulate data efficiently. The **java.util** package contains all the collection classes.

---

## **1. Collection Interfaces**

There are several interfaces in the Java Collections Framework, each representing a different type of collection.

### **Common Collection Interfaces**:

1. **Collection**: The root interface of the collection hierarchy. It is the parent of other collection interfaces like List, Set, and Queue.

   * **Methods**: add(), remove(), clear(), size(), contains(), etc.
   * **Example**: `Collection<Integer> numbers = new ArrayList<>();`

2. **List**: Extends the **Collection** interface. Represents an ordered collection of elements that allows duplicates.

   * **Example**: `List<String> fruits = new ArrayList<>();`
   * **Popular Implementations**: **ArrayList**, **LinkedList**, **Vector**.

3. **Set**: Extends the **Collection** interface. Represents a collection that does not allow duplicates and does not guarantee any specific order of elements.

   * **Example**: `Set<String> uniqueFruits = new HashSet<>();`
   * **Popular Implementations**: **HashSet**, **LinkedHashSet**, **TreeSet**.

4. **Queue**: Extends **Collection** and represents a collection designed for holding elements prior to processing. Typically, queues are used in scenarios like task scheduling and thread management.

   * **Example**: `Queue<String> queue = new LinkedList<>();`
   * **Popular Implementations**: **PriorityQueue**, **LinkedList**, **ArrayDeque**.

5. **Deque**: Extends **Queue** and represents a double-ended queue, which allows elements to be added or removed from both ends.

   * **Example**: `Deque<Integer> deque = new ArrayDeque<>();`

6. **Map**: Does not extend **Collection** but is part of the Java Collections Framework. Represents key-value pairs, where each key is mapped to a specific value. Maps do not allow duplicate keys.

   * **Example**: `Map<String, Integer> map = new HashMap<>();`
   * **Popular Implementations**: **HashMap**, **TreeMap**, **LinkedHashMap**.

---

## **2. Commonly Used Collections**

### **ArrayList** (Implements List):

* **Description**: The **ArrayList** class provides a growable array of elements. It allows duplicate elements and maintains the order in which elements are inserted.

* **Example**:

  ```java
  ArrayList<String> fruits = new ArrayList<>();
  fruits.add("Apple");
  fruits.add("Banana");
  fruits.add("Orange");
  System.out.println(fruits);  // Output: [Apple, Banana, Orange]
  ```

* **Advantages**:

  * Fast access for reading (constant time for get() and set()).
  * Dynamic resizing (grows automatically when full).

* **Disadvantages**:

  * Slow for insertions and deletions in the middle (shifts elements).

### **LinkedList** (Implements List and Queue):

* **Description**: A **LinkedList** stores elements in nodes, where each node contains the data and a reference to the next node. It allows insertions and deletions at both ends with constant time.

* **Example**:

  ```java
  LinkedList<String> fruits = new LinkedList<>();
  fruits.add("Apple");
  fruits.addFirst("Banana");
  fruits.addLast("Orange");
  System.out.println(fruits);  // Output: [Banana, Apple, Orange]
  ```

* **Advantages**:

  * Efficient for frequent insertions and deletions at the ends.

* **Disadvantages**:

  * Slower access to elements compared to **ArrayList**.

### **HashSet** (Implements Set):

* **Description**: The **HashSet** class implements the **Set** interface and uses a hash table for storage. It does not allow duplicate elements and does not guarantee any specific order.

* **Example**:

  ```java
  HashSet<String> fruits = new HashSet<>();
  fruits.add("Apple");
  fruits.add("Banana");
  fruits.add("Apple");  // Duplicate, will not be added
  System.out.println(fruits);  // Output: [Apple, Banana]
  ```

* **Advantages**:

  * Fast operations like add(), remove(), and contains() (average constant time complexity).

* **Disadvantages**:

  * No order guarantees.

### **TreeSet** (Implements Set):

* **Description**: A **TreeSet** is a **Set** that stores its elements in a sorted tree structure (usually a **Red-Black Tree**). It does not allow duplicates and keeps elements in ascending order.

* **Example**:

  ```java
  TreeSet<String> fruits = new TreeSet<>();
  fruits.add("Apple");
  fruits.add("Banana");
  fruits.add("Orange");
  System.out.println(fruits);  // Output: [Apple, Banana, Orange]
  ```

* **Advantages**:

  * Automatically sorts elements.

* **Disadvantages**:

  * Slightly slower than **HashSet** due to sorting.

### **HashMap** (Implements Map):

* **Description**: **HashMap** stores key-value pairs. It allows **null** values and the **null** key. It does not guarantee any specific order of elements.

* **Example**:

  ```java
  HashMap<String, Integer> map = new HashMap<>();
  map.put("Apple", 1);
  map.put("Banana", 2);
  map.put("Orange", 3);
  System.out.println(map);  // Output: {Apple=1, Banana=2, Orange=3}
  ```

* **Advantages**:

  * Provides constant time complexity for basic operations (insert, search, delete).

* **Disadvantages**:

  * No order guarantees (unordered keys).

### **TreeMap** (Implements Map):

* **Description**: **TreeMap** stores key-value pairs and keeps the keys in sorted order according to their natural ordering or by a comparator provided at the time of creation.

* **Example**:

  ```java
  TreeMap<String, Integer> map = new TreeMap<>();
  map.put("Apple", 1);
  map.put("Banana", 2);
  map.put("Orange", 3);
  System.out.println(map);  // Output: {Apple=1, Banana=2, Orange=3}
  ```

* **Advantages**:

  * Automatically sorts keys.

* **Disadvantages**:

  * Slower than **HashMap** for non-sorted operations.

---

## **3. Collection Methods**

Here are some important methods that are common to **Collection**, **List**, **Set**, and **Map**:

### **For Collection Interface**:

* `add(E e)`: Adds the element to the collection.
* `remove(Object o)`: Removes the specified element from the collection.
* `contains(Object o)`: Checks if the collection contains the specified element.
* `size()`: Returns the number of elements in the collection.
* `clear()`: Removes all elements from the collection.

### **For List Interface**:

* `add(int index, E element)`: Inserts the specified element at the specified position.
* `get(int index)`: Retrieves the element at the specified position.
* `set(int index, E element)`: Replaces the element at the specified position.
* `remove(int index)`: Removes the element at the specified position.

### **For Map Interface**:

* `put(K key, V value)`: Inserts a key-value pair into the map.
* `get(Object key)`: Retrieves the value for the specified key.
* `containsKey(Object key)`: Checks if the map contains the specified key.
* `remove(Object key)`: Removes the key-value pair associated with the specified key.

---

## **4. Iterating Over Collections**

You can iterate over **Collections** using several methods:

1. **Using an Iterator**:

   * Example:

     ```java
     Iterator<String> iterator = fruits.iterator();
     while (iterator.hasNext()) {
         System.out.println(iterator.next());
     }
     ```

2. **Using a for-each loop**:

   * Example:

     ```java
     for (String fruit : fruits) {
         System.out.println(fruit);
     }
     ```

3. **Using Streams** (Java 8 and above):

   * Example:

     ```java
     fruits.stream().forEach(System.out::println);
     ```

---

## **5. Java Collections Framework - Summary**

### **Advantages of Collections Framework**:

* Provides easy-to-use interfaces and classes for storing and manipulating data.
* Supports flexible data structures, including lists, sets, and maps.
* Provides high performance, especially with **HashMap** and **HashSet**.

### **Key Points**:

* **List**: Ordered collection that allows duplicates.
* **Set**: Collection that does not allow duplicates.
* **Queue**: A collection designed for holding elements prior to processing.
* **Map**: Collection that stores key-value pairs.

