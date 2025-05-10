### **Complete Notes on Threads in Java**

In Java, **threads** are the smallest unit of execution within a program. They allow for multitasking, which means the ability to run multiple tasks concurrently. Java provides a rich set of APIs for creating and managing threads, allowing developers to write programs that can perform multiple operations at once.

---

### **Introduction to Threads**

* **What is a Thread?**
  A **thread** is a lightweight process, and in a multithreaded environment, multiple threads can run concurrently. A Java program can have multiple threads that work independently and concurrently.

* **Why Use Threads?**
  Threads are useful for tasks such as:

  * Performing background tasks (e.g., downloading files while allowing the user to interact with the UI).
  * Handling multiple client requests in server-side applications.
  * Running tasks that can be performed in parallel (e.g., parallel processing).

* **Thread vs Process**: A thread is part of a process and shares resources such as memory, file descriptors, and CPU time. A process, on the other hand, is an independent program in execution.

---

### **Thread Life Cycle in Java**

A thread goes through several states during its lifetime:

1. **New (Born)**:

   * A thread is created, but the `start()` method hasn’t been invoked yet.
   * Example:

     ```java
     Thread t = new Thread();
     // Thread is in the New state
     ```

2. **Runnable**:

   * After calling the `start()` method, the thread moves to the **Runnable** state. In this state, the thread is ready to execute, but the CPU may or may not be assigned to it.
   * Example:

     ```java
     t.start();  // Thread enters the Runnable state
     ```

3. **Blocked**:

   * A thread moves into the **Blocked** state when it wants to access a resource (like a synchronized block or method) that another thread is using.
   * Example: When one thread holds a lock, another thread attempting to acquire the same lock enters the Blocked state.

4. **Waiting**:

   * The thread enters the **Waiting** state when it is waiting for another thread to perform a particular action (e.g., using `Thread.join()` or `Object.wait()`).
   * Example:

     ```java
     t.join();  // Current thread waits for the thread 't' to finish
     ```

5. **Timed Waiting**:

   * A thread is in the **Timed Waiting** state when it is waiting for a specific period of time (e.g., using `Thread.sleep()` or `Thread.join(long millis)`).
   * Example:

     ```java
     Thread.sleep(1000);  // Thread is in Timed Waiting for 1000ms
     ```

6. **Terminated**:

   * A thread enters the **Terminated** state when it has completed execution, either normally or due to an exception.
   * Once a thread terminates, it cannot be started again.

---

### **Creating Threads in Java**

In Java, threads can be created in three ways:

1. **By Extending the Thread Class**:

   * You can create a thread by extending the `Thread` class and overriding its `run()` method.
   * Example:

     ```java
     class MyThread extends Thread {
         public void run() {
             System.out.println("Thread is running.");
         }
     }

     public class ThreadExample {
         public static void main(String[] args) {
             MyThread t = new MyThread();
             t.start();  // Starts the thread
         }
     }
     ```

2. **By Implementing the Runnable Interface**:

   * Another way to create a thread is by implementing the `Runnable` interface and passing it to a `Thread` object.
   * Example:

     ```java
     class MyRunnable implements Runnable {
         public void run() {
             System.out.println("Runnable thread is running.");
         }
     }

     public class RunnableExample {
         public static void main(String[] args) {
             MyRunnable myRunnable = new MyRunnable();
             Thread t = new Thread(myRunnable);
             t.start();  // Starts the thread
         }
     }
     ```


3. Creating a Thread using Anonymous Class and Overriding the run() Method
    In this method, instead of creating a separate class or implementing the Runnable interface, we create a thread by directly overriding the run() method within an anonymous class and passing it to the Thread constructor.


**Steps:**

- Create a Thread using the Thread constructor that takes a Runnable as an argument.

- Override the run() method in the anonymous class and define the logic that will be executed when the thread starts.

- Start the thread using the start() method.

```java
public class ThreadExample {
    public static void main(String[] args) {
        // Creating a thread using an anonymous class and overriding the run() method
        Thread thread = new Thread(new Runnable() {
            @Override
            public void run() {
                // Code to be executed by the thread
                System.out.println("Thread is running from anonymous class!");
            }
        });
        
        // Starting the thread
        thread.start();
    }
}

```

---

### **Thread Synchronization**

When multiple threads access shared resources (e.g., variables or objects), it can lead to data inconsistency and corruption. To prevent this, **synchronization** is used.

#### **Synchronized Methods and Blocks**

* **Synchronized Method**: You can use the `synchronized` keyword to ensure that only one thread at a time can execute a method.
* **Synchronized Block**: You can also synchronize specific blocks of code within a method using the `synchronized` keyword.

  Example:

  ```java
  public synchronized void method() {
      // Code that must be executed by one thread at a time
  }

  public void method() {
      synchronized(this) {
          // Critical section
      }
  }
  ```

#### **Why Use Synchronization?**

* **Avoid race conditions**: Ensures that multiple threads do not modify shared resources simultaneously.
* **Ensure data consistency**: Makes sure that the data being processed is not corrupted.

---

### **Inter-Thread Communication**

Java allows threads to communicate with each other using methods in the `Object` class: `wait()`, `notify()`, and `notifyAll()`. These methods allow threads to communicate when one thread needs to wait for another to perform some action.

* **wait()**: The current thread gives up its hold on the monitor and enters the waiting state.
* **notify()**: Wakes up one thread that is waiting on the object’s monitor.
* **notifyAll()**: Wakes up all threads that are waiting on the object’s monitor.

Example of inter-thread communication:

```java
class Producer implements Runnable {
    private final Object lock;

    public Producer(Object lock) {
        this.lock = lock;
    }

    public void run() {
        synchronized (lock) {
            System.out.println("Producer producing...");
            lock.notify();
        }
    }
}

class Consumer implements Runnable {
    private final Object lock;

    public Consumer(Object lock) {
        this.lock = lock;
    }

    public void run() {
        synchronized (lock) {
            try {
                System.out.println("Consumer waiting...");
                lock.wait();  // Wait until notified
                System.out.println("Consumer consumed...");
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```

---

### **Daemon Threads**

A **Daemon Thread** is a thread that runs in the background and does not prevent the program from terminating. These threads are usually used for background tasks, such as garbage collection, or logging.

* Daemon threads can be set using the `setDaemon(true)` method:

  ```java
  Thread thread = new Thread();
  thread.setDaemon(true);
  thread.start();
  ```

* Daemon threads automatically terminate when the program finishes. Non-daemon threads, on the other hand, keep the program running until they complete their execution.

---

### **Thread Methods**

Java provides several useful methods in the `Thread` class for managing thread execution:

* **start()**: Starts the thread and invokes the `run()` method.
* **sleep(long millis)**: Causes the current thread to sleep for the specified time in milliseconds.
* **join()**: Causes the current thread to wait until the thread it is called on completes.
* **setPriority(int priority)**: Sets the priority of the thread.
* **getPriority()**: Returns the priority of the thread.
* **isAlive()**: Checks if the thread is alive.
* **interrupt()**: Interrupts the thread, causing it to stop what it is doing and throw an `InterruptedException`.

---

### **Yield vs Join**

* **yield()**: This is a static method that causes the currently executing thread to temporarily pause, allowing other threads of the same or higher priority to execute.

  Example:

  ```java
  Thread.yield();  // Pauses the current thread and gives other threads a chance to run
  ```

* **join()**: The `join()` method makes the current thread wait until the thread it is called on finishes its execution.

  Example:

  ```java
  thread.join();  // Current thread waits for the completion of 'thread'
  ```

---

### **Summary of Thread Concepts**

* **Threads** are lightweight units of execution that allow multiple tasks to run concurrently.
* The **Thread Life Cycle** includes states such as New, Runnable, Blocked, Waiting, Timed Waiting, and Terminated.
* Threads can be created by extending the `Thread` class, implementing the `Runnable` interface, or using an `ExecutorService`.
* **Thread Synchronization** ensures data consistency when multiple threads access shared resources.
* **Inter-Thread Communication** allows threads to coordinate their activities using `wait()`, `notify()`, and `notifyAll()`.
* **Daemon Threads** run in the background and do not prevent the program from terminating.
* Java provides methods like **start()**, **sleep()**, **join()**, and **interrupt()** to manage thread execution.
* **Yield** temporarily pauses the current thread, while **join** makes one thread wait for another to finish.
