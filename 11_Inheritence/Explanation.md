## 💡 What is Inheritance?

Inheritance is the concept where one class shares its properties (variables) and behaviors (methods) with another class. In simple terms, a class can "inherit" from another class, meaning it can acquire the properties and methods of the parent class.

This allows the child class to reuse and build upon the functionality defined in the parent class, enabling code reusability and extensibility.

---

### 🔹 What Are the Benefits of Inheritance?

- **Code Reusability**: The child class can reuse the code written in the parent class, which means the same logic does not have to be written again and again.

- **Method Overriding**: The child class can override the methods inherited from the parent class to provide its own specific implementation.

- **Extension of Functionality**: A child class can add additional features to the functionalities it inherits from the parent class, allowing flexible and modular design.

---

### 🔹 Syntax of Inheritance

To implement inheritance in Java, the `extends` keyword is used. It signifies that the child class is inheriting from the parent class.

The class that inherits is called the **child class** (or subclass), and the class that is being inherited from is called the **parent class** (or superclass).

---

### 🔹 Types of Inheritance in Java

1. **Single Inheritance**  
   In single inheritance, a single child class inherits from a single parent class.  
   This is the most basic form of inheritance.

2. **Multilevel Inheritance**  
   In this type of inheritance, a class inherits from a child class which in turn inherits from another parent class.  
   It forms a chain-like structure where one class extends another, and that class is extended by yet another class.

3. **Hierarchical Inheritance**  
   In hierarchical inheritance, multiple child classes inherit from a single parent class.  
   Each child class has access to the properties and methods of the same parent class.

4. **Multiple Inheritance (Not Directly Supported in Java)**  
   In multiple inheritance, a class would inherit from more than one parent class.  
   Java does not support this directly through classes to avoid ambiguity problems, but it can be achieved through interfaces.

5. **Hybrid Inheritance**  
   Hybrid inheritance is a combination of two or more types of inheritance.  
   Although Java does not support multiple inheritance with classes, hybrid inheritance can still be implemented using interfaces.

---

### 🔹 Summary

Inheritance is a fundamental concept of object-oriented programming that allows a class to inherit properties and methods from another class using the `extends` keyword. It promotes code reusability, allows method overriding, and supports functionality extension.

There are various types of inheritance in Java, including single, multilevel, hierarchical, and hybrid (achieved through interfaces). Multiple inheritance is not directly supported with classes in Java but can be implemented using interfaces.

---

## 🔹 Method Overriding and Inheritance

Method overriding means that the child class redefines or modifies a method that it inherits from the parent class. This allows the child class to provide its own specific implementation of a method that already exists in the parent class.

When a method in the child class has the same name, return type, and parameters as a method in the parent class, the method in the child class overrides the one in the parent class.

If a parent class reference is used to refer to a child class object, and an overridden method is called, the method in the child class will be executed. This is an example of **runtime polymorphism**.

---

## 🔹 Access to Parent Class Members in Child Class

The child class has direct access to the `public` and `protected` members of the parent class. However, the child class **cannot directly access** the `private` members of the parent class.

- **Public members** can be accessed from anywhere.
- **Protected members** can be accessed within the same package and by subclasses.
- **Private members** are only accessible within the same class and cannot be accessed by the child class directly.

To access private data, the parent class must provide getter methods or use other access mechanisms.

---

## 🔹 Constructor in Inheritance

When a child class object is created, the constructor of the parent class is automatically invoked first before the child class constructor executes.

If the parent class has a **parameterized constructor**, then the child class must explicitly call the parent constructor using the `super()` keyword with appropriate arguments.

The `super()` call must be the **first statement** in the child class constructor. If not used explicitly, Java inserts a default call to the no-argument constructor of the parent class.

This ensures that the parent class is properly initialized before the child class begins its own initialization.

---

## 🔹 Accessing Parent Class Methods in Child Class

The child class can access the methods of the parent class directly if those methods are `public` or `protected`.

If a method in the parent class is **not overridden** in the child class, then calling that method on a child object will invoke the parent version.

If the method **is overridden**, the version in the child class will be called instead.

This allows the child class to either use the parent class functionality as-is or to override and change it as needed.

---

## 🔹 Summary of Inheritance in Java

- Inheritance allows one class to acquire the properties and behaviors of another class.
- It promotes **code reusability**, reduces code duplication, and improves code organization.
- Java supports **Single**, **Multilevel**, and **Hierarchical** inheritance.
- **Multiple inheritance** is not supported through classes but can be achieved using interfaces.
- Method Overriding enables the child class to modify inherited behaviors.
- The child class can access `public` and `protected` members of the parent class but **not private** members.
- Parent class constructors are automatically called during the creation of child class objects using `super()`.

Inheritance is a powerful feature in Java that supports **object-oriented design**, **modular development**, and **polymorphism**.

---

## 🔹 What is the `super` Keyword?

In Java, the `super` keyword is used by a child class to refer to its parent class's members. It allows the child class to access variables, methods, and constructors defined in the parent class.

The `super` keyword helps in accessing:
- The parent class constructor.
- The parent class overridden methods.
- The parent class variables (when they are shadowed by child class variables).

---

## 🔹 When is `super` Used?

### 1. To Call Parent Class Constructor

When an object of a child class is created, the constructor of the parent class is called first. If the parent class constructor requires parameters, the child class must explicitly call it using `super()` with appropriate arguments.

This call to `super()` must be the first statement in the child class constructor. Java automatically adds a call to the no-argument constructor of the parent class if no constructor call is provided.

### 2. To Call Parent Class Method

If a method in the child class overrides a method from the parent class, and the child class still needs to access the original version of that method, it can do so using `super.methodName()`.

This is useful when the child class wants to extend or combine the logic of the parent method rather than completely replacing it.

### 3. To Access Parent Class Variables

When the child class defines a variable with the same name as a variable in the parent class, the child class's variable hides the parent’s variable.

To access the parent class's version of the variable in such cases, the `super` keyword is used.

---

## 🔹 Using `super()` Constructor Call

When the child class constructor is invoked, the constructor of the parent class is automatically called first.

If the parent class has a parameterized constructor, the child class must use `super(arguments)` to explicitly call and pass the required values.

This ensures that the parent class's state is initialized before the child class's logic executes.

---

## 🔹 Using `super` to Call Parent Class Method

If a method is overridden in the child class, and the child class wants to execute the parent class’s version of that method, it can call it using `super.methodName()`.

This helps in situations where the child class wants to add extra behavior to the method, but still reuse the original logic of the parent class.

---

## 🔹 Using `super` to Access Parent Class Variables

If the parent class and child class both have variables with the same name, then using the variable name directly in the child class will access the child class’s version.

To access the parent class version of that variable, the child class must use `super.variableName`.

This is particularly useful in cases of variable shadowing.

---

## 🔹 Important Points about `super`

- When a child class constructor is invoked, the parent class constructor is also called automatically. If the parent constructor takes arguments, `super()` must be used to call it.
  
- If a method is overridden in the child class, `super.methodName()` can be used to call the original method from the parent class.

- When a variable in the child class has the same name as in the parent class, `super.variableName` helps access the parent’s version.

---

## 🔹 `super` and Constructor Chaining

Constructor chaining refers to the process where one constructor calls another constructor.

In Java, `super()` is used for constructor chaining between a child class and its parent class.

This ensures that the parent class is properly initialized before the child class constructor runs. It forms a chain where each constructor calls its immediate parent's constructor until the top of the hierarchy is reached.

---

## 🔹 Summary

- The `super` keyword is used to access parent class constructors, methods, and variables from the child class.
- If the parent class constructor is parameterized, `super()` with arguments must be used to call it.
- When a method is overridden in the child class, `super.methodName()` allows calling the original parent version.
- To access a parent class variable that is hidden by a child class variable, `super.variableName` is used.
- Constructor chaining using `super()` ensures proper initialization of the parent class before the child class is constructed.

---

#  Method Overriding in Java – Full Explanation

##  What is Method Overriding?

Method Overriding in Java occurs when a child class provides its own version of a method that is already defined in the parent class. The method must have the **same name**, **same parameters**, and **compatible return type**.

This is useful when we want the child class to define a behavior that is different from or more specific than what is provided in the parent class.

---

##  Real-Life Analogy

Imagine a generic class `Animal` that has a method `makeSound()`. Now, if a `Dog` class extends `Animal` and redefines the `makeSound()` method with its own implementation, it is said to override the method. This allows the dog object to make its own unique sound while still being an animal.

---

##  Rules of Method Overriding

- The method **name must be the same** as in the parent class.
- The **parameters (arguments)** must be exactly the same.
- The **return type** must be the same or a **covariant type** (a subtype).
- Only **instance methods** (non-static) can be overridden.
- The method in the parent class should not be `private`, `final`, or `static`.
- The **access modifier** of the overriding method should be:
  - Same as the parent method, or
  - More accessible (e.g., `protected` → `public` is allowed, but `protected` → `private` is not).
- Only a **child class** can override a method of its parent class.

---

##  Important Terms

| Term             | Meaning                                                                 |
|------------------|-------------------------------------------------------------------------|
| `@Override`      | Annotation that tells the compiler a method is intended to override a method in the parent class. Helps catch errors. |
| Parent Method    | The method that is originally declared in the base (super) class.       |
| Child Method     | The method that overrides the parent method in the derived (sub) class. |

---

##  Why Use Method Overriding?

- To achieve **Runtime Polymorphism** (also called **Dynamic Method Dispatch**).
- To **customize or extend** the behavior of a method defined in the parent class.
- To allow the **child class to provide specific implementation** of a method that is general in the parent class.

---

##  Dynamic Method Dispatch

This is the mechanism by which a call to an overridden method is resolved at runtime, not compile time.

If a parent class reference holds a child class object, and the overridden method is called on that reference, the **child class's version of the method** is executed at runtime.

This is how Java achieves **runtime polymorphism**.

---

## ❌ When Overriding is Not Allowed

| Situation        | Reason                                                                 |
|------------------|-------------------------------------------------------------------------|
| Final Method      | A `final` method cannot be overridden, as it is meant to be constant and unchangeable. |
| Static Method     | `Static` methods belong to the class, not the instance, so they are not overridden but hidden (method hiding). |
| Private Method    | A `private` method is not accessible outside its class, so it cannot be overridden. |

---

##  Best Practices for Method Overriding

- Always use the `@Override` annotation. It helps the compiler catch errors like incorrect method signatures.
- Use overriding to write **specific logic in child classes** while reusing the general structure from parent classes.
- Always respect access control rules: ensure the child class method is not more restrictive than the parent.
- Avoid overriding methods unless customization is necessary to prevent complexity or confusion.

---

##  Summary

- **Method Overriding** allows a child class to redefine a method inherited from a parent class.
- It is used for customizing or extending the behavior of a method.
- It plays a major role in achieving **runtime polymorphism**.
- Only instance methods can be overridden.
- `final`, `static`, and `private` methods cannot be overridden.
- Always use the `@Override` annotation for safer and clearer code.

---

#  Method Overloading vs Method Overriding ( Detailed Comparison)

This guide explains the **key differences** between Method Overloading and Method Overriding in Java, using a comprehensive feature-wise comparison.

---

##  Feature-wise Comparison

| Feature                 | ✅ Method Overloading                                                     | 🔁 Method Overriding                                                                  |
|-------------------------|---------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
|  Definition           | Having the same method name with different parameters in the same class | Redefining a parent class method in the child class with the same name and parameters |
|  Concept Type         | Compile-time Polymorphism                                                 | Runtime Polymorphism                                                                  |
|  Class Involvement    | Occurs within a single class                                              | Requires two classes – parent and child (inheritance involved)                        |
|  Parameters           | Must differ in number, type, or order                                     | Must be exactly the same in number, type, and order                                   |
|  Return Type          | Can be the same or different                                              | Must be the same or a covariant (subtype)                                             |
|  Access Modifier      | No restrictions – can be public, private, final, etc.                    | The overriding method must have same or more accessible modifier than the parent      |
|  Inheritance Required?| ❌ No                                                                      | ✅ Yes                                                                                 |
|  Polymorphism Type    | Static Binding (Resolved at compile time)                                | Dynamic Binding (Resolved at runtime)                                                 |
|  @Override Annotation?| ❌ Not used                                                               | ✅ Recommended (for compiler-level checking)                                           |
|  Final/Static Methods?| Final and static methods can be overloaded                               | Final and static methods cannot be overridden                                         |
|  Use Case           | Used when performing similar operations in different ways (e.g., different input types) | Used when the child class needs to provide a different behavior than the parent       |

---

##  Real-Life Analogy

###  Method Overloading:
Imagine a person responsible for printing things. If they receive a number, they print the number. If they receive a string, they print the string. If they receive an object, they print its details.  
The **task is the same** (printing), but the **input types are different** – this is Method Overloading.

---

###  Method Overriding:
Imagine a general class `Vehicle` that has a method `run()`.  
Now, subclasses like `Car` and `Bike` create their **own version** of the `run()` method.  
When `Bike.run()` is called, the **bike-specific behavior** executes.  
This is Method Overriding – same method name, redefined in the child class.

---

##  One-Liner Summary

| Concept              | Easy Definition                                                                 |
|----------------------|----------------------------------------------------------------------------------|
| Method Overloading   | Defining multiple methods with the same name but different arguments in one class |
| Method Overriding    | Redefining a parent class method in the child class with the same arguments       |

---
