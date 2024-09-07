### Stack Operations with Examples

Here are five sample examples demonstrating stack operations with explanations:

---

### 1. **Push Operation**
**Operation**: Push `5` onto an empty stack.

**Before Push**:  
```
Stack: []
```

**Graphical Representation**:

```
 |   |
 |   |
 |   |
 |___|
```

**After Push**:  
```
Stack: [5]
```

**Graphical Representation**:

```
 | 5 |
 |   |
 |   |
 |___|
```

**Code Example**:
```python
stack = []
stack.append(5)  # Push 5 onto the stack
print(stack)  # Output: [5]
```

---

### 2. **Push Multiple Elements**
**Operation**: Push `10` and `15` onto the stack.

**Before Push**:  
```
Stack: [5]
```

**Graphical Representation**:

```
 | 5 |
 |   |
 |   |
 |___|
```

**After Push**:  
```
Stack: [5, 10, 15]
```

**Graphical Representation**:

```
 | 15|
 | 10|
 |  5|
 |___|
```

**Code Example**:
```python
stack.append(10)  # Push 10 onto the stack
stack.append(15)  # Push 15 onto the stack
print(stack)  # Output: [5, 10, 15]
```

---

### 3. **Pop Operation**
**Operation**: Pop the top element from the stack (`15`).

**Before Pop**:  
```
Stack: [5, 10, 15]
```

**Graphical Representation**:

```
 | 15|
 | 10|
 |  5|
 |___|
```

**After Pop**:  
```
Stack: [5, 10]
```

**Graphical Representation**:

```
 | 10|
 |  5|
 |___|
```

**Code Example**:
```python
item = stack.pop()  # Pop the top element (15)
print(f"Popped item: {item}")  # Output: Popped item: 15
print(stack)  # Output: [5, 10]
```

---

### 4. **Check if Stack is Empty**
**Operation**: Check if the stack is empty.

**Before Operation**:  
```
Stack: [5, 10]
```

**Graphical Representation**:

```
 | 10|
 |  5|
 |___|
```

**Result**: The stack is **not empty**.

**Code Example**:
```python
is_empty = len(stack) == 0
print(f"Is the stack empty? {is_empty}")  # Output: Is the stack empty? False
```

---

### 5. **Peek at the Top Element**
**Operation**: Peek at the top element without popping it.

**Before Operation**:  
```
Stack: [5, 10]
```

**Graphical Representation**:

```
 | 10|
 |  5|
 |___|
```

**Result**: The top element is `10`.

**Code Example**:
```python
top_element = stack[-1]  # Peek the top element
print(f"Top element: {top_element}")  # Output: Top element: 10
```

---

### **Summary of Stack Operations**
| Operation             | Action                                  | Stack State      |
|-----------------------|-----------------------------------------|------------------|
| **Push(5)**           | Pushes `5` onto the stack               | `[5]`            |
| **Push(10), Push(15)**| Pushes `10`, then `15` onto the stack   | `[5, 10, 15]`    |
| **Pop()**             | Removes `15` from the stack             | `[5, 10]`        |
| **IsEmpty()**         | Checks if the stack is empty            | `False`          |
| **Peek()**            | Returns the top element `10`            | `[5, 10]`        |
