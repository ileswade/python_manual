# Chapter 4: Input and Output - Intermediate Solutions Guide

## The `end` Parameter (Questions 1-5)

### Question 1
**Problem:** Print the numbers 1, 2, 3, 4, 5 all on the same line with spaces between them.

**Solution Approach:**
- By default, `print()` adds a newline (`\n`) at the end
- We need to change the ending to a space to stay on the same line
- Use `end=" "` for all prints except the last one

**Complete Solution:**
```python
# Print numbers on same line with spaces
print(1, end=" ")
print(2, end=" ")
print(3, end=" ")
print(4, end=" ")
print(5)  # Last one uses default newline
```

**Alternative - all in one print:**
```python
# Simpler approach using one print
print(1, 2, 3, 4, 5)
```

**Output:**
```
1 2 3 4 5
```

**Key Concepts:**
- Default: `print(1)` outputs "1\n" (with newline)
- Custom end: `print(1, end=" ")` outputs "1 " (with space)
- Last print should use default `end="\n"` to move to next line
- Alternative: Single print with multiple values automatically spaces them

---

### Question 2
**Problem:** Print "Loading" followed by three dots (...) on the same line, with no spaces between them.

**Solution Approach:**
- Print "Loading" without newline
- Print three dots, each without newline
- Need `end=""` to avoid any separation

**Complete Solution:**
```python
# Print loading message with dots on same line
print("Loading", end="")
print(".", end="")
print(".", end="")
print(".")  # Last dot uses default newline
```

**Alternative approaches:**
```python
# Method 2: Using empty string end for all
print("Loading", end="")
print("...", end="")
print()  # Move to next line

# Method 3: All in one print
print("Loading...")

# Method 4: String multiplication
print("Loading", end="")
print("." * 3)
```

**Output:**
```
Loading...
```

**Key Concepts:**
- `end=""` removes all characters between prints
- Without `end=""`, you'd get: "Loading . . ." (with spaces)
- `print()` with no arguments just prints a newline
- String multiplication: `"." * 3` creates "..."

---

### Question 3
**Problem:** Create output that shows "Hello" and "World" on the same line with a hyphen between them (Hello-World).

**Solution Approach:**
- Print "Hello" with hyphen at end
- Print "World" normally
- Use `end="-"` to add hyphen instead of newline

**Complete Solution:**
```python
# Print with hyphen between
print("Hello", end="-")
print("World")
```

**Alternative methods:**
```python
# Method 2: Using concatenation
print("Hello" + "-" + "World")

# Method 3: Using f-string
print(f"Hello-World")

# Method 4: Using sep parameter
print("Hello", "World", sep="-")
```

**Output:**
```
Hello-World
```

**Key Concepts:**
- `end="-"` replaces newline with hyphen
- Many ways to achieve same result
- `sep` parameter is cleaner when printing multiple values
- Choose method based on situation

---

### Question 4
**Problem:** Print the words "Python", "is", "awesome" on the same line with no spaces (Pythonisawesome).

**Solution Approach:**
- Need to eliminate spaces between words
- Use `end=""` to add nothing between prints
- Or use `sep=""` with single print

**Complete Solution:**
```python
# Using end parameter
print("Python", end="")
print("is", end="")
print("awesome")
```

**Better alternative using sep:**
```python
# Using sep parameter (cleaner)
print("Python", "is", "awesome", sep="")
```

**Output:**
```
Pythonisawesome
```

**Key Concepts:**
- `end=""` eliminates character after each print
- `sep=""` eliminates spaces between values in single print
- For this use case, `sep=""` is cleaner (one print vs three)
- Default `sep=" "` would give "Python is awesome"

---

### Question 5
**Problem:** Print "Question: " without a newline, then on the same line print "What is 2+2?"

**Solution Approach:**
- First print should not move to new line
- Second print continues on same line
- Use `end=""` or `end=" "` depending on spacing needs

**Complete Solution:**
```python
# Print question on same line
print("Question: ", end="")
print("What is 2+2?")
```

**Alternative with space consideration:**
```python
# If "Question:" already has space in it
print("Question:", end=" ")
print("What is 2+2?")
```

**Output:**
```
Question: What is 2+2?
```

**Key Concepts:**
- First print: `end=""` keeps cursor on same line
- Second print: uses default newline to complete the line
- Watch for spacing: "Question: " (with space) vs "Question:" (without)
- This pattern useful for prompts and labels

---

## The `sep` Parameter (Questions 6-10)

### Question 6
**Problem:** Print three words separated by commas: apple, banana, orange (output: apple,banana,orange).

**Solution Approach:**
- Use `sep` parameter to control separator
- Default `sep=" "` gives spaces
- Change to `sep=","` for commas

**Complete Solution:**
```python
# Print with comma separator
print("apple", "banana", "orange", sep=",")
```

**Output:**
```
apple,banana,orange
```

**Key Concepts:**
- `sep` parameter controls what goes between values
- Default: `sep=" "` (space)
- `sep=","` uses commas instead
- No spaces added unless you include them: `sep=", "`

**Common variations:**
```python
# With spaces after commas
print("apple", "banana", "orange", sep=", ")  # apple, banana, orange

# With other separators
print("apple", "banana", "orange", sep=" | ")  # apple | banana | orange
```

---

### Question 7
**Problem:** Print a date in the format YYYY-MM-DD using sep parameter with the values 2024, 12, 25.

**Solution Approach:**
- Have three separate values: year, month, day
- Need hyphens between them
- Use `sep="-"` to add hyphens

**Complete Solution:**
```python
# Print date in YYYY-MM-DD format
year = 2024
month = 12
day = 25

print(year, month, day, sep="-")
```

**Alternative with zero-padding:**
```python
# With proper zero-padding for month/day
year = 2024
month = 12
day = 25

# Using f-strings for zero-padding
print(f"{year}-{month:02d}-{day:02d}")
```

**Output:**
```
2024-12-25
```

**Key Concepts:**
- `sep="-"` puts hyphens between values
- For dates, this creates ISO format (YYYY-MM-DD)
- `:02d` in f-string ensures 2-digit formatting (09 vs 9)
- `sep` is simple when values don't need formatting

---

### Question 8
**Problem:** Create a phone number format (123-456-7890) using three separate numbers and the sep parameter.

**Solution Approach:**
- Have three number parts: area code, prefix, line number
- Need hyphens between parts
- Use `sep="-"` to connect them

**Complete Solution:**
```python
# Phone number components
area_code = 123
prefix = 456
line_number = 7890

# Print with hyphen separator
print(area_code, prefix, line_number, sep="-")
```

**With proper formatting:**
```python
# Ensure proper digit counts with f-strings
area_code = 123
prefix = 456
line_number = 7890

# Using f-string for formatting
print(f"{area_code:03d}-{prefix:03d}-{line_number:04d}")
```

**Output:**
```
123-456-7890
```

**Key Concepts:**
- `sep="-"` creates phone number format
- `:03d` ensures 3 digits (adds leading zeros if needed)
- `:04d` ensures 4 digits
- Useful for any segmented number format

---

### Question 9
**Problem:** Print three prices separated by pipe characters: $10.99 | $5.49 | $3.99

**Solution Approach:**
- Three price values
- Need pipe character (|) with spaces
- Use `sep=" | "` to add pipe with spaces

**Complete Solution:**
```python
# Prices with pipe separators
price1 = 10.99
price2 = 5.49
price3 = 3.99

# Print with pipe separator (includes spaces)
print(f"${price1:.2f}", f"${price2:.2f}", f"${price3:.2f}", sep=" | ")
```

**Alternative without f-strings:**
```python
# Using string concatenation for $
print("$" + str(price1), "$" + str(price2), "$" + str(price3), sep=" | ")
```

**Output:**
```
$10.99 | $5.49 | $3.99
```

**Key Concepts:**
- `sep=" | "` includes spaces around pipe
- Need to format each price with $ and decimals first
- F-strings handle $ and formatting: `f"${price:.2f}"`
- `sep` works with pre-formatted strings

---

### Question 10
**Problem:** Print a person's full name with middle initial using periods: John.Q.Public (use sep to add the periods).

**Solution Approach:**
- Three name parts: first, middle initial, last
- Need periods between them
- Use `sep="."` to add periods

**Complete Solution:**
```python
# Name components
first_name = "John"
middle_initial = "Q"
last_name = "Public"

# Print with period separator
print(first_name, middle_initial, last_name, sep=".")
```

**Output:**
```
John.Q.Public
```

**Key Concepts:**
- `sep="."` puts periods between values
- Creates dotted notation
- Simple and clean with `sep` parameter
- Alternative: concatenation `first_name + "." + middle_initial + "." + last_name`

---

## Combining `end` and `sep` (Questions 11-15)

### Question 11
**Problem:** Print "Item1", "Item2", "Item3" separated by commas on one line, followed by " -> Done" on the same line.

**Solution Approach:**
- First print: items with comma separator, stay on line
- Second print: continuation with arrow and "Done"
- Use both `sep=","` and `end=" "`

**Complete Solution:**
```python
# Print items with commas, then continue on same line
print("Item1", "Item2", "Item3", sep=", ", end=" ")
print("-> Done")
```

**Output:**
```
Item1, Item2, Item3 -> Done
```

**Key Concepts:**
- `sep=", "` puts commas and spaces between items
- `end=" "` keeps cursor on same line with space
- Second print continues on same line
- Combining both parameters gives full control

---

### Question 12
**Problem:** Create output showing "A, B, C -> " on one line, then "Next" on the same line.

**Solution Approach:**
- First print: A, B, C with commas, then arrow, stay on line
- Second print: "Next" continues on same line
- Use `sep=", "` and `end=" -> "`

**Complete Solution:**
```python
# Print letters with arrow, then continue
print("A", "B", "C", sep=", ", end=" -> ")
print("Next")
```

**Output:**
```
A, B, C -> Next
```

**Key Concepts:**
- `sep=", "` separates the letters
- `end=" -> "` adds arrow and keeps on same line
- Clean way to show progression or flow
- Both parameters work together seamlessly

---

### Question 13
**Problem:** Print a series of coordinates: (1,2) (3,4) (5,6) all on the same line using both parameters.

**Solution Approach:**
- Each coordinate is a pair in parentheses
- Need spaces between coordinate pairs
- Use both `sep` for internal commas and `end` to stay on line

**Complete Solution:**
```python
# Print coordinates on same line
print("(", 1, ",", 2, ")", sep="", end=" ")
print("(", 3, ",", 4, ")", sep="", end=" ")
print("(", 5, ",", 6, ")", sep="")
```

**Cleaner alternative:**
```python
# Using pre-formatted strings
print("(1,2)", end=" ")
print("(3,4)", end=" ")
print("(5,6)")
```

**Even cleaner with f-strings:**
```python
# Using f-strings for formatting
x1, y1 = 1, 2
x2, y2 = 3, 4
x3, y3 = 5, 6

print(f"({x1},{y1})", end=" ")
print(f"({x2},{y2})", end=" ")
print(f"({x3},{y3})")
```

**Output:**
```
(1,2) (3,4) (5,6)
```

**Key Concepts:**
- `sep=""` removes spaces in first method
- `end=" "` keeps coordinates on same line
- Pre-formatting strings is often cleaner
- Choose method based on readability

---

### Question 14
**Problem:** Create a countdown "5-4-3-2-1-GO!" all on one line using multiple print statements.

**Solution Approach:**
- Each number needs a hyphen after it
- "GO!" at the end
- Use `end="-"` for numbers, default for "GO!"

**Complete Solution:**
```python
# Countdown with hyphens
print(5, end="-")
print(4, end="-")
print(3, end="-")
print(2, end="-")
print(1, end="-")
print("GO!")
```

**Output:**
```
5-4-3-2-1-GO!
```

**Key Concepts:**
- `end="-"` adds hyphen instead of newline
- Last print uses default newline to complete line
- All prints stay on same line with custom separator
- Could also use `sep="-"` with single print

---

### Question 15
**Problem:** Print "Name: " (without newline), then print first and last name separated by a space.

**Solution Approach:**
- Label first, stay on line
- Then print names with space between
- Use `end=""` on label, default `sep` for names

**Complete Solution:**
```python
# Get names (or use predefined)
first_name = "Alice"
last_name = "Johnson"

# Print label and names on same line
print("Name: ", end="")
print(first_name, last_name)  # Default sep=" " gives space
```

**Alternative with explicit sep:**
```python
first_name = "Alice"
last_name = "Johnson"

print("Name: ", end="")
print(first_name, last_name, sep=" ")  # Explicit space
```

**Output:**
```
Name: Alice Johnson
```

**Key Concepts:**
- `end=""` keeps cursor on same line after label
- Default `sep=" "` puts space between names
- Don't need to specify `sep=" "` since it's default
- Clean way to format labeled output

---

## F-String Formatting - Decimal Places (Questions 16-20)

### Question 16
**Problem:** Ask for a decimal number and display it with 0, 1, 2, and 3 decimal places on separate lines.

**Solution Approach:**
- Get number as float
- Use `:.0f`, `:.1f`, `:.2f`, `:.3f` format specifiers
- Each shows different precision level

**Complete Solution:**
```python
# Get number from user
number = float(input("Enter a decimal number: "))

# Display with different decimal places
print(f"With 0 decimals: {number:.0f}")
print(f"With 1 decimal: {number:.1f}")
print(f"With 2 decimals: {number:.2f}")
print(f"With 3 decimals: {number:.3f}")
```

**Sample Run:**
```
Enter a decimal number: 3.14159

With 0 decimals: 3
With 1 decimal: 3.1
With 2 decimals: 3.14
With 3 decimals: 3.142
```

**Key Concepts:**
- `:.0f` rounds to integer (no decimals shown)
- `:.1f` rounds to 1 decimal place
- Each format rounds, doesn't truncate
- 3.14159 → 3.1 (not 3.14, because it rounds)
- Useful for controlling precision display

---

### Question 17
**Problem:** Calculate pi as 22/7 and display it with 2, 4, 6, and 8 decimal places.

**Solution Approach:**
- Calculate pi approximation: 22/7
- Display with increasing precision
- Use `:.Xf` where X is decimal places

**Complete Solution:**
```python
# Calculate pi approximation
pi = 22 / 7

# Display with different precisions
print(f"Pi with 2 decimals: {pi:.2f}")
print(f"Pi with 4 decimals: {pi:.4f}")
print(f"Pi with 6 decimals: {pi:.6f}")
print(f"Pi with 8 decimals: {pi:.8f}")

# Compare to actual pi
import math
print(f"\nActual pi:         {math.pi:.8f}")
print(f"22/7 approximation: {pi:.8f}")
```

**Output:**
```
Pi with 2 decimals: 3.14
Pi with 4 decimals: 3.1429
Pi with 6 decimals: 3.142857
Pi with 8 decimals: 3.14285714

Actual pi:         3.14159265
22/7 approximation: 3.14285714
```

**Key Concepts:**
- 22/7 = 3.142857... (repeating)
- More decimals show more precision
- `:.8f` shows 8 decimal places
- 22/7 is close to pi but not exact
- Format specifier controls display, not calculation

---

### Question 18
**Problem:** Get a price from the user and display it as currency with exactly 2 decimal places (always show cents).

**Solution Approach:**
- Get price as float
- Always show 2 decimal places for cents
- Add $ symbol for currency

**Complete Solution:**
```python
# Get price from user
price = float(input("Enter a price: "))

# Display as currency with 2 decimals
print(f"Price: ${price:.2f}")
```

**With better formatting:**
```python
# Get price from user
price = float(input("Enter a price: $"))

# Display as currency
print(f"\nFormatted price: ${price:.2f}")

# Show why 2 decimals matter
print(f"Without formatting: ${price}")
print(f"With formatting: ${price:.2f}")
```

**Sample Run:**
```
Enter a price: $5

Formatted price: $5.00

Without formatting: $5.0
With formatting: $5.00
```

**Key Concepts:**
- `:.2f` always shows exactly 2 decimals
- 5 becomes 5.00 (adds zeros)
- 5.5 becomes 5.50 (adds zero)
- 5.567 becomes 5.57 (rounds)
- Currency always needs 2 decimal places

---

### Question 19
**Problem:** Ask for two numbers, divide them, and show the result with 5 decimal places.

**Solution Approach:**
- Get two numbers as floats
- Perform division
- Display result with 5 decimal precision

**Complete Solution:**
```python
# Get two numbers
num1 = float(input("Enter first number: "))
num2 = float(input("Enter second number: "))

# Divide and display with 5 decimals
result = num1 / num2
print(f"{num1} ÷ {num2} = {result:.5f}")
```

**Sample Run:**
```
Enter first number: 10
Enter second number: 3

10.0 ÷ 3.0 = 3.33333
```

**Key Concepts:**
- Division often produces many decimals
- `:.5f` shows exactly 5 decimal places
- 10/3 = 3.33333... (repeating)
- Format controls display precision
- Actual calculation still done with full precision

---

### Question 20
**Problem:** Calculate 1/3 and show it with 1, 5, and 10 decimal places to demonstrate precision.

**Solution Approach:**
- Calculate 1/3 (repeating decimal)
- Show how different precision levels display it
- Demonstrate that formatting doesn't change value

**Complete Solution:**
```python
# Calculate 1/3
value = 1 / 3

# Display with different precisions
print("1/3 with different decimal places:")
print(f"1 decimal:  {value:.1f}")
print(f"5 decimals: {value:.5f}")
print(f"10 decimals: {value:.10f}")
print(f"15 decimals: {value:.15f}")

# Show that value itself hasn't changed
print(f"\nActual stored value: {value}")
```

**Output:**
```
1/3 with different decimal places:
1 decimal:  0.3
5 decimals: 0.33333
10 decimals: 0.3333333333
15 decimals: 0.333333333333333

Actual stored value: 0.3333333333333333
```

**Key Concepts:**
- 1/3 = 0.333... (infinite repeating)
- `.1f` rounds to 0.3
- `.5f` shows 0.33333
- More decimals show more precision
- Python stores ~16 digits of precision
- Format only affects display, not storage

---

## F-String Formatting - Alignment and Width (Questions 21-25)

### Question 21
**Problem:** Create a simple two-column table showing three items (names left-aligned in 15 spaces, prices right-aligned in 8 spaces).

**Solution Approach:**
- Set column widths: names = 15, prices = 8
- Use `<` for left align, `>` for right align
- Format prices with 2 decimals

**Complete Solution:**
```python
# Item data
item1 = "Apple"
price1 = 1.99

item2 = "Banana"
price2 = 0.79

item3 = "Orange Juice"
price3 = 3.49

# Print header
print(f"{'Item':<15} {'Price':>8}")
print("-" * 23)

# Print items
print(f"{item1:<15} ${price1:>7.2f}")
print(f"{item2:<15} ${price2:>7.2f}")
print(f"{item3:<15} ${price3:>7.2f}")
```

**Output:**
```
Item                 Price
-----------------------
Apple            $   1.99
Banana           $   0.79
Orange Juice     $   3.49
```

**Key Concepts:**
- `{item:<15}` - left align in 15 characters
- `${price:>7.2f}` - right align in 7 chars ($ adds 1 more = 8 total)
- Headers use same alignment and width
- `-` * 23 creates separator line (15 + 8 = 23)

---

### Question 22
**Problem:** Display three numbers right-aligned in 10-character columns with 2 decimal places each.

**Solution Approach:**
- Three numbers in separate columns
- Each column is 10 characters wide
- Right-align with 2 decimal places

**Complete Solution:**
```python
# Three numbers
num1 = 123.45
num2 = 9.8
num3 = 1234.56

# Display right-aligned in 10-char columns
print(f"{num1:>10.2f} {num2:>10.2f} {num3:>10.2f}")

# With labels
print("Number 1   Number 2   Number 3")
print("-" * 33)
print(f"{num1:>10.2f} {num2:>10.2f} {num3:>10.2f}")
```

**Output:**
```
Number 1   Number 2   Number 3
---------------------------------
    123.45       9.80    1234.56
```

**Key Concepts:**
- `{num:>10.2f}` - right align in 10 chars with 2 decimals
- Right alignment pushes numbers to the right side
- Width includes decimal point and digits
- Consistent column width creates alignment

---

### Question 23
**Problem:** Create a centered header "SALES REPORT" in 40 characters, with = signs as borders on the same line.

**Solution Approach:**
- Center text in 40 characters
- Add = signs before and after
- Use `^` for center alignment

**Complete Solution:**
```python
# Centered header with borders
print("=" * 40)
print(f"{'SALES REPORT':^40}")
print("=" * 40)
```

**Alternative with borders on same line:**
```python
# All on same line with = borders
header = "SALES REPORT"
print(f"===== {header:^30} =====")
```

**More elaborate:**
```python
# Full report header
print("=" * 50)
print(f"{'SALES REPORT':^50}")
print(f"{'Q4 2024':^50}")
print("=" * 50)
```

**Output:**
```
==================================================
                  SALES REPORT                  
==================================================
```

**Key Concepts:**
- `{text:^40}` - center in 40 characters
- `^` is center alignment operator
- Padding added equally on both sides
- Borders frame the centered text

---

### Question 24
**Problem:** Make a table showing Name (left-aligned, 12 chars), Score (right-aligned, 6 chars), and Grade (centered, 8 chars) for three students.

**Solution Approach:**
- Three columns with different alignments
- Name: `<12`, Score: `>6`, Grade: `^8`
- Create header and data rows

**Complete Solution:**
```python
# Student data
name1, score1, grade1 = "Alice", 95, "A"
name2, score2, grade2 = "Bob", 87, "B"
name3, score3, grade3 = "Charlie", 92, "A"

# Print table
print(f"{'Name':<12} {'Score':>6} {'Grade':^8}")
print("-" * 26)
print(f"{name1:<12} {score1:>6} {grade1:^8}")
print(f"{name2:<12} {score2:>6} {grade2:^8}")
print(f"{name3:<12} {score3:>6} {grade3:^8}")
```

**Output:**
```
Name           Score   Grade  
--------------------------
Alice             95     A    
Bob               87     B    
Charlie           92     A    
```

**Key Concepts:**
- `<` = left align
- `>` = right align
- `^` = center align
- Each column has its own alignment
- Total width: 12 + 6 + 8 = 26 (plus spaces)

---

### Question 25
**Problem:** Create a formatted receipt with item names left-aligned (15 chars), quantities right-aligned (5 chars), prices right-aligned with $ (10 chars including 2 decimals), and calculate totals.

**Solution Approach:**
- Three items with name, quantity, price
- Calculate line totals and grand total
- Format with proper alignment
- Add header and total line

**Complete Solution:**
```python
# Item data
item1_name = "Widget"
item1_qty = 3
item1_price = 12.99

item2_name = "Gadget"
item2_qty = 2
item2_price = 8.50

item3_name = "Doohickey"
item3_qty = 1
item3_price = 24.99

# Calculate line totals
item1_total = item1_qty * item1_price
item2_total = item2_qty * item2_price
item3_total = item3_qty * item3_price

# Calculate grand total
grand_total = item1_total + item2_total + item3_total

# Print receipt
print("=" * 45)
print(f"{'RECEIPT':^45}")
print("=" * 45)
print(f"{'Item':<15} {'Qty':>5} {'Price':>10} {'Total':>10}")
print("-" * 45)
print(f"{item1_name:<15} {item1_qty:>5} ${item1_price:>9.2f} ${item1_total:>9.2f}")
print(f"{item2_name:<15} {item2_qty:>5} ${item2_price:>9.2f} ${item2_total:>9.2f}")
print(f"{item3_name:<15} {item3_qty:>5} ${item3_price:>9.2f} ${item3_total:>9.2f}")
print("-" * 45)
print(f"{'GRAND TOTAL':<15} {' ':>5} {' ':>10} ${grand_total:>9.2f}")
print("=" * 45)
```

**Output:**
```
=============================================
                  RECEIPT                  
=============================================
Item              Qty      Price     Total
---------------------------------------------
Widget              3 $    12.99 $    38.97
Gadget              2 $     8.50 $    17.00
Doohickey           1 $    24.99 $    24.99
---------------------------------------------
GRAND TOTAL                        $    80.96
=============================================
```

**Key Concepts:**
- Multiple column alignments in one table
- `<15` for left-aligned items
- `>5` for right-aligned quantities
- `>9.2f` for right-aligned prices with 2 decimals
- `{' ':>5}` creates blank space (for alignment)
- Separator lines improve readability
- Centered header adds professional touch

---

## Summary: Key Formatting Patterns

### Parameter Reference
```python
# end parameter
print("text", end="")      # No newline
print("text", end=" ")     # Space instead of newline
print("text", end="-")     # Hyphen instead of newline

# sep parameter
print(a, b, c, sep=",")    # Comma separator
print(a, b, c, sep=" | ")  # Pipe with spaces
print(a, b, c, sep="")     # No separator

# Both combined
print(a, b, c, sep=",", end=" -> ")
```

### F-String Format Specifiers
```python
# Decimal places
{value:.2f}        # 2 decimal places
{value:.0f}        # No decimal places (rounds)

# Width and alignment
{value:10}         # 10 characters wide
{value:<10}        # Left align in 10 chars
{value:>10}        # Right align in 10 chars
{value:^10}        # Center in 10 chars

# Combined
{value:>10.2f}     # Right align, 10 chars, 2 decimals
{value:<15.3f}     # Left align, 15 chars, 3 decimals
```

### Common Patterns

**Progress indicators:**
```python
print("Loading", end="", flush=True)
for i in range(3):
    time.sleep(0.5)
    print(".", end="", flush=True)
print(" Done!")
```

**CSV output:**
```python
print("Name", "Age", "City", sep=",")
print("Alice", 25, "Calgary", sep=",")
```

**Aligned tables:**
```python
print(f"{'Name':<15} {'Value':>10}")
print(f"{name:<15} {value:>10.2f}")
```

**Receipt formatting:**
```python
print(f"{item:<20} ${price:>8.2f}")
```

These patterns form the foundation for creating professional, well-formatted output in Python!