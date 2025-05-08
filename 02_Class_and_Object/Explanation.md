## What is an Object in Java?

In Object-Oriented Programming (OOPs), **objects** are instances of **classes**. An object is a real-world entity represented in the software, which holds both **data** (properties) and **methods** (behaviors).

An object is a software version of a real-world entity, created from a class. It has:

- **Properties (Attributes/Data)**: Characteristics or features of the object.
- **Methods (Behaviors)**: Actions or operations the object can perform.

### Real-Life Example: Car

- **Properties (Data)**: color, speed, model  
- **Behavior (Methods)**: start the car, accelerate, brake

In Java, you create objects based on a class. A **class** is like a blueprint or design, and an **object** is the actual instance created from that design.

---

## Components of an Object in Java

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

---

## 2. Behavior (Methods/Functions)

The **behavior** of an object defines what the object can do or what actions it can perform. These are implemented as **methods** in the class.

Continuing with the **Car** example, behaviors could include:

- Starting the engine
- Accelerating
- Braking

These methods allow the object to interact with the outside world or change its own internal state.

---

## 3. Identity (Unique Identifier)

The **identity** of an object means that each object has a unique existence in memory, even if it holds the same data as another object.

For example, you can have two car objects with the same color and model, but they are still two different objects — each has its own identity in memory.

In Java, the identity of an object is typically determined by its memory address (reference), which allows Java to distinguish between different instances of the same class.

---

## How to Create an Object in Java

Creating an object in Java is pretty straightforward. Here’s how you can do it:

### Step 1: Create a Class (Blueprint)

Before you can create an object, you need a class. A class is like a blueprint that defines the structure of your object.

---

## What is a Class in Java?

A class in Java is like a blueprint or design for creating objects. It defines the properties (data) and behaviors (methods) that the objects created from it will have.

### Simple Definition

A **class** is a template or blueprint that defines:

* **What data the object will have** (state/properties)
* **What actions the object can perform** (methods/behavior)

### Real-Life Analogy

Imagine you run a car company. You have a common design for every car, such as:

* **Speed**
* **Color**
* **Driving & braking behavior**

**Class = Blueprint/Design/Template**

---

## Basic Structure of OOP in Java

In OOP, there are a few simple steps:

1. Create a **Class** (blueprint).
2. Define the **State** (properties) and **Behavior** (methods) inside it.
3. Create an **Object** and call its methods.

---

## What Happens When You Use `new` in Java?

### What is `new` in Java?

The **`new` keyword** in Java is used to create new objects. It tells the Java Virtual Machine (JVM) to:

1. **Allocate memory** for the new object in **heap memory**.
2. **Call the constructor** of the class to initialize the object.
3. **Return a reference** to that newly created object, which can be stored in a variable.

### Simple Explanation

When you use `new`, you're basically saying:

* "Hey, JVM, make a new object from this class and give me access to it!"

---

## Do Objects Get Created in Heap Memory in Java?

### Yes! Objects in Java Are Created in Heap Memory:

* **Heap Memory** is where all the objects created using `new` are stored.
* **Stack Memory** is used for method calls, local variables, and references to objects.

### Memory Breakdown in Java

| Memory Type | What is Stored?                           |
| ----------- | ----------------------------------------- |
| **Stack**   | Method calls, local variables, references |
| **Heap**    | Actual objects and their data             |

---

## Entity Class and Driver Class in Java

### What is an Entity Class?

An **Entity Class** is like a blueprint or template in which we store the **data** (attributes) of the object. It typically represents a real-world entity, like a **Car**, and its properties (like **color**, **speed**, etc.).

Entity classes are commonly used in frameworks like **Hibernate** to map objects to database tables.

### What is a Driver Class?

A **Driver Class** is a **main class** used to **execute** a program. It contains the `main()` method, which is the entry point to start the execution. In this class, we create objects of **Entity Classes** and test them.

---

## Should the Driver Class be named `UseStudent` if the Entity Class is `Student`?

### Good Practice Explanation

If your entity class is named `Student`, naming your driver class `UseStudent` can be a good approach because it clearly communicates the class’s purpose.

### Naming Suggestions

* **Entity Class (`Student`)**: Holds data about a student.
* **Driver Class (`UseStudent`)**: Creates and uses `Student` objects to perform operations.

#### Alternative Names

* `TestStudent` → Emphasizes testing.
* `MainStudent` → Emphasizes it's the main class.
* `StudentApp` → Implies app-level operations using `Student`.

### Final Thought

The key is clarity. Use `UseStudent`, `TestStudent`, or any name that clearly indicates the purpose.

---

## ☕ Java Object Creation: `Student anush;` vs `anush = new Student();`

Java object creation typically involves two steps:

### Step 1: Declaration

```java
Student anush;
```

* Declares `anush` as a reference of type `Student`.
* At this point, `anush` is just a reference in **stack memory**, pointing to `null`.

### Step 2: Instantiation

```java
anush = new Student();
```

* `new Student()` creates a new object in **heap memory**.
* `anush =` assigns that object’s reference to the variable `anush`.

### Result

* `anush` now refers to a valid object in the heap.

---

## Instance Variable vs Data Member in Java

### What is an Instance Variable?

* Declared **inside a class**, but **outside any method or constructor**.
* Belongs to each object (instance) of the class.
* Every object gets its **own copy** of the instance variable.

### Instance Variable = Data Member?

✅ Yes!

* **Instance Variable** is the more technical term.
* **Data Member** is the informal/common name for the same thing.

---

## Creating Objects

```java
Student s1 = new Student();
Student s2 = new Student();
```

* `s1` and `s2` are different objects.
* Each has its own separate copy of variables like `name`, `age`, etc.

### Key Points

| Concept           | Description                              |
| ----------------- | ---------------------------------------- |
| Instance Variable | Declared in class, outside methods       |
| Data Member       | Another name for instance variable       |
| Scope             | Belongs to each object (separate copies) |
| Accessed Using    | Object reference (e.g., `s1.name`)       |
| Not Declared In   | Methods or constructors                  |

📎 **Important Notes**:

* Not static; they belong to an object.
* Created when you use: `new Student()`
* Stored in heap memory (as part of the object)
