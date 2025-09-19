

# 📘 **Inheritance in Python**

## 🔹 1. What is Inheritance?

* **Definition**: Inheritance is an **Object-Oriented Programming (OOP)** concept where a class (called **child class / subclass**) can **reuse the properties and methods** of another class (called **parent class / superclass**).
* It avoids code duplication and promotes **reusability**.

👉 **Analogy**:
Think of **family inheritance**:

* A child inherits traits (like eyes, hair color) from their parents.
* But the child can also have **unique traits** of their own.
* Similarly, in Python, a subclass inherits attributes and methods from its parent class but can also define new ones or modify existing ones.

---

## 🔹 2. Why Use Inheritance?

* Reuse existing code.
* Reduce duplication.
* Make programs easier to maintain and extend.
* Enable polymorphism (subclasses behave differently for the same function).

---

## 🔹 3. Basic Syntax

```python
class Parent:
    def parent_method(self):
        print("This is parent class method")

class Child(Parent):  # Inheriting Parent class
    def child_method(self):
        print("This is child class method")

# Usage
c = Child()
c.parent_method()  # Inherited from Parent
c.child_method()   # Defined in Child
```

---

## 🔹 4. Types of Inheritance in Python

### 1. **Single Inheritance**

👉 A child class inherits from one parent class.

**Example:**

```python
class Animal:
    def speak(self):
        print("Animals can speak in their own way")

class Dog(Animal):  # Single inheritance
    def bark(self):
        print("Dog barks")

d = Dog()
d.speak()  # Inherited
d.bark()   # Child method
```

---

### 2. **Multiple Inheritance**

👉 A child class inherits from **more than one parent class**.

**Example:**

```python
class Father:
    def skills(self):
        print("Father: Driving, Teaching")

class Mother:
    def skills(self):
        print("Mother: Cooking, Painting")

class Child(Father, Mother):  # Multiple inheritance
    def skills(self):
        print("Child: Gaming, ", end="")
        Father.skills(self)
        Mother.skills(self)

c = Child()
c.skills()
```

---

### 3. **Multilevel Inheritance**

👉 A class inherits from a child class (grandparent → parent → child).

**Example:**

```python
class Grandparent:
    def family_name(self):
        print("Family Name: Johnson")

class Parent(Grandparent):
    def profession(self):
        print("Parent Profession: Engineer")

class Child(Parent):  # Multilevel
    def hobby(self):
        print("Child Hobby: Football")

c = Child()
c.family_name()
c.profession()
c.hobby()
```

---

### 4. **Hierarchical Inheritance**

👉 Multiple child classes inherit from the **same parent class**.

**Example:**

```python
class Vehicle:
    def start(self):
        print("Vehicle started")

class Car(Vehicle):
    def wheels(self):
        print("Car has 4 wheels")

class Bike(Vehicle):
    def wheels(self):
        print("Bike has 2 wheels")

car = Car()
bike = Bike()
car.start()
car.wheels()
bike.start()
bike.wheels()
```

---

### 5. **Hybrid Inheritance**

👉 Combination of multiple inheritance types.

**Example:**

```python
class A:
    def featureA(self):
        print("Feature A")

class B(A):
    def featureB(self):
        print("Feature B")

class C(A):
    def featureC(self):
        print("Feature C")

class D(B, C):  # Hybrid
    def featureD(self):
        print("Feature D")

d = D()
d.featureA()
d.featureB()
d.featureC()
d.featureD()
```

---

## 🔹 5. Method Overriding in Inheritance

👉 Child class can redefine (override) a method of the parent class.

**Example:**

```python
class Animal:
    def sound(self):
        print("Animals make sounds")

class Dog(Animal):
    def sound(self):  # Overriding
        print("Dog barks")

d = Dog()
d.sound()  # Overridden method
```

---

## 🔹 6. The `super()` Keyword

👉 Used to call methods/attributes of the parent class inside the child class.

**Example:**

```python
class Person:
    def __init__(self, name):
        self.name = name
    
    def display(self):
        print("Name:", self.name)

class Student(Person):
    def __init__(self, name, grade):
        super().__init__(name)  # Call parent constructor
        self.grade = grade
    
    def display(self):
        super().display()  # Call parent method
        print("Grade:", self.grade)

s = Student("Eswar", "A")
s.display()
```

---

## 🔹 7. The `isinstance()` and `issubclass()`

* `isinstance(obj, Class)` → Checks if `obj` belongs to `Class`.
* `issubclass(Sub, Parent)` → Checks if a class is a subclass of another.

**Example:**

```python
class Parent: pass
class Child(Parent): pass

c = Child()
print(isinstance(c, Child))   # True
print(isinstance(c, Parent))  # True
print(issubclass(Child, Parent)) # True
```

---

## 🔹 8. Real-Life Example of Inheritance

👉 **Bank Application Example**

```python
class Account:
    def __init__(self, name, balance):
        self.name = name
        self.balance = balance
    
    def show_balance(self):
        print(f"{self.name}'s Balance: {self.balance}")

class SavingsAccount(Account):  # Inheriting
    def __init__(self, name, balance, interest_rate):
        super().__init__(name, balance)
        self.interest_rate = interest_rate
    
    def add_interest(self):
        self.balance += self.balance * self.interest_rate
        print("Interest added!")

s = SavingsAccount("Eswar", 5000, 0.05)
s.show_balance()
s.add_interest()
s.show_balance()
```

---

## 📝 **Summary**

* Inheritance allows **code reuse**.
* Types: **Single, Multiple, Multilevel, Hierarchical, Hybrid**.
* Supports **method overriding** and **`super()`**.
* Real-life analogy: **Child inherits traits from parents**.
* Makes code **cleaner, reusable, and extensible**.

---

👉 Do you want me to also create a **comparison table of all inheritance types** (with definition + example code + output) so it’s easier to study quickly?
