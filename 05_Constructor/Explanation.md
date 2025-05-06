#  Java Constructors

## 🔹 What is a Constructor?

###  Definition:
A constructor is a special method that is automatically invoked when an object of a class is created.

Its main purpose is to **initialize the object**, meaning it assigns initial values to the object's instance variables.

- The name of the constructor **must be the same as the class name**.
- It **does not have any return type**, not even `void`.

---

## 🔹 Characteristics of Constructors

###  Same Name as Class:
The constructor's name must exactly match the class name.

###  No Return Type:
Constructors do not have any return type—not even `void`.

###  Automatic Invocation:
A constructor is automatically called when an object is created using the `new` keyword.

###  Initialization:
Constructors are primarily used to initialize instance variables of the object.

---

## 🔹 Types of Constructors

### 1️⃣ Default Constructor:
- A constructor **without any parameters**.
- If you do not define any constructor, Java automatically provides a default constructor.
- It assigns **default values** to instance variables:
  - `int` → `0`
  - `String` → `null`
  - `boolean` → `false`, etc.

### 2️⃣ Parameterized Constructor:
- A constructor that **accepts parameters**.
- Used when you want to initialize the object with **custom values** during creation.

---

## 🔹 Role of Constructor in Object Lifecycle

###  Initialization:
When you create an object, the constructor initializes the instance variables. You don’t have to set them manually.

###  Overloading:
You can define **multiple constructors** with different parameter lists. This is called **constructor overloading**.

---

##  Summary:
- A constructor is a special method that runs automatically when an object is created.
- It has **no return type** and its name **must match** the class name.
- **Default Constructor** has no parameters and assigns default values.
- **Parameterized Constructor** accepts arguments and assigns custom values to instance variables.

---

#  Default Constructor

## 🔹 What is a Default Constructor?

A **default constructor** is a no-argument constructor that Java **automatically provides** if no constructor is explicitly written in the class.

It is automatically called when you create an object using the `new` keyword.

##  Key Points:

- **No Parameters**: Default constructor does not take any parameters.
- **Default Initialization**: Assigns default values to instance variables.
- **Auto-Creation**: If no constructor is defined in the class, Java creates one for you.

###  When is it Called?
- When you create an object **without defining any constructor**, Java invokes the default constructor.
- If you define **any constructor** (even parameterized), Java **will not provide** a default constructor automatically.

---

#  Role of Constructor in Custom Initialization

Constructors give you the ability to replace default values with **meaningful, custom values**.

When you define your own constructor, you can pass values at the time of object creation to assign them directly to instance variables.

###  Example:
Imagine a `Student` class with `name` and `age`.  
- If you use a default constructor, `name` will be `null` and `age` will be `0`.  
- If you use a parameterized constructor, you can pass `"Anush"` and `20` while creating the object, and those values will be stored.

---

#  Non-Parameterized Constructor

###  Definition:
A non-parameterized constructor (also called default constructor) does not take any arguments.

If no constructor is defined in a class, Java provides one by default.

###  Characteristics:
- **No Parameters**: Takes no arguments.
- **Used for Default Initialization**: Assigns default values like `0`, `null`, `false`, etc.

---

#  Parameterized Constructor

###  Definition:
A parameterized constructor is a constructor that takes arguments.

It allows the object to be initialized with **custom values** at the time of creation.

###  Characteristics:
- **Takes Parameters**: You pass values while creating the object.
- **Used for Custom Initialization**: These values are assigned to the instance variables.

---
