

## 🔹 Type Casting vs Type Conversion in Programming

### 1. **Type Conversion (Type Coercion / Implicit Conversion)**

* **Definition:** Automatic conversion of one data type into another by the compiler.
* **Also called:** *Type coercion* or *implicit conversion*.
* **When it happens:**

  * Assigning a smaller data type to a larger data type (e.g., `int → float`).
  * In expressions where different data types are used, the compiler converts them to the same type.
* **Example in Python:**

  ```python
  x = 10     # int
  y = 2.5    # float
  z = x + y  # int gets converted to float automatically
  print(z)   # 12.5 (float)
  ```

---

### 2. **Type Casting (Explicit Conversion)**

* **Definition:** Manually converting one data type into another using functions or methods.
* **Also called:** *Explicit conversion*.
* **When it happens:**

  * When we want to force a change of type.
  * Risky because data might be **lost** (e.g., float → int removes decimals).
* **Example in Python:**

  ```python
  a = 10.75    # float
  b = int(a)   # explicit casting to int
  print(b)     # 10
  ```

---

### 🔑 **Comparison Table**

| Feature              | Type Conversion (Implicit)   | Type Casting (Explicit) |
| -------------------- | ---------------------------- | ----------------------- |
| **Who performs it?** | Compiler / Interpreter       | Programmer              |
| **Safety**           | Safer (no data loss usually) | Risk of data loss       |
| **Example**          | `int + float → float`        | `int(3.14)` → `3`       |
| **Other names**      | Type Coercion                | Explicit Conversion     |

---

### ✅ Quick Real-life Analogy

* **Type Conversion (automatic):** Like a shopkeeper automatically giving you change in coins if you hand over a larger note.
* **Type Casting (manual):** Like you breaking a note into coins yourself to pay exactly.

---

