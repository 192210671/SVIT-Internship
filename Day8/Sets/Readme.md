
# Python Set - Definition and Methods

## ✅ What is a Set in Python?

A **Set** is an unordered collection of **unique** elements in Python. Sets are mutable, meaning you can add or remove elements after creation. However, elements inside a set must be **immutable** (e.g., numbers, strings, tuples).

### ⚡ Key Properties of Sets
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


# 📋 Python Set - Interview Questions

## 1️⃣ What is a Set in Python?
A **Set** is an unordered collection of **unique** and **immutable** elements. Sets are mutable themselves but contain only immutable objects. They are mainly used for membership testing and eliminating duplicate entries.

---

## 2️⃣ How do you create a Set in Python?
```python
# Using curly braces
my_set = {1, 2, 3}

# Using set() constructor
my_set = set([1, 2, 3])
````

---

## 3️⃣ What are the key properties of a Set?

* Unordered
* No duplicate elements
* Elements must be immutable (numbers, strings, tuples)
* Mutable set itself (can add/remove elements)

---

## 4️⃣ How do you add and remove elements in a Set?

```python
s = {1, 2, 3}

# Add
s.add(4)

# Remove (raises KeyError if element not present)
s.remove(3)

# Discard (no error if element not present)
s.discard(5)

# Pop (removes arbitrary element)
element = s.pop()
```

---

## 5️⃣ What is the difference between `remove()` and `discard()`?

* `remove(x)` throws `KeyError` if `x` is not present.
* `discard(x)` does not raise any error if `x` is absent.

---

## 6️⃣ Explain Set Operations with Examples.

```python
a = {1, 2, 3}
b = {3, 4, 5}

# Union
print(a.union(b))  # {1, 2, 3, 4, 5}

# Intersection
print(a.intersection(b))  # {3}

# Difference
print(a.difference(b))  # {1, 2}

# Symmetric Difference
print(a.symmetric_difference(b))  # {1, 2, 4, 5}
```

---

## 7️⃣ How do you check if one set is a subset or superset of another?

```python
a = {1, 2}
b = {1, 2, 3}

print(a.issubset(b))    # True
print(b.issuperset(a))  # True
```

---

## 8️⃣ What is the time complexity of basic Set operations?

| Operation                         | Time Complexity    |
| --------------------------------- | ------------------ |
| Membership Test (`x in s`)        | O(1) on average    |
| Add/Remove Element                | O(1) on average    |
| Union / Intersection / Difference | O(len(s) + len(t)) |

---

## 9️⃣ Can a Set contain another Set as an element?

No, because a Set is unhashable. But a `frozenset` (immutable set) can be an element in a set.

```python
a = frozenset([1, 2, 3])
s = {a}
print(s)  # Output: {frozenset({1, 2, 3})}
```

---

## 🔟 When would you use a Set instead of a List?

* To remove duplicates
* When fast membership testing is required (`in` operation)
* Performing mathematical set operations (union, intersection, difference)




# 🤔 20 Tricky Python Set Interview Questions and Answers

---

## 1️⃣ Can a Set contain another Set as an element?
❌ No, because sets are mutable and unhashable.  
✅ But you can use `frozenset` (immutable set) as an element.

```python
s = {frozenset([1, 2, 3])}
````

---

## 2️⃣ What happens if you add a list to a Set?

❌ Raises `TypeError` because lists are unhashable.

---

## 3️⃣ How do you create an empty Set?

✅ Correct way:

```python
empty_set = set()
```

❌ `{}` creates an empty dictionary, not a set.

---

## 4️⃣ What is the result of `set("aabbcc")`?

```python
result = set("aabbcc")
# {'a', 'b', 'c'}
```

Duplicates are automatically removed.

---

## 5️⃣ Is the order of elements in a Set preserved?

❌ No.
Sets are unordered and do not preserve element order.

---

## 6️⃣ What is the difference between `symmetric_difference()` and `difference()`?

* `difference()` returns elements in `A` but not in `B`.
* `symmetric_difference()` returns elements in either `A` or `B`, but not in both.

```python
A = {1, 2, 3}
B = {3, 4}

A.difference(B)             # {1, 2}
A.symmetric_difference(B)   # {1, 2, 4}
```

---

## 7️⃣ Can sets have duplicate elements?

❌ No, sets automatically remove duplicates when created.

---

## 8️⃣ What happens if you do `s.add([1, 2])` where `s` is a Set?

❌ Raises `TypeError` because `[1, 2]` is a list and unhashable.

---

## 9️⃣ Can you perform set operations on other iterables (like lists)?

✅ Yes, by converting them into sets.

```python
list1 = [1, 2, 3]
list2 = [3, 4, 5]

result = set(list1).intersection(list2)  # {3}
```

---

## 🔟 What does `isdisjoint()` do?

Returns `True` if two sets have no elements in common.

```python
{1, 2}.isdisjoint({3, 4})  # True
```

---

## 1️⃣1️⃣ How does `pop()` behave in sets?

Removes and returns an **arbitrary** element, because sets are unordered.

```python
s = {1, 2, 3}
element = s.pop()  # Could be 1, 2, or 3
```

---

## 1️⃣2️⃣ What is the difference between `update()` and `union()`?

* `update()` modifies the set in-place.
* `union()` returns a new set.

```python
a = {1, 2}
b = {3, 4}

a.update(b)  # a becomes {1, 2, 3, 4}
c = a.union(b)  # c is a new set {1, 2, 3, 4}
```

---

## 1️⃣3️⃣ Can Sets contain `None`?

✅ Yes.

```python
s = {None}
print(s)  # {None}
```

---

## 1️⃣4️⃣ What happens when you `remove()` an element not present in the set?

❌ Raises `KeyError`.

Use `discard()` if you want to avoid errors.

---

## 1️⃣5️⃣ How to convert a set to a list?

```python
s = {1, 2, 3}
lst = list(s)
```

---

## 1️⃣6️⃣ Can set elements be mutable?

❌ No, elements must be immutable (numbers, strings, tuples).

---

## 1️⃣7️⃣ Is a `frozenset` mutable or immutable?

✅ Immutable.
Good for use as a key in a dictionary or as an element of a set.

---

## 1️⃣8️⃣ How do you get the number of elements in a Set?

```python
s = {1, 2, 3}
length = len(s)  # 3
```

---

## 1️⃣9️⃣ What is the time complexity of checking membership in a Set?

✅ O(1) on average (because of hash table implementation).

---

## 2️⃣0️⃣ What is the difference between `copy()` and direct assignment (`=`)?

```python
a = {1, 2}
b = a         # Both point to same object
c = a.copy()  # c is a separate object

a.add(3)
print(b)  # {1, 2, 3}  (same object)
print(c)  # {1, 2}     (independent copy)
```

---





