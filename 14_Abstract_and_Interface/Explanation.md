# Abstract in Java — Full Detailed Explanation

## 🔹 What is `abstract` in Java?

In Java, `abstract` is a keyword that is used to define an **incomplete structure** — which means something that is only partially implemented. It tells the program that a certain functionality is needed, but its exact implementation will be defined **later by subclasses**.

The `abstract` keyword can be used in two main places:

* Abstract Class
* Abstract Method

---

##  Abstract Class

###  Definition:

An **abstract class** is a class that is only partially complete. It can contain both:

* Fully defined methods (concrete methods)
* Only declared methods (abstract methods)

### 🔹 Key Characteristics:

* An abstract class **cannot be instantiated** directly. You can create a reference of it but not an object.
* It **may or may not** contain abstract methods.
* It **can contain**:

  * Instance variables
  * Constructors
  * Static methods
  * Final methods
  * Concrete methods (fully implemented methods)

---

##  Abstract Method

###  Definition:

An **abstract method** is a method that has no body — it is only declared. The logic of the method is provided by the **subclass that inherits** the abstract class.

### 🔹 Key Characteristics:

* Ends with a semicolon (`;`), since there is no body.
* If a class has even **one abstract method**, then the class **must** be declared as `abstract`.

---

##  Why Use Abstract Classes and Methods?

Abstract classes and methods are useful when you want to **force all subclasses** to implement a particular functionality, but allow them to implement it **in their own way**.

It helps to define a common contract or rule that all child classes must follow.

This enables:

* Code consistency
* Reusability
* Better structure in large systems


##  Real Life Analogy

Imagine a **remote control**. Every brand (Sony, LG, Samsung) uses a similar remote (common reference), but the **functionality differs** based on the TV (object) you connect to.

In the same way, an abstract method defines **what** should happen, but the **actual behavior** is given by the specific subclass.

---

## 🔸 Important Notes

###  Can abstract class have constructor?

✅ Yes, it can. It is used when initializing variables in the subclass constructor.

###  Can abstract class have static methods?

✅ Yes, abstract classes can include static methods.

###  Can abstract method be private or static?

❌ No, because:

* `private` methods cannot be overridden in a subclass.
* `static` methods belong to the class, not the object, and **cannot be overridden**.

###  If a class is abstract, must it have abstract methods?

❌ No. A class can be abstract **even without** any abstract method. In that case, it’s just used to **prevent object creation**.

###  Can we create reference of abstract class?

✅ Yes, but the **object must be of a concrete subclass**.


## 🔸 Summary Table

| Feature                      | Abstract Class                          |
| ---------------------------- | --------------------------------------- |
| Can it have abstract method? | ✅ Yes                                   |
| Can it have concrete method? | ✅ Yes                                   |
| Can it be instantiated?      | ❌ No, only reference can be created     |
| Can constructor be used?     | ✅ Yes                                   |
| Use case                     | Partial implementation + Force override |


## ✅ Conclusion:

The `abstract` keyword in Java provides a **powerful mechanism** for designing flexible and scalable code. It enables you to define common behavior while still **forcing specific implementations** from child classes, thus supporting core Object-Oriented Programming principles like **abstraction** and **polymorphism**.

---

# Understanding Rules of Inheriting an Abstract Class in Java

When a class inherits from an abstract class in Java, there are some important rules and behaviors you must understand. Let's go step-by-step in a very simple and detailed manner:

## 🔹 Scenario:

An abstract class contains an abstract method, and a child class inherits this abstract class. Now depending on whether the child class overrides the abstract method or not, different outcomes occur.


##  Rule 1: If the Child Class Overrides All Abstract Methods

If the child class **provides implementation** for all inherited abstract methods, then that class is **considered complete**. Hence:

* The child class does **not need to be abstract**.
* You can create an object of that class.

**Summary:**

* ✅ Class is complete.
* ✅ Object creation is allowed.


##  Rule 2: If the Child Class Does NOT Override Abstract Methods

If the child class **does not override** one or more abstract methods from its parent abstract class, then Java considers the child class as **incomplete**. So:

* The child class **must be declared abstract**.
* You **cannot create an object** of the child class directly.

**Summary:**

* ❌ Class must be marked as abstract.
* ❌ Object creation is not allowed for that class.


##  Rule 3: Abstract Class Chaining

It's completely valid to create a **chain of abstract classes** where:

* One abstract class extends another abstract class.
* None of them implement the abstract methods.
* The concrete implementation is done in the final subclass.

**Example Logic:**

* AbstractClass1 (defines abstract method)
* AbstractClass2 extends AbstractClass1 (no override)
* ConcreteClass extends AbstractClass2 (provides override)

This is called **chained abstraction**.

**Summary:**

* ✅ Abstract method implementation can be delayed until the final class.
* ✅ Helps in creating reusable abstract layers.


##  Rule 4: Reference vs Object Creation

While you **cannot create an object** of an abstract class, you can still create a **reference variable** of it. This is important in **polymorphism**:

* You can assign the reference of the abstract class to an object of its concrete child class.
* But you can never instantiate an abstract class directly.

**Summary:**

* ✅ Reference creation: Allowed
* ❌ Object creation: Not allowed


##  Final Summary Table

| Condition                                                              | Result                      |
| ---------------------------------------------------------------------- | --------------------------- |
| Child class overrides all abstract methods                             | ✅ Class can be non-abstract |
| Child class does not override abstract methods                         | ❌ Must be declared abstract |
| Abstract method implemented in later child class (chained abstraction) | ✅ Valid                     |
| Abstract class reference variable creation                             | ✅ Allowed                   |
| Abstract class object creation                                         | ❌ Not Allowed               |


Understanding these rules ensures that you use abstraction correctly in Java, enabling better code organization and enforcing method contracts in inheritance hierarchies.

---

# Why Not All Methods Are Abstract in an Abstract Class?

##  Reason: Abstract Class Provides Partial Abstraction

An abstract class in Java is designed to provide **partial abstraction** — this means that it can contain a mix of both abstract (incomplete) and concrete (fully defined) methods.

If you want **100% abstraction** (i.e., every method is abstract and has no implementation), then you should use an **interface** instead of an abstract class.

##  Real-World Use Case

Sometimes, you want to:

* Enforce that certain methods **must be implemented** by child classes (these are abstract methods).
* Provide **some common functionality** that is shared across all child classes (these are concrete methods).

This is exactly where an abstract class is helpful.

##  Example Explanation (Conceptually)

Imagine you have an abstract class `Animal`:

* You declare an abstract method `sound()` because every animal has a different sound and must define it on its own.
* You also define a concrete method `eat()` because all animals eat in a similar way, and the logic is common.

So the abstract class allows you to **define common behavior once** and **force customization where needed**.

##  What If All Methods Are Abstract?

If you make **all methods abstract** in an abstract class:

* Then there is **no concrete logic** left in the class.
* The class is now acting as a **pure contract** — i.e., it only tells what needs to be done, not how.

In that case, Java recommends:

> "You should use an interface instead."

Why? Because interfaces are **meant** for 100% abstraction. Historically, interfaces only contained abstract methods (before Java 8). Even now, this remains their primary role.

##  Summary Table

| Point                             | Explanation                                                               |
| --------------------------------- | ------------------------------------------------------------------------- |
| Abstract Class                    | Provides partial abstraction (mix of abstract and non-abstract methods)   |
| Interface                         | Provides 100% abstraction (by default all methods were abstract)          |
| Why not all methods are abstract? | Because sometimes, we want to give common functionality directly in class |
| What if all methods are abstract? | Then use an interface instead of an abstract class                        |

---

# What is an Interface in Java?

An interface in Java is like a contract or an agreement. It only specifies what actions (methods) should be performed but does not provide the actual implementation of those actions. It only tells you **what to do**, but not **how to do it**.

## Use Case of Interface in Java

Interfaces are used when you want **100% abstraction**, meaning that you want the child classes to define the actual implementation. You only declare the method signatures in the interface, and the implementation is left to the classes that implement the interface.

## Syntax of Interface

An interface in Java only contains method declarations without any method bodies. Here’s an example of an interface:

- All methods inside an interface are public and abstract by default, which means they only have method names and signatures, but no actual code is written.

## How to Implement an Interface?

When a class implements an interface, it must provide the actual implementation for all the methods declared in the interface. This ensures that the class adheres to the contract set by the interface.

### Important Rules about Interfaces

- All methods inside an interface are **public** and **abstract** by default.
- All variables in an interface are **public**, **static**, and **final** by default. This means their values cannot be changed.
- You cannot create an object of an interface, but you can create a reference to it.
- A class can implement multiple interfaces in Java, which supports multiple inheritance (something that Java doesn’t support with classes).

## Advantages of Using Interfaces

1. **Loose Coupling**: The implementation of the methods can be done separately in different classes.
2. **100% Abstraction**: All method implementations are hidden, and only method signatures are provided.
3. **Code Reusability**: Multiple classes can implement the same interface.
4. **Support for Multiple Inheritance**: Unlike classes, a class can implement multiple interfaces.

---

# Method Bodies in Interfaces in Java

In Java, interfaces were traditionally used to define a contract where only method declarations existed, with no body. However, from Java 8 onwards, the concept of default and static methods was introduced, allowing method bodies in interfaces. Let’s break this down in detail.

## Rule for Method Bodies in Interfaces:

### Java 7 and Before:
Before Java 8, interfaces only allowed method declarations. This means you could define the method signature (method name, return type, parameters), but there was no possibility to provide the body or implementation of the method inside the interface.

- **Method Body**: Not allowed.

### Java 8 and Later:
Starting from Java 8, Java introduced two important concepts for interfaces: **default methods** and **static methods**. These methods allow an interface to have a body for certain methods.

1. **Default Method** (Method Body Allowed):
   Default methods in interfaces allow you to provide a method body inside the interface itself. This feature helps in providing a default behavior to classes that implement the interface, while still allowing them to override the method if needed.

   - Default methods have a method body.
   - The implementing class has the option to override the method or use the default implementation provided by the interface.

2. **Static Method** (Method Body Allowed):
   Static methods in interfaces allow the definition of methods with a body, which can be called directly on the interface without the need for an object. These methods are independent of the instances of the implementing classes.

   - Static methods also have a method body.
   - They can be called directly on the interface, not on the object.

3. **Abstract Methods** (No Method Body):
   Abstract methods in interfaces still do not have a method body. The body of these methods must be provided by the implementing class. These methods define the contract that the implementing class must follow.

## Summary:

- **Before Java 8**: Interfaces could only contain method declarations with no body. They defined the structure, but not the implementation.
  
- **Java 8 and After**: With the introduction of default and static methods, interfaces can now contain method bodies. However, abstract methods still don’t have a body, and the implementing class must provide the implementation.

In conclusion, while abstract methods in interfaces still require implementation by the implementing class, default and static methods provide flexibility to include some default behavior in the interface itself.
