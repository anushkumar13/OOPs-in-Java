
# What is an Object in Java?

In Object-Oriented Programming (OOPs), **objects** are instances of **classes**. An object is a real-world entity represented in the software, which holds both **data** (properties) and **methods** (behaviors).

---

## What is an Object?

An object is a software version of a real-world entity, created from a class. It has:
- **Properties (Attributes/Data)**: Characteristics or features of the object.
- **Methods (Behaviors)**: Actions or operations the object can perform.

Think of a real-life **Car**:

- **Properties (Data)**: color, speed, model
- **Behavior (Methods)**: start the car, accelerate, brake

In Java, you create objects based on a class. A **class** is like a blueprint or design, and an **object** is the actual instance created from that design.

---

## Example of Object in Java

Let’s look at a simple example:

```java
class Car {
  int speed = 100; // property
  String color = "Red"; // property

  void drive() { // method
    System.out.println("Car is driving...");
  }
}

---





# Components of an Object in Java

In Object-Oriented Programming (OOPs), an object is made up of three main components:

1. **State (Data/Properties/Attributes)**
2. **Behavior (Methods/Functions)**
3. **Identity (Unique Identifier)**

---

## 1. State (Data/Properties/Attributes)

The **state** of an object refers to the data or properties that describe the object. These are the characteristics that define an object.

For example, if you have a **Car** object, the state could include:

- `color = "red"`
- `speed = 80`
- `brand = "BMW"`

In Java, these properties are stored in **fields** (variables) of the class.

### Example:

```java
class Car {
  int speed = 80;       // state
  String color = "Red"; // state
}


---




# How to Create an Object in Java

Creating an object in Java is pretty straightforward. Here’s how you can do it in just a few simple steps:

---

## Rule: Object = new + Constructor (of the class)

### Step-by-Step Process:

1. **Create a Class (Blueprint)**
   Before you can create an object, you need a class. A class is like a blueprint that defines the structure of your object.

   ```java
   class Car {
     int speed = 100;  // Property of the Car class

     void drive() {    // Method (Behavior) of the Car class
       System.out.println("Car is driving");
     }
   }




---



# What is a Class in Java?

A class in Java is like a blueprint or design for creating objects. It defines the properties (data) and behaviors (methods) that the objects created from it will have.

---

## Simple Definition:
A **class** is a template or blueprint that defines:

- **What data the object will have** (state/properties)
- **What actions the object can perform** (methods/behavior)

### Real-Life Analogy:
Imagine you run a car company. You have a common design for every car, such as:

- **Speed**
- **Color**
- **Driving & braking behavior**

**Class = Blueprint/Design/Template**

---

### Example in Java:

```java
class Car {
  // State (Properties)
  int speed;
  String color;

  // Behavior (Methods)
  void drive() {
    System.out.println("Car is driving...");
  }

  void brake() {
    System.out.println("Car is stopping...");
  }
}




---


# Syntax of OOP in Java

Understanding the syntax of OOP can seem tricky, but I'll explain it in a way that's so simple that you'll easily get it. Let's start!

---

## Basic Structure of OOP in Java:
In OOP, there are a few simple steps, where we:

1. Create a **Class** (blueprint).
2. Define the **State** (properties) and **Behavior** (methods) inside it.
3. Then, we create an **Object** and call its methods.

---

### Step-by-step Syntax:

```java
// Step 1: Create a class (this is the blueprint)
class ClassName {
    
    // Step 2: Define the state (variables/properties)
    datatype variableName;
    
    // Step 3: Define the behavior (methods/functions)
    returnType methodName() {
        // method body
    }
}

// Step 4: The main class where the object is created
public class Main {
    public static void main(String[] args) {
        
        // Step 5: Create an object
        ClassName objName = new ClassName();
        
        // Step 6: Use the object’s method/property
        objName.methodName();
        System.out.println(objName.variableName);
    }
}



---

# What Happens When You Use `new` in Java? 😭😭


## What is `new` in Java?

The **`new` keyword** in Java is used to create new objects. It tells the Java Virtual Machine (JVM) to:

1. **Allocate memory** for the new object in **heap memory**.
2. **Call the constructor** of the class to initialize the object.
3. **Return a reference** to that newly created object, which can be stored in a variable.

---

### Simple Explanation:
When you use `new`, you're basically saying:
- "Hey, JVM, make a new object from this class and give me access to it!"

---

## Example in Java:

```java
Car myCar = new Car();




---



# Do Objects Get Created in Heap Memory in Java? 


## Yes! Objects in Java Are Created in Heap Memory:

- **Heap Memory** is where all the objects created using `new` are stored.
- **Stack Memory** is used for method calls, local variables, and references to objects.

---

## Memory Breakdown in Java:

Java memory is divided mainly into two parts:

| Memory Type | What is Stored?                             |
|-------------|---------------------------------------------|
| **Stack**   | Method calls, local variables, references  |
| **Heap**    | Actual objects and their data              |

---

### Example in Java:

```java
class Car {
    int speed = 100;
}

public class Main {
    public static void main(String[] args) {
        Car myCar = new Car();
    }
}






---


# Entity Class and Driver Class in Java

Anush bhai, tu **Entity Class** aur **Driver Class** ke baare mein poochh raha hai, bilkul sahi jagah pe pucha! Tension na le, ab mai tujhe dono ko asaani se samjhaata hoon. 😊

---

## **Entity Class**

### **What is an Entity Class?**
An **Entity Class** is like a blueprint or template in which we store the **data** (attributes) of the object. It typically represents a real-world entity, like a **Car**, and its properties (like **color**, **speed**, etc.).

An entity class is usually used in frameworks like **Hibernate** to map objects to database tables.

---

### **Syntax of Entity Class:**
```java
public class Car {
    // Private attributes (Encapsulation)
    private String color;
    private int speed;

    // Getter and Setter methods to access and modify private attributes
    public String getColor() {
        return color;
    }

    public void setColor(String color) {
        this.color = color;
    }

    public int getSpeed() {
        return speed;
    }

    public void setSpeed(int speed) {
        this.speed = speed;
    }
}

---

# 🚗 Driver Class in Java

A **Driver Class** is a **main class** used to **execute** a program. It contains the `main()` method, which is the entry point to start the execution. In this class, we create objects of **Entity Classes** and test them.

---

## 🧑‍💻 **Syntax of Driver Class:**
```java
public class Main {
    public static void main(String[] args) {
        // Creating an object of the Entity class
        Car myCar = new Car();
        
        // Setting values using setter methods
        myCar.setColor("Red");
        myCar.setSpeed(120);

        // Getting values using getter methods
        System.out.println("Car Color: " + myCar.getColor());
        System.out.println("Car Speed: " + myCar.getSpeed());
    }
}





---



# 🧐 **Should the Driver Class be named `UseStudent` if the Entity Class is `Student`?**

**Great question, Anush!** If your entity class is named `Student`, naming your driver class `UseStudent` can be a good approach, but let's break it down for clarity. The key is to have a name that clearly communicates the class's purpose.

---

## ✅ **Sahi Approach**:

- **Entity Class (`Student`)**: 
  - This class is responsible for storing data related to a student (e.g., name, age, marks, etc.).
  
- **Driver Class (`UseStudent`)**: 
  - This class serves as the **entry point** for running the program. It will create and use the `Student` objects and test or execute the logic.

### Why `UseStudent`?
- **Clarity**: The name `UseStudent` directly indicates that the class is intended to **use** the `Student` class, making it clear that this is where the `Student` class will be tested or executed.

---

## 🎯 **Alternative Name Suggestions**:

- **`TestStudent`**: 
  - Focuses on the **testing** aspect of the `Student` entity.
  
- **`MainStudent`**: 
  - If the main execution is centered around the `Student` class.

- **`StudentApp`**: 
  - If the program is intended to simulate an **app-level** operation with the `Student` class.

---

## 💡 **Final Thought**:
Naming the driver class as `UseStudent` is perfectly fine, but you can choose other names like `TestStudent`, `MainStudent`, or `StudentApp` depending on what kind of execution you're aiming for. The goal is always clarity and making the code easy to understand!

---



## Example: Entity and Driver Class

### Entity Class (Student)

```java
// Entity class (Student)
public class Student {
    private String name;
    private int age;
    private double marks;

    // Getter and setter methods
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public double getMarks() {
        return marks;
    }

    public void setMarks(double marks) {
        this.marks = marks;
    }
}


---

## Driver Class (UseStudent)

```java
// Driver class (UseStudent)
public class UseStudent {
    public static void main(String[] args) {
        // Creating Student object
        Student student1 = new Student();
        
        // Setting values using setter methods
        student1.setName("Anush");
        student1.setAge(20);
        student1.setMarks(85.5);
        
        // Getting values using getter methods
        System.out.println("Name: " + student1.getName());
        System.out.println("Age: " + student1.getAge());
        System.out.println("Marks: " + student1.getMarks());
    }
}


---



# ☕ Java Object Creation: `Student anush;` vs `anush = new Student();`

In Java, creating an object is typically done in two steps:

```java
Student anush;           // Step 1: Declaration
anush = new Student();   // Step 2: Object creation and assignment

Step 1: Student anush;
Student is the name of the class. It tells the compiler that anush is a reference to an object of type Student.

anush is just a reference variable, meaning it can point to a Student object, but no object is actually created yet.

📌 At this stage:

A reference is declared in the stack memory, but it points to nothing (i.e., null by default).

💡 Step 2: anush = new Student();
new Student() creates a new object in heap memory.

anush = assigns the address of that object (i.e., the reference) to the variable anush.

📌 Now:

The reference anush in stack memory points to a real Student object in the heap memory.




---



# 🔍 Instance Variable vs Data Member in Java

Anush bhai 😭, confusion bilkul valid hai — "instance variable" aur "data member" alag lagte hain, lekin asli mein ye **same hi hote hain**. Chalo simple language mein samjhte hain. 😌

---

## 💡 What is an Instance Variable?

- An **instance variable** (also called a **data member**) is a variable that is:
  - Declared inside a class
  - But **outside any method or constructor**
  - It belongs **to an object (instance)** of the class

➡️ So, **every object gets its own copy** of instance variables.

---

## 🔁 Instance Variable = Data Member?

✅ Yes!  
These are just **two different names** for the same thing.

- **Instance Variable** → More technically correct term
- **Data Member** → Informal or general name

---

## 🔥 Java Example

```java
public class Student {
    // 👇 These are instance variables (aka data members)
    String name;
    int age;
}

👇 Creating Objects

Student s1 = new Student();
Student s2 = new Student();

s1 has its own name and age
s2 has its own name and age

➡️ Means: Each object maintains its own separate copy of these variables.

📌 Key Points

Concept	Description

Instance Variable   --> 	Declared in class but outside methods
Data Member         --> 	Another name for instance variable
Scope               --> 	Belongs to each object (separate copies)
Accessed Using	    -->  Object reference (e.g., s1.name)
Not Declared In	    -->  Methods or constructors

📎 Important Notes
They are not static, so they are tied to an object.

Created when you write: new Student()

Stored in heap memory (because part of the object)

---

Summary
Instance variables are variables that are declared in a class but outside any method.
Data members is just another name people use for them.
Both refer to the same thing — the variables tied to an object’s state.