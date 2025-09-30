# Exp-13-Overloading
# Polymorphism and Overloading in C++

### AIM

To explore **Polymorphism in C++** with a focus on **Overloading**, including:

* Constructor Overloading
* Function Overloading
* Operator Overloading

---

## Introduction to Overloading in C++

In C++, **overloading** allows multiple functions, constructors, or operators to share the same name but differ in **parameter lists** or **behaviors**.

**Purpose:**

* Improve **readability**
* Enhance **flexibility**
* Promote **code reusability**

The compiler determines which version to execute based on the **number or type of arguments** provided.

---

## Theory

### Polymorphism

Polymorphism allows a single name to take on **multiple forms**.

* **Compile-time polymorphism** is achieved through **overloading**.
* Functions, constructors, and operators can behave differently depending on input.

---

## 1️⃣ Constructor Overloading

**Definition:**
Multiple constructors in a class with different parameter lists.

**Purpose:**
Enable objects to be initialized in various ways depending on provided arguments.

**Key Points:**

* All constructors share the **class name**.
* Differentiated by **number or type of parameters**.
* Improves **flexibility and readability**.

**Example:**

```cpp
#include <iostream>
using namespace std;

class Student {
    string name;
    int age;

public:
    Student() { name = "Unknown"; age = 0; }
    Student(string n) { name = n; age = 0; }
    Student(string n, int a) { name = n; age = a; }

    void display() { cout << "Name: " << name << ", Age: " << age << endl; }
};

int main() {
    Student s1;
    Student s2("Rahul");
    Student s3("Ananya", 21);

    s1.display();
    s2.display();
    s3.display();
}
```

---

## 2️⃣ Function Overloading

**Definition:**
Multiple functions with the same name but **different parameter lists**.

**Purpose:**
Perform similar operations on **different types or numbers of inputs**.

**Key Points:**

* Cannot overload based on **return type alone**.
* Parameter lists must differ.
* Resolved at **compile-time**.

**Example:**

```cpp
#include <iostream>
using namespace std;

class Calculator {
public:
    int add(int a, int b) { return a + b; }
    int add(int a, int b, int c) { return a + b + c; }
};

int main() {
    Calculator calc;
    cout << "Sum1: " << calc.add(10, 20) << endl;
    cout << "Sum2: " << calc.add(10, 20, 30) << endl;
}
```

---

## 3️⃣ Operator Overloading

**Definition:**
Redefining the behavior of operators (`+`, `-`, `*`, `==`, etc.) for **user-defined types**.

**Purpose:**
Enable objects to interact using operators naturally, like primitive types.

**Key Points:**

* Defined using the **operator keyword**.
* Enhances **readability and usability** for custom types.
* Cannot overload certain operators: `::`, `sizeof`, `?:`, `.`

**Syntax:**

```cpp
class ClassName {
public:
    returnType operator op(argument) {
        // operator implementation
    }
};
```

---

## Differences Between Overloading Types

| Feature              | Constructor Overloading                         | Function Overloading                                       | Operator Overloading                         |
| -------------------- | ----------------------------------------------- | ---------------------------------------------------------- | -------------------------------------------- |
| **Definition**       | Multiple constructors with different parameters | Multiple functions with same name but different parameters | Redefining operators for user-defined types  |
| **Purpose**          | Create objects in different ways                | Perform similar operations on different inputs             | Make operators work with objects intuitively |
| **Usage**            | Inside class only (constructors)                | Inside or outside classes                                  | With user-defined types (classes/structs)    |
| **Compile-time?**    | Yes                                             | Yes                                                        | Yes                                          |
| **Return Type**      | Not applicable                                  | Cannot overload by return type alone                       | Can differ, but parameters must matter       |
| **Example Use Case** | Initialize objects in multiple ways             | Add numbers of different types                             | Add two complex numbers using `+`            |

---

## Conclusion

* Overloading is a form of **compile-time polymorphism** in C++.
* It improves **code clarity, reusability, and flexibility**.
* **Constructor overloading** allows multiple ways to create objects.
* **Function overloading** enables performing similar tasks with different inputs.
* **Operator overloading** allows intuitive use of operators with custom types.
