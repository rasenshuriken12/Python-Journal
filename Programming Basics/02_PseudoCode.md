# Expressing Algorithms (Flowcharts & Pseudocode)

## 📌 Recap 
- **Algorithm** = A step-by-step procedure to solve a problem.
- **Problem**: Natural languages (like English) can be **ambiguous**—sentences can have multiple meanings.
- **Solution**: Need a **structured, unambiguous** way to express algorithms.

---

## 🎨 Two Main Ways to Express Algorithms

| Method | Description | Best For |
|--------|-------------|----------|
| **Flowchart** | Graphical representation using shapes and arrows. | Visual learners, simple problems. |
| **Pseudocode** | Text-based, structured, uses concise keywords. | Transitioning to actual programming code. |

---

## 📊 Flowcharts: Graphical Algorithms

### Shapes and Their Meanings
| Shape | Name | Purpose |
|-------|------|---------|
| 🟢 **Oval** | Start/End | Marks the beginning and end of the algorithm. |
| 📐 **Parallelogram** | Input/Output | Taking input or displaying output. |
| 📦 **Rectangle** | Processing | Computation or assignment (e.g., `pay = hours * rate`). |
| 💎 **Diamond** | Decision | Conditional branching (if/else). |
| ➡️ **Arrows** | Flow Direction | Show the sequence of steps. |

> 💡 **Tip**: Always use arrows to show flow, especially in complex algorithms with loops and conditions.

---

## 💼 Example: Computing Employee Pay

### Problem Statement
- A company has multiple employees.
- Each employee has:
  - **Hours worked** (different for each employee)
  - **Hourly rate** (different for each employee)
- Task: Compute the **pay** for each employee.

### The Algorithm Steps

| Step | Action | Pseudocode |
|------|--------|------------|
| 1 | Take hours worked as input | `INPUT hours` |
| 2 | Take hourly rate as input | `INPUT rate` |
| 3 | Compute pay | `pay = hours × rate` |
| 4 | Record/print/send the pay | `OUTPUT pay` |

### 📝 Variable Concept
- **Variable** = A placeholder that stores values.
- **Why called variable?** Because the value changes (varies) for different instances.
  - For Employee 1: `hours = 8`, `rate = 100`
  - For Employee 2: `hours = 7`, `rate = 200`

---

## 📝 Pseudocode: Text-Based Algorithms

### What is Pseudocode?
> A concise, structured, and unambiguous way to express an algorithm using a set of **keywords**.

### Characteristics
- **Precise**: Each statement has a unique meaning.
- **Concise**: No unnecessary words.
- **Consistent**: Same keywords for same operations.
- **Readable**: Easy for humans to understand.

### Example Keywords (Customizable)
| Operation | Possible Keywords |
|-----------|-------------------|
| Input | `INPUT`, `GET`, `READ` |
| Output | `OUTPUT`, `PRINT`, `DISPLAY` |
| Computation | `CALCULATE`, `COMPUTE`, `=` |
| Start/End | `BEGIN`, `START` / `END`, `STOP` |

> ⚠️ **Important**: Choose your keywords and **stick with them** consistently throughout the algorithm.

### Example Pseudocode (Employee Pay)

```
BEGIN
    INPUT hours
    INPUT rate
    pay = hours * rate
    OUTPUT pay
END
```

---

## 🆚 Flowcharts vs. Pseudocode

| Aspect | Flowchart | Pseudocode |
|--------|-----------|------------|
| **Format** | Visual/Graphical | Text-based |
| **Ease of drawing** | Simple for small problems | Always easy |
| **Complex problems** | Becomes messy and tedious | Remains readable |
| **Transition to code** | Requires extra step (converting shapes to code) | Direct translation to code |
| **Precision** | Clear visually | Clear textually |
| **Best use case** | Presentations, documentation, teaching beginners | Real-world algorithm design |

### Why Pseudocode is Preferred
1. **Easier to write** for complex problems.
2. **Directly translatable** to any programming language.
3. **More feasible** when the goal is to eventually write code.
4. **Easier to edit** and maintain.

> 💡 **Bottom Line**: Both are valid, but **pseudocode is more practical** for real-world development.

---

## 🧠 Core Takeaways

### 1. Ambiguity is the Enemy
- Natural language is expressive but **ambiguous**.
- Algorithms must be **unambiguous** to work correctly.

### 2. Two Ways, One Goal
- Both flowcharts and pseudocode serve the same purpose: **clearly expressing an algorithm**.
- Choose based on your audience and problem complexity.

### 3. Consistency Matters
- Use a fixed set of keywords in pseudocode.
- Use standard shapes in flowcharts.

### 4. Variables are Placeholders
- They hold data that **varies** for different instances.
- Essential for creating **general solutions**.

### 5. Sequence + Uniqueness = Algorithm
- Steps must be in the correct **sequence**.
- Each step must have a **unique, clear meaning**.

---

## 📖 Glossary

| Term | Meaning |
|------|---------|
| **Flowchart** | A diagram that represents an algorithm using shapes and arrows. |
| **Pseudocode** | A structured, text-based way of writing algorithms using keywords. |
| **Variable** | A named placeholder that stores a value which can change. |
| **Keyword** | A reserved word used in pseudocode with a specific meaning. |
| **Instance** | A specific set of input data for a problem. |

---

## 🔮 Coming Up Next
- **Making Tea** as a pseudocode example.
- More flowchart examples.
- Moving from pseudocode → actual programming code.

---

*"A solution that works for every instance is called an algorithm. How you express it—whether with shapes or words—is up to you, but clarity and unambiguity are non-negotiable."* 🚀
