# Assignment 7
# 1. Student Details
Create a class Student with attributes name and age. Write a method to display
the student details.


```python
class Student:
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def display_info(self):
        print("-----------------Details---------------\n")
        print("Name: ",self.name)
        print("Age: ",self.age)
        
s1=Student("Eswar",20)
s1.display_info()
```

    -----------------Details---------------
    
    Name:  Eswar
    Age:  20
    

# 2.Rectangle Area
Create a class Rectangle with attributes length and breadth. Add a method to
calculate and return the area.


```python
class Rectangle:
    def __init__(self,length,breadth):
        self.length=length
        self.breadth=breadth
    def area(self):
        return self.length*self.breadth
R1=Rectangle(20.5,22)
print("Area of Rectangle: ",R1.area())
```

    Area of Rectangle:  451.0
    

# 3. Car Information
Create a class Car with attributes brand, model, and price. Write a method to
return a formatted string about the car.


```python
class Car:
    def __init__(self,brand,model,price):
        self.brand=brand
        self.model=model
        self.price=price
    def info(self):
        return f"Brand : {self.brand} ,Model: {self.model} , Price: {self.price} "
C1=Car("TATA","XUV",1200000)  
print("---------Details--------\n",C1.info())
```

    ---------Details--------
     Brand : TATA ,Model: XUV , Price: 1200000 
    

# 4. Bank Account
Create a class BankAccount with attributes account_holder and balance. Add
methods to deposit money, withdraw money, and check balance.


```python
class BankAccount:
    def __init__(self,name,acc_number ,balance=0):
        self.name=name
        self.acc_number=acc_number
        self.balance = balance
    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print(f"\n----------------Deposit------------\n\nDeposited ₹{amount}. Current Balance: ₹{self.balance}")
        else:
            print("Deposit amount must be in postive")

    def withdraw(self, amount):
        if amount > 0:
            if self.balance >= amount:
                self.balance -= amount
                print(f"\n---------------Withdraw-----------\n\nWithdrew ₹{amount}. Current Balance: ₹{self.balance}")
            else:
                print("Insufficient balance!")
        else:
            print("Withdrawal amount must be positive!")

    def check_balance(self):
        print(f"\n---------------Details-----------------\n\nAccount Holder: {self.name}\nAccount Number: {self.acc_number}\nBalance: ₹{self.balance}")


acc1 = BankAccount("Eswar",12345678, 1000)

while True:
    print("\n===== Bank Menu =====")
    print("1. Deposit Money")
    print("2. Withdraw Money")
    print("3. Check Balance")
    print("n. Exit")

    choice = input("Select an option: ")

    if choice == "1":
        amount = float(input("Enter amount to deposit: "))
        acc1.deposit(amount)

    elif choice == "2":
        amount = float(input("Enter amount to withdraw: "))
        acc1.withdraw(amount)

    elif choice == "3":
        acc1.check_balance()

    elif choice.lower() == "n":  
        print("Thank you for banking with us! ")
        break

    else:
        print(" Invalid option! Please try again.")
    


```

    
    ===== Bank Menu =====
    1. Deposit Money
    2. Withdraw Money
    3. Check Balance
    n. Exit
    

    Select an option:  1
    Enter amount to deposit:  1000
    

    
    ----------------Deposit------------
    
    Deposited ₹1000.0. Current Balance: ₹2000.0
    
    ===== Bank Menu =====
    1. Deposit Money
    2. Withdraw Money
    3. Check Balance
    n. Exit
    

    Select an option:  n
    

    Thank you for banking with us! 
    

# 5. Book Details
Create a class Book with attributes title, author, and price. Write a method to
return book information


```python
class Book:
    def __init__(self,title,author,price):
        self.title=title
        self.author=author
        self.price=price
    def book_info(self):
        print(f"---------Book Info-----------\nTitle: {self.title}\nAuthor:; {self.author}\nPrice: {self.price}")
B1=Book("Wings of Fire","Abdul Kalam" ,500)
B1.book_info()
                
```

    ---------Book Info-----------
    Title: Wings of Fire
    Author:; Abdul Kalam
    Price: 500
    

# 6.Employee Salary Calculation
Create a class Employee with attributes name, salary, and bonus. Add a method
to calculate the total salary (salary + bonus).


```python
class Employee:
    def __init__(self, name, salary, bonus):
        self.name = name
        self.salary = salary
        self.bonus = bonus

    def total_salary(self):
        return self.salary + self.bonus



emp1 = Employee("Eswar", 40000, 5000)
print(f"Employee: {emp1.name}, Total Salary: {emp1.total_salary()}")

```

    Employee: Eswar, Total Salary: 45000
    

# 7. Circle Properties
Create a class Circle with attribute radius. Add methods to calculate area and
circumference


```python
import math

class Circle:
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return round(math.pi * self.radius ** 2, 2)

    def circumference(self):
        return round(2 * math.pi * self.radius, 2)

c1 = Circle(7)
print(f"Circle Radius: {c1.radius}")
print(f"Area: {c1.area()}")
print(f"Circumference: {c1.circumference()}")

```

    Circle Radius: 7
    Area: 153.94
    Circumference: 43.98
    

# 8.Laptop Specs
Create a class Laptop with attributes brand, ram, storage. Add a method to
compare two laptops and return which one has more RAM.


```python
class Laptop:
    def __init__(self, brand, ram, storage):
        self.brand = brand
        self.ram = ram
        self.storage = storage

    def compare_ram(self, other_laptop):
        if self.ram > other_laptop.ram:
            return f"{self.brand} has more RAM ({self.ram}GB) than {other_laptop.brand} ({other_laptop.ram}GB)"
        elif self.ram < other_laptop.ram:
            return f"{other_laptop.brand} has more RAM ({other_laptop.ram}GB) than {self.brand} ({self.ram}GB)"
        else:
            return f"Both laptops have the same RAM ({self.ram}GB)"

l1 = Laptop("Dell", 16, 512)
l2 = Laptop("HP", 8, 256)

print(l1.compare_ram(l2))

```

    Dell has more RAM (16GB) than HP (8GB)
    

