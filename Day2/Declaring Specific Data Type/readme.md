
# Python Data Types

In Python, data types specify the type of value a variable holds.  
They are mainly classified into **immutable** and **mutable** types.

---

## 1. Numeric Types
- **int** → Integer values (whole numbers).
- **float** → Decimal numbers (floating-point).
- **complex** → Complex numbers with real and imaginary parts.

```python
x = 10        # int
y = 3.14      # float
z = 2 + 3j    # complex
````

---

## 2. Sequence Types

### (a) String (`str`)

* Immutable sequence of Unicode characters.

```python
name = "Python"
s = str("Hello")  # explicit declaration
```

### (b) List (`list`)

* Mutable, ordered collection of items (can hold different data types).

```python
fruits = ["apple", "banana", "cherry"]
numbers = list((1, 2, 3))
```

### (c) Tuple (`tuple`)

* Immutable, ordered collection.

```python
point = (10, 20, 30)
coords = tuple([1, 2, 3])
```

### (d) Range (`range`)

* Immutable sequence of numbers, often used in loops.

```python
nums = range(1, 6)  # 1,2,3,4,5
```

---

## 3. Mapping Type

### Dictionary (`dict`)

* Collection of key-value pairs, mutable and unordered.

```python
student = {"name": "Eswar", "age": 21, "course": "CS"}
student_info = dict(name="John", score=88)
```

---

## 4. Set Types

### (a) Set (`set`)

* Mutable, unordered collection of unique items.

```python
colors = {"red", "green", "blue"}
unique_nums = set([1, 2, 3])
```

### (b) Frozen Set (`frozenset`)

* Immutable version of a set.

```python
numbers = frozenset([1, 2, 3, 2])
```

---

## 5. Boolean Type

* Represents truth values: `True` or `False`.

```python
is_active = True
flag = bool(0)   # False
```

---

## 6. Binary Types

* **bytes** → Immutable sequence of bytes.
* **bytearray** → Mutable sequence of bytes.
* **memoryview** → Memory view object for accessing buffers.

```python
b = b"Hello"                 # bytes
ba = bytearray([65, 66, 67]) # bytearray
mv = memoryview(b"Python")   # memoryview
```

---

## 7. None Type

* Represents the absence of a value.

```python
value = None
```

---

# Type Hints (Optional)

Python supports **type hints** to specify expected types (not enforced at runtime):

```python
age: int = 25
pi: float = 3.1415
name: str = "Eswar"
is_admin: bool = True
marks: list[int] = [85, 90, 95]
student: dict[str, int] = {"roll": 101, "marks": 95}
```

---

# Summary Table

| Category  | Data Type             | Mutable/Immutable |
| --------- | --------------------- | ----------------- |
| Numeric   | int, float, complex   | Immutable         |
| Sequence  | str, tuple, range     | Immutable         |
|           | list                  | Mutable           |
| Mapping   | dict                  | Mutable           |
| Set       | set                   | Mutable           |
|           | frozenset             | Immutable         |
| Boolean   | bool                  | Immutable         |
| Binary    | bytes                 | Immutable         |
|           | bytearray, memoryview | Mutable           |
| None Type | NoneType (`None`)     | Immutable         |

---

# Notes

* Python is **dynamically typed** → no need to declare data types explicitly.
* Use constructors (`int()`, `str()`, `list()`, etc.) for explicit declaration.
* Avoid using names like `str`, `list`, `dict` as variables (they shadow built-in types).
* Type hints improve readability but are **not enforced** by Python itself.

```


