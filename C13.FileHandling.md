# **File Handling in Java**

File handling in Java allows the program to read from and write to files on the system. This is important for many applications, as it enables data persistence. Java provides built-in libraries and classes for working with files.

Java's **File I/O** (Input/Output) operations are performed using classes from the **java.io** package, with two primary types of I/O streams: **Byte Streams** and **Character Streams**. Each stream type serves a different purpose, depending on whether you're dealing with binary or textual data.

---

## **1. File Class**

Before dealing with file operations like reading and writing, Java provides the `File` class to represent file and directory pathnames. The `File` class helps you to check for file existence, manipulate file paths, and access information about files (size, name, etc.).

### **Common Methods of the `File` Class**:

* **`exists()`**: Checks if the file or directory exists.
* **`createNewFile()`**: Creates a new file on the disk (returns `true` if file is created).
* **`delete()`**: Deletes the file or directory.
* **`length()`**: Returns the length of the file in bytes.
* **`isDirectory()`**: Returns `true` if the file is a directory.
* **`isFile()`**: Returns `true` if the file is a regular file.
* **`listFiles()`**: Lists all files in a directory.

### **Example**:

```java
import java.io.File;

public class FileExample {
    public static void main(String[] args) {
        File file = new File("example.txt");

        // Check if the file exists
        if (file.exists()) {
            System.out.println("File exists");
        } else {
            System.out.println("File doesn't exist");
        }
    }
}
```

---

## **2. File Input/Output Streams (Byte Streams)**

Byte Streams are used to perform input and output of **raw binary data**, such as image files, audio files, or any other file type. The classes for byte streams in Java are:

* **InputStream** (used for reading bytes)
* **OutputStream** (used for writing bytes)

### **FileInputStream**:

Used for reading bytes from a file.

### **FileOutputStream**:

Used for writing bytes to a file.

#### **Example of FileInputStream**:

```java
import java.io.FileInputStream;
import java.io.IOException;

public class FileInputStreamExample {
    public static void main(String[] args) {
        try (FileInputStream fis = new FileInputStream("example.txt")) {
            int content;
            while ((content = fis.read()) != -1) {
                System.out.print((char) content);  // Print the character read
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### **Example of FileOutputStream**:

```java
import java.io.FileOutputStream;
import java.io.IOException;

public class FileOutputStreamExample {
    public static void main(String[] args) {
        String data = "Hello, this is a test for FileOutputStream.";

        try (FileOutputStream fos = new FileOutputStream("output.txt")) {
            byte[] bytes = data.getBytes();
            fos.write(bytes);  // Write data to the file
            System.out.println("Data written to the file.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

---

## **3. FileReader and FileWriter (Character Streams)**

Character Streams handle **text data** (Unicode). Java provides the `FileReader` and `FileWriter` classes for reading and writing text files.

* **FileReader**: A class used for reading text files. It reads one character at a time from the file.
* **FileWriter**: A class used for writing text to a file. It writes one character at a time.

### **Example of FileReader**:

```java
import java.io.FileReader;
import java.io.IOException;

public class FileReaderExample {
    public static void main(String[] args) {
        try (FileReader fr = new FileReader("example.txt")) {
            int content;
            while ((content = fr.read()) != -1) {
                System.out.print((char) content);  // Print the character read
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### **Example of FileWriter**:

```java
import java.io.FileWriter;
import java.io.IOException;

public class FileWriterExample {
    public static void main(String[] args) {
        String data = "This is a text written using FileWriter class.";

        try (FileWriter fw = new FileWriter("output.txt")) {
            fw.write(data);  // Write data to the file
            System.out.println("Data written to the file.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

---

## **4. BufferedReader and BufferedWriter**

These classes are used to **read and write text efficiently**. They are a wrapper around `FileReader` and `FileWriter` and provide buffering capabilities, which makes reading and writing large files much faster.

### **BufferedReader**:

Reads text from an input stream (like a file) line by line or character by character.

### **BufferedWriter**:

Writes text to an output stream, buffering the characters to optimize I/O operations.

#### **Example of BufferedReader**:

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class BufferedReaderExample {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("example.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);  // Read and print each line
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### **Example of BufferedWriter**:

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class BufferedWriterExample {
    public static void main(String[] args) {
        String data = "This is a text written using BufferedWriter.";

        try (BufferedWriter bw = new BufferedWriter(new FileWriter("output.txt"))) {
            bw.write(data);  // Write data to the file
            System.out.println("Data written to the file.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

---

## **5. Serialization and Deserialization**

Serialization is the process of converting an object into a byte stream so that it can be easily saved to a file or sent over a network. Deserialization is the reverse process, where the byte stream is converted back into an object.

* **Serializable Interface**: To serialize an object, the class must implement the `Serializable` interface.

### **Example of Serialization**:

```java
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;

public class SerializationExample {
    public static void main(String[] args) {
        Person person = new Person("John", 25);

        try (ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("person.ser"))) {
            oos.writeObject(person);  // Serialize the object
            System.out.println("Object serialized to file.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

class Person implements java.io.Serializable {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

### **Example of Deserialization**:

```java
import java.io.FileInputStream;
import java.io.IOException;
import java.io.ObjectInputStream;

public class DeserializationExample {
    public static void main(String[] args) {
        try (ObjectInputStream ois = new ObjectInputStream(new FileInputStream("person.ser"))) {
            Person person = (Person) ois.readObject();  // Deserialize the object
            System.out.println("Deserialized Person: " + person.name + ", " + person.age);
        } catch (IOException | ClassNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

---

## **6. Random Access File**

Java also provides **RandomAccessFile** for accessing a file at any position (not just sequential). It allows both reading and writing operations at arbitrary positions.

### **Methods of RandomAccessFile**:

* **`seek(long position)`**: Moves the file pointer to a specified position.
* **`read()`**: Reads the next byte of data.
* **`write()`**: Writes a byte of data.

### **Example**:

```java
import java.io.RandomAccessFile;
import java.io.IOException;

public class RandomAccessFileExample {
    public static void main(String[] args) {
        try (RandomAccessFile raf = new RandomAccessFile("example.txt", "rw")) {
            raf.seek(5);  // Move to position 5 in the file
            raf.writeBytes("Hello, world!");  // Write at the 5th position
            System.out.println("Data written at position 5.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

---

## **7. Summary**

File handling in Java is essential for storing and retrieving data. Java provides several classes for working with files, both for text and binary data. Here’s a recap:

1. **File Class**: For file and directory manipulations.
2. **Byte Streams (FileInputStream, FileOutputStream)**: For handling binary data.
3. **Character Streams (FileReader, FileWriter)**: For handling text data.
4. **Buffered Streams (BufferedReader, BufferedWriter)**: For efficient reading/writing of text.
5. **Serialization/Deserialization**: For converting objects into byte streams and vice versa.
6. **Random Access File**: For accessing and modifying a file at arbitrary positions.
