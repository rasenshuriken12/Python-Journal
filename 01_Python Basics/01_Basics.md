# Variables in Python

## 📌 Overview
This set of notes covers the foundational Python concepts:

1. **Variables** – what they are, how to assign values, and how Python handles types.
2. **Variable naming rules** – what's allowed and what's not.
3. **Popular naming conventions** – Camel Case, Pascal Case, Snake Case, Upper Snake Case
4. **Descriptive naming** – why it matters.
5. **Data types** – integer, float, complex, string.
6. **Dynamic typing** – no need to declare types.
7. Displaying output & Taking user input.
8. **Type casting** – Converting between data types.
9. **Memory management** – how variables occupy memory and how to delete them.
10. **Comments** – Documenting your code.
11. **Indentation** – Python's block structure.

---

## 🧠 What is a Variable?

> **Variable** = A symbolic name that stores data for later use.

### Key Points
| Concept | Explanation |
|---------|-------------|
| **Name** | A descriptive label (e.g., `x`, `y`, `sum_of_a_and_b`) |
| **Purpose** | Store data to reuse it throughout the program |
| **Assignment** | The act of storing data in a variable using `=` |
| **Dynamic Typing** | Python automatically determines the type based on the assigned value |

### Assignment
```python
x = 2          # 2 is assigned to x
y = 5          # 5 is assigned to y
xy = 7.2       # 7.2 is assigned to xy
```

> 💡 **Tip**: Use **descriptive variable names** for better readability (e.g., `total_sales` instead of `ts`).

---

## 📜 Variable Naming Rules
| Rule | Explanation | Example |
|------|-------------|---------|
| **Start with letter or `_`** | Cannot start with a digit or special character | `x`, `_x` ✅ |
| **No starting digit** | `3x` is invalid | `3x` ❌ |
| **No special characters** | Except underscore `_` | `@y`, `*t`, `#n` ❌ |
| **Case-sensitive** | `X` and `x` are different | `X ≠ x` |
| **No Python keywords** | Cannot use reserved words | `if`, `for`, `class` ❌ |
| **Can contain letters, digits, `_`** | After the first character | `my_var1` ✅ |

### Allowed Special Characters
| Character | Allowed? | Example |
|-----------|----------|---------|
| `_` (underscore) | ✅ | `_name`, `my_var` |
| `@` | ❌ | `@rate` |
| `#` | ❌ | `#count` |
| `*` | ❌ | `*x` |
| `-` | ❌ | `my-var` |
| `.` | ❌ | `my.var` |
| `$` | ❌ | `$price` |

### Examples of Variable Names
```python
3x = 5          # ❌ SyntaxError: invalid syntax
@y = 4          # ❌ SyntaxError: invalid syntax
_e = 6          # ✅ Valid, `_e` is different from the built-in `_` variable.
* t = 4         # ❌ SyntaxError: invalid syntax
#name = "Hi"    # ❌ SyntaxError: invalid syntax
```

## 📝 Descriptive Variable Names

### Why Descriptive Names Matter
| Reason | Explanation |
|--------|-------------|
| **Readability** | Code is easier to understand |
| **Maintainability** | Easier to debug and modify |
| **Self-documenting** | Names explain what data they hold |
| **Teamwork** | Others can read your code easily |

### Examples

#### ❌ Bad Variable Names
```python
x = 2.0          # What is x?
y = 100          # What is y?
z = 5            # What is z?
```

#### ✅ Good Variable Names
```python
startingTimeOfTheCourse = 2.0
numberOfStudents = 100
maxRetries = 5
```

> 💡 **Key Insight**: By just reading the name, you know what data is inside.

---

## 🐪 Camel Notation

### What is Camel Notation?
> A naming convention where:
> - The first word starts with a **lowercase letter**.
> - Each subsequent word starts with an **uppercase letter**.
> - No underscores between words.

### Format
```
firstWordSecondWordThirdWord
```

> 💡 **Note**: This notation is very popular among **Java developers**.

---

## 🔤 Other Naming Conventions

| Convention | Format | Example | Popular In |
|------------|--------|---------|------------|
| **Camel Case** | `firstWordSecondWord` | `startingTime` | Java, JavaScript |
| **Pascal Case** | `FirstWordSecondWord` | `StartingTime` | C#, Java classes |
| **Snake Case** | `first_word_second_word` | `starting_time` | Python (PEP 8) |
| **Upper Snake Case** | `FIRST_WORD_SECOND_WORD` | `STARTING_TIME` | Constants |

> 📝 **Python Recommendation (PEP 8)**:
> - Use **snake_case** for variables and functions: `starting_time`
> - Use **PascalCase** for classes: `StartingTime`
> - Use **UPPER_SNAKE_CASE** for constants: `MAX_RETRIES`

---

## 📊 Basic Data Types

### 1. Integer (`int`)
- Whole numbers **without** a decimal point.
```python
x = 2          # int
y = -10        # int
```

### 2. Float (`float`)
- Numbers **with** a decimal point.
```python
x = 7.2        # float
y = 5.0        # float (even though it looks like an integer)
```

### 3. Complex (`complex`)
- Numbers with a real and imaginary part (using `j`).
```python
c = 2 + 4j     # complex
```

### 4. String (`str`)
- A **sequence of characters** enclosed in quotes.
```python
s = "Hello"    # string
s2 = "12"      # string, NOT integer 12
```

> 💡 **Key Insight**: `"12"` (string) is different from `12` (integer). The quotes matter!

---

## 🧪 Python is Dynamically Typed

### What Does That Mean?
- You **don't** need to declare the type of a variable.
- The **content** you assign determines the type **automatically**.

### Example
```python
x = 3          # x is int
type(x)        # <class 'int'>

x = 5.7        # x is now float (type changed automatically!)
type(x)        # <class 'float'>
```

> 💡 **Key Insight**: The same variable can change its type based on the assigned value.

---

## 🖨️ The `print()` Function

- Displays output on the console/screen.

### Basic Syntax
```python
print(value1, value2, ..., sep=' ', end='\n')
```

| Parameter | Description | Default |
|-----------|-------------|---------|
| `value1, value2, ...` | Values to print (can be multiple) | Required |
| `sep` | Separator between values | `' '` (space) |
| `end` | What to print at the end | `'\n'` (newline) |

### Examples

#### 1. Print a String
```python
print("Hello World!")
```
**Output:**
```
Hello World!
```

#### 2. Print Multiple Values
```python
name = "Arya"
age = 18
height, weight = 5.0, "54.5"

print(name, age) 
print(type(name), type(age))
print(height, weight)
print(type(height), type(weight))
```
**Output:**
```
Arya 18
<class 'str'> <class 'int'>
5.0 54.5
<class 'float'> <class 'str'>
```

> 💡 **Note**: `print()` automatically adds a newline (`\n`) after each call.

#### 3. Using `sep` Parameter
```python
print("Hello", "World", sep="-")
```
**Output:**
```
Hello-World
```

> By default, `print()` separates comma-separated items with a space. `sep="-"` changes the separator to a hyphen (`-`).

#### 4. Using `end` Parameter
```python
print("Hello", end=" ")
print("World")
```
**Output:**
```
Hello World
```

> By default, `print()` ends with a new line. `end=" "` changes it to a space, so the next `print()` continues on the same line.

#### 5. Printing Numbers
```python
print(42)
print(3.14)
print(2 + 3)
```
**Output:**
```
42
3.14
5
```

#### 6. Printing with f-strings (Formatted Strings)
```python
name = "Vimla"
age = 18
print(f"My name is {name} and I am {age} years old.")
```
**Output:**
```
My name is Vimla and I am 18 years old.
```

#### 7. Repeating Strings with `*`
```python
print("-" * 10)
```
**Output:**
```
----------
```

---

## ⌨️ The `input()` Function

- Takes input from the user as a **string**.

### Basic Syntax
```python
variable = input("prompt message: ")
```

### Examples

#### 1. Basic Input
```python
name = input("Enter your name: ")
print("Hello,", name, "! Welcome!")
```
**Output:**
```
Enter your name: Vidisha
Hello, Vidisha ! Welcome!
```

> ⚠️ **Important**: `input()` **always returns a string**, even if the user enters a number.

#### 2. Multiple Inputs at Once

You can assign values to multiple variables in a **single line**:

```python
x, y, z = input("Enter name, age, weight: ").split()
print("Name : ", x)
print("Age : ", y)
print("Weight : ", z)
print(type(x), type(y), type(z))
```
**Output:**
```
Enter name, age, weight: Vimla 18 52.0
Name : Vimla
Age : 18
Weight : 52.0
<class 'str'> <class 'str'> <class 'str'>
```

> - `.split()` separates the input at spaces and returns a list of strings, which are then unpacked into x, y, and z.
> - Although `18` & `52.0` look like an integer and float, they are stored as a **string**.
> - To use them as numbers, you need **typecasting**.

---

## 🔄 Typecasting

- Converting one data type to another.

### Common Conversion Functions

| Function | Converts To | Example |
|----------|-------------|---------|
| `int()` | Integer | `int("10")` → `10` |
| `float()` | Float | `float("3.14")` → `3.14` |
| `str()` | String | `str(42)` → `"42"` |
| `bool()` | Boolean | `bool(1)` → `True` |
| `list()` | List | `list("abc")` → `['a', 'b', 'c']` |
| `tuple()` | Tuple | `tuple([1, 2])` → `(1, 2)` |
| `set()` | Set | `set([1, 2, 2])` → `{1, 2}` |
| `complex()` | Complex | `complex(1, 2)` → `(1+2j)` |

### Examples

#### 1. Integer Conversion
```python
n = int(input("No. of Students: "))
print(n)
print(type(n))
```
**Output:**
```
No. of Students: 10
10
<class 'int'>
```

#### 2. Float Conversion
```python
m = float(input("Average Marks: "))
print(m)
print(type(m))
```
**Output:**
```
Average Marks: 75.5
75.5
<class 'float'>
```

#### 3. String Conversion
```python
x = str(42)
print(x)
print(type(x))
```
**Output:**
```
42
<class 'str'>
```

#### 4. Boolean Conversion
```python
print(bool(0))      # False
print(bool(1))      # True
print(bool(""))     # False
print(bool("Hi"))   # True
```

> ⚠️ **Warning**: `int("hello")` will cause a **ValueError** because "hello" cannot be converted to an integer.

---

## 💾 Memory Management

### Variables Occupy Memory
- Each variable is a **label** pointing to a location in memory.
- The data is stored at that memory location.

### Checking Variables in Memory
```python
%whos
```
- Shows all variables currently in memory with their types and values.

### Deleting Variables
```python
del variable_name
```
- Removes the variable from memory.
- After deletion, accessing it will cause an **error**.

### Example
```python
abcd = 556.32
%whos

del abcd
print(abcd)    # ❌ NameError: name 'abcd' is not defined
```
**Output:**
```bash
Variable   Type     Data/Info
-----------------------------
abcd       float    556.32
```

---

## 💬 Comments

- Lines in code that Python **ignores** during execution. Used to explain code.

### Types of Comments

#### 1. Single-line Comment (`#`)
```python
# This is a single-line comment.
x = 10  # This comment is after code
```

#### 2. Multi-line Comment (`"""` or `'''`)
```python
"""
This is a multi-line comment.
It spans multiple lines.
"""

'''
This is also a multi-line comment.
Using single quotes.
'''
```

### Why Use Comments?
| Purpose | Example |
|---------|------Comments explain code; ignored by Python.---|
| Explain complex code | `# Calculate compound interest` |
| Document functions | `# This function sorts a list` |
| Temporarily disable code | `# print("Debug:", x)` |
| Add notes for yourself | `# TODO: Optimize this loop` |

### Best Practices
- ✅ Keep comments **short and meaningful**.
- ✅ Update comments when code changes.
- ❌ Don't state the obvious: `# Increment x by 1` for `x += 1` is redundant.
- ✅ Use comments to explain **why**, not **what**.

## 📐 Indentation

### What is Indentation?

- **Whitespace at the beginning of a line** that defines blocks of code.

### Key Rules
| Rule | Explanation |
|------|-------------|
| **Consistent** | Use 4 spaces (standard) or a tab throughout. |
| **Required** | Python uses indentation to define code blocks (unlike `{}` in other languages). |
| **Same level = Same block** | Statements with the same indentation belong to the same block. |
| **Deeper = Nested** | More indentation = inner block. |

### Examples

#### 1. Basic `if` Block
```python
if 10 > 5:
    print("I have indentation.")

print("I have no indentation.")
```
**Output:**
```
I have indentation.
I have no indentation.
```
> The first `print()` is **inside** the `if` block (indented).  
> The second `print()` is **outside** the `if` block (not indented).

#### 2. Nested Blocks
```python
if 10 > 5:
    print("Outer block")
    if 5 > 2:
        print("Inner block")
```
**Output:**
```
Outer block
Inner block
```

#### 3. Common Indentation Error
```python
if 10 > 5:
print("Hello")    # ❌ IndentationError
```
**Error:**
```
IndentationError: expected an indented block
```

### Visual Representation
```
if condition:
    ┌─────────────────┐
    │ Indented block  │  ← 4 spaces
    │ (inside if)     │
    └─────────────────┘
print("Outside")       ← No indentation
```

---

## ❓ Question for Next Video

### Variable Naming Conventions

| Rule | Example | Valid? |
|------|---------|--------|
| Start with letter or `_` | `x`, `_x` | ✅ |
| Start with digit | `3x` | ❌ |
| Contain letters, digits, `_` | `my_var1` | ✅ |
| Contain special symbols | `@rate`, `x*y` | ❌ |
| Use Python keywords | `if`, `for`, `class` | ❌ |
| Case-sensitive | `X` ≠ `x` | ✅ |

---

## 🔑 Key Takeaways

1. **print()** is for output; supports multiple values, separators, and formatting.
2. **input()** always returns a string – use typecasting to convert.
3. **Typecasting** converts between types: int(), float(), str(), bool().
4. **Variables** are named placeholders for data.
5. **Use descriptive variable names** for readability.
6. **Camel notation** is one popular convention: `startingTimeOfTheCourse`.
7. **The value determines the type** – assign `3` → int, assign `5.7` → float.
8. **Multiple assignment** allows setting several variables in one line.
9. **Variables occupy memory** – use `%whos` to view them.
10. **`del` removes variables** from memory permanently.
11. **Comments** explain code; ignored by Python.
12. **Indentation** is **mandatory** in Python – it defines blocks. 

---

## 🔮 What's Next

### Upcoming Topics
- **Operators** – arithmetic, comparison, logical, assignment.

- **Boolean data type** – `True` / `False`
- **Decision making** – using comparisons in `if` statements

---

*"Variables are the building blocks of any program. Understanding them is the first step to mastering Python."* 🚀
