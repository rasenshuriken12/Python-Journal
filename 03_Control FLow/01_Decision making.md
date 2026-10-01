# Notes: Control Flow in Python

## 📌 Overview
This set of videos covers:
1. **`if` statement** – Basic decision making.
2. **`if-else`** – Two-way branching.
3. **`if-elif-else`** – Multi-way branching.
4. **Ternary (short-hand) if** – One-line conditional.
5. **Nested `if`** – `if` inside another `if`.
6. **Indentation** – Python's block definition.

---

## 🎯 What is Control Flow?

> **Control Flow** = The order in which statements are executed in a program.

By default, Python executes code **top to bottom**. Control flow lets you **change that order** based on conditions.

---

## 1️⃣ The `if` Statement

> Executes a block of code **only if** a condition is `True`.

### Syntax
```python
if condition:
    # body of if (indented)
```

### Example: Print the Larger Number
```python
a = int(input("Enter A: "))
b = int(input("Enter B: "))

if a > b:
    print(a)
```
**Output (if A=12, B=10):**
```
12
```

> ⚠️ **Important**: The **colon (`:`)** is required. The body must be **indented**.

---

## 2️⃣ The `if-else` Statement

> Executes one block if the condition is `True`, another if it's `False`.

### Syntax
```python
if condition:
    # body of if
else:
    # body of else
```

### Example: Print the Larger Number (Complete)
```python
a = int(input("Enter A: "))
b = int(input("Enter B: "))

if a > b:
    print(a)
else:
    print(b)
```
**Output (if A=10, B=12):**
```
12
```

> 💡 **Note**: `else` executes in **all other cases** — including when values are equal.

### Example with Equal Values
```python
a = 10
b = 10

if a > b:
    print("A is bigger")
else:
    print("B is bigger or equal")
```
**Output:**
```
B is bigger or equal
```

---

## 3️⃣ The `if-elif-else` Statement

> For **multiple conditions**, checked in order.

### Syntax
```python
if condition1:
    # body 1
elif condition2:
    # body 2
elif condition3:
    # body 3
else:
    # default body
```

### How It Works
1. Check `condition1` → if `True`, run body 1, **skip the rest**.
2. If `False`, check `condition2` → if `True`, run body 2, **skip the rest**.
3. Continue for all `elif` blocks.
4. If **all conditions are False**, run the `else` body.

### Example: Grade Calculator
```python
marks = int(input("Enter marks: "))

if marks >= 85:
    print("A Grade")
elif marks >= 80 and marks < 85:
    print("A- Grade")
elif marks >= 75 and marks < 80:
    print("B Grade")
elif marks >= 70 and marks < 75:
    print("B- Grade")
else:
    print("Below Average")
```

**Output Examples:**
| Marks | Output |
|-------|--------|
| 82 | A- Grade |
| 64 | Below Average |
| 90 | A Grade |

---

## 4️⃣ Ternary (Short-hand) `if`

> A one-line version of `if-else`.

### Syntax
```python
value = value_if_true if condition else value_if_false
```

### Example
```python
a = 9
b = 10

result = a if a > b else b
print(result)    # 10
```

### Long-form Equivalent
```python
if a > b:
    result = a
else:
    result = b
```

> ⚠️ **Recommendation**: Use the **long form** for readability, especially for complex conditions.

---

## 5️⃣ Nested `if`

> An `if` statement **inside** another `if` (or `else`) block.

### Syntax
```python
if condition1:
    # body of outer if
    if condition2:
        # body of inner if
    else:
        # body of inner else
else:
    # body of outer else
```

### Example
```python
a = int(input("Enter a number: "))

if a > 10:
    print("Greater than 10 (inside top if)")
    
    if a > 20:
        print("Greater than 20 (inside nested if)")
    else:
        print("Smaller or equal to 20 (inside else of nested if)")

print("Outside all ifs")
```

### Execution Flow

| Input | Output |
|-------|--------|
| `5` | `Outside all ifs` |
| `15` | `Greater than 10`<br>`Smaller or equal to 20`<br>`Outside all ifs` |
| `25` | `Greater than 10`<br>`Greater than 20`<br>`Outside all ifs` |

---

## 6️⃣ Indentation in Python

> **Indentation** defines the **block** of code.

### Rules
| Rule | Explanation |
|------|-------------|
| **4 spaces** | Standard indentation (per PEP 8) |
| **Consistent** | Use the same indentation throughout a block |
| **Required** | Python uses indentation, not `{}` |
| **Nested = Deeper** | Inner blocks have more indentation |

### Visual Example
```python
if a > 10:                        # Outer if
    print("Greater than 10")      # Inside outer if
    
    if a > 20:                    # Nested if
        print("Greater than 20")  # Inside nested if
    else:                         # Else of nested if
        print("<= 20")            # Inside else of nested if

print("Outside all ifs")          # Outside all ifs
```

### Common Indentation Errors
```python
if a > 10:
print("Hello")    # ❌ IndentationError
```

**Error:**
```
IndentationError: expected an indented block
```

> 💡 **Key Insight**: In Python, **indentation is not optional** — it's part of the syntax.

---

## 🔄 Simulation: `else` Using `elif`

You can simulate `else` without writing it explicitly:

```python
a = 3

if a > 10:
    print("Larger than 10")
elif not a > 10:
    print("Elsewhere")
```

**Output:**
```
Elsewhere
```

> `not a > 10` is `True` when `a > 10` is `False` — so it behaves like `else`.

---

## 📊 Comparison: `if` vs `elif` vs `else`

| Statement | When It Runs |
|-----------|--------------|
| `if` | When its condition is `True` |
| `elif` | When all previous conditions are `False` AND its condition is `True` |
| `else` | When all previous conditions are `False` |

---

## 🧪 Complete Example: Grade Calculator

```python
marks = int(input("Enter marks: "))

if marks >= 85:
    print("A Grade")
elif marks >= 80 and marks < 85:
    print("A- Grade")
elif marks >= 75 and marks < 80:
    print("B Grade")
elif marks >= 70 and marks < 75:
    print("B- Grade")
else:
    print("Below Average")
```

**Output:**
```
Enter marks: 82
A- Grade
```

---

## 📋 Quick Reference

| Concept | Syntax | Purpose |
|---------|--------|---------|
| `if` | `if cond:` | Single condition |
| `if-else` | `if cond: ... else: ...` | Two-way branching |
| `if-elif-else` | `if c1: ... elif c2: ... else: ...` | Multi-way branching |
| Ternary | `x if cond else y` | One-line if-else |
| Nested `if` | `if c1: if c2: ...` | `if` inside `if` |
| Indentation | 4 spaces | Defines blocks |

---

## 🔑 Key Takeaways

1. **`if`** executes code only when a condition is `True`.
2. **`else`** executes when the `if` condition is `False`.
3. **`elif`** allows checking multiple conditions in sequence.
4. **Only one branch** executes in an `if-elif-else` chain.
5. **Nested `if`** allows deeper decision making.
6. **Indentation** is **mandatory** in Python — it defines blocks.
7. **Ternary `if`** is a one-line shortcut for simple cases.
8. **`not`** can simulate `else` (`elif not condition:`).
9. **Comparisons** return Booleans, which drive control flow.
10. **Combine conditions** with `and`, `or`, `not` for complex logic.

---

## 🔮 What's Next

### Upcoming Topics
- **Loops** – `for` and `while` loops.
- **`break`, `continue`, `pass`** – Loop control.
- **More practice** with `if` combinations in Jupyter.

---

*"Control flow is the brain of your program. Master it, and your code will make smart decisions."* 🚀
