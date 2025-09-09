
# 📚 Python Dictionary - Complete Guide

## ✅ What is a Dictionary in Python?

A **Dictionary** is an **unordered**, **mutable** collection of **key-value pairs** in Python.  
Each key must be **unique** and **immutable** (string, number, tuple), while values can be of any data type.

---

## ✅ How to Create a Dictionary

```python
# Create a dictionary with key-value pairs
person = {
    "name": "Alice",
    "age": 25,
    "city": "New York"
}

# Empty dictionary
empty_dict = {}

# Using dict() constructor
another_person = dict(name="Bob", age=30)
````

---

## ✅ Common Built-in Dictionary Methods

| Method                          | Description                                                 |
| ------------------------------- | ----------------------------------------------------------- |
| `dict.clear()`                  | Removes all items from the dictionary.                      |
| `dict.copy()`                   | Returns a shallow copy of the dictionary.                   |
| `dict.get(key, default)`        | Returns value for key if present, else default.             |
| `dict.items()`                  | Returns a view object with (key, value) pairs.              |
| `dict.keys()`                   | Returns a view object with all keys.                        |
| `dict.values()`                 | Returns a view object with all values.                      |
| `dict.pop(key, default)`        | Removes key and returns its value.                          |
| `dict.popitem()`                | Removes and returns the last inserted (key, value) pair.    |
| `dict.update(other_dict)`       | Updates dictionary with key-value pairs from other\_dict.   |
| `dict.setdefault(key, default)` | Returns value if key exists, else inserts key with default. |

---

## ✅ Example Usage of Dictionary Methods

```python
person = {"name": "Alice", "age": 25, "city": "New York"}

# Get
print(person.get("age"))  # 25
print(person.get("country", "USA"))  # USA (default)

# Update
person.update({"age": 26, "country": "USA"})

# Items
for key, value in person.items():
    print(f"{key}: {value}")

# Keys & Values
print(person.keys())    # dict_keys(['name', 'age', 'city', 'country'])
print(person.values())  # dict_values(['Alice', 26, 'New York', 'USA'])

# Pop
age = person.pop("age")
print(age)       # 26

# Set Default
person.setdefault("gender", "Female")
print(person["gender"])  # Female

# Copy
person_copy = person.copy()

# Clear
person_copy.clear()
print(person_copy)  # {}
```

---

## ✅ Real-World Example: Counting Word Frequency

```python
text = "apple banana apple orange banana apple"

word_count = {}
for word in text.split():
    word_count[word] = word_count.get(word, 0) + 1

print(word_count)
# Output: {'apple': 3, 'banana': 2, 'orange': 1}
```

---

## ✅ Tricky Interview Questions on Dictionary

1️⃣ What happens when you try to use a mutable type (like a list) as a dictionary key?
❌ Raises `TypeError: unhashable type: 'list'`

---

2️⃣ How to safely access a key that might not exist?
Use `.get(key, default)` instead of `dict[key]` to avoid `KeyError`.

---

3️⃣ Difference between `.get()` and direct key access (`[]`)?
`.get()` returns `None` or default value if key is missing, while `[]` raises `KeyError`.

---

4️⃣ How do you merge two dictionaries?

```python
dict1 = {"a": 1, "b": 2}
dict2 = {"b": 3, "c": 4}

merged = {**dict1, **dict2}
# {'a': 1, 'b': 3, 'c': 4}
```

---

5️⃣ What is the order of keys in a dictionary?
✅ From Python 3.7+, dictionaries preserve the insertion order.

---

6️⃣ How do you remove the last inserted item?

```python
d = {"a": 1, "b": 2}
last_item = d.popitem()
print(last_item)  # ('b', 2)
```

---

## ✅ Summary

* Use dictionaries when you need **key-value mapping**.
* Fast lookups: O(1) average time for access and updates.
* Ideal for real-time applications: caching, word frequency, configuration storage, etc.

🚀 Master these concepts to ace your Python interviews!

```

