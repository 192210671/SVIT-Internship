
---

#  Operators and Variables Assignment (Python Notes)

---

## **1. Arithmetic Operations on Variables**

```python
# Define variables
a = 12
b = 5

# Perform arithmetic operations
print("Sum:", a + b)          # Addition
print("Difference:", a - b)   # Subtraction
print("Product:", a * b)      # Multiplication
print("Quotient:", a / b)     # Division (float result)
print("Modulus:", a % b)      # Remainder after division
```

###  Explanation:

* `+` adds two numbers.
* `-` subtracts `b` from `a`.
* `*` multiplies `a` and `b`.
* `/` divides `a` by `b` and returns a **float**.
* `%` gives the remainder when `a` is divided by `b`.

---

## **2. Expression with Parentheses**

```python
# Expression with parentheses
result = (8 + 2) * (3 - 1) ** 2 / 2
print("Result:", result)
```

###  Explanation:

* Parentheses `()` **control precedence**.
* `(8 + 2)` → addition first = `10`.
* `(3 - 1)` → subtraction = `2`.
* `2 ** 2` → exponentiation = `4`.
* So expression becomes → `10 * 4 / 2 = 20.0`.

If parentheses were not used, Python would follow **operator precedence rules** and the result would be different.

---

## **3. Boolean Variables**

```python
# Boolean variables
p = True
q = False
r = True

print("p and q:", p and q)  # True only if both are True
print("p or q:", p or q)    # True if at least one is True
print("not r:", not r)      # Negates the value of r
```

###  Explanation:

* `p and q` → `True and False` = `False`.
* `p or q` → `True or False` = `True`.
* `not r` → `not True` = `False`.

---

## **4. Operator Precedence Example**

```python
# Expression with mixed operators
result = 10 + 2 * 3 / 4 - 5 ** 2
print("Result:", result)
```

###  Explanation (Order of operations):

Python follows **PEMDAS** (Parentheses, Exponent, Multiplication/Division, Addition/Subtraction).

1. `5 ** 2` → `25` (exponentiation first).
2. `2 * 3 / 4` → `6 / 4 = 1.5`.
3. `10 + 1.5 - 25` → `-13.5`.

✔ Final result: **`-13.5`**

---

## **5. Logical vs Bitwise Operators**

###  Logical Operators (`and`, `or`, `not`)

Work on **boolean values**.

```python
x = True
y = False

print(x and y)   # False
print(x or y)    # True
print(not x)     # False
```

### 🔹 Bitwise Operators (`&`, `|`, `~`)

Work on **binary (bit-level) integers**.

```python
a = 6   # 110 in binary
b = 3   # 011 in binary

print(a & b)   # 110 & 011 = 010 → 2
print(a | b)   # 110 | 011 = 111 → 7
print(~a)      # Bitwise NOT of 6 → -7 (two’s complement)
```

 **Difference:**

* **Logical** works with `True`/`False`.
* **Bitwise** works with **binary digits** of integers.

---

## **6. Variables in Python**

A **variable** is a name that stores data in memory.
It can hold different data types such as numbers, strings, or boolean values.

```python
# Example of variable
name = "Alice"
age = 21
gpa = 8.7

print("Name:", name)
print("Age:", age)
print("GPA:", gpa)
```

 Variables make programs flexible and reusable.

---

## **7. Expressions with Different Types**

```python
width = 17
height = 12.0
delimiter = '.'

# Expressions
print(width / 2, type(width / 2))          # 8.5 -> float
print(width // 2, type(width // 2))        # 8 -> int (floor division)
print(height / 3, type(height / 3))        # 4.0 -> float
print(1 + 2 * 5, type(1 + 2 * 5))          # 11 -> int
print(delimiter * 5, type(delimiter * 5))  # '.....' -> str
```

---

## **8. Data Types of Different Values**

```python
print(type(10))      # int
print(type('10'))    # str
print(type(True))    # bool
print(type(10.5))    # float
```

---

## **9. Volume of a Sphere**

Formula:

$$
V = \frac{4}{3} \pi r^3
$$

```python
import math

r = 5
volume = (4/3) * math.pi * r**3
print("Volume of sphere:", volume)
```

 Result: `523.5987755982989`

---

# Summary

* Arithmetic, Boolean, and Operator Precedence → help us control **calculations**.
* Logical vs Bitwise operators → different use cases.
* Variables → containers for data.
* Data types → important for correct operation.
* Real-life example → calculating **sphere volume**.

---


