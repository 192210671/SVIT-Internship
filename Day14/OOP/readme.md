

# ✅ Object-Oriented Programming (OOP) in Python

---

## 🌟 1. What is OOP?

* **Object-Oriented Programming (OOP)** is a programming paradigm that organizes software design around **objects**, rather than functions and logic.

* An **Object** is a real-world entity with **attributes (properties)** and **methods (functions)** that define its behavior.

* A **Class** is a blueprint/template for creating objects.

---

## ✅ 2. Key Concepts of OOP

### 1️⃣ Class

* A **class** is a user-defined blueprint or prototype that defines the variables and methods common to all objects of a certain kind.

#### ✅ Example:

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def display_info(self):
        print(f"Car Make: {self.make}, Model: {self.model}")

# Create an object
my_car = Car("Toyota", "Corolla")
my_car.display_info()
```

🔔 Output:

```
Car Make: Toyota, Model: Corolla
```

---

### 2️⃣ Object

* An **object** is an instance of a class.
* Each object can hold its own data (attributes) and use methods of the class.

---

### 3️⃣ Encapsulation

* **Encapsulation** is wrapping data (attributes) and methods into a single unit (class).
* Data is hidden from outside the class by using **private variables**.

#### ✅ Example:

```python
class BankAccount:
    def __init__(self, owner, balance):
        self.owner = owner
        self.__balance = balance  # Private attribute

    def deposit(self, amount):
        self.__balance += amount
        print(f"Deposited {amount}. New Balance: {self.__balance}")

    def get_balance(self):
        return self.__balance

# Usage
account = BankAccount("Eswar", 5000)
account.deposit(1500)
print(account.get_balance())    # Works
# print(account.__balance)     # ❌ Error: Cannot access private attribute
```

---

### 4️⃣ Abstraction

* **Abstraction** hides internal implementation details and shows only essential functionality to the user.
* Achieved by providing simple interfaces (methods).

#### ✅ Example:

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

# Usage
rect = Rectangle(5, 3)
print("Area of rectangle:", rect.area())
```

🔔 Output:

```
Area of rectangle: 15
```

---

### 5️⃣ Inheritance

* **Inheritance** allows a class to inherit properties and methods from another class.
* Promotes code reuse.

#### ✅ Example:

```python
# Parent Class
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        print(f"{self.name} makes a sound")

# Child Class
class Dog(Animal):
    def speak(self):
        print(f"{self.name} barks")

# Usage
dog = Dog("Tommy")
dog.speak()
```

🔔 Output:

```
Tommy barks
```

---

### 6️⃣ Polymorphism

* **Polymorphism** means “many forms”.
* A method can behave differently depending on the object calling it.

#### ✅ Example:

```python
class Cat:
    def sound(self):
        print("Cat meows")

class Dog:
    def sound(self):
        print("Dog barks")

def animal_sound(animal):
    animal.sound()

# Usage
cat = Cat()
dog = Dog()

animal_sound(cat)  # Output: Cat meows
animal_sound(dog)  # Output: Dog barks
```

---

### 7️⃣ Constructor (`__init__`)

* A special method called when an object is created.
* Used to initialize object attributes.

#### ✅ Example:

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print(f"Name: {self.name}, Age: {self.age}")

person = Person("Eswar", 22)
person.display()
```

---

### 8️⃣ Destructor (`__del__`)

* Called when an object is destroyed (optional in Python due to garbage collection).

#### ✅ Example:

```python
class Test:
    def __init__(self):
        print("Object created")

    def __del__(self):
        print("Destructor called, object deleted")

obj = Test()
del obj
```

---

### 9️⃣ Class Variables vs Instance Variables

| Feature               | Class Variables | Instance Variables      |
| --------------------- | --------------- | ----------------------- |
| Shared by all objects | Yes             | No (specific to object) |
| Example               | Company name    | Employee name, age      |

#### ✅ Example:

```python
class Employee:
    company = "ABC Corp"  # Class variable

    def __init__(self, name, age):
        self.name = name  # Instance variable
        self.age = age

e1 = Employee("Eswar", 22)
e2 = Employee("Anitha", 25)

print(e1.company)  # ABC Corp
print(e2.company)  # ABC Corp
print(e1.name)     # Eswar
```

---

### 🔥 Summary of Key Concepts

| Concept       | Purpose                                    |
| ------------- | ------------------------------------------ |
| Class         | Blueprint for creating objects             |
| Object        | Instance of a class                        |
| Encapsulation | Data hiding                                |
| Abstraction   | Expose only necessary features             |
| Inheritance   | Child class inherits from parent class     |
| Polymorphism  | Methods behave differently based on object |
| Constructor   | Initializes object attributes              |
| Destructor    | Clean up when object is deleted            |

---

## ✅ Real-World Analogy

* Class → Blueprint (like a house plan)
* Object → Actual house built from blueprint
* Encapsulation → Keep electrical wiring hidden from users
* Abstraction → Power button hides internal circuitry
* Inheritance → A car is a type of vehicle (Vehicle → Car)
* Polymorphism → Different appliances responding differently to the same button press

---

##  Final Thoughts

OOP makes code:

* Easy to maintain and organize
* Reusable through inheritance
* Readable and scalable

---
