
# Python Set - Definition and Methods

## ✅ What is a Set in Python?

A **Set** is an unordered collection of **unique** elements in Python. Sets are mutable, meaning you can add or remove elements after creation. However, elements inside a set must be **immutable** (e.g., numbers, strings, tuples).

### ⚡ Key Properties of Sets:
- No duplicate elements
- Unordered (no indexing)
- Mutable (but elements must be immutable)

---

## ✅ How to Create a Set

```python
# Create a set with elements
my_set = {1, 2, 3, 4}

# Create a set from a list
another_set = set([1, 2, 3, 4, 4])  # Duplicates removed automatically

# Empty set (use set() not {})
empty_set = set()
````

---

## ✅ Common Set Methods

### 1️⃣ `add(element)`

Adds a single element to the set.

```python
my_set = {1, 2, 3}
my_set.add(4)
# Result: {1, 2, 3, 4}
```

---

### 2️⃣ `remove(element)`

Removes an element from the set. Raises `KeyError` if element not present.

```python
my_set = {1, 2, 3}
my_set.remove(2)
# Result: {1, 3}
```

---

### 3️⃣ `discard(element)`

Removes element if present, otherwise does nothing (no error).

```python
my_set = {1, 2, 3}
my_set.discard(2)
my_set.discard(5)  # No error even though 5 is not in the set
# Result: {1, 3}
```

---

### 4️⃣ `pop()`

Removes and returns an arbitrary element from the set.

```python
my_set = {1, 2, 3}
element = my_set.pop()
# Result: element contains one of 1, 2, or 3 and my_set size is reduced by one
```

---

### 5️⃣ `clear()`

Removes all elements from the set.

```python
my_set = {1, 2, 3}
my_set.clear()
# Result: set()
```

---

### 6️⃣ `union(other_set)`

Returns a new set with elements from both sets.

```python
a = {1, 2, 3}
b = {3, 4, 5}
result = a.union(b)
# result: {1, 2, 3, 4, 5}
```

---

### 7️⃣ `intersection(other_set)`

Returns a new set with elements common to both sets.

```python
a = {1, 2, 3}
b = {2, 3, 4}
result = a.intersection(b)
# result: {2, 3}
```

---

### 8️⃣ `difference(other_set)`

Returns a new set with elements in `a` but not in `b`.

```python
a = {1, 2, 3}
b = {2, 3, 4}
result = a.difference(b)
# result: {1}
```

---

### 9️⃣ `symmetric_difference(other_set)`

Returns a new set with elements in either `a` or `b` but not in both.

```python
a = {1, 2, 3}
b = {3, 4, 5}
result = a.symmetric_difference(b)
# result: {1, 2, 4, 5}
```

---

### 🔟 `issubset(other_set)`

Returns `True` if all elements of the set are in `other_set`.

```python
a = {1, 2}
b = {1, 2, 3}
result = a.issubset(b)
# result: True
```

---

### 1️⃣1️⃣ `issuperset(other_set)`

Returns `True` if the set contains all elements of `other_set`.

```python
a = {1, 2, 3}
b = {1, 2}
result = a.issuperset(b)
# result: True
```

---

## ✅ Example Use Case

```python
fruits = {"apple", "banana", "cherry"}
print("Original set:", fruits)

# Add a fruit
fruits.add("orange")

# Remove a fruit safely
fruits.discard("grape")

# Check membership
print("Is 'banana' in set?", "banana" in fruits)

# Union with another set
tropical = {"mango", "banana"}
all_fruits = fruits.union(tropical)
print(all_fruits)
```

---

## ✅ Conclusion

Python sets are useful for:

* Removing duplicates
* Membership tests (fast)
* Performing set operations like union, intersection, and difference

They provide a powerful way to handle collections where uniqueness matters.

---



### ✅ **All Common Python Set Methods**

| Method                                   | Description                                                     |
| ---------------------------------------- | --------------------------------------------------------------- |
| `add(element)`                           | Adds an element to the set.                                     |
| `clear()`                                | Removes all elements from the set.                              |
| `copy()`                                 | Returns a shallow copy of the set.                              |
| `difference(other_set)`                  | Returns elements in the set but not in `other_set`.             |
| `difference_update(other_set)`           | Removes elements found in another set from this set.            |
| `discard(element)`                       | Removes the element if present; does nothing if not.            |
| `intersection(other_set)`                | Returns elements common to both sets.                           |
| `intersection_update(other_set)`         | Updates the set with elements common to itself and `other_set`. |
| `isdisjoint(other_set)`                  | Returns `True` if sets have no elements in common.              |
| `issubset(other_set)`                    | Returns `True` if every element is in `other_set`.              |
| `issuperset(other_set)`                  | Returns `True` if the set contains all elements of `other_set`. |
| `pop()`                                  | Removes and returns an arbitrary element from the set.          |
| `remove(element)`                        | Removes the specified element; raises `KeyError` if not found.  |
| `symmetric_difference(other_set)`        | Returns elements in either set but not in both.                 |
| `symmetric_difference_update(other_set)` | Updates the set with elements in either set, but not both.      |
| `union(other_set)`                       | Returns a set with all elements from both sets.                 |
| `update(other_set)`                      | Adds elements from another set (or iterable) to the set.        |

---

### ✅ **Example Summary of Usage**

```python
a = {1, 2, 3}
b = {3, 4, 5}

a.add(6)
a.clear()
c = a.copy()

diff = a.difference(b)
a.difference_update(b)
a.discard(2)
inter = a.intersection(b)
a.intersection_update(b)

print(a.isdisjoint(b))
print(a.issubset(b))
print(a.issuperset(b))

popped_element = a.pop()
a.remove(3)
sym_diff = a.symmetric_difference(b)
a.symmetric_difference_update(b)

union_set = a.union(b)
a.update(b)
```

---

### ✅ Notes:

* Methods ending with `_update` modify the set in-place.
* `union`, `intersection`, `difference`, `symmetric_difference` return new sets without modifying originals.
* `add`, `remove`, `discard`, `pop`, `clear`, `update`, and `_update` methods modify the original set.

---

Would you like me to export this full list of methods as a `.md` file for easy reference?



