### Stack Data Structure - Notes

#### 1. **Introduction to Stack**
A **Stack** is a linear data structure that follows the **LIFO (Last In First Out)** principle. This means that the last element added to the stack will be the first one to be removed. Think of a stack of plates: you add plates to the top, and you remove plates from the top.

#### 2. **Basic Operations**
Here are the key operations on a stack:

- **Push**: Add an element to the top of the stack.
- **Pop**: Remove and return the top element from the stack.
- **Peek/Top**: Return the top element without removing it.
- **isEmpty**: Check whether the stack is empty.
- **Size**: Return the number of elements in the stack.

#### 3. **Real-Life Examples**
- Browser history (back button)
- Undo feature in text editors
- Call stack in recursive function calls

#### 4. **Python Implementation Using List**

In Python, a list can be used to implement a stack, with the following built-in methods:

- `append()` to push an element onto the stack.
- `pop()` to remove an element from the stack.

```python
class Stack:
    def __init__(self):
        self.stack = []
    
    # Push an element onto the stack
    def push(self, item):
        self.stack.append(item)
        print(f"Pushed {item} onto the stack.")
    
    # Pop an element from the stack
    def pop(self):
        if self.is_empty():
            return "Stack is empty."
        return self.stack.pop()
    
    # Peek the top element of the stack
    def peek(self):
        if self.is_empty():
            return "Stack is empty."
        return self.stack[-1]
    
    # Check if the stack is empty
    def is_empty(self):
        return len(self.stack) == 0
    
    # Return the size of the stack
    def size(self):
        return len(self.stack)

# Example usage:
s = Stack()
s.push(1)
s.push(2)
s.push(3)
print(f"Top element: {s.peek()}")  # Output: Top element: 3
print(f"Popped element: {s.pop()}")  # Output: Popped element: 3
print(f"Stack size: {s.size()}")  # Output: Stack size: 2
```

#### 5. **Common Stack Use Cases**

1. **Balancing Parentheses**
   You can use a stack to check whether parentheses (or brackets) in an expression are balanced.
   
   Example:
   ```python
   def is_balanced(expr):
       stack = []
       pairs = {')': '(', ']': '[', '}': '{'}
       for char in expr:
           if char in pairs.values():  # If it's an opening bracket
               stack.append(char)
           elif char in pairs.keys():  # If it's a closing bracket
               if stack == [] or pairs[char] != stack.pop():
                   return False
       return stack == []
   
   print(is_balanced("(a + b)"))  # Output: True
   print(is_balanced("(a + b]"))  # Output: False
   ```

2. **Reversing a String**
   Using a stack, you can reverse the characters of a string.
   
   Example:
   ```python
   def reverse_string(s):
       stack = []
       for char in s:
           stack.append(char)
       reversed_str = ''
       while stack:
           reversed_str += stack.pop()
       return reversed_str
   
   print(reverse_string("hello"))  # Output: "olleh"
   ```

3. **Evaluating Postfix Expressions**
   A stack is useful in evaluating postfix (Reverse Polish Notation) expressions.

   Example:
   ```python
   def evaluate_postfix(expression):
       stack = []
       for char in expression:
           if char.isdigit():
               stack.append(int(char))
           else:
               val1 = stack.pop()
               val2 = stack.pop()
               if char == '+':
                   stack.append(val2 + val1)
               elif char == '-':
                   stack.append(val2 - val1)
               elif char == '*':
                   stack.append(val2 * val1)
               elif char == '/':
                   stack.append(val2 / val1)
       return stack.pop()
   
   print(evaluate_postfix("231*+9-"))  # Output: -4
   ```

#### 6. **Stack in Real-World Applications**
- **Depth-First Search (DFS)**: In graph traversal, DFS uses a stack to explore nodes.
- **Expression Evaluation**: Stacks are used to convert and evaluate infix, prefix, and postfix expressions.
- **Backtracking Algorithms**: Problems like solving mazes, Sudoku, etc., often utilize stacks for backtracking.
