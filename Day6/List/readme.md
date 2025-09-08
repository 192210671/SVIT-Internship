
# 📌 Python List and Its Built-in Functions

A **list** in Python is an **ordered, mutable, and iterable** data structure that can hold elements of different data types.  
Lists are defined using **square brackets `[ ]`**.

---

## 🔹 Creating a List
```python
my_list = [1, 2, 3, "apple", 4.5]
````

---

## 🔹 Common Built-in Functions and Methods for Lists

### 1. Adding Elements

* `append(x)` → Add element at the end
* `insert(i, x)` → Insert at index `i`
* `extend(iterable)` → Add multiple elements

```python
lst = [1, 2, 3]
lst.append(4)           # [1, 2, 3, 4]
lst.insert(1, 10)       # [1, 10, 2, 3, 4]
lst.extend([5, 6])      # [1, 10, 2, 3, 4, 5, 6]
```

---

### 2. Removing Elements

* `remove(x)` → Remove first occurrence of `x`
* `pop([i])` → Remove and return element at index (default last)
* `clear()` → Remove all elements

```python
lst = [1, 2, 3, 4, 5]
lst.remove(3)      # [1, 2, 4, 5]
lst.pop()          # [1, 2, 4]
lst.pop(1)         # [1, 4]
lst.clear()        # []
```

---

### 3. Searching & Counting

* `index(x)` → Return index of first occurrence
* `count(x)` → Count occurrences

```python
nums = [1, 2, 2, 3, 4, 2]
print(nums.index(2))   # 1
print(nums.count(2))   # 3
```

---

### 4. Sorting & Reversing

* `sort()` → Sort list (ascending by default)
* `sort(reverse=True)` → Sort descending
* `reverse()` → Reverse in place

```python
nums = [4, 1, 3, 2]
nums.sort()              # [1, 2, 3, 4]
nums.sort(reverse=True)  # [4, 3, 2, 1]
nums.reverse()           # [1, 2, 3, 4] → [4, 3, 2, 1]
```

---

### 5. Copying & Slicing

* `copy()` → Shallow copy of list
* Slicing `[start:end:step]`

```python
lst = [1, 2, 3, 4, 5]
new_lst = lst.copy()     # [1, 2, 3, 4, 5]
print(lst[1:4])          # [2, 3, 4]
print(lst[::-1])         # [5, 4, 3, 2, 1]
```

---

### 6. Built-in Functions that Work on Lists

* `len(lst)` → Number of elements
* `max(lst)` → Maximum value
* `min(lst)` → Minimum value
* `sum(lst)` → Sum of numeric values
* `sorted(lst)` → Returns new sorted list
* `any(lst)` → True if any element is truthy
* `all(lst)` → True if all elements are truthy

```python
nums = [1, 2, 3, 4, 5]
print(len(nums))     # 5
print(max(nums))     # 5
print(min(nums))     # 1
print(sum(nums))     # 15
print(sorted(nums, reverse=True))  # [5, 4, 3, 2, 1]
print(any([0, "", False, 5]))  # True
print(all([1, 2, 3]))          # True
```

---

## ✅ Summary

* **Mutable**: Lists can be changed after creation
* **Ordered**: Preserves insertion order
* **Versatile**: Can store mixed data types
* **Supports many methods**: add, remove, search, sort, etc.

```

Would you like me to also add a **visual table (method → description → example)** inside the README for quick reference?
```
