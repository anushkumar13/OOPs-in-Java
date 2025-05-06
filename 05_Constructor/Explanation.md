##  What is a Constructor?

### Definition:
A constructor is a special method that is automatically called when an object of a class is created.

Its purpose is to initialize the object (i.e., to set the values of the object's variables).

The name of the constructor must be the same as the class name, and it does not have a return type (neither `void` nor any data type).

---

## Constructor Characteristics:

### Same Name as Class:
The constructor's name must always be the same as the class name.

### No Return Type:
A constructor does not have any return type. Hence, you don't specify `void` or any data type for it.

### Automatic Invocation:
When you create an object of a class using the `new` keyword, the constructor is automatically called.

### Initialization:
The primary task of a constructor is to initialize the object's variables.

---

##  Types of Constructors:

### Default Constructor:
When you don't write a constructor, Java automatically creates a default constructor. It has no parameters and assigns default values to the object's instance variables.

### Parameterized Constructor:
In this type, you pass parameters to the constructor to set specific values for the object's variables when the object is created.

---

##  Role of Constructors in Life:

### Initialization:
When you create an object, the constructor automatically initializes the object's variables. You don't need to manually set them.

### Overloading:
You can create multiple constructors with different parameters (this is known as constructor overloading).

---

##  Summary:
A constructor is a special method that is automatically called when an object is created and is responsible for initializing the object.

Its name must be the same as the class name, and it has no return type.

A Default Constructor is parameterless, while a Parameterized Constructor initializes the object with the values you provide.

---

##  What is a Default Constructor?

### Definition:
A default constructor is a constructor that is automatically created if you don't explicitly write a constructor in your class.

When you create an object using the `new` keyword, the default constructor is automatically called and assigns default values to your instance variables.

### Key Points About Default Constructor:

- **No Parameters:** The default constructor does not take any parameters.
- **Initialization:** This constructor assigns default values to instance variables. 
    - For example: 
        - `int` is assigned `0`
        - `String` is assigned `null`
        - `boolean` is assigned `false`, etc.
- **No Explicit Definition:** If you don't define a constructor in your class, Java automatically creates a default constructor for you.

---

## Role of Default Constructor:

- When you don’t write a constructor in your class, the default constructor is automatically created.
- Through the default constructor, the object’s instance variables are assigned default values.

## When is the Default Constructor Called in Java?
- The default constructor is called when you create an object and you haven't defined any constructor.
- If you define your own constructor (whether it's parameterized or default), Java will not create the default constructor automatically.

---

## Summary:
A default constructor is a constructor that is automatically created if you don't explicitly write any constructor in your class. 

This constructor assigns default values to the instance variables.

If you define your own constructor, Java will not provide the default constructor.

---

## Role of Constructor in Initialization:

A constructor gives you the opportunity to initialize default values with meaningful ones. 

When you explicitly define your constructor, you can assign custom values to the instance variables of the object during creation. In other words, you can replace the default values with values you choose.

### Example:
Imagine you have a `Student` class where you need to initialize `name` and `age`. If you use the default constructor, the variables will be assigned default values (like `null` and `0`). But if you create a parameterized constructor, you can assign the desired values when the object is created.

---

## Non-Parameterized Constructor (Default Constructor)

### Definition:
A non-parameterized constructor is a constructor that does not take any parameters. When you create an object, you do not pass any specific values.

If you do not explicitly define a constructor, Java automatically creates a default constructor for you.

### Characteristics:
- **No Parameters**: This constructor does not take any parameters.
- **Used for Default Initialization**: It is generally used to assign default values to the object's instance variables, such as `null`, `0`, etc.

---

## Parameterized Constructor

### Definition:
A parameterized constructor is a constructor in which you pass parameters when creating an object.

This allows you to provide specific values for the object's instance variables at the time of object creation.

### Characteristics:
- **Has Parameters**: You pass parameters when creating the object.
- **Used for Custom Initialization**: This constructor assigns custom values to the object's instance variables, which you provide as arguments in the constructor.

--- 


