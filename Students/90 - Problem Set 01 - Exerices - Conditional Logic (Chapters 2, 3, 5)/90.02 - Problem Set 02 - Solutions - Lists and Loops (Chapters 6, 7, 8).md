# Introduction to Python Programming
## Problem Set 02 - Solutions - Lists and Loops

### How to Use This Guide

- Try solving problems yourself before reading solutions
- Read the "Thinking Process" to understand the approach
- Later solutions assume you understand earlier concepts
- Focus on new techniques introduced in each problem

---

## Level 1: Basic List Operations (Problems 1-5)

### Problem 1: Create and Print

**Thinking Process:**
Create a list with square brackets and strings. Use a for-each loop since we just need the values, not indices.

**Solution:**
```python
fruits = ["apple", "banana", "cherry", "date", "elderberry"]

for fruit in fruits:
    print(fruit)
```

**Key Points:**
- Lists created with square brackets `[]`
- Items separated by commas
- For-each loop: `for item in list` gives us each value directly

---

### Problem 2: List Access

**Thinking Process:**
Remember that lists use zero-based indexing. First item is index 0, last item is index -1 or `len(list) - 1`.

**Solution:**
```python
numbers = [10, 20, 30, 40, 50, 60, 70]

print(f"First: {numbers[0]}")
print(f"Last: {numbers[-1]}")
print(f"Middle: {numbers[3]}")
```

**Key Points:**
- First element: index 0
- Last element: index -1 (or `len(numbers) - 1`)
- Middle of 7 items is index 3 (the 4th item)

---

### Problem 3: Sum of Numbers

**Thinking Process:**
Use an accumulator pattern: start with 0, add each number as we loop through.

**Solution:**
```python
numbers = [10, 20, 30, 40, 50]
total = 0

for number in numbers:
    total = total + number

print(f"Sum: {total}")
```

**Key Points:**
- Accumulator starts at 0
- Each iteration adds current number to total
- For-each is perfect here - we don't need indices

---

### Problem 4: Count Items

**Thinking Process:**
Use a counter that increments each time we find the target value. Check each item with an if statement.

**Solution:**
```python
numbers = [3, 7, 3, 9, 3, 5, 3]
count = 0

for number in numbers:
    if number == 3:
        count = count + 1

print(f"Number 3 appears {count} times")
```

**Key Points:**
- Counter starts at 0
- Increment counter when condition matches
- Use `==` for comparison (not `=` which is assignment)

---

### Problem 5: Find Maximum

**Thinking Process:**
Start by assuming the first element is the maximum. Then compare each subsequent element, updating maximum if we find something larger.

**Solution:**
```python
numbers = [45, 23, 67, 89, 12, 56]
maximum = numbers[0]

for number in numbers:
    if number > maximum:
        maximum = number

print(f"Maximum: {maximum}")
```

**Key Points:**
- Initialize maximum with first element `numbers[0]`
- Compare each number to current maximum
- Update maximum when we find something larger
- This works even if the first element is the largest

---

## Level 2: List Modification (Problems 6-10)

### Problem 6: Build a List

**Thinking Process:**
Start with an empty list and use `.append()` to add items. We need a loop that runs 5 times.

**Solution:**
```python
numbers = []

for i in range(5):
    num = int(input(f"Enter number {i + 1}: "))
    numbers.append(num)

print(f"Your list: {numbers}")
```

**Key Points:**
- Start with empty list: `[]`
- `.append()` adds items to the end
- `i + 1` for display since humans count from 1, Python counts from 0

---

### Problem 7: Double the Values

**Thinking Process:**
Create a new list and add doubled values. Don't modify the original - create a separate list.

**Solution:**
```python
original = [5, 10, 15, 20, 25]
doubled = []

for number in original:
    doubled.append(number * 2)

print(f"Original: {original}")
print(f"Doubled: {doubled}")
```

**Key Points:**
- Create new empty list for results
- Multiply each value by 2 before appending
- Original list remains unchanged

---

### Problem 8: Replace Values

**Thinking Process:**
Use index access to replace a specific item. Need to find which index "banana" is at.

**Solution:**
```python
fruits = ["apple", "banana", "cherry", "date"]
fruits[1] = "blueberry"
print(fruits)
```

**Key Points:**
- Direct index assignment: `list[index] = new_value`
- "banana" is at index 1
- Lists are mutable - we can change them

---

### Problem 9: Remove Negatives

**Thinking Process:**
Check each number. If positive, add to new list. Only include items that meet our condition.

**Solution:**
```python
numbers = [5, -2, 8, -7, 3, -1, 9]
positives = []

for number in numbers:
    if number > 0:
        positives.append(number)

print(f"Positive numbers: {positives}")
```

**Key Points:**
- Filter pattern: check condition, then add to new list
- `> 0` means positive (excludes 0 and negatives)
- Original list unchanged

---

### Problem 10: Reverse Order

**Thinking Process:**
Loop backwards through indices. Start at last index, go down to 0. Use range with negative step.

**Solution:**
```python
items = ["a", "b", "c", "d", "e", "f"]

for i in range(len(items) - 1, -1, -1):
    print(items[i])
```

**Key Points:**
- `len(items) - 1` is the last index
- `-1` is the stop value (exclusive, so we stop before -1, meaning we include 0)
- `-1` step means count backwards
- `range(5, -1, -1)` gives: 5, 4, 3, 2, 1, 0

---

## Level 3: Slicing and Searching (Problems 11-15)

### Problem 11: First and Last Three

**Thinking Process:**
Slicing syntax is `[start:stop]`. Remember stop is exclusive. For first 3: start at 0, stop at 3. For last 3: start at -3, go to end.

**Solution:**
```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

first_three = numbers[:3]
last_three = numbers[-3:]

print(f"First three: {first_three}")
print(f"Last three: {last_three}")
```

**Key Points:**
- `[:3]` means "from start to index 3 (exclusive)" = indices 0, 1, 2
- `[-3:]` means "from third-to-last to end"
- Omitting start/stop means "from beginning" or "to end"

---

### Problem 12: Every Other Item

**Thinking Process:**
Use step parameter in slicing. `[::2]` means start at beginning, go to end, step by 2.

**Solution:**
```python
items = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j"]

every_other = items[::2]
print(every_other)
```

**Key Points:**
- `[::2]` = `[start:stop:step]` with start and stop omitted
- Step of 2 means take every second item
- Results in indices 0, 2, 4, 6, 8

---

### Problem 13: Middle Section

**Thinking Process:**
12 items total, want middle 6. That's indices 3, 4, 5, 6, 7, 8. Start at 3, stop at 9 (exclusive).

**Solution:**
```python
items = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l"]

middle = items[3:9]
print(middle)
```

**Key Points:**
- Slice `[3:9]` gets indices 3 through 8 (9 is exclusive)
- Count the items: indices 3, 4, 5, 6, 7, 8 = 6 items

---

### Problem 14: Search and Report

**Thinking Process:**
Use `in` operator to check existence. If found, use `.index()` to get position. Handle "not found" case.

**Solution:**
```python
fruits = ["apple", "banana", "cherry", "date", "elderberry"]
search = input("Enter a fruit to search for: ")

if search in fruits:
    position = fruits.index(search)
    print(f"{search} found at position {position}")
else:
    print("Not found")
```

**Key Points:**
- `in` operator checks if item exists in list
- `.index()` returns position (but errors if not found)
- Always check with `in` before using `.index()`

---

### Problem 15: Split List

**Thinking Process:**
Find midpoint, slice from start to midpoint, then midpoint to end.

**Solution:**
```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
midpoint = len(numbers) // 2

first_half = numbers[:midpoint]
second_half = numbers[midpoint:]

print(f"First half: {first_half}")
print(f"Second half: {second_half}")
```

**Key Points:**
- `//` is floor division (gives whole number)
- `[:midpoint]` gets first half
- `[midpoint:]` gets second half
- The two halves don't overlap because stop is exclusive

---

## Level 4: Advanced List Operations (Problems 16-20)

### Problem 16: Remove Duplicates

**Thinking Process:**
Build new list, only add items that aren't already in it. Check membership before adding.

**Solution:**
```python
numbers = [1, 2, 3, 2, 4, 1, 5, 3, 6]
unique = []

for number in numbers:
    if number not in unique:
        unique.append(number)

print(unique)
```

**Key Points:**
- Check `not in` before appending
- Maintains original order
- First occurrence of each number is kept

---

### Problem 17: List Statistics

**Thinking Process:**
Calculate average (sum/count), find max/min, then count how many exceed average. Multiple passes through data.

**Solution:**
```python
scores = [85, 92, 78, 90, 88, 76, 95, 82]

total = sum(scores)
average = total / len(scores)
highest = max(scores)
lowest = min(scores)

above_average = 0
for score in scores:
    if score > average:
        above_average = above_average + 1

print(f"Average: {average:.2f}")
print(f"Highest: {highest}")
print(f"Lowest: {lowest}")
print(f"Above average: {above_average}")
```

**Key Points:**
- Built-in functions: `sum()`, `max()`, `min()`
- Calculate average first, then use it in loop
- `.2f` formats to 2 decimal places

---

### Problem 18: Merge and Sort

**Thinking Process:**
Combine lists with `+`, then sort. Use `.sort()` to modify in place or `sorted()` for new list.

**Solution:**
```python
list1 = [5, 2, 8, 1]
list2 = [9, 3, 7, 4]

merged = list1 + list2
merged.sort()

print(f"Merged and sorted: {merged}")
```

**Key Points:**
- `+` concatenates lists
- `.sort()` modifies the list in place
- Could also use: `sorted(list1 + list2)`

---

### Problem 19: Shopping List Manager

**Thinking Process:**
Menu loop needs `while True` with `break` to exit. Each option modifies the list or displays it.

**Solution:**
```python
shopping_list = []

while True:
    print("\n=== Shopping List ===")
    print("1. Add item")
    print("2. Remove item")
    print("3. View list")
    print("4. Quit")
    
    choice = input("Choose option: ")
    
    if choice == "1":
        item = input("Enter item to add: ")
        shopping_list.append(item)
        print(f"Added: {item}")
    
    elif choice == "2":
        item = input("Enter item to remove: ")
        if item in shopping_list:
            shopping_list.remove(item)
            print(f"Removed: {item}")
        else:
            print("Item not found")
    
    elif choice == "3":
        if shopping_list:
            print("Your shopping list:")
            for item in shopping_list:
                print(f"  - {item}")
        else:
            print("List is empty")
    
    elif choice == "4":
        print("Goodbye!")
        break
    
    else:
        print("Invalid choice")
```

**Key Points:**
- `while True` creates infinite loop, `break` exits
- Check if item exists before removing
- `if shopping_list:` checks if list is not empty

---

### Problem 20: Word Reverser

**Thinking Process:**
Split sentence into words, reverse each word using slicing, join them back together.

**Solution:**
```python
sentence = input("Enter a sentence: ")
words = sentence.split()
reversed_words = []

for word in words:
    reversed_word = word[::-1]
    reversed_words.append(reversed_word)

result = " ".join(reversed_words)
print(result)
```

**Key Points:**
- `.split()` creates list of words
- `[::-1]` reverses a string
- `" ".join(list)` combines list items with spaces

---

## Level 5: Complex Operations (Problems 21-23)

### Problem 21: Grade Distribution

**Thinking Process:**
Count items in ranges. Use multiple if-elif to categorize each grade, increment appropriate counter.

**Solution:**
```python
grades = [95, 87, 76, 92, 68, 55, 89, 73, 91, 82, 78, 64]

a_count = 0
b_count = 0
c_count = 0
d_count = 0
f_count = 0

for grade in grades:
    if grade >= 90:
        a_count = a_count + 1
    elif grade >= 80:
        b_count = b_count + 1
    elif grade >= 70:
        c_count = c_count + 1
    elif grade >= 60:
        d_count = d_count + 1
    else:
        f_count = f_count + 1

print(f"A: {a_count}")
print(f"B: {b_count}")
print(f"C: {c_count}")
print(f"D: {d_count}")
print(f"F: {f_count}")
```

**Key Points:**
- Multiple counters for different categories
- Order matters in if-elif: check highest first
- Each grade increments exactly one counter

---

### Problem 22: Two-List Comparison

**Thinking Process:**
Need three separate results: items in both, only in first, only in second. Check membership in opposite list.

**Solution:**
```python
list1 = ["Alice", "Bob", "Charlie", "David"]
list2 = ["Bob", "David", "Eve", "Frank"]

in_both = []
only_first = []
only_second = []

# Find items in both
for name in list1:
    if name in list2:
        in_both.append(name)

# Find items only in first
for name in list1:
    if name not in list2:
        only_first.append(name)

# Find items only in second
for name in list2:
    if name not in list1:
        only_second.append(name)

print(f"In both: {in_both}")
print(f"Only in first: {only_first}")
print(f"Only in second: {only_second}")
```

**Key Points:**
- Three separate loops for three results
- Check membership in other list
- Could combine first two loops for efficiency (check once, add to appropriate list)

---

### Problem 23: Matrix Operations

**Thinking Process:**
Matrix is a list of lists. Need nested loops: outer for rows, inner for items in each row. Column sum requires accessing same index from each row.

**Solution:**
```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

# Sum of all numbers
total = 0
for row in matrix:
    for number in row:
        total = total + number
print(f"Total sum: {total}")

# Sum of each row
print("Row sums:")
for i, row in enumerate(matrix):
    row_sum = sum(row)
    print(f"  Row {i}: {row_sum}")

# Sum of each column
print("Column sums:")
for col in range(3):
    col_sum = 0
    for row in matrix:
        col_sum = col_sum + row[col]
    print(f"  Column {col}: {col_sum}")
```

**Key Points:**
- Nested loops: outer iterates rows, inner iterates items
- `enumerate()` gives index and value
- Column sum: fix column index, iterate through rows
- `row[col]` accesses same column from different rows

---

## Level 6: Advanced Challenges (Problems 24-25)

### Problem 24: List Rotation

**Thinking Process:**
Rotation means move items from end to beginning. Slice last N items and first (length - N) items, concatenate in reverse order.

**Solution:**
```python
items = [1, 2, 3, 4, 5]
positions = int(input("Rotate how many positions right? "))

# Handle rotations larger than list length
positions = positions % len(items)

rotated = items[-positions:] + items[:-positions]
print(f"Original: {items}")
print(f"Rotated: {rotated}")
```

**Key Points:**
- `[-positions:]` gets last N items
- `[:-positions]` gets all but last N items
- Concatenate: last items + first items
- `% len(items)` handles rotations larger than list length
- Rotating 7 positions in 5-item list = rotating 2 positions

---

### Problem 25: Contact Manager with Nested Lists

**Thinking Process:**
Each contact is a list: `[name, phone, email]`. Main list holds all contacts. Menu system needs add, search, display, delete, update operations. Search requires iterating through contacts, comparing names.

**Solution:**
```python
contacts = []

while True:
    print("\n=== Contact Manager ===")
    print("1. Add contact")
    print("2. Search contact")
    print("3. List all contacts")
    print("4. Delete contact")
    print("5. Update contact")
    print("6. Quit")
    
    choice = input("Choose option: ")
    
    if choice == "1":
        name = input("Name: ")
        phone = input("Phone: ")
        email = input("Email: ")
        contacts.append([name, phone, email])
        print(f"Added {name}")
    
    elif choice == "2":
        search_name = input("Search for: ")
        found = False
        for contact in contacts:
            if contact[0] == search_name:
                print(f"Name: {contact[0]}")
                print(f"Phone: {contact[1]}")
                print(f"Email: {contact[2]}")
                found = True
                break
        if not found:
            print("Contact not found")
    
    elif choice == "3":
        if contacts:
            print("\nAll Contacts:")
            for contact in contacts:
                print(f"  {contact[0]}: {contact[1]}, {contact[2]}")
        else:
            print("No contacts")
    
    elif choice == "4":
        delete_name = input("Delete contact: ")
        found = False
        for contact in contacts:
            if contact[0] == delete_name:
                contacts.remove(contact)
                print(f"Deleted {delete_name}")
                found = True
                break
        if not found:
            print("Contact not found")
    
    elif choice == "5":
        update_name = input("Update contact: ")
        found = False
        for contact in contacts:
            if contact[0] == update_name:
                print("1. Update phone")
                print("2. Update email")
                update_choice = input("Choose: ")
                if update_choice == "1":
                    contact[1] = input("New phone: ")
                elif update_choice == "2":
                    contact[2] = input("New email: ")
                print("Updated!")
                found = True
                break
        if not found:
            print("Contact not found")
    
    elif choice == "6":
        print("Goodbye!")
        break
    
    else:
        print("Invalid choice")
```

**Key Points:**
- Nested list structure: `[[name, phone, email], [name, phone, email], ...]`
- Access elements: `contact[0]` = name, `contact[1]` = phone, `contact[2]` = email
- Search pattern: loop through contacts, compare first element
- Modify nested list: `contact[1] = new_value` changes phone
- Use `break` after finding to avoid checking remaining contacts
- Always check if found to give appropriate feedback

**This problem combines:**
- Nested lists (lists within lists)
- Menu system with multiple operations
- Searching through structured data
- Modifying nested structures
- User input validation
- Multiple nested conditions

---

## Key Takeaways from Solutions

### Patterns Learned:

1. **Accumulator Pattern:** Start with initial value, modify in loop (sum, count, max)
2. **Filter Pattern:** Check condition, add to new list if true
3. **Transform Pattern:** Apply operation to each item, store in new list
4. **Search Pattern:** Loop until found, use flag variable
5. **Menu Pattern:** `while True` with `break`, handle each option
6. **Nested Structures:** Outer loop for containers, inner for items

### Slicing Mastery:

- `[start:stop]` - basic slice (stop exclusive)
- `[:n]` - first n items
- `[-n:]` - last n items
- `[::step]` - every nth item
- `[::-1]` - reverse
- Works identically for lists and strings

### Common Techniques:

- Check membership before removing (`if item in list`)
- Initialize with first element when finding max/min
- Use `enumerate()` when you need both index and value
- Split/join for string-list conversions
- Modulo (`%`) for wraparound problems

---

## Debugging Tips Applied

1. **Index errors?** Check list length, verify indices exist
2. **Not found errors?** Check membership with `in` before accessing
3. **Wrong results?** Print intermediate values to trace logic
4. **Infinite loops?** Ensure break condition is reachable
5. **Nested list confusion?** Print the structure to visualize
