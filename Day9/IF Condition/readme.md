
# 🐍 Python Conditional Statements: if, elif, and Nested if

## ✅ What Are Conditional Statements?

Conditional statements allow you to execute specific blocks of code based on logical conditions.  
They help your program **make decisions**.

---

## ✅ 1️⃣ Simple if Statement

The `if` statement executes a block of code only if the condition is `True`.

### ✅ Example:

```python
age = 18

if age >= 18:
    print("You are eligible to vote.")
````

---

## ✅ 2️⃣ if...else Statement

The `else` block runs if the `if` condition is `False`.

### ✅ Example:

```python
age = 16

if age >= 18:
    print("You are eligible to vote.")
else:
    print("You are not eligible to vote.")
```

---

## ✅ 3️⃣ if...elif...else Ladder

Use `elif` when you have **multiple conditions** to check.

### ✅ Example:

```python
marks = 75

if marks >= 90:
    print("Grade A")
elif marks >= 75:
    print("Grade B")
elif marks >= 50:
    print("Grade C")
else:
    print("Fail")
```

---

## ✅ 4️⃣ Nested if Statements

An `if` statement inside another `if` statement allows checking **complex conditions**.

### ✅ Example:

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Allowed to enter the club.")
    else:
        print("You must show your ID.")
else:
    print("You are not allowed to enter the club.")
```

---

## ✅ 5️⃣ Practical Example: Temperature Checker

```python
temperature = 35

if temperature > 40:
    print("It's extremely hot!")
elif temperature > 30:
    print("It's hot.")
elif temperature > 20:
    print("It's warm.")
elif temperature > 10:
    print("It's cool.")
else:
    print("It's cold.")
```

---

## ✅ 6️⃣ Example: Grading System with Nested if

```python
marks = 85
attendance = 90

if marks >= 75:
    if attendance >= 80:
        print("Passed with Distinction")
    else:
        print("Passed, but insufficient attendance for distinction")
else:
    print("Failed")
```

---

## ✅ 7️⃣ Best Practices

* Keep code blocks properly indented (use 4 spaces).
* Avoid excessive nesting—refactor if logic becomes too complex.
* Use descriptive variable names.

---

## ✅ 8️⃣ Common Interview Questions

---

### ❓ Q1: What is the difference between `if`, `elif`, and multiple `if` statements?

✅ **Answer**:

* `if` checks a single condition.
* `elif` checks another condition **only if previous conditions are False**.
* Multiple separate `if` statements are evaluated independently.

---

### ❓ Q2: Can `else` exist without `if`?

❌ No, `else` always follows an `if` or `elif`.

---

### ❓ Q3: How to write a concise if-else in Python?

✅ Use ternary operator:

```python
status = "Adult" if age >= 18 else "Minor"
```

---

### ❓ Q4: What happens if multiple conditions are true in if-elif-else ladder?

✅ Only the **first matching condition is executed**.

---

### ❓ Q5: Why avoid deep nested if statements?

✅ They reduce code readability and increase complexity. Prefer using functions or logical operators (`and`, `or`).

---

## ✅ 9️⃣ Real-world Scenario: Login System

```python
username = "admin"
password = "securepass"

if username == "admin":
    if password == "securepass":
        print("Login Successful")
    else:
        print("Incorrect Password")
else:
    print("Unknown User")
```

---

## ✅ 1️⃣0️⃣ Multiple Conditions with Logical Operators

```python
age = 25
has_license = True

if age >= 18 and has_license:
    print("Allowed to drive")
else:
    print("Not allowed to drive")
```

---

## ✅ 1️⃣1️⃣ Nested if Example: Banking Eligibility

```python
age = 30
salary = 50000

if age >= 18:
    if salary >= 30000:
        print("Eligible for Premium Credit Card")
    else:
        print("Eligible for Regular Credit Card")
else:
    print("Not eligible for Credit Card")
```

---

## ✅ 1️⃣2️⃣ Ternary Example for Simplicity

```python
age = 16
status = "Adult" if age >= 18 else "Minor"
print(status)
```

---

## ✅ 1️⃣3️⃣ Looping with Conditional

```python
numbers = [5, 10, 15, 20, 25]

for num in numbers:
    if num % 2 == 0:
        print(f"{num} is even")
    else:
        print(f"{num} is odd")
```

---

## ✅ Summary of Key Concepts

| Statement        | Purpose                                          |
| ---------------- | ------------------------------------------------ |
| `if`             | Check a single condition                         |
| `elif`           | Check multiple, exclusive conditions             |
| `else`           | Catch-all if none of the conditions match        |
| Nested `if`      | Check multiple related conditions hierarchically |
| Ternary Operator | Compact one-liner if-else expression             |

---

## ✅ Conclusion

Conditional statements form the backbone of decision-making in Python programs.
Master them to write efficient, clean, and logical code for any application.

🚀 Keep practicing with real problems to become proficient!

---

⭐ Happy Coding with Python Conditionals! 🚀

```

---

Would you like me to export this as a `.md` file for your reference or use?
```
