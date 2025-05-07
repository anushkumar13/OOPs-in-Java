#  Encapsulation in Java

##  What is Encapsulation?

Encapsulation means **wrapping data and code together** in a single unit and **restricting direct access** to some of the object’s components.

###  Simple Definition:

> "Encapsulation = Data (variables) + Code (methods) wrapped inside a class, with restricted access to data."

Instead of accessing data directly, users should interact with it **only through methods** (getters and setters). This helps maintain control, security, and consistency.

---

##  Real-Life Example

Think of a **medicine capsule**:

- It contains many chemicals inside it.
- But a patient never directly consumes the raw chemicals.
- The capsule's outer shell protects and **delivers the medicine in a controlled way**.

🔁 Similarly in Java:

- Variables = sensitive data  
- You **hide them** using `private` access modifier  
- And provide access **only through public methods**

---

## Steps to Achieve Encapsulation in Java

### 1. Make data members private:
We make the variables (data members) of the class private so that no one can access them directly from outside the class.

### 2. Provide public getter and setter methods:
Then, we make getter and setter methods public, so that users can read or update the data. However, direct access to the data members is restricted.

### 3. Wrap everything inside a class:
All the data and methods are properly wrapped inside a class to maintain encapsulation.

---

## Benefits of Encapsulation

### 1. Data Security:
Sensitive data is kept secure. Users cannot directly change the data.

### 2. Controlled Access:
You decide what data to expose and how to expose it through getter/setter methods.

### 3. Code Flexibility:
If you need to make changes to any method in the future, you only need to modify the method, not the entire program.

---

## Encapsulation in a Bank Account

Imagine a bank account where you have private information like your account number and balance. You wouldn’t want anyone to directly change these details, right? That’s where **encapsulation** comes in.

In a bank, your **account number** and **balance** are **private**. They are not exposed to the outside world. To interact with these details, you use public methods like `deposit()` and `withdraw()`.

### Data Security:
Your `balance` is private. No one can directly change it. If you want to add money, you use the `deposit()` method. If you want to withdraw money, you use the `withdraw()` method. These methods have built-in checks to make sure you can’t withdraw more than what’s available in your account.

### Controlled Access:
The bank provides a controlled way of accessing and modifying data. For example, you can’t directly access your balance. Instead, you call the `getBalance()` method, which returns your balance in a secure way. This ensures that only valid operations can happen.

### Code Flexibility:
If in the future, the bank wants to change how the interest is calculated or how fees are applied, it can modify the logic inside the `deposit()` and `withdraw()` methods without affecting the rest of the system. All the operations outside (like transferring money, showing balance) remain the same.

In this way, **encapsulation** keeps your bank account safe and easy to manage, while allowing you to perform specific actions without direct access to sensitive data.

## Benefits of Encapsulation in this Example?

### 1. Data Security:
Your `accountNumber` and `balance` are not directly exposed. They can only be accessed through methods.

### 2. Controlled Access:
While performing operations like deposit or withdrawal, validation ensures that illegal actions do not occur. For example, if a user tries to withdraw more than their balance, the transaction will be rejected.

### 3. Code Flexibility:
If you need to change the logic for updating the balance (like adding interest, fees, etc.), you only need to modify the `deposit()` and `withdraw()` methods. The rest of the class code remains unaffected.

---


