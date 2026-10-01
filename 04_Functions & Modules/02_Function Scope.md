# Functions – Scope, Return, *args, **kwargs, and Default Values

## 📌 Overview
This set of videos covers advanced function concepts:
1. **Variable Scope** – Local vs global variables.
2. **`return` statement** – Returning values (and exiting functions).
3. **`*args`** – Arbitrary number of positional arguments.
4. **`**kwargs`** – Arbitrary number of keyword arguments.
5. **Default values** – Parameters with default values.
6. **The mutable default trap** – A common pitfall.

---

## 1️⃣ Variable Scope

> **Scope** = The region of a program where a variable is accessible.

### Types of Scope

| Scope | Description | Accessible |
|-------|-------------|------------|
| **Local** | Defined inside a function | Only inside that function |
| **Global** | Defined outside all functions | Everywhere in the program |

### Local Variables (Inside Function)
```python
def my_add(a, b):
    some_value = a + b    # Local variable
    print("Inside:", some_value)

my_add(2, 3)
# print(some_value)    # ❌ NameError: name 'some_value' is not defined
```
**Output:**
```
Inside: 5
```

> ⚠️ **Key Rule**: Variables defined **inside** a function are **destroyed** when the function finishes.

### Global Variables (Outside Function)
```python
variable_outside = 3    # Global variable

def g():
    print("Inside function:", variable_outside)

g()                        # Inside function: 3
print("Outside:", variable_outside)    # Outside: 3
```
> ✅ Global variables are **accessible inside** functions.

### Local Shadows Global
```python
variable_outside = 3    # Global

def g():
    variable_outside = 5    # Local (shadows global)
    print("Inside:", variable_outside)

g()                        # Inside: 5
print("Outside:", variable_outside)    # Outside: 3
```

### Visual Representation
```
Global Scope
├── variable_outside = 3
│
└── Function g() Scope
    ├── variable_outside = 5  (shadows global)
    └── print → 5
```

> 💡 **Best Practice**: Pass values as **arguments** instead of relying on global variables — it reduces confusion.

---

## 2️⃣ The `return` Statement

> **`return`** sends a value back from a function to the caller.

### Purpose 1: Return a Value
```python
def my_add(a, b):
    c = a + b
    return c

d = my_add(2, 3)
print(d)    # 5
```

### Purpose 2: Exit the Function Early
```python
def h():
    print("A")
    a = 5
    b = 3
    c = a + b
    return    # Exit here (returns None)
    print("This will never print")

h()
```
**Output:**
```
A
```

### Returning Multiple Values
```python
def r():
    a = 5
    b = 7
    d = "something"
    return a, b, d

x, y, z = r()
print(x, y, z)    # 5 7 something
```

> 💡 **Note**: Python returns multiple values as a **tuple**.

### Functions Always Return Something
```python
def g():
    pass    # No explicit return

result = g()
print(result)         # None
print(type(result))   # <class 'NoneType'>
```

> ⚠️ **Key Rule**: If no `return` is specified, Python returns `None` automatically.

---

## 3️⃣ `*args` – Arbitrary Positional Arguments

> **`*args`** lets a function accept **any number** of positional arguments.

### Syntax
```python
def function_name(*args):
    # args is a tuple of all positional arguments
```

### Example: Universal Add Function
```python
def my_add_universal(*args):
    """Adds any number of arguments."""
    s = 0
    for i in range(len(args)):
        s += args[i]
    return s

print(my_add_universal(2, 4, 5))                # 11
print(my_add_universal(1, 2, 3, 4, 5))          # 15
print(my_add_universal(10))                     # 10
print(my_add_universal(1, 2, 3, 4, 5, 6, 7))    # 28
```

### How It Works
| Call | `args` Value | Length |
|------|-------------|--------|
| `my_add_universal(2, 4, 5)` | `(2, 4, 5)` | 3 |
| `my_add_universal(1, 2, 3, 4, 5)` | `(1, 2, 3, 4, 5)` | 5 |
| `my_add_universal(10)` | `(10,)` | 1 |

> 💡 **Note**: `args` is a **tuple** — accessed by index (`args[0]`, `args[1]`, ...).

---

## 4️⃣ `**kwargs` – Arbitrary Keyword Arguments

> **`**kwargs`** lets a function accept **any number** of keyword arguments.

### Syntax
```python
def function_name(**kwargs):
    # kwargs is a dictionary of key-value pairs
```

### Example: Print All Variables and Values
```python
def print_all_variable_names_and_values(**kwargs):
    """Prints each variable name and its value."""
    for x in kwargs:
        print("Variable name is:", x, "and value is:", kwargs[x])

print_all_variable_names_and_values(a=3, b="B", c="CCC", y=6.7)
```
**Output:**
```
Variable name is: a and value is: 3
Variable name is: b and value is: B
Variable name is: c and value is: CCC
Variable name is: y and value is: 6.7
```

### How It Works
| Call | `kwargs` Value |
|------|----------------|
| `f(a=3, b="B")` | `{'a': 3, 'b': 'B'}` |
| `f(x=1, y=2, z=3)` | `{'x': 1, 'y': 2, 'z': 3}` |

> 💡 **Note**: `kwargs` is a **dictionary** — accessed by key.

---

## 5️⃣ Default Values

> **Default value** = A value assigned to a parameter in the function definition.

### Syntax
```python
def function_name(param=default_value):
    # body
```

### Example
```python
def f(s=4):
    print(s)

f()       # 4 (uses default)
f(56)     # 56 (overrides default)
```

### Multiple Default Values
```python
def greet(name="Guest", greeting="Hello"):
    print(greeting, name)

greet()                       # Hello Guest
greet("Alice")                # Hello Alice
greet("Bob", "Hi")            # Hi Bob
greet(greeting="Hey")         # Hey Guest
```

### Rules
| Rule | Explanation |
|------|-------------|
| Defaults must come **after** non-default parameters | `def f(a, b=5):` ✅ |
| Non-defaults cannot follow defaults | `def f(a=5, b):` ❌ |
| Defaults are evaluated **once** at function definition | Important for mutable defaults |

---

## 6️⃣ The Mutable Default Trap ⚠️

> **Warning**: Mutable default values (like lists) are shared across all calls!

### The Problem
```python
def f(L=[1, 2]):
    print(L)

f()            # [1, 2]
f([10, 20])    # [10, 20]
f()            # [1, 2]  ← Still [1, 2] (not changed)
```

### Why? Defaults Are Evaluated Once
- The default list `[1, 2]` is created **once** when the function is defined.
- It's **not** re-created on each call.

### The Classic Trap
```python
def append_to_list(item, L=[]):
    L.append(item)
    return L

print(append_to_list(1))    # [1]
print(append_to_list(2))    # [1, 2]  ← Surprise!
print(append_to_list(3))    # [1, 2, 3]
```

### The Fix: Use `None` as Default
```python
def append_to_list(item, L=None):
    if L is None:
        L = []
    L.append(item)
    return L

print(append_to_list(1))    # [1]
print(append_to_list(2))    # [2]
print(append_to_list(3))    # [3]
```

> 💡 **Best Practice**: **Never use mutable objects as default values** — use `None` instead.

---

## 📊 Summary Table

| Concept | Syntax | Purpose |
|---------|--------|---------|
| Local variable | Inside function | Only accessible inside |
| Global variable | Outside function | Accessible everywhere |
| `return value` | `return x` | Send value back |
| `return` (bare) | `return` | Exit function |
| `*args` | `def f(*args):` | Arbitrary positional args (tuple) |
| `**kwargs` | `def f(**kwargs):` | Arbitrary keyword args (dict) |
| Default value | `def f(x=5):` | Optional parameter |
| Mutable default | `def f(L=[]):` | ⚠️ Avoid — use `None` |

---

## 🧪 Complete Practice Example

```python
# Scope
global_var = 100

def show_scope(local_var):
    print("Local:", local_var)
    print("Global:", global_var)

show_scope(50)
# Local: 50
# Global: 100

# Return
def add(a, b):
    return a + b

print(add(2, 3))    # 5

# *args
def total(*args):
    return sum(args)

print(total(1, 2, 3))          # 6
print(total(1, 2, 3, 4, 5))    # 15

# **kwargs
def show(**kwargs):
    for k, v in kwargs.items():
        print(f"{k} = {v}")

show(name="Alice", age=25)
# name = Alice
# age = 25

# Default values
def greet(name="Guest"):
    print("Hello,", name)

greet()            # Hello, Guest
greet("Bob")       # Hello, Bob
```

---

## 🔑 Key Takeaways

1. **Local variables** exist only inside functions.
2. **Global variables** are accessible everywhere.
3. **`return`** sends values back and exits the function.
4. **Functions always return** something (at least `None`).
5. **`*args`** accepts any number of positional arguments (as a tuple).
6. **`**kwargs`** accepts any number of keyword arguments (as a dictionary).
7. **Default values** make parameters optional.
8. **Defaults are evaluated once** at function definition.
9. **Never use mutable defaults** (lists, dicts) — use `None`.
10. **Pass arguments** instead of relying on globals — better practice.

---

## 🔮 What's Next

### Upcoming Topics
- **Lambda functions** – Anonymous functions.
- **Higher-order functions** – Functions that take/return functions.
- **`map()`, `filter()`, `reduce()`** – Functional programming tools.
- **Practice** – Building real programs with functions.

---

*"Functions are the verbs of programming. Master them, and you can build anything."* 🚀
