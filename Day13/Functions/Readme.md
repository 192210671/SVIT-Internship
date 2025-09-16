

## 1. **What is a Function?**

A **function** is a block of reusable code that performs a specific task.
Instead of writing the same code many times, you can define a function once and use it whenever needed.

👉 Think of it like a machine: you give input (arguments), the machine processes it, and gives output (return value).

---

## 2. **Why Use Functions?**

* **Reusability** → Write once, use many times.
* **Organization** → Makes code neat and modular.
* **Maintainability** → Easy to debug and update.
* **Abstraction** → You don’t need to know the details, just how to use it.

---

## 3. **Types of Functions in Python**

1. **Built-in functions** → Already provided by Python.
   Examples: `print()`, `len()`, `max()`, `sum()`.

2. **User-defined functions** → Functions we create using `def`.

---

## 4. **Defining a Function**

Syntax:

```python
def function_name(parameters):
    """docstring (optional): explains what the function does"""
    # body of function
    return value  # optional
```

Example:

```python
def greet(name):
    """This function greets the person passed in."""
    return f"Hello, {name}!"
```

---

## 5. **Calling a Function**

After defining, call it using its name:

```python
print(greet("Eswar"))  
# Output: Hello, Eswar!
```

---

## 6. **Function Components**

1. **Function Name** → Identifier (e.g., `greet`).
2. **Parameters / Arguments** → Inputs given to function.
3. **Docstring (Optional)** → Documentation string.
4. **Body** → Code inside function.
5. **Return Statement** → Sends result back.

---

## 7. **Parameters vs Arguments**

* **Parameter**: Variable in function definition.
* **Argument**: Actual value passed during call.

Example:

```python
def add(x, y):   # x, y are parameters
    return x + y

print(add(3, 5))  # 3, 5 are arguments
```

---

## 8. **Types of Arguments**

Python supports multiple ways to pass arguments:

1. **Positional Arguments**

   ```python
   def power(base, exp):
       return base ** exp

   print(power(2, 3))  # 8
   ```

2. **Keyword Arguments**

   ```python
   print(power(exp=3, base=2))  # 8
   ```

3. **Default Arguments**

   ```python
   def greet(name="Guest"):
       return f"Hello, {name}!"

   print(greet())  # Hello, Guest!
   ```

4. **Variable-length Arguments**

   * `*args` → handles multiple positional arguments.
   * `**kwargs` → handles multiple keyword arguments.

   ```python
   def add_all(*args):
       return sum(args)

   print(add_all(1, 2, 3, 4))  # 10
   ```

   ```python
   def print_info(**kwargs):
       for key, value in kwargs.items():
           print(f"{key}: {value}")

   print_info(name="Eswar", age=21)
   # name: Eswar
   # age: 21
   ```

---

## 9. **Return Statement**

* Functions can return values using `return`.
* If no `return`, function returns `None`.

```python
def square(x):
    return x * x

result = square(5)  # 25
```

---

## 10. **Scope of Variables**

* **Local variables** → defined inside function, accessible only inside it.
* **Global variables** → defined outside all functions, accessible everywhere.

```python
x = 10  # global

def func():
    x = 5  # local
    print(x)

func()   # 5
print(x) # 10
```

Use `global` keyword to modify global variables inside a function.

---

## 11. **Lambda Functions (Anonymous Functions)**

* Small, one-line functions without `def`.
* Syntax: `lambda arguments: expression`

```python
square = lambda x: x * x
print(square(5))  # 25
```

---

## 12. **Recursive Functions**

A function that calls itself.

Example: Factorial

```python
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n - 1)

print(factorial(5))  # 120
```

---

## 13. **Built-in Higher-order Functions**

These functions take other functions as arguments:

* `map()` → applies function to each element.
* `filter()` → filters elements based on condition.
* `reduce()` (from `functools`) → reduces sequence to single value.

Example:

```python
nums = [1, 2, 3, 4]
squares = list(map(lambda x: x*x, nums))
print(squares)  # [1, 4, 9, 16]
```

---

## 14. **Best Practices for Functions**

* Use meaningful names.
* Write docstrings.
* Keep functions small and focused.
* Avoid too many parameters (prefer \*args/\*\*kwargs when flexible).

---

✅ Quick Check for You:
Suppose you want to write a function `is_even(num)` that checks if a number is even.

* What should be the **parameter**?
* What should the function **return**?

Would you like to try answering that before I show the code?
