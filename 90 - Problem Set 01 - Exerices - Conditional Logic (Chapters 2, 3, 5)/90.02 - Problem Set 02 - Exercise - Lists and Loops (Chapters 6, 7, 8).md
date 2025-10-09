# Introduction to Python Programming
## Problem Set 02 - Exercise - Lists and Loops

### Instructions

These 25 problems progressively test your understanding of lists, loops, slicing, and advanced list operations from Chapters 6 and 7. They start simple and become increasingly challenging.

**How to use this problem set:**
- Work through them in order - difficulty increases gradually
- Try each problem independently before looking at hints or solutions
- Test your code with different inputs
- Don't expect to solve all 25 - problems 20-25 are intentionally very challenging
- Where you get stuck shows you what to practice more!

---

## Level 1: Basic List Operations (Problems 1-5)

### Problem 1: Create and Print
Create a list containing the names of 5 fruits. Print each fruit on a separate line using a for loop.

### Problem 2: List Access
Create a list of 7 numbers. Print:
- The first number
- The last number
- The middle number (index 3)

### Problem 3: Sum of Numbers
Create a list of 5 numbers. Calculate and print their sum using a for loop.

### Problem 4: Count Items
Create a list with the values: `[3, 7, 3, 9, 3, 5, 3]`
Count how many times the number 3 appears (use a for loop, not count()).

### Problem 5: Find Maximum
Create a list of numbers. Use a for loop to find and print the largest number (don't use max()).

---

## Level 2: List Modification (Problems 6-10)

### Problem 6: Build a List
Start with an empty list. Ask the user to enter 5 numbers, adding each to the list. Print the final list.

### Problem 7: Double the Values
Create a list of 5 numbers. Create a new list where each number is doubled. Print both lists.

### Problem 8: Replace Values
Create a list: `["apple", "banana", "cherry", "date"]`
Replace "banana" with "blueberry". Print the modified list.

### Problem 9: Remove Negatives
Create a list: `[5, -2, 8, -7, 3, -1, 9]`
Create a new list containing only the positive numbers. Print the new list.

### Problem 10: Reverse Order
Create a list of 6 items. Print the list in reverse order using a for loop (don't use reverse() or [::-1]).

---

## Level 3: Slicing and Searching (Problems 11-15)

### Problem 11: First and Last Three
Create a list of 10 numbers. Use slicing to:
- Print the first 3 numbers
- Print the last 3 numbers

### Problem 12: Every Other Item
Create a list of 10 items. Use slicing to print every other item (indices 0, 2, 4, 6, 8).

### Problem 13: Middle Section
Create a list of 12 items. Use slicing to extract and print the middle 6 items (indices 3-8).

### Problem 14: Search and Report
Create a list: `["apple", "banana", "cherry", "date", "elderberry"]`
Ask the user for a fruit name. If it's in the list, print its position. If not, print "Not found."

### Problem 15: Split List
Create a list of 10 numbers. Split it into two equal lists (first 5 and last 5) using slicing. Print both.

---

## Level 4: Advanced List Operations (Problems 16-20)

### Problem 16: Remove Duplicates
Create a list: `[1, 2, 3, 2, 4, 1, 5, 3, 6]`
Create a new list with duplicates removed (maintain original order). Print the result.

### Problem 17: List Statistics
Create a list of test scores. Calculate and print:
- Average score
- Highest score
- Lowest score
- Number of scores above average

### Problem 18: Merge and Sort
Create two lists of numbers. Merge them into one list, sort it, and print the result.

### Problem 19: Shopping List Manager
Create an empty shopping list. Create a menu system that allows users to:
- Add an item
- Remove an item
- View the list
- Quit

Use a while loop for the menu.

### Problem 20: Word Reverser
Ask the user for a sentence. Create a new sentence where each word is reversed (but word order stays the same).
Example: "Hello World" becomes "olleH dlroW"

---

## Level 5: Complex Operations (Problems 21-23)

### Problem 21: Grade Distribution
Create a list of numeric grades (0-100). Count and print how many grades fall into each category:
- A: 90-100
- B: 80-89
- C: 70-79
- D: 60-69
- F: Below 60

### Problem 22: Two-List Comparison
Create two lists of names. Find and print:
- Names that appear in both lists
- Names only in the first list
- Names only in the second list

### Problem 23: Matrix Operations
Create a list containing 3 lists (a 3x3 matrix):
```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```
Calculate and print:
- Sum of all numbers
- Sum of each row
- Sum of each column

---

## Level 6: Advanced Challenges (Problems 24-25)

### Problem 24: List Rotation
Create a list of items. Ask the user how many positions to rotate the list to the right.
Example: `[1, 2, 3, 4, 5]` rotated 2 positions becomes `[4, 5, 1, 2, 3]`

Hint: Use slicing!

### Problem 25: Contact Manager with Nested Lists
Create a contact management system where each contact is stored as a list: `[name, phone, email]`

Your program should:
- Start with an empty contacts list
- Provide a menu to:
  - Add a new contact (ask for name, phone, email)
  - Search for a contact by name (print all their info)
  - List all contacts (print nicely formatted)
  - Delete a contact by name
  - Update a contact's phone or email
  - Quit

Use nested lists to store contacts, and use loops to search/display them.

Example structure:
```python
contacts = [
    ["Alice", "555-1234", "alice@email.com"],
    ["Bob", "555-5678", "bob@email.com"]
]
```

---

## Reflection

After completing these problems (or getting as far as you can):

1. **Which problem was your first real challenge?** This identifies your current skill level.

2. **What concepts did you struggle with?**
   - Basic list access and iteration?
   - Slicing syntax?
   - Building lists dynamically?
   - Nested loops with lists?
   - Lists within lists?

3. **What patterns did you notice?**
   - When to use for-each vs range-based loops?
   - When slicing is better than loops?
   - How to avoid index errors?
   - When to create new lists vs modify existing ones?

4. **Which problems required multiple attempts?**
   - Understanding the problem?
   - Translating the logic to code?
   - Debugging errors?
   - Handling edge cases?

### Problem Difficulty Breakdown

- **Problems 1-5:** Basic list creation, access, and simple loops
- **Problems 6-10:** Modifying lists, building lists, basic algorithms
- **Problems 11-15:** Slicing, searching, list manipulation
- **Problems 16-20:** Advanced operations, menu systems, string/list combinations
- **Problems 21-23:** Complex logic, nested lists, multiple operations
- **Problems 24-25:** Challenge problems requiring multiple concepts combined

**Remember:** Problems 20-25 are intentionally difficult. If you can solve problems 1-15 confidently, you have a solid foundation. Problems 16-19 show strong understanding. Problems 20-25 indicate advanced skill.

**Getting stuck is part of learning!** Use where you struggle as a guide for what to review and practice more.

---

## Testing Tips

1. **Start small:** Test with simple inputs first
2. **Check boundaries:** What happens with empty lists? Single items?
3. **Verify indices:** Are you accessing valid indices?
4. **Print intermediate values:** Use print() to see what's happening
5. **Test edge cases:** What if the user enters unexpected input?

---

## Common Mistakes to Watch For

- **Index errors:** Accessing indices that don't exist
- **Off-by-one errors:** Especially with slicing and range()
- **Modifying while iterating:** Can cause unexpected behavior
- **Reference vs copy:** Remember list_b = list_a creates a reference!
- **Forgetting to return/store results:** When creating new lists
