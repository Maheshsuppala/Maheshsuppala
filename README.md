Q1.

def find_pairs(arr, target_sum):
    pairs = []
    seen = set()

    for num in arr:
        complement = target_sum - num
        if complement in seen:
            pairs.append((num, complement))
        seen.add(num)

    return pairs
Q2. 
def reverse_array(arr):
    start = 0
    end = len(arr) - 1

    while start < end:
        arr[start], arr[end] = arr[end], arr[start]
        start += 1
        end -= 1
Q3. 
def are_rotations(str1, str2):
    if len(str1) != len(str2):
        return False

    temp = str1 + str1
    if str2 in temp:
        return True
    else:
        return False
Q4. 
from collections import Counter

def first_non_repeated_char(string):
    char_counts = Counter(string)

    for char in string:
        if char_counts[char] == 1:
            return char

    return None
Q5.
def tower_of_hanoi(n, source, auxiliary, target):
    if n > 0:
        # Move n-1 disks from source to auxiliary peg
        tower_of_hanoi(n-1, source, target, auxiliary)
        
        # Move the nth disk from source to target peg
        print(f"Move disk {n} from {source} to {target}")
        
        # Move the n-1 disks from auxiliary to target peg
        tower_of_hanoi(n-1, auxiliary, source, target)
Q6. 
def is_operator(char):
    operators = ['+', '-', '*', '/']
    return char in operators

def postfix_to_prefix(expression):
    stack = []

    for char in expression:
        if is_operator(char):
            operand2 = stack.pop()
            operand1 = stack.pop()
            prefix = char + operand1 + operand2
            stack.append(prefix)
        else:
            stack.append(char)

    return stack.pop()
Q7.
def is_operator(char):
    operators = ['+', '-', '*', '/']
    return char in operators

def prefix_to_infix(expression):
    stack = []

    for char in reversed(expression):
        if is_operator(char):
            operand1 = stack.pop()
            operand2 = stack.pop()
            infix = '(' + operand1 + char + operand2 + ')'
            stack.append(infix)
        else:
            stack.append(char)

    return stack.pop()
Q8. 
def are_brackets_balanced(code):
    stack = []

    for char in code:
        if
Q9.
def reverse_stack(stack):
    if not stack:
        return

    temp = stack.pop()
    reverse_stack(stack)
    insert_at_bottom(stack, temp)


def insert_at_bottom(stack, item):
    if not stack:
        stack.append(item)
        return

    temp = stack.pop()
    insert_at_bottom(stack, item)
    stack.append(temp)
Q10. 
class Stack:
    def __init__(self):
        self.items = []
        self.min_stack = []

    def push(self, item):
        self.items.append(item)
        if not self.min_stack or item <= self.min_stack[-1]:
            self.min_stack.append(item)

    def pop(self):
        if not self.items:
            return None

        item = self.items.pop()
        if item == self.min_stack[-1]:
            self.min_stack.pop()

        return item

    def get_min(self):
        if not self.min_stack:
            return None

        return self.min_stack[-1]










Regenerate response



