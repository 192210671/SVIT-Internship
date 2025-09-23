

# **Polymorphism in OOP**

---

## **1. What is Polymorphism?**

* **Definition**:
  *Polymorphism* means **“many forms”**.
  In Object-Oriented Programming (OOP), polymorphism allows the **same method or operator** to perform **different tasks** depending on the object or the context.

* It helps achieve **flexibility, reusability, and extensibility** in code.

---

## **2. Analogy**

Imagine the word **“Run”**:

* A person **runs** 🏃‍♂️.
* A car **runs** 🚗.
* A program **runs** 💻.

👉 The word “run” is **the same**, but its **behavior changes** depending on the object.
This is exactly what **polymorphism** is in programming.

---

## **3. Types of Polymorphism**

### **A. Compile-time Polymorphism (Static)**

* Also called **Method Overloading** or **Operator Overloading**.
* Decided **at compile time**.
* Same function/operator behaves differently with **different inputs**.

📌 **Python Example (Operator Overloading)**:

```python
print(5 + 10)       # Adds numbers (15)
print("Hi" + "All") # Concatenates strings ("HiAll")
```

📌 **Java Example (Method Overloading)**:

```java
class MathOps {
    int add(int a, int b) {
        return a + b;
    }
    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class Demo {
    public static void main(String[] args) {
        MathOps m = new MathOps();
        System.out.println(m.add(2, 3));    // 5
        System.out.println(m.add(2, 3, 4)); // 9
    }
}
```

---

### **B. Runtime Polymorphism (Dynamic)**

* Also called **Method Overriding**.
* Decided **at runtime**.
* A subclass provides a **specific implementation** of a method that is already defined in its parent class.

📌 **Python Example (Method Overriding)**:

```python
class Animal:
    def sound(self):
        print("Animals make sound")

class Dog(Animal):
    def sound(self):
        print("Dog barks")

class Cat(Animal):
    def sound(self):
        print("Cat meows")

# Usage
animals = [Dog(), Cat(), Animal()]
for a in animals:
    a.sound()
```

🔹 Output:

```
Dog barks
Cat meows
Animals make sound
```

📌 **Java Example (Method Overriding)**:

```java
class Animal {
    void sound() {
        System.out.println("Animals make sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Demo {
    public static void main(String[] args) {
        Animal a1 = new Dog();
        Animal a2 = new Cat();
        a1.sound(); // Dog barks
        a2.sound(); // Cat meows
    }
}
```

---

## **4. Polymorphism in Python**

Python is **dynamically typed**, so it naturally supports polymorphism without explicit overloading.

Example:

```python
def multiply(a, b):
    return a * b

print(multiply(2, 3))        # 6 (int * int)
print(multiply("Hi", 3))     # HiHiHi (string * int)
```

---

## **5. Benefits of Polymorphism**

1. **Code Reusability** – Write one method, use it for multiple types.
2. **Flexibility** – The same interface can work with different data types or classes.
3. **Extensibility** – New classes can extend existing ones and override behavior.
4. **Maintainability** – Cleaner, more understandable code.

---

## **6. Key Differences Between Overloading & Overriding**

| Feature            | Method Overloading 🟦                  | Method Overriding 🟩                |
| ------------------ | -------------------------------------- | ----------------------------------- |
| **Definition**     | Same method name, different parameters | Subclass redefines method of parent |
| **Type**           | Compile-time polymorphism              | Runtime polymorphism                |
| **Inheritance**    | Not required                           | Must have inheritance               |
| **Python Support** | Simulated with default args/`*args`    | Fully supported                     |
| **Java Support**   | Fully supported                        | Fully supported                     |

---

## **7. Real-Life Use Case**

* **Banking App** 🏦

  * A generic method `calculateInterest()` can be **overridden** by `SavingsAccount`, `FixedDepositAccount`, etc.
  * Same name, but behavior differs.
* **E-commerce App** 🛒

  * A function `checkout(item)` can be **overloaded** to work for **single item, multiple items, or coupons**.

---

✅ **In short**:

* **Polymorphism = many forms (same name, different behavior).**
* Achieved via **Overloading (compile-time)** and **Overriding (runtime)**.
* Helps write **flexible, reusable, and clean OOP code**.



---

# ✅ **Method Overriding in Python**

👉 **Yes, Python fully supports method overriding.**

* Happens when a **subclass redefines a method** from its parent class.
* It is **runtime polymorphism**.

📌 Example:

```python
class Animal:
    def sound(self):
        print("Animals make sound")

class Dog(Animal):
    def sound(self):   # Overriding
        print("Dog barks")

a = Animal()
a.sound()   # Animals make sound

d = Dog()
d.sound()   # Dog barks
```

---

# ❌ **Method Overloading in Python (Not Directly Supported)**

👉 Unlike Java or C++, Python **does not support method overloading directly** (same method name with different parameter lists).

If you define multiple methods with the same name, **the last one overrides the previous ones**.

📌 Example:

```python
class Demo:
    def show(self, a):
        print("One argument:", a)

    def show(self, a, b):  # This overwrites the first one
        print("Two arguments:", a, b)

obj = Demo()
# obj.show(5)   # ❌ Error: missing argument
obj.show(5, 10)  # ✅ Works, prints "Two arguments: 5 10"
```

---

# 🌀 But... Python Simulates Overloading

Since Python is **dynamic**, you can mimic overloading using:

* **Default arguments**
* `*args` / `**kwargs`

📌 Example (simulated overloading):

```python
class MathOps:
    def add(self, *args):
        return sum(args)

m = MathOps()
print(m.add(2, 3))        # 5
print(m.add(2, 3, 4))     # 9
print(m.add(1, 2, 3, 4))  # 10
```

---

# 🎯 Final Answer

* ✅ **Method Overriding** → Supported in Python.
* ❌ **Method Overloading** → Not supported directly, but can be simulated with \**default arguments, *args, or single method handling multiple types**.

---

👉 Do you want me to also compare this with **Java/C++ support** side by side (since they support both natively)?
