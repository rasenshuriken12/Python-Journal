# While Loops in Python

## 📌 Overview
This set of videos covers:
1. **What is a loop?** – Repeating a block of code.
2. **`while` loop** – Repeats as long as a condition is `True`.
3. **`if` inside a loop** – Making decisions during each iteration.
4. **`break`** – Exits the loop immediately.
5. **`continue`** – Skips the rest of the loop body and starts the next iteration.
6. **`pass`** – Does nothing (placeholder).
7. **`while True`** – Infinite loop (combined with `break`).

---

## 🔄 What is a Loop?

> **Loop** = A structure that repeats a block of code **multiple times**.

### Why Loops?
Without loops, printing numbers 1 to 1000 would require 1000 lines of code. Loops solve this elegantly.

### Example Problem
> User enters a number `n`. Print all numbers from `1` to `n`.

**Without a loop:**
```python
print(1)
print(2)
print(3)
# ... hundreds of lines
```

**With a loop:**
```python
i = 1
while i <= n:
    print(i)
    i += 1
```

---

## 1️⃣ The `while` Loop

> Repeats a block of code **as long as** the condition is `True`.

### Syntax
```python
while condition:
    # body of loop (indented)
```

### How It Works
1. Check the condition.
2. If `True`, execute the body.
3. Go back to step 1.
4. If `False`, exit the loop.

### Example: Print Numbers 1 to n
```python
n = int(input("Enter a number: "))
i = 1

while i < n:
    print("Square of", i, "is", i ** 2)
    print("Iteration number:", i)
    i += 1    # same as i = i + 1

print("Loop done")
```

**Output (n = 5):**
```
Square of 1 is 1
Iteration number: 1
Square of 2 is 4
Iteration number: 2
Square of 3 is 9
Iteration number: 3
Square of 4 is 16
Iteration number: 4
Loop done
```

### Flow Visualization
```
i = 1
   ↓
┌─→ Check: i < n? → False → Exit loop → print("Loop done")
│      ↓ True
│   Execute body
│      ↓
│   i += 1
│      ↓
└──────┘
```

---

## 2️⃣ `if` Inside a Loop

> You can make decisions **during each iteration**.

### Example: Print Only Even Numbers
```python
n = 5
i = 1

while i < n:
    if i % 2 == 0:
        print(i)
    else:
        pass    # do nothing
    i += 1

print("Done")
```

**Output:**
```
2
4
Done
```

### How It Works
| Iteration | `i` | `i % 2 == 0`? | Action |
|-----------|-----|---------------|--------|
| 1 | 1 | False | `pass` |
| 2 | 2 | True | Print `2` |
| 3 | 3 | False | `pass` |
| 4 | 4 | True | Print `4` |
| 5 | 5 | Loop exits | — |

> 💡 **Note**: `pass` means "do nothing." Omitting the `else` block would give the same result.

---

## 3️⃣ The `break` Statement

> **Exits the loop immediately** when encountered.

### Syntax
```python
while condition:
    # some code
    if some_condition:
        break    # exit the loop now
    # more code (skipped if break runs)
```

### Example
```python
i = 1
while True:
    if i % 9 == 0:
        break
    else:
        print("Inside else")
        i += 1

print("Loop done")
```

**Output:**
```
Inside else
Inside else
Inside else
Inside else
Inside else
Inside else
Inside else
Inside else
Loop done
```

### How It Works
| Iteration | `i` | `i % 9 == 0`? | Action |
|-----------|-----|---------------|--------|
| 1 | 1 | False | Print `Inside else`, `i=2` |
| 2 | 2 | False | Print `Inside else`, `i=3` |
| ... | ... | ... | ... |
| 8 | 8 | False | Print `Inside else`, `i=9` |
| 9 | 9 | **True** | **`break`** — exit loop |

> 💡 **Key Insight**: `break` **immediately** stops the loop, regardless of the condition.

---

## 4️⃣ The `continue` Statement

> **Skips the rest of the loop body** and starts the next iteration immediately.

### Syntax
```python
while condition:
    # some code
    if some_condition:
        continue    # skip to next iteration
    # more code (skipped if continue runs)
```

### Example
```python
i = 1
while True:
    if i % 9 != 0:
        i += 1
        print("Inside if")
        continue
    print("This prints only when i is divisible by 9")
    break

print("Done")
```

**Output:**
```
Inside if
Inside if
Inside if
Inside if
Inside if
Inside if
Inside if
Inside if
This prints only when i is divisible by 9
Done
```

### How It Works
| Iteration | `i` | `i % 9 != 0`? | Action |
|-----------|-----|---------------|--------|
| 1 | 1 | True | Print `Inside if`, `i=2`, **`continue`** |
| 2 | 2 | True | Print `Inside if`, `i=3`, **`continue`** |
| ... | ... | ... | ... |
| 8 | 8 | True | Print `Inside if`, `i=9`, **`continue`** |
| 9 | 9 | **False** | Skip `if`, print final message, `break` |

> 💡 **Key Insight**: `continue` **skips** the remaining body and starts the next iteration.

---

## 5️⃣ `break` vs `continue`

| Feature | `break` | `continue` |
|---------|---------|------------|
| **Effect** | Exits the loop **immediately** | Skips remaining body, **next iteration** |
| **Loop continues?** | ❌ No | ✅ Yes |
| **Use case** | Stop when condition met | Skip certain iterations |

### Visual Comparison
```
break:                          continue:
┌─→ Check condition              ┌─→ Check condition
│      ↓ True                    │      ↓ True
│   Execute body                 │   Execute body (partial)
│      ↓                         │      ↓
│   break → EXIT LOOP            │   continue → Back to check
│                                │
└──────┘                         └──────┘
```

---

## 6️⃣ `while True` — Infinite Loop

> Loops **forever** until a `break` is encountered.

```python
i = 1
while True:
    if i % 9 == 0:
        break
    i += 1

print("Loop done")
```

> ⚠️ **Warning**: Without `break`, `while True` creates an **infinite loop** that never ends.

---

## 7️⃣ `pass` Statement

> Does **nothing** — a placeholder.

```python
if condition:
    pass    # do nothing
else:
    print("Something")
```

> 💡 **Note**: Omitting the `else` block would give the same result.

---

## 🧪 Complete Practice Examples

### Example 1: Print Numbers 1 to n
```python
n = int(input("Enter n: "))
i = 1
while i <= n:
    print(i)
    i += 1
```

### Example 2: Print Only Even Numbers
```python
n = 10
i = 1
while i <= n:
    if i % 2 == 0:
        print(i)
    i += 1
```

### Example 3: Break When Divisible by 9
```python
i = 1
while True:
    if i % 9 == 0:
        break
    i += 1
print("First multiple of 9:", i)
```

### Example 4: Continue to Skip Multiples of 3
```python
i = 1
while i <= 10:
    if i % 3 == 0:
        i += 1
        continue
    print(i)
    i += 1
```
**Output:**
```
1
2
4
5
7
8
10
```

---

## 📊 Summary Table

| Statement | Purpose | Loop Continues? |
|-----------|---------|-----------------|
| `while condition:` | Repeat while True | ✅ Yes |
| `break` | Exit loop immediately | ❌ No |
| `continue` | Skip to next iteration | ✅ Yes |
| `pass` | Do nothing | ✅ Yes |
| `while True:` | Infinite loop (needs break) | ✅ Yes |

---

## 🔑 Key Takeaways

1. **`while` loop** repeats code as long as the condition is `True`.
2. **`if` inside a loop** allows decision making per iteration.
3. **`break`** exits the loop immediately.
4. **`continue`** skips the rest of the body and starts next iteration.
5. **`pass`** does nothing (placeholder).
6. **`while True`** creates an infinite loop — use with `break`.
7. **Indentation** defines the loop body.
8. **`i += 1`** is shorthand for `i = i + 1`.
9. **Nested loops** (loop inside loop) are allowed.
10. **Loops + `if`** = Powerful problem-solving.

---

## 🔮 What's Next

### Upcoming Topics
- **`for` loop** – Iterating over sequences.
- **`range()`** – Generating sequences of numbers.
- **Nested loops** – Loop inside a loop.
- **`for` vs `while`** – When to use which.

---

## 💡 Pro Tip: When to Use `while`

Use `while` when:
- You **don't know** how many iterations you need.
- You're waiting for a condition to become `False`.
- You're reading input until a specific value.

Use `for` when:
- You know the **exact number** of iterations.
- You're iterating over a sequence (list, string, etc.).

---

*"Loops are the heartbeat of programming. They turn repetition into elegance."* 🚀
