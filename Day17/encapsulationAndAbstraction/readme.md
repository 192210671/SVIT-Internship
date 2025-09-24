

# 🔒 **Encapsulation vs Abstraction in Python**

---

## **1. Encapsulation**

👉 **Definition**:
Encapsulation is the concept of **wrapping data (variables) and methods (functions)** into a single unit (class). It also allows us to **control access** to data using **access modifiers** (`public`, `protected`, `private`).

* In Python:

  * `public` → accessible everywhere.
  * `_protected` → conventionally for internal use (can still be accessed outside).
  * `__private` → name-mangled, not directly accessible outside.

---

### **Analogy**

Think of a **capsule medicine 💊**:

* It contains different drugs inside (data + functions).
* You can’t directly access the raw medicine, but you **consume it as one capsule**.

That’s **encapsulation** — data is **hidden inside** but used in a controlled way.

---

### **Python Example (Encapsulation)**

```python
class BankAccount:
    def __init__(self, name, balance=0):
        self.name = name        # public
        self._account_type = "Savings"  # protected (convention)
        self.__balance = balance # private

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount
            print(f"{amount} deposited. New balance: {self.__balance}")
        else:
            print("Invalid deposit amount")

    def get_balance(self):
        return self.__balance   # controlled access

# Usage
acc = BankAccount("Eswar", 1000)
acc.deposit(500)             # ✅ Works
print(acc.get_balance())     # ✅ Works through method
# print(acc.__balance)       # ❌ AttributeError (private)
print(acc._account_type)     # ⚠️ Can access but discouraged
```

---

## **2. Abstraction**

👉 **Definition**:
Abstraction means **hiding implementation details** and showing only the **essential features**.
It lets you work with **what a method does, not how it does it**.

* In Python, abstraction is implemented using **abstract classes** and **abstract methods** (via the `abc` module).

---

### **Analogy**

Think of a **car 🚗**:

* You use the **steering wheel, brake, accelerator** to drive.
* You don’t know (or care) **how the engine, brakes, or transmission work internally**.

That’s **abstraction** — exposing only **necessary functions** and hiding **internal complexity**.

---

### **Python Example (Abstraction)**

```python
from abc import ABC, abstractmethod

class BankAccount(ABC):
    def __init__(self, name, balance=0):
        self.name = name
        self.balance = balance

    @abstractmethod
    def withdraw(self, amount):  # abstract method
        pass

    @abstractmethod
    def account_type(self):
        pass


class SavingsAccount(BankAccount):
    def withdraw(self, amount):
        if self.balance - amount < 500:
            print("Minimum balance rule violated!")
        else:
            self.balance -= amount
            print(f"{amount} withdrawn. Remaining balance = {self.balance}")

    def account_type(self):
        return "Savings Account"


class CurrentAccount(BankAccount):
    def withdraw(self, amount):
        if self.balance - amount < -1000:  # overdraft
            print("Overdraft limit exceeded!")
        else:
            self.balance -= amount
            print(f"{amount} withdrawn. Remaining balance = {self.balance}")

    def account_type(self):
        return "Current Account"
```

---

## ✅ **Usage**

```python
s1 = SavingsAccount("Eswar", 2000)
c1 = CurrentAccount("Arun", 500)

s1.withdraw(1700)   # Enforces min balance
print(s1.account_type())

c1.withdraw(1200)   # Allows overdraft
print(c1.account_type())
```

---

## ⚡ Output

```
Minimum balance rule violated!
Savings Account
1200 withdrawn. Remaining balance = -700
Current Account
```

---

## **3. Key Differences**

| Feature            | Encapsulation 🔒                                         | Abstraction 🎭                                                   |
| ------------------ | -------------------------------------------------------- | ---------------------------------------------------------------- |
| **Definition**     | Binding data & methods into one unit, controlling access | Hiding internal implementation & showing only essential features |
| **Focus**          | Data hiding                                              | Implementation hiding                                            |
| **Achieved by**    | Access modifiers (`public`, `_protected`, `__private`)   | Abstract classes & methods (`abc` module)                        |
| **Analogy**        | Capsule medicine 💊                                      | Car controls 🚗                                                  |
| **Python Support** | Directly via naming conventions (`_`, `__`)              | `abc` module, `@abstractmethod`                                  |

---

✅ **In short**:

* **Encapsulation** = *“Hide the data inside the class, access it safely”*.
* **Abstraction** = *“Hide how it works, just expose what it does”*.

---

