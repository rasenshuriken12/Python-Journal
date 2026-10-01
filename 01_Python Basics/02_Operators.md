# Operators in Python

## 📌 Overview
This video covers:
1. **Operators** – All types (Arithmetic, Comparison, Logical, Assignment, Identity, Membership, Bitwise, Ternary).
2. **Type upcasting** – mixing int and float.
3. Combining Operations
4. **Operator overloading** (brief intro – operators work on strings too).
5. The **underscore (`_`)** default variable in Jupyter.

## ➕ Operators (Complete Guide)

### Unary Operators

- Work on a **single** operand.
- A unary operator takes only one value and produces a result.

#### 1. Arithmetic Unary
```python
x = 3.14

print(+x)      # 3.14 (positive)
print(-x)      # -3.14 (negation)

print(+-5)     # -5
print(--5)     # 5 (double negative)
```

#### 2. Logical Unary (`not`)
```python
print(not True)    # False
print(not False)   # True
```
> `not` flips the Boolean value.

#### 3. Bitwise Unary (`~`)
```python
print(~10)    # -11 (inverts all bits)
```

---

### Binary Operators

- Work on **two** operands.
- A binary operator takes two values and produces a result.

#### 1. Arithmetic Operators

| Operator | Name | Example | Result | Description |
|----------|------|---------|--------|-------------|
| `+` | Addition | `10 + 3` | `13` | Adds two values |
| `-` | Subtraction | `10 - 3` | `7` | Subtracts right from left |
| `*` | Multiplication | `10 * 3` | `30` | Multiplies two values |
| `/` | Division | `10 / 3` | `3.333...` | Returns float result |
| `%` | Modulus | `27 % 5` | `2` | Returns the **remainder** |
| `//` | Floor Division | `10 // 3` | `3` | Returns the **quotient** (integer part) |
| `**` | Exponent | `2 ** 4` | `16` | Raises to a power |

**String Repetition:**
```python
print("-" * 10)   # ----------
```

> ⚠️ **Note**: In Python, we use `*` (star), not `×` (cross symbol).

> 💡 **Note**: Modulus (`%`) useful for checking **even/odd**, **divisibility**, etc.

---

**Combining Operations:**
```python
a = 5
d = 2.5
V = (a + d) ** 3 / 4
print(V)    # Result stored in V
```

**Order of Operations (PEMDAS)**
| Priority | Operator | Description |
|----------|----------|-------------|
| 1 | `()` | Parentheses |
| 2 | `**` | Exponent |
| 3 | `*`, `/`, `//`, `%` | Multiplication, Division |
| 4 | `+`, `-` | Addition, Subtraction |

---

#### 2. Comparison (Relational) Operators

- Compare two values and return True or False.

| Operator | Description | Example | Result |
|----------|-------------|---------|--------|
| `==` | Equal to | `10 == 5` | `False` |
| `!=` | Not equal | `10 != 5` | `True` |
| `>` | Greater than | `10 > 5` | `True` |
| `<` | Less than | `10 < 5` | `False` |
| `>=` | Greater or equal | `10 >= 5` | `True` |
| `<=` | Less or equal | `10 <= 5` | `False` |

```python
x = 10
y = 5

print("Equal:", x == y)              # False
print("Not equal:", x != y)          # True

print("Greater than:", x > y)        # True
print("Less than:", x < y)           # False

print("Greater or equal:", x >= y)   # True
print("Less or equal:", x <= y)      # False

print(3 == 3.0)   # True (Even though 3 is int and 3.0 is float, they are equal in value.)
```

**String Comparison:**
```python
print("apple" < "banana")    # True (alphabetical order)
```

**Combining comparisons:**
```python
x = 15
print(10 < x < 20)    # True (chained comparison)
```

> 💡 **Note**: `=` is assignment, `==` is comparison

---

#### 3. Logical Operators

- Combine Boolean values.

| A | B | A and B | A or B | not A |
|---|---|---------|--------|-------|
| True | True | True | True | False |
| True | False | False | True | False |
| False | True | False | True | True |
| False | False | False | False | True |

```python
age = 25
has_license = True

can_drive = age >= 18 and has_license
print("Can drive?", can_drive)        # True

has_discount = age < 12 or age >= 60
print("Has discount?", has_discount)  # False

is_adult = not (age < 18)
print("Is adult?", is_adult)          # True

result = not ((A and B) or (C or D))  # Complex Combination
print(result)                         # False
```

---

#### 4. Assignment Operators

| Operator | Description | Equivalent |
|----------|-------------|------------|
| `=` | Assign | `x = 10` |
| `+=` | Add & assign | `x = x + 5` |
| `-=` | Subtract & assign | `x = x - 3` |
| `*=` | Multiply & assign | `x = x * 2` |
| `/=` | Divide & assign | `x = x / 4` |
| `//=` | Floor divide & assign | `x = x // 2` |
| `%=` | Modulus & assign | `x = x % 2` |
| `**=` | Power & assign | `x = x ** 3` |

```python
x = 10
x += 5       # 15
x -= 3       # 12
x *= 2       # 24
x /= 4       # 6.0
x //= 2      # 3.0
x %= 2       # 1.0
x **= 3      # 1.0

# Multiple assignment
a, b, c = 1, 2, 3
print(a, b, c)    # 1 2 3
```

---

#### 5. Identity Operators

| Operator | Description |
|----------|-------------|
| `is` | True if both refer to **same object** |
| `is not` | True if they refer to **different objects** |

```python
a = [1, 2, 3]
b = [1, 2, 3]
c = a

print("a is b:", a is b)          # False (different objects)
print("a is c:", a is c)          # True (same object)
print("a is not b:", a is not b)  # True

print("a == b:", a == b)          # True (same values)
```

> 💡 **Key Difference**:
> - `==` compares **values**.
> - `is` compares **memory locations** (identity).

---

#### 6. Membership Operators

| Operator | Description |
|----------|-------------|
| `in` | True if value exists in sequence |
| `not in` | True if value does NOT exist |

```python
fruits = ["apple", "banana", "cherry"]

print("banana" in fruits)          # True
print("orange" not in fruits)      # True

# Works with strings
text = "Hello World"
print("World" in text)             # True

# Works with dictionaries (checks keys)
person = {"name": "Alice", "age": 30}
print("name" in person)            # True
print("Alice" in person)           # False (checks keys, not values)
```

|----------|-------------|
| `is` | True if both refer to **same object** |
| `is not` | True if they refer to **different objects** |

```python
a = [1, 2, 3]
b = [1, 2, 3]
```

---

#### 7. Bitwise Operators

> Work on numbers at the **binary level**.

| a | b | AND (`&`) | OR (`\|`) | XOR (`^`) |
|---|---|-----------|-----------|-----------|
| 1 | 1 | 1 | 1 | 0 |
| 1 | 0 | 0 | 1 | 1 |
| 0 | 1 | 0 | 1 | 1 |
| 0 | 0 | 0 | 0 | 0 |

```python
a = 10    # Binary: 1010
b = 4     # Binary: 0100

print("AND:", a & b)          # 0   (1010 & 0100 = 0000)
print("OR:", a | b)           # 14  (1010 | 0100 = 1110)
print("XOR:", a ^ b)          # 14  (1010 ^ 0100 = 1110)
print("NOT:", ~a)             # -11 (inverts bits)
print("Left shift:", a << 1)  # 20  (1010 → 10100)
print("Right shift:", a >> 1) # 5   (1010 → 0101)
```

**Practical Example: Check Even/Odd**
```python
num = 15
print(f"{num} is even?", (num & 1) == 0)    # False
```

---

### Ternary Operator
> Works on **three** operands (conditional expression).

```python
age = 20
status = "adult" if age >= 18 else "minor"
print(f"Age {age}: {status}")    # Age 20: adult
```

**Equivalent to:**
```python
if age >= 18:
    status = "adult"
else:
    status = "minor"
```

---

## 🔤 Operator Overloading (Beyond Numbers)

- Same operator, different behavior based on data type.

### `+` Works on Strings Too!
```python
S1 = "Hello"
S2 = "World"
S = S1 + S2
print(S)    # "HelloWorld"
```
- This is called **concatenation**.
- `+` is **overloaded** – its behavior depends on the data type.

### `*` on Strings
```python
print("-" * 10)    # ----------
```
- This is called repetition.

### `==` and `!=` on Strings (Equality)

```python
print("Hello" == "Hello")    # True
print("hello" == "Hello")    # False (case-sensitive)
```

> 💡 **Key Insight**: Operators are **not limited to integers and floats**. They work on many data types with different meanings.

---

## 📊 Operator Precedence (Highest to Lowest)

| Priority | Operator | Description |
|----------|----------|-------------|
| 1 | `()` | Parentheses |
| 2 | `**` | Exponentiation |
| 3 | `+x`, `-x`, `~x` | Unary operators |
| 4 | `*`, `/`, `//`, `%` | Multiplication, Division |
| 5 | `+`, `-` | Addition, Subtraction |
| 6 | `<<`, `>>` | Bitwise shifts |
| 7 | `&` | Bitwise AND |
| 8 | `^` | Bitwise XOR |
| 9 | `\|` | Bitwise OR |
| 10 | `==`, `!=`, `>`, `<`, `>=`, `<=` | Comparisons |
| 11 | `is`, `is not` | Identity |
| 12 | `in`, `not in` | Membership |
| 13 | `not` | Logical NOT |
| 14 | `and` | Logical AND |
| 15 | `or` | Logical OR |

---

### Example
```python
result = 2 + 3 * 4      # 14, precedance( * > + )
result = (2 + 3) * 4    # 20, Parentheses has greeater precedance

result = 5 + 2 * 3 ** 2 - 4 / 2

Step	Solve	                  Result
1       3 ** 2 = 9                5 + 2 * 9 - 4 / 2
2       2 * 9 = 18, 4 / 2 = 2     5 + 18 - 2
3       5 + 18 = 23, 23 - 2 = 21  21
print(result)    # 21.0

print(not 2 != 3 and True or False and True)

Step	Expression	    Explanation	         Result
1	    2 != 3	        2 is not equal to 3	 True
2	    not True	    Flip the value	     False
3	    False and True	and evaluates first	 False
4	    False and True	Second and	         False
5	    False or False	Final or	         False

✅ Answer: False 
```

> 💡 **Best Practice**: Always use parentheses to make your intent clear.

---

## 🔄 Type Upcasting (Mixed Types)

### Rule: When mixing `int` and `float`, the result is always `float`.

```python
a = 5            # int
d = 2.5          # float
result = a + d   # 7.5 (float)
```

### Why?
- **Float is a superset of integer**.
- Every integer can be represented as a float (e.g., `5` → `5.0`).
- So Python **upcasts** the integer to float for the operation.

### Type Hierarchy
```
int  →  float  →  complex
(Lower)            (Higher)
```
> Operations between different types promote to the **higher type**.

---


## 🔢 The Underscore (`_`) Variable

### What is `_`?
- In Jupyter/IPython, `_` stores the **last computed result** that wasn't explicitly assigned.

### Example
```python
10 / 3        # Output: 3.3333333333333335
_             # Output: 3.3333333333333335 (same as above)
```

### ⚠️ Warning
- **Do NOT assign** to `_` – it will lose its special property.
- Just **read** it, don't write to it.

---

## 🖥️ Jupyter Notebook Demonstration

### Step-by-Step

#### 1. Create Markdown Heading
- Press `Esc` → `M` → Type `# Operators` → `Shift + Enter`

#### 2. Define Variables
```python
a = 3
b = 5
c = 6.0
d = 7.2
```

#### 3. Addition (int + int = int)
```python
sum_of_a_and_b = a + b
print(sum_of_a_and_b)    # 8
print(type(sum_of_a_and_b))    # <class 'int'>
```

#### 4. Addition (int + float = float)
```python
result = a + d
print(result)    # 10.2
print(type(result))    # <class 'float'>
```

#### 5. Chained Operations
```python
V = (a + d) ** 3 / 4
print(V)
```

#### 6. String Concatenation
```python
S1 = "Hello"
S2 = "World"
S = S1 + S2
print(S)    # HelloWorld
```

#### 7. Floor Division vs. Regular Division
```python
10 // 3    # 3 (floor division)
10 / 3     # 3.333... (regular division)
```

#### 8. Using the Underscore Variable
```python
10 / 3     # 3.333...
_          # 3.333... (last result)
```

---

## 🔑 Key Takeaways

1. **Operators** are powerful tools for computation and logic.
2. **Arithmetic operators**: `+`, `-`, `*`, `/`, `%`, `//`, `**`.
3. **Modulus (`%`)** gives the remainder; **floor division (`//`)** gives the quotient.
4. **Comparison operators** always return a Boolean.
5. == compares values, not types (3 == 3.0 → True).
6. Use parentheses to make your intent clear.
7. **Type upcasting**: int + float → float.
8. **Operators are overloaded** – `+` works on strings too.
9. **Underscore (`_`)** in Jupyter stores the last unassigned result.

## 🔮 What's Next

### Upcoming Topics
- **Useful Python functions** – a few essential built-in functions.
- **Control flow** – `if` conditions and decision making.

- **More data types** – boolean, strings, lists, tuples, dictionaries.









