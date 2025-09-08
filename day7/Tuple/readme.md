
#  Python Tuple and Its Built-in Functions

A **tuple** in Python is an **ordered, immutable, iterable** collection that can hold elements of different data types.  
Unlike lists, tuples **cannot be modified** (no item assignment, no append/remove).  

---

## 🔹 Creating Tuples

```python
# Empty tuple
t1 = ()

# Tuple with elements
t2 = (1, 2, 3)

# Tuple without parentheses (tuple packing)
t3 = 4, 5, 6

# Nested tuple
t4 = (1, (2, 3), 4)

# Single-element tuple (must include a comma)
t5 = (10,)
````

---

## 🔹 Characteristics of Tuples

* **Ordered** → Elements have a defined order, which will not change.
* **Immutable** → Once created, elements cannot be changed or removed.
* **Allow duplicates** → Tuples can contain repeated values.
* **Heterogeneous** → Can store different data types (int, str, list, dict, etc.).

---

## 🔹 Tuple Built-in Methods

Tuples have only **two methods**:

| Method                     | Description                                                   | Example                     |
| -------------------------- | ------------------------------------------------------------- | --------------------------- |
| `count(x)`                 | Returns number of times `x` appears                           | `(1, 2, 2, 3).count(2) → 2` |
| `index(x[, start[, end]])` | Returns first index of `x` (raises `ValueError` if not found) | `(1, 2, 3, 2).index(2) → 1` |

---

## 🔹 Built-in Functions that Work on Tuples

Although tuples have only two direct methods, many **Python built-in functions** work on them:

| Function          | Description                         | Example                     |
| ----------------- | ----------------------------------- | --------------------------- |
| `len(t)`          | Returns number of elements          | `len((1,2,3)) → 3`          |
| `max(t)`          | Returns largest element             | `max((1,5,3)) → 5`          |
| `min(t)`          | Returns smallest element            | `min((1,5,3)) → 1`          |
| `sum(t)`          | Returns sum of numeric elements     | `sum((1,2,3)) → 6`          |
| `sorted(t)`       | Returns new sorted list (not tuple) | `sorted((3,1,2)) → [1,2,3]` |
| `any(t)`          | True if any element is truthy       | `any((0, "", 5)) → True`    |
| `all(t)`          | True if all elements are truthy     | `all((1,2,3)) → True`       |
| `tuple(iterable)` | Converts iterable into tuple        | `tuple([1,2,3]) → (1,2,3)`  |

---

## 🔹 Tuple Operations

### 1. Concatenation

```python
a = (1, 2)
b = (3, 4)
print(a + b)   # (1, 2, 3, 4)
```

### 2. Repetition

```python
x = (1, 2)
print(x * 3)   # (1, 2, 1, 2, 1, 2)
```

### 3. Membership Test

```python
t = (1, 2, 3)
print(2 in t)      # True
print(4 not in t)  # True
```

### 4. Indexing & Slicing

```python
t = (10, 20, 30, 40, 50)
print(t[0])      # 10
print(t[-1])     # 50
print(t[1:4])    # (20, 30, 40)
```

---

## 🔹 Tuple Unpacking

You can assign tuple elements to variables directly.

```python
point = (3, 4, 5)
x, y, z = point
print(x, y, z)   # 3 4 5
```

---

## 🔹 Nested Tuples

Tuples can contain other tuples.

```python
nested = (1, (2, 3), (4, (5, 6)))
print(nested[1])     # (2, 3)
print(nested[2][1])  # (5, 6)
```

---

## 🔹 Example Program

```python
numbers = (1, 2, 3, 2, 4, 2)

# Methods
print(numbers.count(2))      # 3
print(numbers.index(4))      # 4

# Functions
print(len(numbers))          # 6
print(max(numbers))          # 4
print(min(numbers))          # 1
print(sum(numbers))          # 14
print(sorted(numbers))       # [1, 2, 2, 2, 3, 4]

# Operations
print(numbers + (5, 6))      # (1, 2, 3, 2, 4, 2, 5, 6)
print(numbers * 2)           # (1, 2, 3, 2, 4, 2, 1, 2, 3, 2, 4, 2)
```

---

## ✅ Summary

* Tuples are **ordered, immutable** collections.
* They support only **two methods**: `count()` and `index()`.
* Many Python **built-in functions** work with tuples.
* Useful for fixed collections of data (e.g., coordinates, database records).

```

Would you like me to also prepare a **comparison table (List vs Tuple)** in the README so it’s easier to see when to use which?
```
