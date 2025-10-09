# Chapter 7: Lists - Introduction - Practice Questions

## Example Problems with Detailed Walkthroughs

### Example 1: Understanding Zero-Based Indexing and List Length
**Problem:** Create a list of 5 fruit names. Display the first fruit, last fruit, and middle fruit using indexing. Then show how to access the last element using both positive and negative indexing. Explain the relationship between list length and the last index.

**Detailed Solution:**

**Step 1: Understanding zero-based indexing**
Python starts counting at 0, not 1:
- First element: index 0
- Second element: index 1
- Third element: index 2
- And so on...

**Step 2: Create the list and understand positions**
```python
fruits = ["apple", "banana", "orange", "grape", "mango"]
#          0        1         2         3        4
```

**Step 3: Calculate important indices**
- Length: 5 elements
- First index: 0
- Last index: length - 1 = 5 - 1 = 4
- Middle index: length // 2 = 5 // 2 = 2

**Step 4: Understand negative indexing**
Negative indices count from the end:
```python
fruits = ["apple", "banana", "orange", "grape", "mango"]
#          -5       -4        -3        -2       -1
```
- Last element: index -1
- Second to last: index -2
- And so on...

**Step 5: Access elements both ways**

**Complete Solution:**
```python
# Create list of fruits
fruits = ["apple", "banana", "orange", "grape", "mango"]

# Display list information
print(f"List: {fruits}")
print(f"Length: {len(fruits)}")
print()

# First element (index 0)
print("=== First Element ===")
print(f"Index 0: {fruits[0]}")
print()

# Last element (two ways)
print("=== Last Element ===")
print(f"Index 4 (positive): {fruits[4]}")
print(f"Index -1 (negative): {fruits[-1]}")
print(f"Using len(): {fruits[len(fruits) - 1]}")
print()

# Middle element
middle_index = len(fruits) // 2
print("=== Middle Element ===")
print(f"Index {middle_index}: {fruits[middle_index]}")
print()

# Show the relationship
print("=== Key Relationship ===")
print(f"List length: {len(fruits)}")
print(f"Last index: {len(fruits) - 1}")
print(f"Why? Because indexing starts at 0!")
print(f"Indices available: 0, 1, 2, 3, 4 (that's {len(fruits)} indices)")
```

**Output:**
```
List: ['apple', 'banana', 'orange', 'grape', 'mango']
Length: 5

=== First Element ===
Index 0: apple

=== Last Element ===
Index 4 (positive): mango
Index -1 (negative): mango
Using len(): mango

=== Middle Element ===
Index 2: orange

=== Key Relationship ===
List length: 5
Last index: 4
Why? Because indexing starts at 0!
Indices available: 0, 1, 2, 3, 4 (that's 5 indices)
```

**Key Concepts:**
- **Zero-based indexing**: First element is at index 0
- **Last index = len(list) - 1**: Critical relationship
- **Negative indexing**: -1 is last, -2 is second to last, etc.
- **Length vs index**: 5 elements means indices 0-4
- **Why start at 0?**: Relates to memory addresses (see chapter appendix)

**Common mistakes to avoid:**
```python
fruits = ["apple", "banana", "orange", "grape", "mango"]

# WRONG - trying to access index 5
# print(fruits[5])  # IndexError! Only indices 0-4 exist

# RIGHT - last element
print(fruits[4])    # Correct
print(fruits[-1])   # Also correct
print(fruits[len(fruits) - 1])  # Verbose but correct
```

---

### Example 2: For-Each vs Range-Based Iteration
**Problem:** You have a list of test scores: [85, 92, 78, 90, 88]. Show three ways to iterate through this list: (1) using for-each to just access values, (2) using range to access by index, and (3) using enumerate to get both index and value. Explain when to use each approach.

**Detailed Solution:**

**Step 1: Understand the three iteration methods**

**Method 1: For-Each (Direct Iteration)**
- Access values directly
- Don't get index numbers
- Simplest and most common

**Method 2: Range-Based Iteration**
- Access by index position
- Can use index for calculations or modifications
- More verbose

**Method 3: Enumerate**
- Get both index AND value
- Best of both worlds
- Clean syntax

**Step 2: Compare the approaches**

**Complete Solution:**
```python
# Test scores list
scores = [85, 92, 78, 90, 88]

print("Original scores:", scores)
print(f"Number of scores: {len(scores)}")
print()

# METHOD 1: For-Each Loop (Most Common)
print("=== METHOD 1: For-Each Loop ===")
print("Use when: You only need the values")
print()

total = 0
for score in scores:
    print(f"Score: {score}")
    total += score

average = total / len(scores)
print(f"Average: {average:.1f}")
print()

# METHOD 2: Range-Based Loop
print("=== METHOD 2: Range-Based Loop ===")
print("Use when: You need the index position")
print()

for i in range(len(scores)):
    print(f"Test {i + 1} (index {i}): {scores[i]}")

print()

# METHOD 3: Enumerate (Best of Both)
print("=== METHOD 3: Enumerate ===")
print("Use when: You need both index and value")
print()

for index, score in enumerate(scores):
    print(f"Position {index} → Score {score}")

print()

# Practical example of each
print("=== PRACTICAL EXAMPLES ===")
print()

# For-each: Calculate average (don't need index)
print("1. Calculate average (for-each):")
total = 0
for score in scores:
    total += score
print(f"   Average: {total / len(scores):.1f}")
print()

# Range: Show test numbers starting from 1
print("2. Display with test numbers (range):")
for i in range(len(scores)):
    print(f"   Test {i + 1}: {scores[i]} points")
print()

# Enumerate: Find position of highest score
print("3. Find highest score position (enumerate):")
highest_score = 0
highest_position = 0

for index, score in enumerate(scores):
    if score > highest_score:
        highest_score = score
        highest_position = index

print(f"   Highest: {highest_score} at position {highest_position}")
print(f"   (Test #{highest_position + 1})")
```

**Output:**
```
Original scores: [85, 92, 78, 90, 88]
Number of scores: 5

=== METHOD 1: For-Each Loop ===
Use when: You only need the values

Score: 85
Score: 92
Score: 78
Score: 90
Score: 88
Average: 86.6

=== METHOD 2: Range-Based Loop ===
Use when: You need the index position

Test 1 (index 0): 85
Test 2 (index 1): 92
Test 3 (index 2): 78
Test 4 (index 3): 90
Test 5 (index 4): 88

=== METHOD 3: Enumerate ===
Use when: You need both index and value

Position 0 → Score 92
Position 1 → Score 92
Position 2 → Score 78
Position 3 → Score 90
Position 4 → Score 88

=== PRACTICAL EXAMPLES ===

1. Calculate average (for-each):
   Average: 86.6

2. Display with test numbers (range):
   Test 1: 85 points
   Test 2: 92 points
   Test 3: 78 points
   Test 4: 90 points
   Test 5: 88 points

3. Find highest score position (enumerate):
   Highest: 92 at position 1
   (Test #2)
```

**Decision Guide:**
```python
# Use FOR-EACH when:
# - You only need values
# - You don't need index positions
# Example: Calculate sum, find max, print all items

for score in scores:
    print(score)

# Use RANGE when:
# - You need to access by index
# - You need to modify list elements
# - You're working with multiple lists in parallel

for i in range(len(scores)):
    scores[i] = scores[i] + 5  # Curve all scores up

# Use ENUMERATE when:
# - You need both index and value
# - You want cleaner code than range

for index, score in enumerate(scores):
    print(f"Test {index + 1}: {score}")
```

**Key Concepts:**
- **For-each is most common**: Simpler and clearer when index not needed
- **Range gives index access**: Use when position matters
- **Enumerate gives both**: Best when you need index and value
- **Naming convention**: `scores` → `score`, `names` → `name`
- **Performance**: All three have similar performance for most cases

---

### Example 3: Working with Strings as Lists
**Problem:** Create a program that takes a word and analyzes it as if it were a list. Count vowels, find the position of each vowel, reverse the word, and demonstrate that strings are immutable (can't be changed) while lists are mutable (can be changed).

**Detailed Solution:**

**Step 1: Understand strings as sequences**
Strings behave like lists of characters:
- Can access by index: `word[0]`
- Can iterate through: `for char in word`
- Have a length: `len(word)`
- BUT: Cannot be modified (immutable)

**Step 2: Plan the analysis**
1. Count vowels
2. Find position of each vowel
3. Show string immutability
4. Show list mutability
5. Reverse the word

**Step 3: Understand mutability**
```python
# Strings are IMMUTABLE
word = "hello"
# word[0] = "j"  # ERROR! Can't change strings

# Lists are MUTABLE
letters = ["h", "e", "l", "l", "o"]
letters[0] = "j"  # Works! Can change lists
```

**Complete Solution:**
```python
# Get word from user
word = input("Enter a word: ").lower()

print(f"\n=== Analyzing '{word}' ===")
print(f"Length: {len(word)} characters")
print()

# 1. Count vowels using string iteration
print("=== Vowel Analysis ===")
vowels = "aeiou"
vowel_count = 0
vowel_positions = []

for index, char in enumerate(word):
    if char in vowels:
        vowel_count += 1
        vowel_positions.append(index)
        print(f"Found '{char}' at position {index}")

print(f"Total vowels: {vowel_count}")
print()

# 2. Show character-by-character access (like a list)
print("=== Character Access (like lists) ===")
print(f"First character: {word[0]}")
print(f"Last character: {word[-1]}")
print(f"Middle character: {word[len(word) // 2]}")
print()

# 3. Demonstrate immutability
print("=== String Immutability ===")
print(f"Original word: {word}")
print("Trying to change first letter...")
print("# word[0] = 'X'  # This would cause an ERROR")
print("Strings cannot be modified!")
print()

# 4. Show how to "change" a string (create new one)
print("=== Creating Modified Strings ===")
# Convert to list, modify, convert back
word_list = list(word)
print(f"As a list: {word_list}")

word_list[0] = word_list[0].upper()
modified_word = "".join(word_list)
print(f"Modified: {modified_word}")
print(f"Original unchanged: {word}")
print()

# 5. Reverse the word (multiple methods)
print("=== Reversing the Word ===")

# Method 1: Using slicing
reversed_word = word[::-1]
print(f"Method 1 (slicing): {reversed_word}")

# Method 2: Using loop
reversed_word2 = ""
for char in word:
    reversed_word2 = char + reversed_word2
print(f"Method 2 (loop): {reversed_word2}")

# Method 3: Convert to list, reverse, convert back
word_list = list(word)
word_list.reverse()
reversed_word3 = "".join(word_list)
print(f"Method 3 (list): {reversed_word3}")
print()

# 6. Show all characters with indices
print("=== Complete Character Map ===")
for i in range(len(word)):
    print(f"Index {i}: '{word[i]}'")
```

**Sample Run:**
```
Enter a word: python

=== Analyzing 'python' ===
Length: 6 characters

=== Vowel Analysis ===
Found 'y' at position 1
Found 'o' at position 4
Total vowels: 2

=== Character Access (like lists) ===
First character: p
Last character: n
Middle character: t

=== String Immutability ===
Original word: python
Trying to change first letter...
# word[0] = 'X'  # This would cause an ERROR
Strings cannot be modified!

=== Creating Modified Strings ===
As a list: ['p', 'y', 't', 'h', 'o', 'n']
Modified: Python
Original unchanged: python

=== Reversing the Word ===
Method 1 (slicing): nohtyp
Method 2 (loop): nohtyp
Method 3 (list): nohtyp

=== Complete Character Map ===
Index 0: 'p'
Index 1: 'y'
Index 2: 't'
Index 3: 'h'
Index 4: 'o'
Index 5: 'n'
```

**Key Concepts:**
- **Strings are like lists**: Can index, iterate, get length
- **Strings are immutable**: Cannot change individual characters
- **Lists are mutable**: Can change individual elements
- **String iteration**: `for char in word` accesses each character
- **Conversion**: `list(string)` creates mutable list, `"".join(list)` creates string
- **Multiple approaches**: Many ways to accomplish same task

**The immutability difference:**
```python
# STRINGS - Immutable
word = "hello"
# word[0] = "j"     # ERROR!
word = "jello"      # OK - creates NEW string

# LISTS - Mutable  
letters = ["h", "e", "l", "l", "o"]
letters[0] = "j"    # OK - modifies existing list
# Result: ["j", "e", "l", "l", "o"]
```

---

## Practice Questions (25 Questions - Increasing Complexity)

### List Basics and Indexing (Questions 1-5)

1. Create a list of 5 colors. Print the first color, the last color, and the color at index 2.

2. Make a list of numbers [10, 20, 30, 40, 50]. Access and print the last element using both positive and negative indexing.

3. Create a list of your 4 favorite foods. Print the length of the list and the index of the last element (calculate it using len()).

4. Make a list [5, 10, 15, 20, 25, 30]. Print elements at indices 0, 2, and 4. Then print the element at index -2.

5. Create a list of 6 names. Print the first three names using positive indices, then print the last three names using negative indices.

### Iterating with For-Each (Questions 6-10)

6. Create a list of 5 numbers. Use a for-each loop to print each number.

7. Make a list of fruit names and use a for-each loop to print each one with "I like [fruit]".

8. Create a list of prices [9.99, 15.50, 7.25, 22.00]. Use a for-each loop to calculate and print the total.

9. Make a list of temperatures [72, 68, 75, 80, 71]. Use a for-each loop to count how many are above 70.

10. Create a list of words. Use a for-each loop to print each word and its length.

### Iterating with Range (Questions 11-15)

11. Create a list [10, 20, 30, 40, 50]. Use a range-based loop to print each element with its index position.

12. Make a list of 5 scores. Use range to print them in the format "Test 1: [score]" (starting from 1, not 0).

13. Create two lists of equal length with names and ages. Use range to print each person's info: "Name: [name], Age: [age]".

14. Make a list [100, 200, 300, 400]. Use range to double each element in the list (modify the original list).

15. Create a list of numbers. Use range to print elements at only even indices (0, 2, 4, etc.).

### Using Enumerate (Questions 16-20)

16. Create a list of colors. Use enumerate to print each color with its position number (starting from 0).

17. Make a list of scores. Use enumerate to find and print the position of the highest score.

18. Create a list of names. Use enumerate to print them as a numbered list starting from 1 (not 0).

19. Make a list [5, 10, 15, 20, 25]. Use enumerate to create a new list containing only elements at odd indices.

20. Create a shopping list. Use enumerate to print each item as "Item #: [name]" and count the total items.

### Strings as Lists (Questions 21-25)

21. Ask for a word and print each character on a separate line using a for loop.

22. Get a word from the user and count how many vowels (a, e, i, o, u) it contains.

23. Take a word and print it in reverse using a for loop (don't use slicing or reverse()).

24. Ask for a sentence and count how many words it contains (split by spaces).

25. Get a word from the user, convert it to a list, capitalize the first and last characters, and print the modified word.

---

## Tips for Solving These Problems

### List Indexing Rules
1. **First element**: Always index 0
2. **Last element**: index -1 OR index len(list) - 1
3. **Second element**: index 1
4. **Second to last**: index -2 OR index len(list) - 2
5. **Remember**: `len(list)` is always one MORE than the last index

### When to Use Each Loop Type

**For-Each Loop (Most Common):**
```python
for item in my_list:
    # Use when you only need values
    print(item)
```

**Range-Based Loop:**
```python
for i in range(len(my_list)):
    # Use when you need index
    print(f"Position {i}: {my_list[i]}")
```

**Enumerate:**
```python
for index, item in enumerate(my_list):
    # Use when you need both
    print(f"Position {index}: {item}")
```

### Common Patterns

**Find maximum:**
```python
maximum = my_list[0]
for num in my_list:
    if num > maximum:
        maximum = num
```

**Count occurrences:**
```python
count = 0
for item in my_list:
    if item == target:
        count += 1
```

**Sum all elements:**
```python
total = 0
for num in my_list:
    total += num
```

**Modify all elements:**
```python
for i in range(len(my_list)):
    my_list[i] = my_list[i] * 2
```

### Working with Strings

**Iterate through characters:**
```python
for char in word:
    print(char)
```

**Check if character in string:**
```python
if char in vowels:
    # char is a vowel
```

**Convert string to list:**
```python
char_list = list(word)
```

**Convert list to string:**
```python
word = "".join(char_list)
```

### Naming Conventions

**Use plural for lists, singular for loop variables:**
```python
# Good
names = ["Alice", "Bob", "Charlie"]
for name in names:
    print(name)

# Good
scores = [85, 92, 78]
for score in scores:
    print(score)

# Less clear
names = ["Alice", "Bob", "Charlie"]
for x in names:  # What is x?
    print(x)
```

### Problem-Solving Strategy

1. **Understand what you need**:
   - Just values? Use for-each
   - Need position? Use range or enumerate
   - Need both? Use enumerate

2. **Check if you need to modify**:
   - Modifying list? Use range with index
   - Just reading? Use for-each

3. **Consider string operations**:
   - Strings act like lists for reading
   - Must convert to list for modifications

4. **Watch for off-by-one errors**:
   - Length is n, last index is n-1
   - Human counting starts at 1, Python starts at 0

### Debugging Tips

1. **Print the list**:
   ```python
   print(my_list)
   print(f"Length: {len(my_list)}")
   ```

2. **Print loop variable**:
   ```python
   for i in range(len(my_list)):
       print(f"i={i}, value={my_list[i]}")
   ```

3. **Check valid indices**:
   ```python
   print(f"Valid indices: 0 to {len(my_list) - 1}")
   ```

4. **Test with small lists**:
   ```python
   test_list = [1, 2, 3]  # Easy to trace
   ```

5. **Remember the relationships**:
   ```python
   # If length is 5:
   # - Indices: 0, 1, 2, 3, 4
   # - Last index: 4 (which is 5 - 1)
   ```