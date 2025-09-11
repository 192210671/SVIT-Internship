

## ✅ For Loop in Python – Theory

A **for loop** in Python is used for iterating over a sequence (like a list, tuple, dictionary, set, or string). It executes a block of code repeatedly for each item in the sequence.

### 🔍 Syntax:

```python
for variable in sequence:
    # code block to execute
```

### ✅ How It Works:

* The **variable** takes the value of each element in the **sequence**, one by one.
* The loop runs until it goes through all items in the sequence.

### ✅ Example:

```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```

#### ✅ Output:

```
apple
banana
cherry
```

### ✅ Key Points:

* Can iterate over strings, lists, tuples, sets, dictionaries, and even files.
* Can be combined with `range()` for numeric iteration.
* Supports `break`, `continue`, and `else` clauses.

---

## ✅ Advanced Example – Using `range()`:

```python
for i in range(5):
    print(i)
```

#### ✅ Output:

```
0
1
2
3
4
```

---

## ✅ 10 Interview Questions + Answers on For Loop in Python

---

### ❓ 1. What is a for loop in Python?

👉 **Answer:**
A for loop in Python is a control flow statement used to iterate over elements of a sequence like a list, tuple, or string and execute a block of code for each element.

---

### ❓ 2. How is a for loop different from a while loop in Python?

👉 **Answer:**
A for loop iterates over a sequence of items and is used when the number of iterations is known.
A while loop runs as long as a condition is true and is typically used when the number of iterations is unknown.

---

### ❓ 3. What does the `range()` function do in a for loop?

👉 **Answer:**
The `range()` function generates a sequence of numbers which can be used for looping a specific number of times, e.g., `range(5)` generates numbers from 0 to 4.

---

### ❓ 4. Can we loop over a dictionary using a for loop? How?

👉 **Answer:**
Yes. You can loop over the keys or values of a dictionary:

```python
my_dict = {'a': 1, 'b': 2}
for key in my_dict:
    print(key, my_dict[key])
```

---

### ❓ 5. What is the use of the `else` block in a for loop?

👉 **Answer:**
The `else` block executes after the for loop finishes normally (without encountering a `break` statement).

Example:

```python
for i in range(3):
    print(i)
else:
    print("Loop completed successfully")
```

---

### ❓ 6. How can you break a for loop prematurely?

👉 **Answer:**
Using the `break` keyword.

```python
for i in range(5):
    if i == 3:
        break
    print(i)
```

---

### ❓ 7. How do you skip the current iteration in a for loop?

👉 **Answer:**
Use the `continue` keyword.

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

---

### ❓ 8. Is it possible to have nested for loops in Python?

👉 **Answer:**
Yes, you can nest for loops.

```python
for i in range(2):
    for j in range(3):
        print(i, j)
```

---

### ❓ 9. How do you iterate over a string using a for loop?

👉 **Answer:**

```python
word = "hello"
for letter in word:
    print(letter)
```

---

### ❓ 10. How do you loop over a list with access to index and value?

👉 **Answer:**
Use `enumerate()`.

```python
fruits = ["apple", "banana"]
for index, fruit in enumerate(fruits):
    print(index, fruit)
```

---

## 🎯 Summary

| Feature        | Example                                   |
| -------------- | ----------------------------------------- |
| Simple loop    | `for i in range(5): print(i)`             |
| Loop over list | `for fruit in fruits: print(fruit)`       |
| Break loop     | `if i == 3: break`                        |
| Continue       | `if i == 2: continue`                     |
| Enumerate      | `for index, value in enumerate(my_list):` |
| Loop over dict | `for key in dict: print(key, dict[key])`  |

---

This should help you prepare for interviews and understand the for loop deeply. Do you want me to generate this in a markdown file for GitHub documentation?
