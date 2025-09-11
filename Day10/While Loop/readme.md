

## ✅ While Loop in Python – Theory

A **while loop** in Python is used to repeatedly execute a block of code as long as a given condition is **True**. It is typically used when the number of iterations is not known beforehand and depends on a condition.

### 🔍 Syntax:

```python
while condition:
    # code block to execute
```

### ✅ How It Works:

* The **condition** is evaluated before each iteration.
* If the condition is `True`, the code block inside the loop runs.
* If the condition becomes `False`, the loop stops.

---

### ✅ Simple Example:

```python
count = 0

while count < 5:
    print(count)
    count += 1
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

### ✅ Key Points:

* Make sure the condition eventually becomes `False`, or the loop will run infinitely.
* Can use `break` to stop the loop prematurely.
* Can use `continue` to skip the current iteration.

---

### ✅ Advanced Example – Using `break` and `continue`:

```python
i = 0
while i < 5:
    i += 1
    if i == 3:
        continue  # Skip printing 3
    print(i)
```

#### ✅ Output:

```
1
2
4
5
```

---

## ✅ 10 Interview Questions + Answers on While Loop in Python

---

### ❓ 1. What is a while loop in Python?

👉 **Answer:**
A while loop is a control flow statement that runs a block of code repeatedly as long as a given condition is `True`.

---

### ❓ 2. What is the key difference between a for loop and a while loop?

👉 **Answer:**

* **For loop** is generally used when the number of iterations is known or finite.
* **While loop** is used when the number of iterations depends on a condition and may be indefinite.

---

### ❓ 3. How do you prevent an infinite while loop?

👉 **Answer:**
Ensure that the loop’s condition will eventually become `False`, typically by updating a variable used in the condition inside the loop.

Example:

```python
i = 0
while i < 5:
    print(i)
    i += 1  # Increment to avoid infinite loop
```

---

### ❓ 4. How do you exit a while loop prematurely?

👉 **Answer:**
Use the `break` statement.

```python
i = 0
while i < 10:
    if i == 5:
        break
    print(i)
    i += 1
```

---

### ❓ 5. How do you skip the current iteration in a while loop?

👉 **Answer:**
Use the `continue` statement.

```python
i = 0
while i < 5:
    i += 1
    if i == 3:
        continue
    print(i)
```

---

### ❓ 6. What happens if the condition in the while loop is never false?

👉 **Answer:**
The loop will run indefinitely (infinite loop), which may cause the program to hang or crash.

---

### ❓ 7. Can you use an else block with a while loop?

👉 **Answer:**
Yes, the else block runs if the while loop completes normally (no break).

```python
i = 0
while i < 3:
    print(i)
    i += 1
else:
    print("Loop ended normally")
```

---

### ❓ 8. Give an example of a while loop that takes user input until the correct input is entered.

👉 **Answer:**

```python
password = ""

while password != "secret":
    password = input("Enter password: ")
print("Access granted")
```

---

### ❓ 9. How do you implement a loop that counts down from 10 to 1 using a while loop?

👉 **Answer:**

```python
count = 10
while count > 0:
    print(count)
    count -= 1
```

---

### ❓ 10. Why is it important to update the condition variable inside a while loop?

👉 **Answer:**
To ensure that the loop will eventually terminate. Otherwise, the condition stays `True` forever, causing an infinite loop.

---

## 🎯 Summary Table

| Feature           | Example                               |
| ----------------- | ------------------------------------- |
| Simple while loop | `while i < 5: i += 1`                 |
| Break loop        | `if i == 5: break`                    |
| Continue loop     | `if i == 3: continue`                 |
| Else block        | `else: print("Done")`                 |
| User input loop   | `while password != "secret": input()` |
| Countdown loop    | `while count > 0: count -= 1`         |




## ✅ Pass Statement in Python – Theory

The **`pass` statement** in Python is a **null operation** — it does nothing. It is used as a placeholder when a statement is syntactically required but no action is needed.

### ✅ Why Use `pass` in Loops?

* When you need a loop structure for future implementation.
* To avoid syntax errors while developing.
* To explicitly show that no action is needed in a particular block.

---

### ✅ Syntax:

```python
for i in range(5):
    pass
```

---

### ✅ Example 1 – Using `pass` in a for loop

```python
for i in range(3):
    pass  # Placeholder for future code

print("Loop executed without doing anything")
```

#### ✅ Output:

```
Loop executed without doing anything
```

---

### ✅ Example 2 – Using `pass` in a while loop

```python
count = 0

while count < 5:
    count += 1
    pass  # No action inside loop

print("While loop executed successfully")
```

---

### ✅ Key Points:

* `pass` helps to avoid empty block syntax errors.
* Useful for designing the program structure before filling in actual logic.
* Does not affect the flow or execution of the loop.

---

## ✅ 10 Interview Questions + Answers on Pass Statement in Loops

---

### ❓ 1. What is the `pass` statement in Python?

👉 **Answer:**
`pass` is a null statement in Python that performs no action. It is used as a placeholder when a statement is syntactically required.

---

### ❓ 2. Why would you use `pass` inside a loop?

👉 **Answer:**
To create an empty loop block without causing a syntax error, typically during development or when no operation is needed.

---

### ❓ 3. What happens if you omit the code inside a loop without `pass`?

👉 **Answer:**
Python raises an `IndentationError` because a block is expected after the loop declaration.

---

### ❓ 4. Can `pass` be used in both `for` and `while` loops?

👉 **Answer:**
Yes, `pass` works in both `for` and `while` loops.

---

### ❓ 5. Will a loop with only a `pass` statement run infinitely?

👉 **Answer:**
Only if the loop condition is always `True`.
Example:

```python
while True:
    pass  # Infinite loop unless interrupted
```

---

### ❓ 6. Is `pass` equivalent to `continue`?

👉 **Answer:**
No.

* `pass` does nothing and moves to the next statement.
* `continue` skips the remaining code in the loop for the current iteration and goes to the next iteration.

---

### ❓ 7. When is it useful to use `pass`?

👉 **Answer:**

* During program development to outline structure.
* When implementing abstract methods or interface placeholders.

---

### ❓ 8. Can `pass` be used in conditional statements inside loops?

👉 **Answer:**
Yes.

```python
for i in range(5):
    if i < 3:
        pass  # No action
    else:
        print(i)
```

#### Output:

```
3
4
```

---

### ❓ 9. Does `pass` affect performance?

👉 **Answer:**
Negligibly.
It simply tells Python to do nothing and continue.

---

### ❓ 10. Show a real-life use case where `pass` is helpful in a loop.

👉 **Answer:**

```python
tasks = ["process data", "save file", "send report"]
for task in tasks:
    if task == "save file":
        pass  # Saving logic not implemented yet
    else:
        print(f"Executing: {task}")
```

---

## 🎯 Summary Table

| Feature                        | Example                                         |
| ------------------------------ | ----------------------------------------------- |
| Simple pass in for loop        | `for i in range(3): pass`                       |
| Simple pass in while loop      | `while count < 5: pass`                         |
| Pass inside conditional        | `if condition: pass`                            |
| Pass vs Continue               | `pass` does nothing; `continue` skips iteration |
| Placeholder during development | Useful when code is not ready yet               |

