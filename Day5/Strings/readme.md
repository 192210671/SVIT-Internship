
#  Strings in Python

Strings are one of the most commonly used data types in Python. A **string** is a sequence of characters enclosed within **single quotes (' ')**, **double quotes (" ")**, or **triple quotes (''' ''' or """ """)**.

---

##  Creating Strings

```python
# Single quotes
str1 = 'Hello'

# Double quotes
str2 = "World"

# Triple quotes (used for multi-line strings)
str3 = '''This is 
a multi-line 
string'''
````

---

##  String Indexing and Slicing

Strings are **indexed** starting from `0`.

```python
s = "Python"

# Indexing
print(s[0])   # P
print(s[-1])  # n (last character)

# Slicing
print(s[0:4])   # Pyth
print(s[:3])    # Pyt
print(s[2:])    # thon
```

---

##  String Operations

```python
# Concatenation
a = "Hello"
b = "World"
print(a + " " + b)   # Hello World

# Repetition
print(a * 3)         # HelloHelloHello

# Membership
print("H" in a)      # True
print("z" not in a)  # True
```

---

##  String Methods

Python provides many **built-in string methods**.

```python
text = "  hello world  "

print(text.upper())      # HELLO WORLD
print(text.lower())      # hello world
print(text.title())      # Hello World
print(text.strip())      # "hello world" (removes spaces)
print(text.replace("world", "Python"))  # hello Python
print(text.find("world"))  # 8 (index of substring)
print(text.split())        # ['hello', 'world']
print("-".join(["Python", "is", "fun"]))  # Python-is-fun
```

---

##  String Formatting

### 1. **f-strings (Python 3.6+)**

```python
name = "Alice"
age = 25
print(f"My name is {name}, and I am {age} years old.")
```

### 2. **`format()` method**

```python
print("My name is {}, and I am {} years old.".format("Alice", 25))
```

### 3. **Percentage formatting**

```python
print("My name is %s, and I am %d years old." % ("Alice", 25))
```

---

##  Escape Sequences

```python
print("Line1\nLine2")   # Newline
print("Hello\tWorld")   # Tab
print("He said, \"Python is fun!\"")  # Quotes inside string
```

---

##  Raw Strings

Raw strings ignore escape sequences (useful for file paths, regex).

```python
path = r"C:\Users\Alice\Documents"
print(path)   # C:\Users\Alice\Documents
```

---

##  String Immutability

Strings are **immutable** in Python, meaning they **cannot be changed** after creation.

```python
s = "Python"
# s[0] = "J"   # Error
s = "Jython"   # Creates a new string
```

---

##  Useful Built-in Functions

```python
s = "Python"

print(len(s))      # 6
print(max(s))      # y (highest character by ASCII value)
print(min(s))      # P (lowest character by ASCII value)
print(sorted(s))   # ['P', 'h', 'n', 'o', 't', 'y']
```

---

##  Summary

* Strings in Python are **sequences of characters**.
* Defined using `'`, `"`, or `'''` quotes.
* Support **indexing, slicing, concatenation, repetition, formatting**.
* Strings are **immutable**.
* Rich set of **methods** for manipulation.

---

##  Example Program

```python
# String Example Program
name = "Eswar"
language = "Python"

msg = f"Hello, my name is {name} and I love {language}!"
print(msg)

print("Reversed:", name[::-1])
print("Uppercase:", name.upper())
print("Length of name:", len(name))
```


