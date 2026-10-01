# Functions in Python

## 📌 Overview
This set of videos covers:
1. **What is a function?** – Why we need them.
2. **Defining a function** – `def` keyword, body, calling.
3. **Docstrings** – Documenting your functions.
4. **Arguments/Parameters** – Passing data to functions.
5. **Multiple arguments** – Functions with several inputs.
6. **Order of arguments** – Positional vs keyword arguments.

---

## 🧠 What is a Function?

> **Function** = A reusable block of code that performs a specific task.

### Why Use Functions?
| Reason | Explanation |
|--------|-------------|
| **Reusability** | Write once, use many times |
| **Modularity** | Break large programs into smaller pieces |
| **Readability** | Code is easier to understand |
| **Debugging** | Fix a bug in one place |
| **Maintainability** | Update logic in one location |

### Without Functions (Repetitive)
```python
print("Task successful")
print("Moving to the next task")
print("Send me the next task")

# ... later in the program ...

print("Task successful")
print("Moving to the next task")
print("Send me the next task")
```

### With Functions (Clean)
```python
def print_success():
    print("Task successful")
    print("Moving to the next task")
    print("Send me the next task")

print_success()    # Call it once
print_success()    # Call it again
```

---

## 1️⃣ Defining a Function

### Syntax
```python
def function_name():
    # body of function (indented)
```

### Components
| Part | Description | Example |
|------|-------------|---------|
| `def` | Keyword to define a function | `def` |
| `function_name` | Descriptive name | `print_success` |
| `()` | Parentheses (for parameters) | `()` |
| `:` | Colon at end | `:` |
| **Body** | Indented code block | `print("Hello")` |

### Example
```python
def print_success():
    print("I am done")
    print("Send me another task")

print_success()
```
**Output:**
```
I am done
Send me another task
```

> 💡 **Note**: Defining a function does **not** run it. You must **call** it.

---

## 2️⃣ Docstrings (Documentation Strings)

> **Docstring** = A description of what the function does. Written as the **first statement** inside the function.

### Syntax
```python
def function_name():
    """Description of the function."""
    # body
```

### Example
```python
def print_message(message):
    """
    This function prints the message supplied by the user.
    If the message is not a string, it prints a warning.
    """
    if isinstance(message, str):
        print(message)
    else:
        print("Your input argument is not a string.")
        print("Here is what you have supplied:", message)
        print("Type:", type(message))
```

### Accessing Docstrings
| Method | What It Shows |
|--------|---------------|
| `function_name?` | Docstring only |
| `function_name??` | Docstring + implementation |
| `help(function_name)` | Docstring + signature |

**Example:**
```python
print_message?
```
**Output:**
```
Signature: print_message(message)
Docstring:
This function prints the message supplied by the user.
If the message is not a string, it prints a warning.
File:      <ipython-input-...>
Type:      function
```

> 💡 **Best Practice**: **Always write docstrings** for your functions.

---

## 3️⃣ Arguments (Parameters)

> **Argument** = Data passed to a function when calling it.

### Single Argument
```python
def print_message(message):
    print(message)

print_message("Hello")      # Hello
print_message("Success")    # Success
print_message(74)           # 74
```

### How It Works
- `message` is a **parameter** (variable in the function definition).
- `"Hello"` is an **argument** (value passed at call time).
- The argument is **copied** into the parameter.

---

## 4️⃣ Multiple Arguments

> Functions can accept **multiple arguments**.

### Syntax
```python
def function_name(arg1, arg2, arg3):
    # body
```

### Example: Custom Power Function
```python
def my_power(a, b):
    """This function computes power, just like the built-in pow function."""
    c = a ** b
    print(c)

my_power(3, 4)    # 81
```

### Example: Type Checking Function
```python
def check_args(a, b, c):
    """Check if all arguments are numeric and print their sum of squares."""
    if isinstance(a, (int, float)) and isinstance(b, (int, float)) and isinstance(c, (int, float)):
        print((a + b + c) ** 2)
    else:
        print("Error: Input arguments are not of the expected types.")

check_args(3, 4, 5)         # 144
check_args(3, 4, "g")       # Error message
```

### ⚠️ Argument Count Must Match
```python
check_args(3, 4)            # ❌ TypeError: missing 1 required argument
check_args(3, 4, 5, 6)      # ❌ TypeError: too many arguments
```

> 💡 **Note**: The number of arguments at call time must match the definition.

---

## 5️⃣ Order of Arguments

> Arguments are matched **by position** by default.

### Positional Arguments
```python
def f(a, b, c):
    print("A is", a)
    print("B is", b)
    print("C is", c)

f(2, 3, "game")
```
**Output:**
```
A is 2
B is 3
C is game
```

### Changing Order Changes Behavior
```python
f("game", 3, 2)
```
**Output:**
```
A is game
B is 3
C is 2
```

> ⚠️ **Important**: The **first value** goes to the **first parameter**, the **second value** to the **second parameter**, etc.

---

## 6️⃣ Keyword Arguments

> You can specify **which argument goes to which parameter** by name.

### Syntax
```python
function_name(param1=value1, param2=value2)
```

### Example
```python
def f(a, b, c):
    print("A is", a)
    print("B is", b)
    print("C is", c)

f(a=2, b=3, c="game")
```
**Output:**
```
A is 2
B is 3
C is game
```

### Order Doesn't Matter with Keywords
```python
f(c="game", a=2, b=3)
```
**Output:**
```
A is 2
B is 3
C is game
```

### Mixing Positional and Keyword Arguments
```python
f(2, c="game", b=3)
```
**Output:**
```
A is 2
B is 3
C is game
```

> ⚠️ **Rule**: Positional arguments must come **before** keyword arguments.

---

## 📊 Positional vs Keyword Arguments

| Feature | Positional | Keyword |
|---------|-----------|---------|
| **Matching** | By position | By name |
| **Order matters?** | ✅ Yes | ❌ No |
| **Readability** | Less clear | More clear |
| **Syntax** | `f(2, 3, "game")` | `f(a=2, b=3, c="game")` |
| **Mixing** | Must come first | Must come after positional |

---

## 🧪 Complete Practice Example

```python
def print_message(message):
    """
    Prints the message if it's a string.
    Otherwise, prints a warning with the type.
    """
    if isinstance(message, str):
        print(message)
    else:
        print("Your input is not a string.")
        print("Type:", type(message))

# Call with string
print_message("Hello there")    # Hello there

# Call with integer
print_message(23)
# Your input is not a string.
# Type: <class 'int'>

# Call with variable
y = "Hello there"
print_message(y)                # Hello there
```

---

## 📋 Quick Reference

| Concept | Syntax | Example |
|---------|--------|---------|
| **Define** | `def name():` | `def greet():` |
| **Call** | `name()` | `greet()` |
| **Docstring** | `"""..."""` | Inside function |
| **One argument** | `def f(x):` | `def f(message):` |
| **Multiple arguments** | `def f(a, b):` | `def f(x, y):` |
| **Positional** | `f(1, 2)` | Matches by order |
| **Keyword** | `f(a=1, b=2)` | Matches by name |

---

## 🔑 Key Takeaways

1. **Functions** are reusable blocks of code.
2. **`def`** keyword defines a function.
3. **Docstrings** document what a function does.
4. **Arguments** are data passed to functions.
5. **Multiple arguments** allow flexible functions.
6. **Positional arguments** match by order.
7. **Keyword arguments** match by name (order-free).
8. **Argument count must match** (unless using defaults or `*args`).
9. **Docstrings are accessible** via `?`, `??`, or `help()`.
10. **Functions improve** readability, maintainability, and debugging.

---

## 🔮 What's Next

### Upcoming Topics
- **Default arguments** – Parameters with default values.
- **`*args` and `**kwargs`** – Variable number of arguments.
- **Return values** – Getting data back from functions.
- **Scope** – Local vs global variables.
- **Lambda functions** – Anonymous functions.

---

*"Functions are the building blocks of clean code. Write once, use everywhere."* 🚀
