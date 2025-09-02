
# Declaring Variables in Python

In Python, variables are **created automatically when you assign a value**.  
There is no need for explicit declaration like in C/Java.

---

## 1. Basic Declaration
```python
x = 10          # integer
name = "Eswar"  # string
pi = 3.1415     # float
is_active = True # boolean
````

---

## 2. Declaring Multiple Variables

```python
a, b, c = 1, 2, 3       # multiple assignment
x = y = z = 100         # single value to multiple variables
```

---

## 3. Explicit Type Casting

You can declare a variable with a specific type using **constructors**:

```python
x = int(25)         # integer
y = float(25)       # float
z = str(25)         # string "25"
flag = bool(1)      # True
```

---

## 4. Using Type Hints (Optional)

Python supports **type hints** for clarity (not enforced at runtime):

```python
age: int = 21
pi: float = 3.14159
name: str = "Python"
is_admin: bool = False
scores: list[int] = [90, 85, 88]
student: dict[str, int] = {"roll": 101, "marks": 95}
```

---

## 5. Reassigning Variables

A variable can hold different data types at different times:

```python
x = 10        # int
x = "Hello"   # now string
```

---

## 6. Constants (by convention)

Python does not have real constants, but uppercase variable names are used:

```python
PI = 3.14159
MAX_USERS = 100
```

---

## 7. Variable Naming Rules

* Must start with a letter or `_` (underscore).
* Cannot start with a digit.
* Can contain letters, digits, and underscores.
* Case-sensitive (`age`, `Age`, and `AGE` are different).
* Should not use reserved keywords (`str`, `list`, `dict`, etc.).

Valid:

```python
name = "Eswar"
_age = 21
user123 = "active"
```

Invalid:

```python
2user = "wrong"     # starts with digit
class = "Python"    # reserved keyword
```

---

# Summary

* Variables are created when you assign a value.
* Python infers the type automatically.
* Use constructors (`int()`, `str()`, etc.) for explicit declaration.
* Use type hints (`x: int = 5`) for readability.
* Avoid overwriting built-in names like `str`, `list`, `dict`.



