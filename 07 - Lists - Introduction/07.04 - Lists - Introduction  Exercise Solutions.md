# Chapter 7: Lists - Introduction - Solutions Guide

## List Basics and Indexing (Questions 1-5)

### Question 1
**Problem:** Create a list of 5 colors. Print the first color, the last color, and the color at index 2.

**Solution Approach:**
- Create list with 5 colors
- First: index 0
- Last: index 4 or -1
- Index 2: third element (remember zero-based!)

**Complete Solution:**
```python
# Create list of colors
colors = ["red", "blue", "green", "yellow", "purple"]

# Print specific elements
print(f"First color: {colors[0]}")
print(f"Last color: {colors[4]}")  # or colors[-1]
print(f"Color at index 2: {colors[2]}")
```

**Output:**
```
First color: red
Last color: purple
Color at index 2: green
```

**Key Concepts:**
- Index 0 is always the first element
- Index 2 is the third element (0, 1, 2)
- Last element can be accessed with -1 or len()-1
- Zero-based indexing: position n is at index n-1

---

### Question 2
**Problem:** Make a list of numbers [10, 20, 30, 40, 50]. Access and print the last element using both positive and negative indexing.

**Solution Approach:**
- List has 5 elements, so indices 0-4
- Positive index for last: 4
- Negative index for last: -1
- Show both methods

**Complete Solution:**
```python
# Create list
numbers = [10, 20, 30, 40, 50]

# Access last element both ways
print(f"Using positive index [4]: {numbers[4]}")
print(f"Using negative index [-1]: {numbers[-1]}")

# Show why positive index is 4
print(f"\nList has {len(numbers)} elements")
print(f"Last positive index: {len(numbers) - 1}")
```

**Output:**
```
Using positive index [4]: 50
Using negative index [-1]: 50

List has 5 elements
Last positive index: 4
```

**Key Concepts:**
- Last positive index = len(list) - 1
- Negative index -1 always gives last element
- Both methods access the same element
- Negative indices count backwards from end

---

### Question 3
**Problem:** Create a list of your 4 favorite foods. Print the length of the list and the index of the last element (calculate it using len()).

**Solution Approach:**
- Create list of 4 foods
- Use len() to get length
- Calculate last index: len() - 1
- Show the relationship

**Complete Solution:**
```python
# Create list of favorite foods
foods = ["pizza", "sushi", "tacos", "pasta"]

# Get length
length = len(foods)
print(f"Number of foods: {length}")

# Calculate last index
last_index = len(foods) - 1
print(f"Last index: {last_index}")

# Verify by accessing it
print(f"Element at last index: {foods[last_index]}")

# Show the relationship
print(f"\nRelationship: length={length}, last_index={last_index}")
print(f"Why? Because indexing starts at 0!")
```

**Output:**
```
Number of foods: 4
Last index: 3
Element at last index: pasta

Relationship: length=4, last_index=3
Why? Because indexing starts at 0!
```

**Key Concepts:**
- len() returns number of elements
- Last index is always len() - 1
- 4 elements means indices 0, 1, 2, 3
- This relationship is fundamental to list indexing

---

### Question 4
**Problem:** Make a list [5, 10, 15, 20, 25, 30]. Print elements at indices 0, 2, and 4. Then print the element at index -2.

**Solution Approach:**
- Access specific positive indices
- Then use negative index -2 (second from end)
- Show what -2 corresponds to in positive indexing

**Complete Solution:**
```python
# Create list
numbers = [5, 10, 15, 20, 25, 30]

# Print elements at specified indices
print("Elements at positive indices:")
print(f"Index 0: {numbers[0]}")
print(f"Index 2: {numbers[2]}")
print(f"Index 4: {numbers[4]}")

# Print element at negative index
print(f"\nElement at index -2: {numbers[-2]}")

# Show the equivalence
print(f"\nNote: Index -2 is the same as index {len(numbers) - 2}")
print(f"Verify: numbers[{len(numbers) - 2}] = {numbers[len(numbers) - 2]}")
```

**Output:**
```
Elements at positive indices:
Index 0: 5
Index 2: 15
Index 4: 25

Element at index -2: 25

Note: Index -2 is the same as index 4
Verify: numbers[4] = 25
```

**Key Concepts:**
- Can access any valid index directly
- -2 means second from the end
- -2 equivalent to len(list) - 2 in positive indexing
- Negative indices are counted from the right

---

### Question 5
**Problem:** Create a list of 6 names. Print the first three names using positive indices, then print the last three names using negative indices.

**Solution Approach:**
- First three: indices 0, 1, 2
- Last three: indices -3, -2, -1
- Show both methods access the same elements

**Complete Solution:**
```python
# Create list of names
names = ["Alice", "Bob", "Charlie", "Diana", "Eve", "Frank"]

# Print first three using positive indices
print("First three names (positive indices):")
print(f"Index 0: {names[0]}")
print(f"Index 1: {names[1]}")
print(f"Index 2: {names[2]}")

# Print last three using negative indices
print("\nLast three names (negative indices):")
print(f"Index -3: {names[-3]}")
print(f"Index -2: {names[-2]}")
print(f"Index -1: {names[-1]}")

# Show the equivalence
print("\nVerification:")
print(f"names[3] = {names[3]}, names[-3] = {names[-3]}")
print(f"names[4] = {names[4]}, names[-2] = {names[-2]}")
print(f"names[5] = {names[5]}, names[-1] = {names[-1]}")
```

**Output:**
```
First three names (positive indices):
Index 0: Alice
Index 1: Bob
Index 2: Charlie

Last three names (negative indices):
Index -3: Diana
Index -4: Eve
Index -1: Frank

Verification:
names[3] = Diana, names[-3] = Diana
names[4] = Eve, names[-2] = Eve
names[5] = Frank, names[-1] = Frank
```

**Key Concepts:**
- Positive indices: 0, 1, 2, 3, 4, 5
- Negative indices: -6, -5, -4, -3, -2, -1
- -1 is last, -2 is second to last, etc.
- Both access same memory locations

---

## Iterating with For-Each (Questions 6-10)

### Question 6
**Problem:** Create a list of 5 numbers. Use a for-each loop to print each number.

**Solution Approach:**
- For-each directly accesses values
- No need for indices
- Simplest iteration method

**Complete Solution:**
```python
# Create list of numbers
numbers = [10, 25, 30, 45, 50]

# Print each number using for-each
print("Numbers in the list:")
for number in numbers:
    print(number)
```

**Output:**
```
Numbers in the list:
10
25
30
45
50
```

**Key Concepts:**
- For-each syntax: `for item in list:`
- Loop variable takes each value automatically
- No indexing needed
- Most straightforward iteration method

---

### Question 7
**Problem:** Make a list of fruit names and use a for-each loop to print each one with "I like [fruit]".

**Solution Approach:**
- Create list of fruits
- Use for-each to access each fruit
- Format string with fruit name

**Complete Solution:**
```python
# Create list of fruits
fruits = ["apples", "bananas", "oranges", "grapes"]

# Print preference for each fruit
for fruit in fruits:
    print(f"I like {fruit}")
```

**Output:**
```
I like apples
I like bananas
I like oranges
I like grapes
```

**Key Concepts:**
- Loop variable name should be singular form of list name
- fruits → fruit (good naming convention)
- F-strings make formatting easy
- Each iteration, `fruit` holds the next value

---

### Question 8
**Problem:** Create a list of prices [9.99, 15.50, 7.25, 22.00]. Use a for-each loop to calculate and print the total.

**Solution Approach:**
- Initialize total to 0
- Add each price to total (accumulator pattern)
- Print final total

**Complete Solution:**
```python
# Create list of prices
prices = [9.99, 15.50, 7.25, 22.00]

# Calculate total using for-each
total = 0
for price in prices:
    total = total + price

# Display result
print(f"Prices: {prices}")
print(f"Total: ${total:.2f}")
```

**Output:**
```
Prices: [9.99, 15.5, 7.25, 22.0]
Total: $54.74
```

**Key Concepts:**
- Accumulator pattern: initialize before loop, update inside loop
- Start with 0 for sum operations
- No indices needed for simple summation
- `.2f` formats to 2 decimal places for currency

---

### Question 9
**Problem:** Make a list of temperatures [72, 68, 75, 80, 71]. Use a for-each loop to count how many are above 70.

**Solution Approach:**
- Initialize counter to 0
- Check each temperature
- Increment counter if above 70
- Display count

**Complete Solution:**
```python
# Create list of temperatures
temperatures = [72, 68, 75, 80, 71]

# Count temperatures above 70
count = 0
for temp in temperatures:
    if temp > 70:
        count = count + 1

# Display result
print(f"Temperatures: {temperatures}")
print(f"Number above 70°: {count}")
```

**Alternative with details:**
```python
temperatures = [72, 68, 75, 80, 71]

count = 0
print("Temperature analysis:")
for temp in temperatures:
    if temp > 70:
        print(f"{temp}° - Above 70 ✓")
        count += 1
    else:
        print(f"{temp}° - Not above 70")

print(f"\nTotal above 70°: {count}")
```

**Output:**
```
Temperatures: [72, 68, 75, 80, 71]
Number above 70°: 4
```

**Key Concepts:**
- Counter pattern: initialize to 0, increment when condition met
- Conditional counting using if statement
- For-each works well when you don't need positions
- 4 out of 5 temperatures are above 70

---

### Question 10
**Problem:** Create a list of words. Use a for-each loop to print each word and its length.

**Solution Approach:**
- Create list of words
- For each word, use len() to get length
- Display both word and length

**Complete Solution:**
```python
# Create list of words
words = ["python", "programming", "list", "iteration", "code"]

# Print each word with its length
print("Word lengths:")
for word in words:
    print(f"{word}: {len(word)} characters")
```

**With formatting:**
```python
words = ["python", "programming", "list", "iteration", "code"]

print("Word Analysis:")
print("-" * 30)
for word in words:
    print(f"{word:<15} {len(word)} characters")
```

**Output:**
```
Word lengths:
python: 6 characters
programming: 11 characters
list: 4 characters
iteration: 9 characters
code: 4 characters
```

**Key Concepts:**
- len() works on strings to count characters
- Can call functions on loop variable
- F-strings allow embedding function calls
- Each word is processed independently

---

## Iterating with Range (Questions 11-15)

### Question 11
**Problem:** Create a list [10, 20, 30, 40, 50]. Use a range-based loop to print each element with its index position.

**Solution Approach:**
- Use range(len(list)) to get all indices
- Access list elements using indices
- Display both index and value

**Complete Solution:**
```python
# Create list
numbers = [10, 20, 30, 40, 50]

# Print with indices using range
print("Index : Value")
print("-" * 15)
for i in range(len(numbers)):
    print(f"  {i}   :  {numbers[i]}")
```

**Output:**
```
Index : Value
---------------
  0   :  10
  1   :  20
  2   :  30
  3   :  40
  4   :  50
```

**Key Concepts:**
- range(len(numbers)) produces 0, 1, 2, 3, 4
- These are all valid indices for the list
- Use i to access: numbers[i]
- Shows both position and value

---

### Question 12
**Problem:** Make a list of 5 scores. Use range to print them in the format "Test 1: [score]" (starting from 1, not 0).

**Solution Approach:**
- Use range(len(scores)) for indices
- Display i + 1 for human-readable numbering
- Access scores using index i

**Complete Solution:**
```python
# Create list of scores
scores = [85, 92, 78, 90, 88]

# Print with test numbers starting from 1
print("Test Results:")
for i in range(len(scores)):
    print(f"Test {i + 1}: {scores[i]} points")
```

**Output:**
```
Test Results:
Test 1: 85 points
Test 2: 92 points
Test 3: 78 points
Test 4: 90 points
Test 5: 88 points
```

**Key Concepts:**
- i goes from 0 to 4
- i + 1 goes from 1 to 5 (human counting)
- People count from 1, computers from 0
- This is when range-based is useful over for-each

---

### Question 13
**Problem:** Create two lists of equal length with names and ages. Use range to print each person's info: "Name: [name], Age: [age]".

**Solution Approach:**
- Create parallel lists (same length)
- Use same index for both lists
- Range iterates through valid indices

**Complete Solution:**
```python
# Create parallel lists
names = ["Alice", "Bob", "Charlie", "Diana"]
ages = [25, 30, 22, 28]

# Print information for each person
print("People Information:")
for i in range(len(names)):
    print(f"Name: {names[i]}, Age: {ages[i]}")
```

**With validation:**
```python
names = ["Alice", "Bob", "Charlie", "Diana"]
ages = [25, 30, 22, 28]

# Verify lists are same length
if len(names) == len(ages):
    print("People Information:")
    for i in range(len(names)):
        print(f"Name: {names[i]}, Age: {ages[i]}")
else:
    print("Error: Lists have different lengths!")
```

**Output:**
```
People Information:
Name: Alice, Age: 25
Name: Bob, Age: 30
Name: Charlie, Age: 22
Name: Diana, Age: 28
```

**Key Concepts:**
- Parallel lists: same index refers to related data
- Single index accesses both lists
- This is where range shines over for-each
- Always verify lists are same length

---

### Question 14
**Problem:** Make a list [100, 200, 300, 400]. Use range to double each element in the list (modify the original list).

**Solution Approach:**
- Range-based needed to modify in place
- Access by index, modify using index
- Original list is changed

**Complete Solution:**
```python
# Create list
numbers = [100, 200, 300, 400]

print(f"Original: {numbers}")

# Double each element using range
for i in range(len(numbers)):
    numbers[i] = numbers[i] * 2

print(f"Doubled: {numbers}")
```

**With detailed tracking:**
```python
numbers = [100, 200, 300, 400]

print(f"Original: {numbers}\n")
print("Doubling process:")

for i in range(len(numbers)):
    old_value = numbers[i]
    numbers[i] = numbers[i] * 2
    print(f"Index {i}: {old_value} → {numbers[i]}")

print(f"\nFinal: {numbers}")
```

**Output:**
```
Original: [100, 200, 300, 400]
Doubled: [200, 400, 600, 800]
```

**Key Concepts:**
- Must use range to modify list in place
- For-each gives copy of value, can't modify original
- Index assignment: numbers[i] = new_value
- List is mutable, can be changed

---

### Question 15
**Problem:** Create a list of numbers. Use range to print elements at only even indices (0, 2, 4, etc.).

**Solution Approach:**
- Use range with step of 2: range(0, len(list), 2)
- This gives only even indices
- Access elements at those indices

**Complete Solution:**
```python
# Create list
numbers = [10, 15, 20, 25, 30, 35, 40, 45, 50]

print(f"Full list: {numbers}")
print("\nElements at even indices:")

# Iterate through even indices only
for i in range(0, len(numbers), 2):
    print(f"Index {i}: {numbers[i]}")
```

**Alternative checking each index:**
```python
numbers = [10, 15, 20, 25, 30, 35, 40, 45, 50]

print("Elements at even indices:")
for i in range(len(numbers)):
    if i % 2 == 0:  # Check if index is even
        print(f"Index {i}: {numbers[i]}")
```

**Output:**
```
Full list: [10, 15, 20, 25, 30, 35, 40, 45, 50]

Elements at even indices:
Index 0: 10
Index 2: 20
Index 4: 30
Index 6: 40
Index 8: 50
```

**Key Concepts:**
- range(0, len(list), 2) gives 0, 2, 4, 6, 8...
- Step parameter skips indices
- More efficient than checking each index
- Even indices: 0, 2, 4, 6... (divisible by 2)

---

## Using Enumerate (Questions 16-20)

### Question 16
**Problem:** Create a list of colors. Use enumerate to print each color with its position number (starting from 0).

**Solution Approach:**
- enumerate gives both index and value
- Clean syntax: for index, value in enumerate(list)
- Shows built-in position numbering

**Complete Solution:**
```python
# Create list of colors
colors = ["red", "blue", "green", "yellow", "purple"]

# Print with enumerate
print("Colors with positions:")
for index, color in enumerate(colors):
    print(f"Position {index}: {color}")
```

**Output:**
```
Colors with positions:
Position 0: red
Position 1: blue
Position 2: green
Position 3: yellow
Position 4: purple
```

**Key Concepts:**
- enumerate returns pairs: (index, value)
- Two variables: index, color
- Cleaner than range(len(list))
- Positions start at 0 by default

---

### Question 17
**Problem:** Make a list of scores. Use enumerate to find and print the position of the highest score.

**Solution Approach:**
- Track highest score and its position
- Use enumerate to get both values
- Update when higher score found

**Complete Solution:**
```python
# Create list of scores
scores = [85, 92, 78, 96, 88, 91]

# Find highest score and position
highest_score = scores[0]
highest_position = 0

for index, score in enumerate(scores):
    if score > highest_score:
        highest_score = score
        highest_position = index

# Display result
print(f"Scores: {scores}")
print(f"Highest score: {highest_score}")
print(f"Position: {highest_position}")
print(f"(Test #{highest_position + 1})")
```

**Output:**
```
Scores: [85, 92, 78, 96, 88, 91]
Highest score: 96
Position: 3
(Test #4)
```

**Key Concepts:**
- enumerate perfect for finding position of value
- Track both score and position
- Initialize with first element
- Show human-readable test number (position + 1)

---

### Question 18
**Problem:** Create a list of names. Use enumerate to print them as a numbered list starting from 1 (not 0).

**Solution Approach:**
- enumerate gives index starting at 0
- Add 1 to index for human-readable numbering
- Format as numbered list

**Complete Solution:**
```python
# Create list of names
names = ["Alice", "Bob", "Charlie", "Diana", "Eve"]

# Print as numbered list (1-based)
print("Student Roster:")
for index, name in enumerate(names):
    print(f"{index + 1}. {name}")
```

**Alternative with start parameter:**
```python
names = ["Alice", "Bob", "Charlie", "Diana", "Eve"]

# enumerate can start at any number!
print("Student Roster:")
for number, name in enumerate(names, start=1):
    print(f"{number}. {name}")
```

**Output:**
```
Student Roster:
1. Alice
2. Bob
3. Charlie
4. Diana
5. Eve
```

**Key Concepts:**
- Add 1 to index for 1-based numbering
- Or use enumerate(list, start=1) to start at 1
- Standard numbered list format
- index + 1 converts 0-based to 1-based

---

### Question 19
**Problem:** Make a list [5, 10, 15, 20, 25]. Use enumerate to create a new list containing only elements at odd indices.

**Solution Approach:**
- enumerate gives index and value
- Check if index is odd (index % 2 == 1)
- Add to new list if condition met

**Complete Solution:**
```python
# Create original list
numbers = [5, 10, 15, 20, 25]

# Create new list with elements at odd indices
odd_index_elements = []

for index, value in enumerate(numbers):
    if index % 2 == 1:  # Odd index
        odd_index_elements.append(value)

# Display results
print(f"Original list: {numbers}")
print(f"Elements at odd indices: {odd_index_elements}")
print(f"(Indices 1, 3)")
```

**Output:**
```
Original list: [5, 10, 15, 20, 25]
Elements at odd indices: [10, 20]
(Indices 1, 3)
```

**Key Concepts:**
- Odd indices: 1, 3, 5, 7... (index % 2 == 1)
- enumerate provides index for checking
- Build new list with filtered elements
- Indices 1 and 3 have values 10 and 20

---

### Question 20
**Problem:** Create a shopping list. Use enumerate to print each item as "Item #: [name]" and count the total items.

**Solution Approach:**
- enumerate for position and item name
- Add 1 to index for item numbering
- Count is just the length

**Complete Solution:**
```python
# Create shopping list
shopping_list = ["milk", "bread", "eggs", "cheese", "apples"]

# Print with item numbers
print("Shopping List:")
print("-" * 20)
for index, item in enumerate(shopping_list):
    print(f"Item #{index + 1}: {item}")

print("-" * 20)
print(f"Total items: {len(shopping_list)}")
```

**Output:**
```
Shopping List:
--------------------
Item #1: milk
Item #2: bread
Item #3: eggs
Item #4: cheese
Item #5: apples
--------------------
Total items: 5
```

**Key Concepts:**
- enumerate for clean numbered display
- Item numbers start at 1 (index + 1)
- Total count is len(list)
- Professional-looking list format

---

## Strings as Lists (Questions 21-25)

### Question 21
**Problem:** Ask for a word and print each character on a separate line using a for loop.

**Solution Approach:**
- Strings act like lists of characters
- Can iterate directly through characters
- Each character printed on new line

**Complete Solution:**
```python
# Get word from user
word = input("Enter a word: ")

# Print each character
print(f"\nCharacters in '{word}':")
for char in word:
    print(char)
```

**With index numbers:**
```python
word = input("Enter a word: ")

print(f"\nCharacters in '{word}':")
for index, char in enumerate(word):
    print(f"Position {index}: {char}")
```

**Sample Output:**
```
Enter a word: Python

Characters in 'Python':
P
y
t
h
o
n
```

**Key Concepts:**
- Strings are iterable like lists
- for char in word: iterates through each character
- Each character is accessed one at a time
- Can use enumerate for positions too

---

### Question 22
**Problem:** Get a word from the user and count how many vowels (a, e, i, o, u) it contains.

**Solution Approach:**
- Define vowels string
- Iterate through word characters
- Check if each character is in vowels
- Count matches

**Complete Solution:**
```python
# Get word from user
word = input("Enter a word: ").lower()

# Define vowels
vowels = "aeiou"

# Count vowels
vowel_count = 0
for char in word:
    if char in vowels:
        vowel_count += 1

# Display result
print(f"The word '{word}' has {vowel_count} vowel(s)")
```

**With details:**
```python
word = input("Enter a word: ").lower()
vowels = "aeiou"

vowel_count = 0
found_vowels = []

for char in word:
    if char in vowels:
        vowel_count += 1
        found_vowels.append(char)

print(f"Word: '{word}'")
print(f"Vowels found: {found_vowels}")
print(f"Total vowels: {vowel_count}")
```

**Sample Output:**
```
Enter a word: education

Word: 'education'
Vowels found: ['e', 'u', 'a', 'i', 'o']
Total vowels: 5
```

**Key Concepts:**
- .lower() makes checking case-insensitive
- char in vowels checks membership
- Strings can be searched like lists
- Counter pattern for accumulation

---

### Question 23
**Problem:** Take a word and print it in reverse using a for loop (don't use slicing or reverse()).

**Solution Approach:**
- Build new string character by character
- Add each character to the front (not back)
- Result is reversed word

**Complete Solution:**
```python
# Get word from user
word = input("Enter a word: ")

# Reverse using loop
reversed_word = ""
for char in word:
    reversed_word = char + reversed_word

# Display result
print(f"Original: {word}")
print(f"Reversed: {reversed_word}")
```

**With explanation:**
```python
word = input("Enter a word: ")

reversed_word = ""
print(f"\nReversing '{word}':")

for char in word:
    old_reversed = reversed_word
    reversed_word = char + reversed_word
    print(f"  '{old_reversed}' + '{char}' = '{reversed_word}'")

print(f"\nFinal: {reversed_word}")
```

**Sample Output:**
```
Enter a word: python

Original: python
Reversed: nohtyp
```

**Key Concepts:**
- char + reversed_word puts char at front
- Empty string + 'p' = 'p'
- 'p' + 'y' = 'yp'
- Continues building: 'yp' + 't' = 'typ'
- Each new character goes to front

---

### Question 24
**Problem:** Ask for a sentence and count how many words it contains (split by spaces).

**Solution Approach:**
- Use .split() to separate by spaces
- .split() returns a list of words
- Count is len() of that list

**Complete Solution:**
```python
# Get sentence from user
sentence = input("Enter a sentence: ")

# Split into words
words = sentence.split()

# Count words
word_count = len(words)

# Display result
print(f"\nSentence: '{sentence}'")
print(f"Words: {words}")
print(f"Word count: {word_count}")
```

**Sample Output:**
```
Enter a sentence: Python is an amazing programming language

Sentence: 'Python is an amazing programming language'
Words: ['Python', 'is', 'an', 'amazing', 'programming', 'language']
Word count: 6
```

**Key Concepts:**
- .split() splits string by spaces (default)
- Returns a list of words
- len() of list gives word count
- split() removes the spaces

---

### Question 25
**Problem:** Get a word from the user, convert it to a list, capitalize the first and last characters, and print the modified word.

**Solution Approach:**
- Convert string to list with list()
- Modify first element [0]
- Modify last element [-1]
- Join back to string with "".join()

**Complete Solution:**
```python
# Get word from user
word = input("Enter a word: ").lower()

# Convert to list
char_list = list(word)

print(f"Original word: {word}")
print(f"As list: {char_list}")

# Capitalize first and last characters
if len(char_list) > 0:
    char_list[0] = char_list[0].upper()
    if len(char_list) > 1:
        char_list[-1] = char_list[-1].upper()

# Convert back to string
modified_word = "".join(char_list)

print(f"Modified list: {char_list}")
print(f"Modified word: {modified_word}")
```

**Sample Output:**
```
Enter a word: python

Original word: python
As list: ['p', 'y', 't', 'h', 'o', 'n']
Modified list: ['P', 'y', 't', 'h', 'o', 'N']
Modified word: PythoN
```

**Key Concepts:**
- list(string) converts to list of characters
- Lists are mutable, strings are not
- [0] is first, [-1] is last
- "".join(list) converts list back to string
- Empty string "" means no separator between characters

---

## Summary: Key List Concepts

### Indexing Relationships
```python
my_list = [10, 20, 30, 40, 50]

# Length and indices
len(my_list)           # 5
# Valid indices: 0, 1, 2, 3, 4
# Last index: len(my_list) - 1 = 4

# Positive indexing
my_list[0]            # First: 10
my_list[4]            # Last: 50

# Negative indexing  
my_list[-1]           # Last: 50
my_list[-5]           # First: 10
```

### Iteration Methods
```python
# For-each (most common)
for item in my_list:
    print(item)

# Range-based (when index needed)
for i in range(len(my_list)):
    print(f"{i}: {my_list[i]}")

# Enumerate (index + value)
for index, item in enumerate(my_list):
    print(f"{index}: {item}")
```

### String as List
```python
word = "hello"

# Access by index
word[0]               # 'h'
word[-1]              # 'o'

# Iterate
for char in word:
    print(char)

# Convert to list (for modification)
chars = list(word)    # ['h', 'e', 'l', 'l', 'o']
chars[0] = 'H'
new_word = "".join(chars)  # "Hello"
```

### Common Patterns
```python
# Find maximum
maximum = my_list[0]
for num in my_list:
    if num > maximum:
        maximum = num

# Count occurrences
count = 0
for item in my_list:
    if item == target:
        count += 1

# Modify in place (need range)
for i in range(len(my_list)):
    my_list[i] = my_list[i] * 2

# Build new list (can use for-each)
new_list = []
for item in my_list:
    if condition:
        new_list.append(item)
```