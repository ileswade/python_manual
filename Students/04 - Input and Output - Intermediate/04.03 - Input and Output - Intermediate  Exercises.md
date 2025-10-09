# Chapter 4: Input and Output - Intermediate Practice Questions

## Example Problems with Detailed Walkthroughs

### Example 1: Creating a Progress Bar with `end` and `flush`
**Problem:** Create a simple countdown from 5 to 1 that prints all numbers on the same line with spaces between them, followed by "GO!" on the same line. Use the `end` parameter to keep everything on one line.

**Detailed Solution:**

**Step 1: Understand the requirements**
- Print numbers 5, 4, 3, 2, 1 on the same line
- Add spaces between numbers
- End with "GO!" on the same line
- By default, `print()` adds a newline - we need to change this

**Step 2: Understand the `end` parameter**
- Default: `print()` adds `\n` (newline) at the end
- We can change it to anything: `end=" "` adds a space
- `end=""` adds nothing

**Step 3: Plan the approach**
```python
print(5, end=" ")  # Prints "5 " and stays on same line
print(4, end=" ")  # Prints "4 " on same line
# ... and so on
```

**Step 4: Use a loop pattern (simulated without loops)**
Since we haven't learned loops yet, we'll write each print statement:

```python
print(5, end=" ")
print(4, end=" ")
print(3, end=" ")
print(2, end=" ")
print(1, end=" ")
print("GO!")  # This one uses default newline to end the line
```

**Step 5: Add visual enhancement**
```python
print("Countdown: ", end="")
print(5, end=" ")
print(4, end=" ")
print(3, end=" ")
print(2, end=" ")
print(1, end=" ")
print("GO!")
```

**Complete Solution:**
```python
# Countdown program using end parameter
print("Countdown: ", end="")
print(5, end=" ")
print(4, end=" ")
print(3, end=" ")
print(2, end=" ")
print(1, end=" ")
print("GO!")
```

**Output:**
```
Countdown: 5 4 3 2 1 GO!
```

**With flush for real-time display:**
```python
import time

print("Countdown: ", end="", flush=True)
time.sleep(0.5)
print(5, end=" ", flush=True)
time.sleep(0.5)
print(4, end=" ", flush=True)
time.sleep(0.5)
print(3, end=" ", flush=True)
time.sleep(0.5)
print(2, end=" ", flush=True)
time.sleep(0.5)
print(1, end=" ", flush=True)
time.sleep(0.5)
print("GO!")
```

**Key Concepts:**
- `end=" "` changes the ending from newline to space
- Without changing `end`, each number would be on its own line
- `flush=True` forces immediate output (important with delays)
- The last print uses default `end="\n"` to move to next line
- This technique is useful for progress indicators

**Why this works:**
- Default: `print("Hi")` → "Hi\n" (newline added)
- With end: `print("Hi", end=" ")` → "Hi " (space added)
- Multiple prints with custom `end` stay on same line

---

### Example 2: Creating Aligned Tables with F-String Formatting
**Problem:** Create a price list for three items with proper column alignment. Each item has a name, price, and quantity. Use f-string formatting to align the columns so prices align on the right and names align on the left. Show the total at the bottom.

**Detailed Solution:**

**Step 1: Understand the formatting needs**
- Names should left-align (like "Apple     ")
- Prices should right-align (like "   $1.99")
- Need consistent column widths for alignment
- Want 2 decimal places for prices

**Step 2: Review f-string alignment syntax**
- `{value:<10}` - Left align in 10 spaces
- `{value:>10}` - Right align in 10 spaces
- `{value:^10}` - Center in 10 spaces
- `{value:.2f}` - 2 decimal places
- Can combine: `{value:>10.2f}` - Right align with 2 decimals

**Step 3: Plan the table structure**
```
Item         Price    Qty    Total
--------------------------------
Apple        $1.99     12    $23.88
```

**Step 4: Determine column widths**
- Item name: 12 characters (left aligned)
- Price: 8 characters (right aligned, includes $)
- Quantity: 5 characters (right aligned)
- Line total: 10 characters (right aligned)

**Step 5: Create the header**
```python
print(f"{'Item':<12} {'Price':>8} {'Qty':>5} {'Total':>10}")
print("-" * 45)
```

**Step 6: Create data rows with calculations**
```python
# Item 1
name1 = "Apple"
price1 = 1.99
qty1 = 12
total1 = price1 * qty1

print(f"{name1:<12} ${price1:>7.2f} {qty1:>5} ${total1:>9.2f}")
```

**Complete Solution:**
```python
# Store item information
item1_name = "Apple"
item1_price = 1.99
item1_qty = 12

item2_name = "Banana"
item2_price = 0.79
item2_qty = 20

item3_name = "Orange"
item3_price = 2.49
item3_qty = 8

# Calculate line totals
item1_total = item1_price * item1_qty
item2_total = item2_price * item2_qty
item3_total = item3_price * item3_qty

# Calculate grand total
grand_total = item1_total + item2_total + item3_total

# Print table header
print(f"{'Item':<12} {'Price':>8} {'Qty':>5} {'Total':>10}")
print("-" * 45)

# Print items
print(f"{item1_name:<12} ${item1_price:>7.2f} {item1_qty:>5} ${item1_total:>9.2f}")
print(f"{item2_name:<12} ${item2_price:>7.2f} {item2_qty:>5} ${item2_total:>9.2f}")
print(f"{item3_name:<12} ${item3_price:>7.2f} {item3_qty:>5} ${item3_total:>9.2f}")

# Print total
print("-" * 45)
print(f"{'GRAND TOTAL':<12} {' ':>8} {' ':>5} ${grand_total:>9.2f}")
```

**Output:**
```
Item            Price   Qty      Total
---------------------------------------------
Apple           $1.99    12     $23.88
Banana          $0.79    20     $15.80
Orange          $2.49     8     $19.92
---------------------------------------------
GRAND TOTAL                     $59.60
```

**Key Concepts:**
- `<` = left align, `>` = right align, `^` = center
- Number after colon is width: `{value:10}`
- Combine alignment and decimals: `{value:>10.2f}`
- Width includes the decimal point and digits
- Empty strings for spacing: `{' ':>5}` creates 5 spaces

**Format breakdown:**
- `{item1_name:<12}` - Left align name in 12 chars
- `${item1_price:>7.2f}` - Right align price in 7 chars (+ $ makes 8)
- `{item1_qty:>5}` - Right align quantity in 5 chars
- `${item1_total:>9.2f}` - Right align total in 9 chars (+ $ makes 10)

---

### Example 3: Using `sep` Parameter for CSV Output
**Problem:** Create a program that asks for student information (name, student ID, grade) and outputs it in CSV format (comma-separated values). Then show how to change the separator to create pipe-delimited (|) and tab-delimited output for comparison.

**Detailed Solution:**

**Step 1: Understand CSV format**
- CSV = Comma-Separated Values
- Format: `Name,ID,Grade`
- No spaces after commas (usually)
- Used for spreadsheet data

**Step 2: Understand the `sep` parameter**
- Default: `print(a, b, c)` uses spaces between values
- `sep=","` changes separator to comma
- `sep="|"` uses pipe character
- `sep="\t"` uses tab character

**Step 3: Get user input**
```python
name = input("Enter student name: ")
student_id = input("Enter student ID: ")
grade = input("Enter grade: ")
```

**Step 4: Output in different formats**

**CSV format (commas):**
```python
print(name, student_id, grade, sep=",")
```

**Pipe-delimited format:**
```python
print(name, student_id, grade, sep="|")
```

**Tab-delimited format:**
```python
print(name, student_id, grade, sep="\t")
```

**Complete Solution:**
```python
# Get student information
print("=== Student Data Entry ===")
name = input("Enter student name: ")
student_id = input("Enter student ID: ")
grade = input("Enter grade: ")

# Display in different formats
print("\n=== CSV Format (Comma-Separated) ===")
print("Name,ID,Grade")  # Header
print(name, student_id, grade, sep=",")

print("\n=== Pipe-Delimited Format ===")
print("Name|ID|Grade")  # Header
print(name, student_id, grade, sep="|")

print("\n=== Tab-Delimited Format ===")
print("Name\tID\tGrade")  # Header
print(name, student_id, grade, sep="\t")

print("\n=== Default Format (Spaces) ===")
print("Name ID Grade")  # Header
print(name, student_id, grade)  # Uses default sep=" "
```

**Sample Run:**
```
=== Student Data Entry ===
Enter student name: Alice Johnson
Enter student ID: 12345
Enter grade: A

=== CSV Format (Comma-Separated) ===
Name,ID,Grade
Alice Johnson,12345,A

=== Pipe-Delimited Format ===
Name|ID|Grade
Alice Johnson|12345|A

=== Tab-Delimited Format ===
Name	ID	Grade
Alice Johnson	12345	A

=== Default Format (Spaces) ===
Name ID Grade
Alice Johnson 12345 A
```

**Multiple students example:**
```python
# Get information for three students
print("=== Enter Data for 3 Students ===\n")

print("Student 1:")
name1 = input("Name: ")
id1 = input("ID: ")
grade1 = input("Grade: ")

print("\nStudent 2:")
name2 = input("Name: ")
id2 = input("ID: ")
grade2 = input("Grade: ")

print("\nStudent 3:")
name3 = input("Name: ")
id3 = input("ID: ")
grade3 = input("Grade: ")

# Output as CSV
print("\n=== CSV Export ===")
print("Name,StudentID,Grade")
print(name1, id1, grade1, sep=",")
print(name2, id2, grade2, sep=",")
print(name3, id3, grade3, sep=",")
```

**Key Concepts:**
- `sep` parameter controls what goes between values
- Default `sep=" "` (space)
- CSV uses `sep=","`
- Pipe-delimited uses `sep="|"`
- Tab-delimited uses `sep="\t"`
- Headers should use same separator
- Useful for exporting data to spreadsheets

**Practical applications:**
- Exporting to Excel/Google Sheets
- Creating data files
- Database imports
- Log files
- Data interchange between programs

---

## Practice Questions (25 Questions - Increasing Complexity)

### The `end` Parameter (Questions 1-5)

1. Print the numbers 1, 2, 3, 4, 5 all on the same line with spaces between them.

2. Print "Loading" followed by three dots (...) on the same line, with no spaces between them.

3. Create output that shows "Hello" and "World" on the same line with a hyphen between them (Hello-World).

4. Print the words "Python", "is", "awesome" on the same line with no spaces (Pythonisawesome).

5. Print "Question: " without a newline, then on the same line print "What is 2+2?"

### The `sep` Parameter (Questions 6-10)

6. Print three words separated by commas: apple, banana, orange (output: apple,banana,orange).

7. Print a date in the format YYYY-MM-DD using sep parameter with the values 2024, 12, 25.

8. Create a phone number format (123-456-7890) using three separate numbers and the sep parameter.

9. Print three prices separated by pipe characters: $10.99 | $5.49 | $3.99

10. Print a person's full name with middle initial using periods: John.Q.Public (use sep to add the periods).

### Combining `end` and `sep` (Questions 11-15)

11. Print "Item1", "Item2", "Item3" separated by commas on one line, followed by " -> Done" on the same line.

12. Create output showing "A, B, C -> " on one line, then "Next" on the same line.

13. Print a series of coordinates: (1,2) (3,4) (5,6) all on the same line using both parameters.

14. Create a countdown "5-4-3-2-1-GO!" all on one line using multiple print statements.

15. Print "Name: " (without newline), then print first and last name separated by a space.

### F-String Formatting - Decimal Places (Questions 16-20)

16. Ask for a decimal number and display it with 0, 1, 2, and 3 decimal places on separate lines.

17. Calculate pi as 22/7 and display it with 2, 4, 6, and 8 decimal places.

18. Get a price from the user and display it as currency with exactly 2 decimal places (always show cents).

19. Ask for two numbers, divide them, and show the result with 5 decimal places.

20. Calculate 1/3 and show it with 1, 5, and 10 decimal places to demonstrate precision.

### F-String Formatting - Alignment and Width (Questions 21-25)

21. Create a simple two-column table showing three items (names left-aligned in 15 spaces, prices right-aligned in 8 spaces).

22. Display three numbers right-aligned in 10-character columns with 2 decimal places each.

23. Create a centered header "SALES REPORT" in 40 characters, with = signs as borders on the same line.

24. Make a table showing Name (left-aligned, 12 chars), Score (right-aligned, 6 chars), and Grade (centered, 8 chars) for three students.

25. Create a formatted receipt with item names left-aligned (15 chars), quantities right-aligned (5 chars), prices right-aligned with $ (10 chars including 2 decimals), and calculate totals.

---

## Tips for Solving These Problems

### Understanding `end` Parameter
1. **Default behavior**: `print()` adds `\n` (newline) at end
2. **Change with end**: `print("Hi", end=" ")` adds space instead
3. **No addition**: `print("Hi", end="")` adds nothing
4. **Stay on same line**: Use `end=""` or `end=" "` to continue on same line
5. **Final print**: Last print usually uses default `end="\n"` to move to next line

### Understanding `sep` Parameter
1. **Default behavior**: `print(a, b, c)` separates with spaces
2. **Change separator**: `print(a, b, c, sep=",")` uses commas
3. **Common separators**: 
   - CSV: `sep=","`
   - Pipe: `sep="|"`
   - Tab: `sep="\t"`
   - None: `sep=""`
4. **Not for concatenation**: Only works with multiple print arguments

### F-String Formatting Syntax
1. **Decimal places**: `{value:.2f}` - 2 decimal places
2. **Width**: `{value:10}` - use 10 characters
3. **Alignment**: 
   - Left: `{value:<10}`
   - Right: `{value:>10}`
   - Center: `{value:^10}`
4. **Combine**: `{value:>10.2f}` - right-align, 10 chars, 2 decimals
5. **Width includes decimals**: `{value:8.2f}` means 8 total chars (including decimal point)

### Common Patterns
1. **Progress indicators**: Use `end=""` or `end=" "` with `flush=True`
2. **CSV output**: Use `sep=","` for comma-separated values
3. **Aligned tables**: Use width and alignment: `{name:<15} {price:>8.2f}`
4. **Money formatting**: Always use `:.2f` for currency
5. **Headers and data**: Use same formatting for consistent alignment

### Problem-Solving Strategy
1. **Read carefully**: What's the exact output format required?
2. **Identify**: Do I need `end`, `sep`, or f-string formatting?
3. **Plan layout**: For tables, decide column widths first
4. **Test incrementally**: Print one piece at a time
5. **Refine formatting**: Adjust widths and alignment as needed

### Debugging Tips
1. **Check alignment**: Is width big enough for your data?
2. **Count characters**: Include decimal point in width calculation
3. **Test with different inputs**: Try long names, large numbers
4. **Use print with end**: Add `|` marks to see spacing: `print("Hi", end="|")`
5. **One step at a time**: Build complex formatting gradually