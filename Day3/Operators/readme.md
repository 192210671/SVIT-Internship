
---

# 🐍 Operators in Python

In Python, **operators** are special symbols that perform operations on values or variables (called **operands**).

---

## 🔹 1. Arithmetic Operators

Used for mathematical operations.

| Operator | Description            | Example (`a=10, b=3`) | Result  |
| -------- | ---------------------- | --------------------- | ------- |
| `+`      | Addition               | `a + b`               | `13`    |
| `-`      | Subtraction            | `a - b`               | `7`     |
| `*`      | Multiplication         | `a * b`               | `30`    |
| `/`      | Division (float)       | `a / b`               | `3.333` |
| `//`     | Floor Division         | `a // b`              | `3`     |
| `%`      | Modulus (remainder)    | `a % b`               | `1`     |
| `**`     | Exponentiation (power) | `a ** b`              | `1000`  |

---

## 🔹 2. Comparison (Relational) Operators

Used to compare two values.

| Operator | Description         | Example (`a=10, b=3`) | Result  |
| -------- | ------------------- | --------------------- | ------- |
| `==`     | Equal to            | `a == b`              | `False` |
| `!=`     | Not equal to        | `a != b`              | `True`  |
| `>`      | Greater than        | `a > b`               | `True`  |
| `<`      | Less than           | `a < b`               | `False` |
| `>=`     | Greater or equal to | `a >= b`              | `True`  |
| `<=`     | Less or equal to    | `a <= b`              | `False` |

---

## 🔹 3. Logical Operators

Used to combine conditional statements.

| Operator | Description       | Example (`a=10, b=3`) | Result  |
| -------- | ----------------- | --------------------- | ------- |
| `and`    | True if both true | `(a > 5) and (b < 5)` | `True`  |
| `or`     | True if one true  | `(a < 5) or (b < 5)`  | `True`  |
| `not`    | Negates condition | `not(a > 5)`          | `False` |

---

## 🔹 4. Assignment Operators

Used to assign values to variables.

| Operator | Example   | Equivalent to |
| -------- | --------- | ------------- |
| `=`      | `x = 5`   | `x = 5`       |
| `+=`     | `x += 3`  | `x = x + 3`   |
| `-=`     | `x -= 3`  | `x = x - 3`   |
| `*=`     | `x *= 3`  | `x = x * 3`   |
| `/=`     | `x /= 3`  | `x = x / 3`   |
| `//=`    | `x //= 3` | `x = x // 3`  |
| `%=`     | `x %= 3`  | `x = x % 3`   |
| `**=`    | `x **= 3` | `x = x ** 3`  |

---

## 🔹 5. Bitwise Operators

Operate on binary numbers (bit by bit).

| Operator | Description       | Example (`a=10 (1010), b=3 (0011)`) | Result |          |        |      |
| -------- | ----------------- | ----------------------------------- | ------ | -------- | ------ | ---- |
| `&`      | AND               | `a & b` → `1010 & 0011`             | `2`    |          |        |      |
| \`       | \`                | OR                                  | \`a    | b`→`1010 | 0011\` | `11` |
| `^`      | XOR               | `a ^ b` → `1010 ^ 0011`             | `9`    |          |        |      |
| `~`      | NOT (invert bits) | `~a`                                | `-11`  |          |        |      |
| `<<`     | Left shift        | `a << 2`                            | `40`   |          |        |      |
| `>>`     | Right shift       | `a >> 2`                            | `2`    |          |        |      |

---

## 🔹 6. Identity Operators

Used to compare **object identity** (not values).

| Operator | Description                             | Example      |
| -------- | --------------------------------------- | ------------ |
| `is`     | True if both refer to same object       | `a is b`     |
| `is not` | True if they don’t refer to same object | `a is not b` |

---

## 🔹 7. Membership Operators

Used to test membership in sequences like lists, strings, tuples.

| Operator | Description                 | Example                     |
| -------- | --------------------------- | --------------------------- |
| `in`     | True if value exists        | `'a' in 'apple' → True`     |
| `not in` | True if value doesn’t exist | `'x' not in 'apple' → True` |

---

## ✅ Example Program

```python
a = 10
b = 3

print("Arithmetic:", a + b, a - b, a * b, a / b)
print("Comparison:", a > b, a == b)
print("Logical:", (a > 5) and (b < 5))
print("Assignment:")
x = 5
x += 2
print("x after += 2:", x)
print("Bitwise:", a & b, a | b, a ^ b)
print("Identity:", a is b, a is not b)
print("Membership:", 'a' in 'apple', 'x' not in 'apple')
```

---

