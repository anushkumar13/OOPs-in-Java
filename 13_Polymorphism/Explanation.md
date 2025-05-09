#  Polymorphism in Java — Full Detailed Guide

##  What is Polymorphism?

**Polymorphism** is derived from two Greek words:

* **"Poly"** = many
* **"Morph"** = forms

So, polymorphism means **"one thing in many forms"**.

In Java, polymorphism means:

> One method or object behaves differently based on the context.


##  Real-Life Analogy

Imagine a single human being playing multiple roles:

* At home: **a son/daughter**
* In college: **a student**
* In a market: **a customer**
* Online: **a user**

Even though it's the same person, behavior changes based on the situation.
That is exactly what **polymorphism** is in Java!

---

##  Types of Polymorphism in Java

| Type         | Description        |
| ------------ | ------------------ |
| Compile-Time | Method Overloading |
| Run-Time     | Method Overriding  |

---

##  1. Compile-Time Polymorphism (Method Overloading)

This happens **within the same class** where:

* The method name remains the same
* But the number, type, or order of arguments is different

**Key Point**:
The decision of which method to call is made **at compile time** by the compiler. Hence, it's called **Compile-Time Polymorphism**.


##  2. Run-Time Polymorphism (Method Overriding)

This happens **between parent and child classes**, where:

* A method in the parent class is **overridden** in the child class with the same name and parameters.

**Key Point**:
The method to be executed is decided **at runtime**, based on the actual object. This is known as **Dynamic Method Dispatch**, hence called **Run-Time Polymorphism**.


##  Why Use Polymorphism?

* Makes the code **more flexible** and **reusable**
* Allows handling of **multiple behaviors** using a single interface or reference
* Supports **runtime decisions** for method execution
* Helps in writing **easily maintainable** and **extensible** code


##  Summary Table

| Type         | Name               | Decided When?    | Based On                              |
| ------------ | ------------------ | ---------------- | ------------------------------------- |
| Compile-Time | Method Overloading | Compilation Time | Number / Type / Order of parameters   |
| Run-Time     | Method Overriding  | Runtime          | Actual object type (dynamic dispatch) |


##  Real-Life Analogy (Again!)

| Situation   | Action/Response                  |
| ----------- | -------------------------------- |
| Phone rings | Mom picks up: "Hello beta"       |
|             | Friend picks up: "Kya haal hai?" |
|             | Boss picks up: "Yes sir?"        |

**Same action** = phone call is picked up, but the **response changes** depending on who answers.

That's Polymorphism in real life — and the same applies to Java objects and methods!

---

#  Binding in Java — Complete Explanation

##  What is Binding in Java?

Binding in Java refers to the process of linking a method call with its actual method body (definition).

In simple terms, when Java decides *which* method to run in a program, that decision-making process is called **Binding**.

##  Types of Binding in Java

| Type            | Also Known As | When is it Decided? | Related Concept    |
| --------------- | ------------- | ------------------- | ------------------ |
| Static Binding  | Early Binding | Compile Time        | Method Overloading |
| Dynamic Binding | Late Binding  | Runtime             | Method Overriding  |

This file will focus entirely on **Static Binding (Early Binding)** with deep, line-by-line clarity.

---

##  Static Binding (Early Binding) in Java — Complete Detail

###  What is Static Binding?

Static binding means that the method call is resolved at **compile time**. The Java compiler already decides which method will be called even *before* the program is run.

###  Why is it called "Early Binding"?

Because the method or variable is linked or bound **early** — i.e., during compilation — rather than at runtime.

###  When Does Static Binding Happen in Java?

Java performs static binding in the following cases:

* For **static** methods
* For **private** methods
* For **final** methods
* In **method overloading**

All of these are resolved based on **reference type** and not object type.

###  What Does Java Look At — Reference or Object?

➡ **Static Binding only checks the reference type**, not the object type.

That means:

* If a method is `static`, `final`, or `private`, then during method call, the **reference type** is what determines which method will be used.
* Even if the actual object belongs to a subclass, Java will not consider it during static binding.

###  Real-World Example Explanation

If a `Dog` object is assigned to a `Animal` reference and a static method `display()` is called, the method in `Animal` class will be executed — not the one in `Dog`. This is because the binding is done **statically**, using the **reference type**.

###  What About Private and Final Methods?

Private and Final methods are also statically bound:

* **Private** methods cannot be overridden, so compiler binds them early.
* **Final** methods are locked from being overridden, so they too are bound at compile time.

Even calling a private method from within a public method still uses early binding.

###  Method Overloading Uses Static Binding Too

In method overloading:

* Multiple methods with the same name but different parameters exist
* Java determines **at compile time** which method to call based on the argument types, number, and order

This selection is done using static binding.

###  Performance Advantage of Static Binding

Static Binding is **faster** because:

* No decision-making is needed at runtime
* The method's memory address is already known during compilation
* There’s **no dynamic dispatch** or runtime lookup, which saves performance


##  Summary Table: Static Binding

| Feature                 | Static Binding                             |
| ----------------------- | ------------------------------------------ |
| When is it decided?     | Compile Time (Early)                       |
| Who decides it?         | Java Compiler                              |
| What is considered?     | Reference Type                             |
| Is object type checked? | ❌ No                                       |
| Applies to              | static, private, final, overloaded methods |
| Speed                   | Fast (No runtime method dispatch)          |


This is the complete conceptual explanation of **Static Binding (Early Binding)** in Java.

---

# Dynamic Binding (Late Binding) in Java — Complete Explanation

## What is Dynamic Binding?

Dynamic Binding, also called Late Binding, means that:

> The decision about which method to call is made during **runtime**, not at compile time.

Java uses dynamic binding when it encounters method overriding. It checks the actual object (not the reference type) during program execution to decide which method implementation to execute.


## When Does Java Use Dynamic Binding?

Java performs dynamic binding in the case of **method overriding**, especially when:

* A parent class reference variable is used to refer to a child class object.
* The method being called is overridden in the child class.

At runtime, Java checks the actual class of the object and invokes the overridden method from the appropriate class.


## Important Conditions for Dynamic Binding

Dynamic Binding only happens when:

* The method is **overridden**.
* The method is **not** static.
* The method is **not** final.
* The method is **not** private.

If any of these conditions are violated, dynamic binding will not take place.


## Reference Type vs Object Type in Dynamic Binding

In Dynamic Binding:

> Java decides method execution based on the **object type**, not the reference type.

* If the object is of the subclass, the method of the subclass will execute — even if the reference type is the parent class.
* This supports polymorphism in Java.


## Why Is It Called "Late Binding"?

It’s called **Late Binding** because:

* Java does not resolve the method call during compilation.
* The decision is made **later**, during the actual execution of the program.

This is why it's also known as runtime polymorphism.


## Real-World Analogy of Dynamic Binding

Imagine you have a **remote control** (reference type: Animal), but the **actual TV** it's connected to is of a specific brand (object type: Dog).

* The remote (reference) is generic.
* The actual TV (object) decides what will happen when you press a button.

So when you press a button like `sound()`, the **specific TV brand's behavior** (e.g., Dog's overridden method) is what you'll experience — not the generic remote behavior.


## Summary Table: Dynamic Binding vs Static Binding

| Feature                        | Static Binding                                   | Dynamic Binding                           |
| ------------------------------ | ------------------------------------------------ | ----------------------------------------- |
| **Binding Time**               | Compile Time                                     | Runtime                                   |
| **Based On**                   | Reference Type                                   | Object Type                               |
| **Use Case**                   | Method Overloading, static/final/private methods | Method Overriding                         |
| **Performance**                | Fast                                             | Slightly Slower (due to runtime dispatch) |
| **Example**                    | `a.display()` (static method)                    | `a.sound()` (overridden method)           |
| **Flexibility (Polymorphism)** | Low                                              | High                                      |


## Interview Tip:

If a method is:

* **static**
* **final**
* **private**

→ Then **Static Binding** will be used.

If a method is:

* **Overridden** (in a subclass)

→ Then **Dynamic Binding** will be used.


Dynamic Binding plays a key role in achieving **runtime polymorphism**, allowing Java programs to be flexible and scalable based on actual object behavior, not just reference types.

---

# Run-Time Polymorphism in Java

##  What is Run-Time Polymorphism?

Run-time polymorphism in Java means that the decision of which method to call is taken by the JVM at **run-time**, based on the **actual object type**, not the reference type.

It allows different behaviors for the same method depending on which class’s object is being referenced.

##  Why is it called "Run-Time"?

It is called run-time polymorphism because the binding of method call to the actual method body is **delayed until the program runs**. That means Java doesn’t decide the method call during compile time, but instead it waits till the object is created at runtime.

##  When does Run-Time Polymorphism occur in Java?

Run-time polymorphism occurs when:

* **Method overriding** is used
* A **parent class reference** is used to refer to a **child class object**

##  Real-World Analogy

Imagine a **universal TV remote** — it can control any brand like LG or Sony.

* The remote control is the **parent class reference**.
* The specific TV brand (LG, Sony, etc.) is the **child class object**.
* When you press a button, the actual function depends on **which TV (object)** is connected, not on the remote itself.

This dynamic behavior is similar to **run-time polymorphism**.

##  Step-by-Step Explanation of How it Works:

1. A **reference variable** is declared with the **parent class type**.
2. The **object** assigned to that reference is of a **child class**.
3. The **child class overrides** a method from the parent class.
4. When the method is called using the parent reference, Java looks at the **actual object’s type** (not the reference) and invokes the overridden method of the **child class**.

##  Key Points to Remember

* Only **non-static**, **non-final**, and **non-private** methods can be **overridden** and used in run-time polymorphism.
* Run-time polymorphism always depends on **object type**, not reference type.
* Another name for this behavior is **Dynamic Method Dispatch**.

##  Advantages of Run-Time Polymorphism

| Benefit             | Description                                                                  |
| ------------------- | ---------------------------------------------------------------------------- |
|  Flexibility       | Code becomes more flexible and can support new types easily.                 |
|  Maintainability   | New child classes can be added without changing the parent class logic.      |
|  True Polymorphism | Multiple objects can behave differently with the same interface/method call. |

##  Common Interview Question

**Q: What is the difference between Method Overloading and Method Overriding?**

* **Method Overloading** → Compile-time polymorphism
* **Method Overriding** → Run-time polymorphism

##  Real-Life Example: Bank Scenario

* Suppose there is a `Bank` class with a method `getRateOfInterest()`.
* Different banks like `SBI` and `HDFC` override this method with their own interest rates.
* Using the `Bank` reference, you can assign it to `SBI` or `HDFC` objects.
* At runtime, Java will decide which bank’s rate method to call based on the **object type**, not the reference.

This scenario shows how **run-time polymorphism** gives real flexibility to software systems by allowing one interface to be used for different underlying forms (data types).
