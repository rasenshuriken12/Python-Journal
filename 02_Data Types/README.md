# Data Types in Python

## 📌 Overview

This covers all Python data types:
1. **Numeric** – Integer, Float, Complex.
2. **Boolean** – True/False.
3. **Sequence** – String, List, Tuple.
4. **Dictionary** – Key-value pairs.
5. **Set & Frozenset** – Unordered unique elements.

---

## 🧠 What is a Data Type?

> **Data Type** = The classification of data that tells Python:
> - What kind of value is stored.
> - What operations can be performed on it.
> - How much memory it occupies.

### Python is Dynamically Typed

- You **don't** need to declare the type.
- The **value** determines the type automatically.

```python
x = 10          # int
x = 3.14        # float (type changed automatically)
x = "Hello"     # str (type changed again)
```

---

## 📊 Quick Reference: All Data Types

| Category | Type | Mutable? | Ordered? | Duplicates? | Syntax |
|----------|------|----------|----------|-------------|--------|
| **Numeric** | `int` | ❌ | N/A | N/A | `10` |
| **Numeric** | `float` | ❌ | N/A | N/A | `3.14` |
| **Numeric** | `complex` | ❌ | N/A | N/A | `2+4j` |
| **Boolean** | `bool` | ❌ | N/A | N/A | `True` / `False` |
| **Sequence** | `str` | ❌ | ✅ | ✅ | `"Hello"` |
| **Sequence** | `list` | ✅ | ✅ | ✅ | `[1, 2, 3]` |
| **Sequence** | `tuple` | ❌ | ✅ | ✅ | `(1, 2, 3)` |
| **Mapping** | `dict` | ✅ | ✅ | ❌ (keys) | `{"a": 1}` |
| **Set** | `set` | ✅ | ❌ | ❌ | `{1, 2, 3}` |
| **Set** | `frozenset` | ❌ | ❌ | ❌ | `frozenset({1, 2})` |

---

## 1️⃣ Numeric Types

### ❇️ 1.1 Integer (`int`)
- Whole numbers without a decimal point.

```python
x = int(1)
print(x)          # 1
print(type(x))    # <class 'int'>
```

**Examples:**
```python
a = -5
b = 0
c = 10
```

---

### ❇️ 1.2 Float (`float`)
- Numbers with a decimal point.

```python
y = float(2)
print(y)          # 2.0
print(type(y))    # <class 'float'>
```

**Examples:**
```python
a = 3.14
b = -0.5
c = 1.5e3    # Scientific notation = 1500.0
```

---

### ❇️ 1.3 Complex (`complex`)
- Numbers with a real and imaginary part (using `j`).

```python
z = complex(1, 2)
print(z)          # (1+2j)
print(type(z))    # <class 'complex'>
```

**Examples:**
```python
a = 2 + 4j
b = 3 - 1j
c = complex(5, 7)    # (5+7j)
```

**Accessing Parts:**
```python
z = 2 + 4j
print(z.real)    # 2.0
print(z.imag)    # 4.0
```

---

## 2️⃣ Boolean (`bool`)

- Represents **True** or **False**.

### Boolean Values
```python
x = True
y = False
print(type(x))    # <class 'bool'>
```

### Truthy & Falsy Values

| Falsy (False) | Truthy (True) |
|---------------|---------------|
| `False` | `True` |
| `0` | Any non-zero number |
| `0.0` | Any non-zero float |
| `""` (empty string) | Any non-empty string |
| `[]` (empty list) | Any non-empty list |
| `()` (empty tuple) | Any non-empty tuple |
| `{}` (empty dict) | Any non-empty dict |
| `set()` (empty set) | Any non-empty set |
| `None` | — |

### Examples
```python
print(bool({}))       # False (empty mapping)
print(bool(()))       # False (empty sequence)
print(bool(None))     # False
print(bool(0.0))      # False
print(bool(1))        # True
print(bool(-1.5))     # True
print(bool("Hello"))  # True
```

### ❇️ Boolean Operators

| A | B | A or B | A and B | not A |
|---|---|--------|---------|-------|
| True | True | True | True | False |
| True | False | True | False | False |
| False | True | True | False | True |
| False | False | False | False | True |

```python
A, B = True, False
print(A or B)     # True
print(A and B)    # False
print(not A)      # False
print(not B)      # True
```

### ❇️ Boolean with Other Operators

🔸 Equivalent & Not equivalent Operator

```python
A, B = True, False
print(A == B)     # False (equality)
print(A != B)     # True (not equal)
```

🔸 is Operator

```python
a, b = 5, 5
print(a is b)     # True (same memory location)
```

> `==` operator focuses on same values while `is` operator focuses on values at same Memory location.

🔸 in Operator

```python
fruits = ["apple", "banana", "mango"]
print("banana" in fruits)    # True
```

> It checks if a value exists within a sequence (like a list, tuple, string, or range).

---

## 3️⃣ Sequence Types

### 3.1 String (`str`)

- A **sequence of characters** enclosed in quotes.

### ❇️ Creating Strings
```python
string1 = "Hello Good Morning"
print(string1)           # Hello Good Morning
print(type(string1))     # <class 'str'>

string2 = 'How are you?'
print(string2)           # How are you?
```

### ❇️ Multi-line Strings
```python
s1 = """Hi guys,
I am learning Python String."""
print(s1)
```
**Output:**
```
Hi guys,
I am learning Python String.
```

```python
s2 = '''Hello Good Morning,
I live in Mumbai, India.'''
print(s2)
```
**Output:**
```
Hello Good Morning,
I live in Mumbai, India.
```

### ❇️ String Operations
```python
s1 = "Hello"
s2 = "World"
```
🔸 1. Concatenation
```python
print(s1 + " " + s2)    # Hello World
```

🔸 2. Repetition
```python
print(s1 * 3)           # HelloHelloHello
```

🔸 3. Indexing
```python
print(s1[0])            # H
print(s1[-1])           # o
```

🔸 4. Slicing
```python
print(s1[1:4])          # ell
```

> 💡 **Note**: Strings are **immutable** – you cannot change a character in place.

---

### 3.2 List

- An **ordered, mutable** collection of items.

### ❇️ Creating Lists
```python
list1 = [1, 2, 3, 4, 5]
list2 = ["apple", "banana", "cherry"]
list3 = [1, "Hello", 3.14, True]    # Mixed types
list4 = []                          # Empty list
```

### ❇️ Accessing Items
```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0])       # apple
print(fruits[-1])      # cherry
print(fruits[1:3])     # ['banana', 'cherry']
```

### ❇️ Modifying Lists
```python
fruits = ["apple", "banana", "cherry"]
fruits[1] = "orange"
print(fruits)          # ['apple', 'orange', 'cherry']
```

### ❇️ Adding Elements

1. `append(x)`

- Adds **one item** to the **end** of the list.

```python
fruits = ["apple", "banana"]
fruits.append("cherry")
print(fruits)    # ['apple', 'banana', 'cherry']

# Append different types
fruits.append(100)
fruits.append(True)
print(fruits)    # ['apple', 'banana', 'cherry', 100, True]

# Append a list (creates nested list)
fruits.append([1, 2])
print(fruits)    # ['apple', 'banana', 'cherry', 100, True, [1, 2]]
```

> ⚠️ **Note**: `append()` adds the **entire object** as a single element.

---

2. `insert(i, x)`

- Inserts an item at a **specific position**.

```python
fruits = ["apple", "cherry"]
fruits.insert(1, "banana")
print(fruits)    # ['apple', 'banana', 'cherry']

# Insert at beginning
fruits.insert(0, "mango")
print(fruits)    # ['mango', 'apple', 'banana', 'cherry']

# Insert at end (same as append)
fruits.insert(len(fruits), "grape")
print(fruits)    # ['mango', 'apple', 'banana', 'cherry', 'grape']
```

---

3. `extend(iterable)` 

- Adds **all items** from an iterable to the end.

```python
L1 = [1, 2, 3]
L1.extend([4, 5, 6])
print(L1)    # [1, 2, 3, 4, 5, 6]

# Extend with a string (adds each character)
L2 = ["a"]
L2.extend("hello")
print(L2)    # ['a', 'h', 'e', 'l', 'l', 'o']

# Extend with a tuple
L3 = [1]
L3.extend((2, 3))
print(L3)    # [1, 2, 3]
```

🔸 `append()` vs `extend()`

| `append([4, 5])` | `extend([4, 5])` |
|------------------|------------------|
| Adds the **list as one item** | Adds **each item separately** |
| `[1, 2, 3, [4, 5]]` | `[1, 2, 3, 4, 5]` |

---

### ❇️ Removing Elements

1. `remove(x)` 

- Removes the **first occurrence** of a value.

```python
fruits = ["apple", "banana", "cherry", "banana"]
fruits.remove("banana")
print(fruits)    # ['apple', 'cherry', 'banana']
```

⚠️ Error If Not Found
```python
fruits.remove("orange")    # ❌ ValueError: list.remove(x): x not in list
```

---

2. `pop(i)` 

- Removes and returns the item at index `i`. Default is the **last item**.

```python
fruits = ["apple", "banana", "cherry"]

# Pop last item
last = fruits.pop()
print(last)      # cherry
print(fruits)    # ['apple', 'banana']

# Pop by index
first = fruits.pop(0)
print(first)     # apple
print(fruits)    # ['banana']

# Pop from empty list
empty = []
empty.pop()      # ❌ IndexError: pop from empty list
```

---

3. `clear()` 

- Removes **all items** from the list.

```python
fruits = ["apple", "banana", "cherry"]
fruits.clear()
print(fruits)    # []
```

---

### ❇️ `index(x)`

- Returns the **index** of the first occurrence.

```python
fruits = ["apple", "banana", "cherry", "banana"]
print(fruits.index("banana"))    # 1

# With start and end
print(fruits.index("banana", 2))    # 3
```

⚠️ Error If Not Found
```python
fruits.index("orange")    # ❌ ValueError: 'orange' is not in list
```

---

### ❇️ Count Occurrences

`count(x)` 

- Counts how many times a value appears.

```python
nums = [1, 2, 2, 3, 3, 3, 4]
print(nums.count(2))    # 2
print(nums.count(3))    # 3
print(nums.count(5))    # 0
```

---

### ❇️ `sort()`

- Sorts the list **in place** (ascending by default).

```python
nums = [3, 1, 4, 1, 5, 9, 2]
nums.sort()
print(nums)    # [1, 1, 2, 3, 4, 5, 9]

# Descending
nums.sort(reverse=True)
print(nums)    # [9, 5, 4, 3, 2, 1, 1]

# Sort strings
fruits = ["banana", "apple", "cherry"]
fruits.sort()
print(fruits)    # ['apple', 'banana', 'cherry']
```

> ⚠️ **Note**: `sort()` modifies the original list and returns `None`.

🔸 Sorting with `key`
```python
words = ["banana", "apple", "kiwi"]
words.sort(key=len)
print(words)    # ['kiwi', 'apple', 'banana']
```

---

### ❇️ `reverse()` 

- Reverses the list **in place**.

```python
nums = [1, 2, 3, 4, 5]
nums.reverse()
print(nums)    # [5, 4, 3, 2, 1]
```

🔸 `reverse()` vs Slicing
```python
nums = [1, 2, 3]
print(nums[::-1])    # [3, 2, 1] (returns new list)
nums.reverse()       # modifies in place
```

---

### ❇️ `copy()` — Shallow Copy

- Creates a **shallow copy** of the list.

```python
L1 = [1, 2, 3]
L2 = L1.copy()
L2.append(4)

print(L1)    # [1, 2, 3]
print(L2)    # [1, 2, 3, 4]
```

🔸 `=` vs `copy()`

| `L2 = L1` | `L2 = L1.copy()` |
|-----------|------------------|
| Both refer to **same list** | Two **separate lists** |
| Changes affect both | Changes affect only one |

```python
# Assignment (same object)
L1 = [1, 2, 3]
L2 = L1
L2.append(4)
print(L1)    # [1, 2, 3, 4] ❌ Changed!

# Copy (separate object)
L1 = [1, 2, 3]
L2 = L1.copy()
L2.append(4)
print(L1)    # [1, 2, 3] ✅ Unchanged!
```

---

## 🧪 Complete Practice Example

```python
# Create a list
fruits = ["banana", "apple", "cherry"]

# Add items
fruits.append("mango")
fruits.insert(1, "kiwi")
print(fruits)      # ['banana', 'kiwi', 'apple', 'cherry', 'mango']

# Remove items
fruits.remove("apple")
popped = fruits.pop()
print(popped)      # mango
print(fruits)      # ['banana', 'kiwi', 'cherry']

# Find and count
print(fruits.index("kiwi"))    # 1
print(fruits.count("banana"))  # 1

# Sort and reverse
fruits.sort()
print(fruits)      # ['banana', 'cherry', 'kiwi']
fruits.reverse()
print(fruits)      # ['kiwi', 'cherry', 'banana']

# Copy
new_fruits = fruits.copy()
new_fruits.append("grape")
print(fruits)      # ['kiwi', 'cherry', 'banana']
print(new_fruits)  # ['kiwi', 'cherry', 'banana', 'grape']
```

---

### 3.3 Tuple

- An **ordered, immutable** collection of items.

### ❇️ Creating Tuples
```python
tuple1 = (1, 2, 3, 4, 5)
tuple2 = ("apple", "banana", "cherry")
tuple3 = (1, "Hello", 3.14)    # Mixed types
tuple4 = ()                    # Empty tuple
tuple5 = (5,)                  # Single-element tuple (comma required!)
```

### ❇️ Accessing Items
```python
t = (1, 2, 3, 4, 5)
print(t[0])       # 1
print(t[-1])      # 5
print(t[1:3])     # (2, 3)
```

### ❇️ Why Use Tuples?
| Reason | Explanation |
|--------|-------------|
| **Immutable** | Cannot be changed (safer) |
| **Faster** | Slightly faster than lists |
| **Hashable** | Can be used as dictionary keys |
| **Intent** | Signals "this data should not change" |

### ❇️ Tuple Unpacking
```python
a, b, c = (1, 2, 3)
print(a, b, c)    # 1 2 3

# Swap variables
x, y = 10, 20
x, y = y, x
print(x, y)       # 20 10
```

---

## 4️⃣ Dictionary (`dict`)

- Stores **key-value pairs**.

### Key Characteristics
| Feature | Description |
|---------|-------------|
| **Mutable** | Can be changed |
| **No duplicate keys** | Keys must be unique, Duplicate values are allowed  |
| **Insertion order** | Maintained (Python 3.7+) |
| **No indexing** | Access via keys, not positions |
| **Syntax** | `{ "key" : "value" }` |

### ❇️ Creating Dictionaries

🔸 1. Direct Creation
```python
d1 = {1: 'Hello', 2: 'Good', 3: 'Morning'}
print(d1)
```

**Output:**
```
{1: 'Hello', 2: 'Good', 3: 'Morning'}
```

🔸 2. Using `dict()`
```python
d2 = dict(a="Hello", b="Good", c="Morning")
print(d2)
```

**Output:**
```
{'a': 'Hello', 'b': 'Good', 'c': 'Morning'}
```
> ⚠️ **Note**: `dict()` with keyword arguments only allows **string keys**.

🔸 3. Using `dict()` & `zip()`
```python
keys = [1, 2, 3]
values = ['Geeks', 'For', 'Geeks']
d3 = dict(zip(keys, values))
print(d3)
```

**Output:**
```
{1: 'Geeks', 2: 'For', 3: 'Geeks'}
```
> 💡 **Note**: Duplicate keys are overwritten:

```python
d3 = dict(zip(['Geeks', 'For', 'Geeks'], [1, 2, 3]))
print(d3)    # {'Geeks': 3, 'For': 2}
```

🔸 4. Case Sensitivity
```python
d4 = {'GEEKS': 1, 'For': 2, 'Geeks': 3}
print(d4)
```

**Output:**
```
{'GEEKS': 1, 'For': 2, 'Geeks': 3}
```
> Keys are **case-sensitive**.

🔸 5. Different Types of Values
```python
d5 = {'name': 'Tanmay', 'age': 18}
print(d5)
```

🔸 6. Different Types of Keys
```python
d6 = {"name": 'Dhanesh', 2025: "year"}
print(d6)
```

---

### ❇️ Accessing Dictionary Items

🔸 1. Using `[]` (Direct Access)
```python
d = {'name': 'Deva', 1: 'Python', (1,2): [1,2,4]}
print(d['name'])      # Deva
print(d[1])           # Python
print(d[(1,2)])       # [1, 2, 4]
```
> ⚠️ **Warning**: Raises `KeyError` if key doesn't exist.

🔸 2. Using `.get()` (Safe Access)
```python
d = {'name': 'Deva', 1: 'Python', (1,2): [1,2,4]}
print(d.get("name"))    # Deva
print(d.get(1))         # Python
print(d.get((1,2)))     # [1, 2, 4]
print(d.get("age"))     # None (no error!)
print(d.get("age", 0))  # 0 (default value)
```

---

### ❇️ Adding & Updating Items

🔸 Adding a New Key-Value
```python
d = {1: 'Hello', '2': 'Good', 3: 'Morning'}
d[4] = "Sampada"
print(d)
```
**Output:**
```
{1: 'Hello', '2': 'Good', 3: 'Morning', 4: 'Sampada'}
```

🔸 Updating an Existing Key
```python
d = {1: 'Hello', '2': 'Good', 3: 'Morning', 4: 'Astha'}
d[3] = "Evening"
print(d)
```
**Output:**
```
{1: 'Hello', '2': 'Good', 3: 'Evening', 4: 'Astha'}
```

---

### ❇️ Deleting Dictionary Items

🔸 1. Using `del`
```python
d = {1: 'Hello', '2': 'Good', 3: 'Morning', 4: 'Shrutika'}
del d[3]
print(d)
```
**Output:**
```
{1: 'Hello', '2': 'Good', 4: 'Shrutika'}
```

🔸 2. Using `.pop()`
```python
d = {1: 'Hello', '2': 'Good', 4: 'Shrutika'}
print(d.pop('2'))    # Good (returns value)
print(d)
```
**Output:**
```
Good
{1: 'Hello', 4: 'Shrutika'}
```

🔸 3. Using `.popitem()`
```python
d = {1: 'Hello', 4: 'Shrutika'}
K, V = d.popitem()
print(f"Key: {K}, Value: {V}")
print(d)
```
**Output:**
```
Key: 4, Value: Shrutika
{1: 'Hello'}
```
> Removes and returns the **last** key-value pair.

🔸 4. Using `.clear()`
```python
d = {1: 'Hello', 2: 'Good'}
d.clear()
print(d)    # {}
```

---

### ❇️ Iterating Through Dictionary

🔸 1. Iterating Keys
```python
d = {1: 'Hello', '2': 'Good', 'Morning': 3}
for K in d.keys():
    print(f"Key: {K}")
```
**Output:**
```
Key: 1
Key: 2
Key: Morning
```

🔸 2. Iterating Values
```python
for V in d.values():
    print(f"Value: {V}")
```
**Output:**
```
Value: Hello
Value: Good
Value: 3
```

🔸 3. Iterating Key-Value Pairs
```python
for K, V in d.items():
    print(f"Key, Value: {K}, {V}")
```
**Output:**
```
Key, Value: 1, Hello
Key, Value: 2, Good
Key, Value: Morning, 3
```

---

### ❇️ Nested Dictionaries
```python
d = {
    1: 'Welcome',
    2: 'To',
    3: {
        'A': 'Harry',
        'B': 'Potter',
        'C': 'And The',
        'D': "Philosopher's",
        'E': 'Stone'
    }
}
print(d)
```

---

## 5️⃣ Set & Frozenset

### 5.1 Set

- Stores **unordered unique elements**.

### Key Characteristics
| Feature | Description |
|---------|-------------|
| **Unordered** | No indexing |
| **Mutable** | Can add/remove items |
| **No duplicates** | Each element is unique |
| **Syntax** | `{ item1, item2, item3 }` |

### ❇️ Creating Sets

🔸 1. Using `set()`
```python
set1 = set("Hello Good Morning")
print(set1)
print(type(set1))
```
**Output:**
```
{'n', 'r', ' ', 'o', 'g', 'i', 'l', 'd', 'G', 'M', 'H', 'e'}
<class 'set'>
```
> Duplicates removed, order random.

🔸 2. Heterogeneous Elements
```python
set2 = {"Hello", 10, 52.7, True}
print(set2)
```
**Output:**
```
{'Hello', True, 10, 52.7}
```
> Output order varies.

### ❇️ Accessing Set Items
```python
set1 = set(["Hello", "Good", "Morning"])
for i in set1:
    print(i, end=" ")
```
**Output:**
```
Morning Hello Good
```
> Order varies.

### ❇️ Adding Items

🔸 1. Using `.add()` (Single Item)
```python
set1 = {1, 2, 3, 4}
set1.add(5)
print(set1)    # {1, 2, 3, 4, 5}
```

🔸 2. Using `.update()` (Multiple Items)
```python
set2 = {1, 2, 3, 4}
set2.update([5, 6])
print(set2)    # {1, 2, 3, 4, 5, 6}
```
> Duplicates ignored.

### ❇️ Removing Items

🔸 1. Using `.remove()`
```python
set1 = {1, 2, 3, 4, 5}
set1.remove(3)
print(set1)    # {1, 2, 4, 5}

set1.remove(7)  # ❌ KeyError!
```
> Raises error if element doesn't exist.

🔸 2. Using `.discard()`
```python
set1 = {1, 2, 3, 4, 5}
set1.discard(3)
print(set1)    # {1, 2, 4, 5}

set1.discard(7)  # ✅ No error
print(set1)      # {1, 2, 4, 5}
```
> No error if element doesn't exist.

🔸 3. Using `.pop()`
```python
set1 = {1, 2, 3, 4, 5}
val = set1.pop()
print(val)     # Random element
print(set1)    # Remaining set
```

🔸 4. Using `.clear()`
```python
set1 = {1, 2, 3, 4, 5}
set1.clear()
print(set1)    # set()
```

### ❇️ Set Operations

| Operation | Operator | Method |
|-----------|----------|--------|
| Union | `\|` | `.union()` |
| Intersection | `&` | `.intersection()` |
| Difference | `-` | `.difference()` |
| Symmetric Difference | `^` | `.symmetric_difference()` |

```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}

print(a | b)    # {1, 2, 3, 4, 5, 6}
print(a & b)    # {3, 4}
print(a - b)    # {1, 2}
print(a ^ b)    # {1, 2, 5, 6}
```

---

### 5.2 Frozenset

- Same as `set()`, but **immutable**.

### Key Characteristics
| Feature | Description |
|---------|-------------|
| **Immutable** | Cannot be modified after creation |
| **Hashable** | Can be used as dictionary keys |
| **Syntax** | `frozenset(iterable)` |

### ❇️ Creating Frozensets

🔸 1. From Dictionary
```python
d = {"name": "Devaratha", "age": 19}
print(frozenset(d))
```
**Output:**
```
frozenset({'age', 'name'})
```

🔸 2. From List
```python
l = ["Hello", "Good", "Morning"]
print(frozenset(l))
```
**Output:**
```
frozenset({'Good', 'Hello', 'Morning'})
```

🔸 3. From Tuple
```python
t = ()    # Empty tuple
print(frozenset(t))
```
**Output:**
```
frozenset()
```

### ❇️ Frozenset Operations

🔸 1. Copy
```python
a = frozenset([1, 2, 3, 4])
c = a.copy()
print(c)    # frozenset({1, 2, 3, 4})
```

🔸 2. Union
```python
a = frozenset([1, 2, 3, 4])
b = frozenset([3, 4, 5, 6])
print(a.union(b))    # frozenset({1, 2, 3, 4, 5, 6})
```

🔸 3. Intersection
```python
print(a.intersection(b))    # frozenset({3, 4})
```

🔸 4. Difference
```python
print(a.difference(b))      # frozenset({1, 2})
```

🔸 5. Symmetric Difference
```python
print(a.symmetric_difference(b))    # frozenset({1, 2, 5, 6})
```

---

## 📋 Summary Table: All Data Types

| Type | Example | Mutable? | Ordered? | Duplicates? | Use Case |
|------|---------|----------|----------|-------------|----------|
| `int` | `10` | ❌ | N/A | N/A | Counting |
| `float` | `3.14` | ❌ | N/A | N/A | Measurements |
| `complex` | `2+4j` | ❌ | N/A | N/A | Scientific computing |
| `bool` | `True` | ❌ | N/A | N/A | Conditions |
| `str` | `"Hello"` | ❌ | ✅ | ✅ | Text |
| `list` | `[1, 2, 3]` | ✅ | ✅ | ✅ | Ordered collection |
| `tuple` | `(1, 2, 3)` | ❌ | ✅ | ✅ | Fixed collection |
| `dict` | `{"a": 1}` | ✅ | ✅ | ❌ (keys) | Key-value mapping |
| `set` | `{1, 2, 3}` | ✅ | ❌ | ❌ | Unique collection |
| `frozenset` | `frozenset({1, 2})` | ❌ | ❌ | ❌ | Immutable set |

---

## 🔑 Key Takeaways

1. **Numeric types** – `int`, `float`, `complex` for numbers.
2. **Boolean** – `True`/`False`; many values are "truthy" or "falsy".
3. **String** – Immutable sequence of characters.
4. **List** – Mutable, ordered collection.
5. **Tuple** – Immutable, ordered collection.
6. **Dictionary** – Key-value pairs; mutable, ordered (Python 3.7+).
7. **Set** – Unordered, unique, mutable.
8. **Frozenset** – Unordered, unique, immutable.
9. **Choose the right type** based on:
   - Do you need order? → List, Tuple, String
   - Do you need uniqueness? → Set, Frozenset
   - Do you need key-value pairs? → Dictionary
   - Do you need immutability? → Tuple, Frozenset, String

---

## 🔮 What's Next

### Upcoming Topics
- **Control Flow** – `if`, `elif`, `else`, loops.
- **Functions** – Defining and using functions.
- **File Handling** – Reading and writing files.
- **Modules & Packages** – Organizing code.

---

*"Data types are the foundation of Python. Choose wisely, and your code will be clean, efficient, and bug-free."* 🚀
