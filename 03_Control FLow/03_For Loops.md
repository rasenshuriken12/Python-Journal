# For Loops in Python

## 📌 Overview
This set of videos covers:
1. **`for` loop** – Iterating over sequences.
2. **`range()` function** – Generating number sequences.
3. **Iterating over lists, sets, dictionaries**.
4. **`else` clause with `for` loop** (Python-specific).
5. **Nested loops** – Loop inside a loop.
6. **Sorting problem** using nested loops (Selection Sort).

---

## 🔄 What is a `for` Loop?

> **`for` loop** = Repeats a block of code for **each item** in a sequence.

### Syntax
```python
for variable in sequence:
    # body of loop (indented)
```

### How It Works
1. Pick the first item from the sequence.
2. Execute the body.
3. Pick the next item.
4. Repeat until all items are processed.

---

## 1️⃣ Basic `for` Loop with `range()`

### `range()` Function
> Generates a sequence of numbers.

| Syntax | Meaning | Example |
|--------|---------|---------|
| `range(n)` | 0 to n-1 | `range(5)` → 0,1,2,3,4 |
| `range(start, end)` | start to end-1 | `range(2, 6)` → 2,3,4,5 |
| `range(start, end, step)` | start to end-1 with step | `range(0, 10, 2)` → 0,2,4,6,8 |

### Example: Print Numbers 1 to n
```python
n = 10
for i in range(n):
    print(i + 1)
```
**Output:**
```
1
2
3
...
10
```

### Example: Populate a List
```python
L = []
for i in range(10):
    L.append(i + 1)
print(L)    # [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

### Example: With Step Size
```python
for i in range(0, 10, 2):
    print(i)
```
**Output:**
```
0
2
4
6
8
```

---

## 2️⃣ Iterating Over Different Data Structures

### Over a List
```python
L = [2, 3, 4, 53]
for x in L:
    print(x)
```
**Output:**
```
2
3
4
53
```

### Over a Set
```python
S = {"apple", 4.9, "cherry"}
for x in S:
    print(x)
```
**Output (order may vary):**
```
apple
4.9
cherry
```

### Over a Dictionary
```python
D = {"A": 10, "B": -19, "C": "ABC"}
for key in D:
    print("Key:", key, "Value:", D[key])
```
**Output:**
```
Key: A Value: 10
Key: B Value: -19
Key: C Value: ABC
```

---

## 3️⃣ `else` Clause with `for` Loop

> Python allows an `else` block with `for` loops. It executes **only if the loop completes all iterations** (no `break`).

### Syntax
```python
for x in sequence:
    # body
else:
    # executes if loop completes normally
```

### Example 1: Normal Completion
```python
S = {"apple", 4.9, "cherry"}
for x in S:
    print(x)
else:
    print("Loop completed all iterations")

print("Outside the loop")
```
**Output:**
```
apple
4.9
cherry
Loop completed all iterations
Outside the loop
```

### Example 2: With `break` (else skipped)
```python
S = {"apple", 4.9, "cherry"}
i = 1
for x in S:
    print(x)
    i += 1
    if i == 3:
        break
else:
    print("Loop completed all iterations")

print("Outside the loop")
```
**Output:**
```
apple
4.9
Outside the loop
```
> 💡 **Note**: `else` didn't run because `break` interrupted the loop.

### ⚠️ Recommendation
> Avoid using `else` with `for` loops initially — it can confuse with `if-else`.

---

## 4️⃣ Nested Loops

> A loop **inside** another loop.

### Syntax
```python
for i in range(3):
    for j in range(2):
        print(i, j)
```
**Output:**
```
0 0
0 1
1 0
1 1
2 0
2 1
```

### Example: Multiplication Table
```python
for i in range(1, 4):
    for j in range(1, 4):
        print(i * j, end=" ")
    print()    # new line
```
**Output:**
```
1 2 3 
2 4 6 
3 6 9 
```

---

## 5️⃣ Finding Minimum from a List

### Example: Find Minimum Value
```python
L = [1, 24, -5, 8, 7, 9, 3, 2]

m = L[0]    # Assume first is minimum
for i in L:
    if i < m:
        m = i

print("Minimum:", m)    # -5
```

### Example: Find Minimum and Its Index
```python
L = [1, 24, -5, 8, 7, 9, 3, 2]
m = L[0]
index = 0
c = 0

for i in L:
    if i < m:
        m = i
        index = c
    c += 1

print("Minimum:", m, "at index:", index)    # -5 at index 2
```

---

## 6️⃣ Sorting a List (Selection Sort)

### Problem Statement
> Given a list, arrange it in **ascending order**.

### Logic
1. Find the minimum value.
2. Swap it with the first value.
3. Find the minimum from the remaining list.
4. Swap with the second value.
5. Repeat until sorted.

### Code
```python
L = [1, 24, -5, 8, 7, 9, 3, 2]

for j in range(len(L)):
    m = L[j]
    c = j
    
    for i in range(j, len(L)):
        if L[i] < m:
            m = L[i]
            c = i
    
    # Swap
    temp = L[j]
    L[j] = L[c]
    L[c] = temp

print(L)    # [-5, 1, 2, 3, 7, 8, 9, 24]
```

### How It Works
| Outer Loop `j` | Inner Loop finds min | After swap |
|----------------|----------------------|------------|
| 0 | -5 at index 2 | `[-5, 24, 1, 8, 7, 9, 3, 2]` |
| 1 | 1 at index 2 | `[-5, 1, 24, 8, 7, 9, 3, 2]` |
| 2 | 2 at index 7 | `[-5, 1, 2, 8, 7, 9, 3, 24]` |
| ... | ... | ... |

> 💡 **Note**: Python has built-in `L.sort()` — this is just for learning purposes.

---

## 📊 `for` vs `while`

| Feature | `for` Loop | `while` Loop |
|---------|-----------|--------------|
| **Use case** | Known number of iterations | Unknown iterations |
| **Iteration** | Over a sequence | Based on condition |
| **Syntax** | `for x in seq:` | `while cond:` |
| **Infinite loop** | `for` over infinite generator | `while True:` |
| **`else` clause** | ✅ Available | ❌ Not available |

---

## 📋 Quick Reference

| Concept | Syntax | Example |
|---------|--------|---------|
| `for` loop | `for x in seq:` | `for i in range(5):` |
| `range(n)` | 0 to n-1 | `range(5)` → 0,1,2,3,4 |
| `range(a, b)` | a to b-1 | `range(2, 6)` → 2,3,4,5 |
| `range(a, b, s)` | a to b-1, step s | `range(0, 10, 2)` → 0,2,4,6,8 |
| `else` with `for` | After loop | Runs if no `break` |
| Nested loop | Loop inside loop | `for i: for j:` |

---

## 🔑 Key Takeaways

1. **`for` loop** iterates over sequences (lists, strings, sets, dicts, ranges).
2. **`range()`** generates number sequences.
3. **`range(start, end, step)`** – start included, end excluded.
4. **`else` with `for`** executes only if the loop completes without `break`.
5. **Nested loops** – loop inside a loop.
6. **`for` is handy** for iterating over data structures.
7. **`while` is handy** for condition-based repetition.
8. **Both loops can achieve the same tasks** — choose based on readability.
9. **Selection sort** can be implemented with nested loops.
10. **Python has built-in `sort()`** — no need to write sorting manually.

---

## 🔮 What's Next

### Upcoming Topics
- **Functions** – Writing your own functions.
- **`def` keyword** – Defining functions.
- **Parameters and return values**.
- **Scope** – Local vs global variables.

---

*"For loops are the most Pythonic way to iterate. When you know what you're iterating over, use `for`."* 🚀
