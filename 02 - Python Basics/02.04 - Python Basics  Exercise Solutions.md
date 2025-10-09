# Chapter 2: Python Basics - Solutions Guide

## Variables and Data Types (Questions 1-5)

### Question 1
**Problem:** Create a variable called `my_age` and assign it your age. Print the variable and its type.

**Solution Approach:**
- Choose an appropriate data type (integer for whole number age)
- Use snake_case naming convention
- Use `print()` to display the value
- Use `type()` to check the data type

**Complete Solution:**
```python
# Create the variable
my_age = 25

# Print the value
print(my_age)

# Print the type
print(type(my_age))
```

**Output:**
```
25
<class 'int'>
```

**Key Concepts:**
- Variable naming follows snake_case convention
- Age is typically stored as an integer
- `type()` returns the data type of any variable

---

### Question 2
**Problem:** Create three variables: `item_name` (string), `item_price` (float), and `in_stock` (boolean). Print all three.

**Solution Approach:**
- Identify the correct data type for each variable
- String uses quotes, float has decimal, boolean is True/False
- Print each variable to verify

**Complete Solution:**
```python
# Create variables with appropriate types
item_name = "Laptop"          # String (text)
item_price = 899.99           # Float (decimal number)
in_stock = True               # Boolean (True/False)

# Print all variables
print(item_name)
print(item_price)
print(in_stock)
```

**Output:**
```
Laptop
899.99
True
```

**Key Concepts:**
- Strings need quotes (single or double)
- Floats contain decimal points
- Booleans must be capitalized: `True` or `False`
- Each variable stores a different type of data

---

### Question 3
**Problem:** Create a variable `x` with value 10. Change it to 20, then to "twenty". Print it after each change along with its type.

**Solution Approach:**
- Start with integer value
- Reassign to new integer value
- Reassign to string value
- Print value and type after each change

**Complete Solution:**
```python
# Initial value (integer)
x = 10
print(f"Value: {x}, Type: {type(x)}")

# Change to different integer
x = 20
print(f"Value: {x}, Type: {type(x)}")

# Change to string
x = "twenty"
print(f"Value: {x}, Type: {type(x)}")
```

**Output:**
```
Value: 10, Type: <class 'int'>
Value: 20, Type: <class 'int'>
Value: twenty, Type: <class 'str'>
```

**Key Concepts:**
- Python uses **dynamic typing** - variables can change type
- Same variable can hold different types at different times
- Reassignment completely replaces the previous value

---

### Question 4
**Problem:** Create a constant `MAX_SPEED` with value 120. Try to write it in the correct Python convention.

**Solution Approach:**
- Constants use ALL_CAPS naming convention
- Underscores separate words
- Note: Python doesn't enforce constants (they can be changed), but convention signals intent

**Complete Solution:**
```python
# Create a constant using ALL_CAPS convention
MAX_SPEED = 120

# Print the constant
print(f"Maximum speed: {MAX_SPEED}")
print(f"Type: {type(MAX_SPEED)}")
```

**Output:**
```
Maximum speed: 120
Type: <class 'int'>
```

**Key Concepts:**
- Constants use UPPERCASE_WITH_UNDERSCORES convention
- This signals to other programmers: "Don't change this value"
- Python doesn't prevent changes, but convention matters
- Examples: `PI = 3.14159`, `TAX_RATE = 0.05`, `MAX_ATTEMPTS = 3`

---

### Question 5
**Problem:** Create variables using both good and bad naming conventions. Identify which ones follow Python's snake_case convention correctly.

**Solution Approach:**
- Create examples of correct snake_case
- Create examples of incorrect conventions (camelCase, PascalCase, etc.)
- Explain why each is correct or incorrect

**Complete Solution:**
```python
# GOOD: Correct snake_case convention
student_name = "Alice"
total_price = 99.99
is_logged_in = True
user_age = 25

# BAD: Wrong conventions
studentName = "Bob"      # camelCase (used in JavaScript/Java)
StudentName = "Charlie"  # PascalCase (used for classes)
student-name = "David"   # Hyphens (causes syntax error!)
StudentNAME = "Eve"      # Mixed case (inconsistent)
s = "Frank"              # Too vague (not descriptive)

# Print the good examples
print("Good conventions (snake_case):")
print(f"student_name: {student_name}")
print(f"total_price: {total_price}")
print(f"is_logged_in: {is_logged_in}")
print(f"user_age: {user_age}")
```

**Output:**
```
Good conventions (snake_case):
student_name: Alice
total_price: 99.99
is_logged_in: True
user_age: 25
```

**Key Concepts:**
- **Correct:** `student_name`, `total_price`, `is_logged_in` (snake_case)
- **Wrong:** `studentName` (camelCase), `StudentName` (PascalCase)
- **Error:** `student-name` (hyphens cause syntax errors)
- **Bad Practice:** `s` (not descriptive enough)

---

## Type Checking and Conversion (Questions 6-10)

### Question 6
**Problem:** Create a variable with value `"123"`. Check its type, convert it to an integer, then check the type again.

**Solution Approach:**
- Create string variable
- Use `type()` to check initial type
- Use `int()` to convert
- Check type again to confirm conversion

**Complete Solution:**
```python
# Create string variable
number_string = "123"

# Check initial type
print(f"Value: {number_string}")
print(f"Type: {type(number_string)}")

# Convert to integer
number_int = int(number_string)

# Check new type
print(f"\nAfter conversion:")
print(f"Value: {number_int}")
print(f"Type: {type(number_int)}")
```

**Output:**
```
Value: 123
Type: <class 'str'>

After conversion:
Value: 123
Type: <class 'int'>
```

**Key Concepts:**
- Strings can contain numbers but are still text
- `int()` converts string to integer
- The value looks the same, but the type changes
- Now we can do math with it!

---

### Question 7
**Problem:** What happens when you try to convert `"12.5"` directly to an integer? Try it and explain the error.

**Solution Approach:**
- Attempt the conversion
- Observe the error message
- Explain why it fails

**Complete Solution:**
```python
# This will cause an error!
decimal_string = "12.5"

try:
    result = int(decimal_string)
    print(result)
except ValueError as e:
    print(f"Error occurred: {e}")
    print("\nExplanation:")
    print("int() cannot convert a string with a decimal point directly.")
    print("The string '12.5' contains a decimal, so int() doesn't know what to do.")
    print("You must convert to float first, then to int.")
```

**Output:**
```
Error occurred: invalid literal for int() with base 10: '12.5'

Explanation:
int() cannot convert a string with a decimal point directly.
The string '12.5' contains a decimal, so int() doesn't know what to do.
You must convert to float first, then to int.
```

**Key Concepts:**
- `int()` expects whole number strings like "12" or "100"
- Decimal strings like "12.5" cause a `ValueError`
- Python can't guess whether you want 12 or 13
- Solution: convert to float first, then to int

---

### Question 8
**Problem:** Convert `"12.5"` to a float first, then to an integer. What value do you get and why?

**Solution Approach:**
- Convert string to float (works because string contains valid decimal)
- Convert float to integer (loses decimal part)
- Explain the lossy conversion

**Complete Solution:**
```python
# Start with decimal string
decimal_string = "12.5"
print(f"Original string: {decimal_string} (type: {type(decimal_string)})")

# Step 1: Convert to float
as_float = float(decimal_string)
print(f"As float: {as_float} (type: {type(as_float)})")

# Step 2: Convert to int
as_int = int(as_float)
print(f"As int: {as_int} (type: {type(as_int)})")

print("\nExplanation:")
print("When converting float to int, Python TRUNCATES (cuts off) the decimal.")
print("It does NOT round. 12.5 becomes 12, not 13.")
print("The .5 is permanently lost - this is a LOSSY conversion.")
```

**Output:**
```
Original string: 12.5 (type: <class 'str'>)
As float: 12.5 (type: <class 'float'>)
As int: 12 (type: <class 'int'>)

Explanation:
When converting float to int, Python TRUNCATES (cuts off) the decimal.
It does NOT round. 12.5 becomes 12, not 13.
The .5 is permanently lost - this is a LOSSY conversion.
```

**Key Concepts:**
- Two-step conversion: string → float → int
- `int()` truncates (cuts off) decimals, doesn't round
- 12.5 becomes 12, 12.9 becomes 12, 12.1 becomes 12
- Data is permanently lost (lossy conversion)

---

### Question 9
**Problem:** Create a float `7.9` and convert it to an integer. Is this a lossy conversion? Why or why not?

**Solution Approach:**
- Create float variable
- Convert to integer
- Compare values before and after
- Explain what data was lost

**Complete Solution:**
```python
# Create float
original_float = 7.9
print(f"Original float: {original_float}")

# Convert to integer
converted_int = int(original_float)
print(f"Converted to int: {converted_int}")

# Check if data was lost
print(f"\nIs this lossy? YES!")
print(f"We lost the decimal part: .9")
print(f"Original had: {original_float}")
print(f"After conversion: {converted_int}")
print(f"Lost value: {original_float - converted_int}")
```

**Output:**
```
Original float: 7.9
Converted to int: 7

Is this lossy? YES!
We lost the decimal part: .9
Original had: 7.9
After conversion: 7
Lost value: 0.8999999999999999
```

**Key Concepts:**
- **YES, this is lossy!** The .9 is permanently lost
- float → int conversion ALWAYS loses decimal precision
- This is called "truncation" - cutting off the decimal
- Once converted, you can't get the .9 back
- Any float → int conversion is lossy unless the float is a whole number (like 7.0)

---

### Question 10
**Problem:** Take the integer `100`, convert it to a float, then to a string. Print the result and all intermediate types.

**Solution Approach:**
- Start with integer
- Convert to float (adds .0)
- Convert to string
- Show type after each conversion

**Complete Solution:**
```python
# Start with integer
original = 100
print(f"Step 1 - Original: {original}, Type: {type(original)}")

# Convert to float
as_float = float(original)
print(f"Step 2 - As float: {as_float}, Type: {type(as_float)}")

# Convert to string
as_string = str(as_float)
print(f"Step 3 - As string: {as_string}, Type: {type(as_string)}")

print("\nConversion chain: int → float → string")
print("100 → 100.0 → '100.0'")
print("Notice: The float adds '.0' and the string preserves it as text")
```

**Output:**
```
Step 1 - Original: 100, Type: <class 'int'>
Step 2 - As float: 100.0, Type: <class 'float'>
Step 3 - As string: '100.0', Type: <class 'str'>

Conversion chain: int → float → string
100 → 100.0 → '100.0'
Notice: The float adds '.0' and the string preserves it as text
```

**Key Concepts:**
- int → float: Adds decimal point (100 becomes 100.0)
- float → string: Preserves the decimal in text form
- Final result is "100.0" as a string
- These conversions are NOT lossy (no data lost)
- We can see the type change at each step

---

## Basic Math Operations (Questions 11-15)

### Question 11
**Problem:** Calculate `23 + 45` and store it in a variable. Then calculate `23 - 45`. Compare the results.

**Solution Approach:**
- Perform addition and store result
- Perform subtraction and store result
- Display both results
- Compare and explain the difference

**Complete Solution:**
```python
# Addition
sum_result = 23 + 45
print(f"23 + 45 = {sum_result}")

# Subtraction
diff_result = 23 - 45
print(f"23 - 45 = {diff_result}")

# Comparison
print(f"\nComparison:")
print(f"Sum: {sum_result}")
print(f"Difference: {diff_result}")
print(f"The sum is positive ({sum_result})")
print(f"The difference is negative ({diff_result})")
print(f"They differ by: {sum_result - diff_result}")
```

**Output:**
```
23 + 45 = 68
23 - 45 = -22

Comparison:
Sum: 68
Difference: -22
The sum is positive (68)
The difference is negative (-22)
They differ by: 90
```

**Key Concepts:**
- Addition combines values
- Subtraction finds the difference
- Results can be positive or negative
- When subtracting a larger number from smaller, result is negative
- Both operations work with any numeric types

---

### Question 12
**Problem:** What is `17 / 5`? What is `17 // 5`? What is `17 % 5`? Explain the difference between these three operations.

**Solution Approach:**
- Perform all three division operations
- Show the results
- Explain what each operator does

**Complete Solution:**
```python
# Three different division operations
regular_division = 17 / 5
floor_division = 17 // 5
modulus = 17 % 5

print("Three types of division with 17 and 5:")
print(f"17 / 5  = {regular_division}  (Regular division - gives decimal)")
print(f"17 // 5 = {floor_division}      (Floor division - rounds down to integer)")
print(f"17 % 5  = {modulus}      (Modulus - gives remainder)")

print("\nExplanation:")
print("/ (division)        → How many times with decimals")
print("// (floor division) → How many times (whole number, rounded down)")
print("% (modulus)         → What's left over (remainder)")

print("\nThink of it this way:")
print("17 ÷ 5 = 3 with 2 left over")
print("- The 3 is what you get from //")
print("- The 2 is what you get from %")
print("- The 3.4 is what you get from /")
```

**Output:**
```
Three types of division with 17 and 5:
17 / 5  = 3.4  (Regular division - gives decimal)
17 // 5 = 3      (Floor division - rounds down to integer)
17 % 5  = 2      (Modulus - gives remainder)

Explanation:
/ (division)        → How many times with decimals
// (floor division) → How many times (whole number, rounded down)
% (modulus)         → What's left over (remainder)

Think of it this way:
17 ÷ 5 = 3 with 2 left over
- The 3 is what you get from //
- The 2 is what you get from %
- The 3.4 is what you get from /
```

**Key Concepts:**
- `/` gives exact decimal result (always returns float)
- `//` gives whole number, rounds down (floor division)
- `%` gives remainder after division (modulus operator)
- Together, `//` and `%` break division into parts

---

### Question 13
**Problem:** Calculate `2 ** 8` (2 to the power of 8). Then calculate `8 ** 2`. Are they the same?

**Solution Approach:**
- Calculate first exponentiation
- Calculate second exponentiation
- Compare results
- Explain why they're different

**Complete Solution:**
```python
# Calculate both exponentiations
power1 = 2 ** 8
power2 = 8 ** 2

print(f"2 ** 8 = {power1}")
print(f"8 ** 2 = {power2}")

print(f"\nAre they the same? {power1 == power2}")

print("\nExplanation:")
print("2 ** 8 means: 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 = 256")
print("8 ** 2 means: 8 × 8 = 64")
print("\nExponentiation is NOT commutative (order matters!)")
print("Unlike addition (3+5 = 5+3) or multiplication (3×5 = 5×3)")
print("With exponents: 2^8 ≠ 8^2")
```

**Output:**
```
2 ** 8 = 256
8 ** 2 = 64

Are they the same? False

Explanation:
2 ** 8 means: 2 × 2 × 2 × 2 × 2 × 2 × 2 × 2 = 256
8 ** 2 means: 8 × 8 = 64

Exponentiation is NOT commutative (order matters!)
Unlike addition (3+5 = 5+3) or multiplication (3×5 = 5×3)
With exponents: 2^8 ≠ 8^2
```

**Key Concepts:**
- `**` is the exponentiation operator (power)
- `2 ** 8` = 2 raised to power of 8 = 256
- `8 ** 2` = 8 raised to power of 2 = 64
- Exponentiation is NOT commutative (order matters!)
- `a ** b` is very different from `b ** a`

---

### Question 14
**Problem:** Calculate the area of a rectangle with width `12.5` and height `8.3`. Store each dimension in a variable.

**Solution Approach:**
- Create variables for dimensions
- Use formula: area = width × height
- Calculate and display result

**Complete Solution:**
```python
# Store dimensions in variables
width = 12.5
height = 8.3

# Calculate area (width × height)
area = width * height

# Display result
print(f"Rectangle Dimensions:")
print(f"Width: {width}")
print(f"Height: {height}")
print(f"\nArea: {area}")
print(f"Area (rounded): {area:.2f}")

# Verification
print(f"\nVerification: {width} × {height} = {area}")
```

**Output:**
```
Rectangle Dimensions:
Width: 12.5
Height: 8.3

Area: 103.75
Area (rounded): 103.75

Verification: 12.5 × 8.3 = 103.75
```

**Key Concepts:**
- Area of rectangle = width × height
- Using variables makes formula clear and reusable
- Multiplication works the same with floats and ints
- Good practice to store inputs in named variables
- `.2f` formats to 2 decimal places (useful for measurements)

---

### Question 15
**Problem:** Use the formula for the area of a circle (πr²) to calculate the area of a circle with radius 7. Use `3.14159` for π.

**Solution Approach:**
- Store π (pi) as a constant
- Store radius in a variable
- Apply formula: area = π × r²
- Use `**` for squaring

**Complete Solution:**
```python
# Define pi as a constant
PI = 3.14159

# Store radius
radius = 7

# Calculate area using formula: π × r²
area = PI * (radius ** 2)

# Alternative: area = PI * radius * radius

# Display result
print(f"Circle with radius: {radius}")
print(f"Area = π × r²")
print(f"Area = {PI} × {radius}²")
print(f"Area = {PI} × {radius ** 2}")
print(f"Area = {area}")
print(f"\nArea (rounded to 2 decimals): {area:.2f}")
```

**Output:**
```
Circle with radius: 7
Area = π × r²
Area = 3.14159 × 7²
Area = 3.14159 × 49
Area = 153.93804

Area (rounded to 2 decimals): 153.94
```

**Key Concepts:**
- Formula: Area = π × r² (pi times radius squared)
- Use `**` operator for exponentiation (r²)
- `radius ** 2` is clearer than `radius * radius`
- PI is a constant (uppercase convention)
- Parentheses ensure correct order: `PI * (radius ** 2)`

---

## Order of Operations (Questions 16-20)

### Question 16
**Problem:** Calculate `5 + 3 * 2`. Then calculate `(5 + 3) * 2`. Explain why the results are different.

**Solution Approach:**
- Calculate without parentheses (follows PEMDAS)
- Calculate with parentheses (forces addition first)
- Explain order of operations

**Complete Solution:**
```python
# Without parentheses - follows PEMDAS
result1 = 5 + 3 * 2
print(f"5 + 3 * 2 = {result1}")
print("Step by step: 3 * 2 = 6, then 5 + 6 = 11")

# With parentheses - addition happens first
result2 = (5 + 3) * 2
print(f"\n(5 + 3) * 2 = {result2}")
print("Step by step: (5 + 3) = 8, then 8 * 2 = 16")

# Explanation
print("\nWhy are they different?")
print("Python follows PEMDAS (order of operations):")
print("1. Parentheses")
print("2. Exponents")
print("3. Multiplication/Division (left to right)")
print("4. Addition/Subtraction (left to right)")
print("\nWithout parentheses: Multiplication happens BEFORE addition")
print("With parentheses: Parentheses force addition to happen FIRST")
```

**Output:**
```
5 + 3 * 2 = 11
Step by step: 3 * 2 = 6, then 5 + 6 = 11

(5 + 3) * 2 = 16
Step by step: (5 + 3) = 8, then 8 * 2 = 16

Why are they different?
Python follows PEMDAS (order of operations):
1. Parentheses
2. Exponents
3. Multiplication/Division (left to right)
4. Addition/Subtraction (left to right)

Without parentheses: Multiplication happens BEFORE addition
With parentheses: Parentheses force addition to happen FIRST
```

**Key Concepts:**
- PEMDAS: Parentheses, Exponents, Multiplication/Division, Addition/Subtraction
- Multiplication has higher precedence than addition
- Parentheses override natural precedence
- Use parentheses to make your intentions clear

---

### Question 17
**Problem:** Evaluate `10 - 3 - 2`. Does this equal `10 - (3 - 2)`? Why or why not?

**Solution Approach:**
- Calculate left-to-right evaluation
- Calculate with parentheses
- Explain associativity (left-to-right rule)

**Complete Solution:**
```python
# Left to right (natural evaluation)
result1 = 10 - 3 - 2
print(f"10 - 3 - 2 = {result1}")
print("Evaluated left to right: (10 - 3) - 2 = 7 - 2 = 5")

# With parentheses on the right
result2 = 10 - (3 - 2)
print(f"\n10 - (3 - 2) = {result2}")
print("Parentheses first: 10 - (1) = 9")

# Comparison
print(f"\nAre they equal? {result1 == result2}")

print("\nExplanation:")
print("Subtraction is LEFT-ASSOCIATIVE")
print("10 - 3 - 2 is evaluated as (10 - 3) - 2")
print("NOT as 10 - (3 - 2)")
print("\nLeft to right: (10 - 3) - 2 = 7 - 2 = 5")
print("With parentheses: 10 - (3 - 2) = 10 - 1 = 9")
print("Parentheses change the order!")
```

**Output:**
```
10 - 3 - 2 = 5
Evaluated left to right: (10 - 3) - 2 = 7 - 2 = 5

10 - (3 - 2) = 9
Parentheses first: 10 - (1) = 9

Are they equal? False

Explanation:
Subtraction is LEFT-ASSOCIATIVE
10 - 3 - 2 is evaluated as (10 - 3) - 2
NOT as 10 - (3 - 2)

Left to right: (10 - 3) - 2 = 7 - 2 = 5
With parentheses: 10 - (3 - 2) = 10 - 1 = 9
Parentheses change the order!
```

**Key Concepts:**
- Subtraction is left-associative (evaluates left to right)
- `10 - 3 - 2` = `(10 - 3) - 2` = `7 - 2` = `5`
- `10 - (3 - 2)` = `10 - 1` = `9`
- They are NOT equal!
- Same precedence operators go left to right

---

### Question 18
**Problem:** Calculate `2 ** 3 ** 2`. Then calculate `(2 ** 3) ** 2`. Compare the results and explain the order of operations for exponents.

**Solution Approach:**
- Calculate with right-associative rule
- Calculate with parentheses (left-associative)
- Explain that exponents are right-associative

**Complete Solution:**
```python
# Without parentheses - right associative!
result1 = 2 ** 3 ** 2
print(f"2 ** 3 ** 2 = {result1}")
print("This evaluates RIGHT TO LEFT: 2 ** (3 ** 2)")
print("Step by step: 3 ** 2 = 9, then 2 ** 9 = 512")

# With parentheses - forced left to right
result2 = (2 ** 3) ** 2
print(f"\n(2 ** 3) ** 2 = {result2}")
print("Parentheses force LEFT TO RIGHT evaluation")
print("Step by step: 2 ** 3 = 8, then 8 ** 2 = 64")

# Comparison
print(f"\nAre they equal? {result1 == result2}")

print("\nKey Insight:")
print("Exponentiation is RIGHT-ASSOCIATIVE!")
print("Unlike +, -, *, / which go left to right")
print("Exponents go RIGHT TO LEFT")
print("\n2 ** 3 ** 2 means 2 ** (3 ** 2) = 2 ** 9 = 512")
print("NOT (2 ** 3) ** 2 = 8 ** 2 = 64")
```

**Output:**
```
2 ** 3 ** 2 = 512
This evaluates RIGHT TO LEFT: 2 ** (3 ** 2)
Step by step: 3 ** 2 = 9, then 2 ** 9 = 512

(2 ** 3) ** 2 = 64
Parentheses force LEFT TO RIGHT evaluation
Step by step: 2 ** 3 = 8, then 8 ** 2 = 64

Are they equal? False

Key Insight:
Exponentiation is RIGHT-ASSOCIATIVE!
Unlike +, -, *, / which go left to right
Exponents go RIGHT TO LEFT

2 ** 3 ** 2 means 2 ** (3 ** 2) = 2 ** 9 = 512
NOT (2 ** 3) ** 2 = 8 ** 2 = 64
```

**Key Concepts:**
- Exponentiation is RIGHT-ASSOCIATIVE (unusual!)
- `2 ** 3 ** 2` = `2 ** (3 ** 2)` = `2 ** 9` = `512`
- Most operators go left to right, but `**` goes right to left
- Use parentheses when chaining exponents for clarity
- This is mathematically consistent with standard notation

---

### Question 19
**Problem:** Calculate `20 / 4 * 2`. Does this equal `20 / (4 * 2)`? Explain the left-to-right rule.

**Solution Approach:**
- Calculate with left-to-right evaluation
- Calculate with parentheses
- Explain equal precedence operators

**Complete Solution:**
```python
# Left to right evaluation (default)
result1 = 20 / 4 * 2
print(f"20 / 4 * 2 = {result1}")
print("Evaluated left to right: (20 / 4) * 2 = 5.0 * 2 = 10.0")

# With parentheses on the right
result2 = 20 / (4 * 2)
print(f"\n20 / (4 * 2) = {result2}")
print("Parentheses first: 20 / 8 = 2.5")

# Comparison
print(f"\nAre they equal? {result1 == result2}")

print("\nExplanation:")
print("Division (/) and Multiplication (*) have EQUAL precedence")
print("When operators have equal precedence, Python evaluates LEFT TO RIGHT")
print("\n20 / 4 * 2 is evaluated as (20 / 4) * 2:")
print("  Step 1: 20 / 4 = 5.0")
print("  Step 2: 5.0 * 2 = 10.0")
print("\n20 / (4 * 2) forces multiplication first:")
print("  Step 1: 4 * 2 = 8")
print("  Step 2: 20 / 8 = 2.5")
```

**Output:**
```
20 / 4 * 2 = 10.0
Evaluated left to right: (20 / 4) * 2 = 5.0 * 2 = 10.0

20 / (4 * 2) = 2.5
Parentheses first: 20 / 8 = 2.5

Are they equal? False

Explanation:
Division (/) and Multiplication (*) have EQUAL precedence
When operators have equal precedence, Python evaluates LEFT TO RIGHT

20 / 4 * 2 is evaluated as (20 / 4) * 2:
  Step 1: 20 / 4 = 5.0
  Step 2: 5.0 * 2 = 10.0

20 / (4 * 2) forces multiplication first:
  Step 1: 4 * 2 = 8
  Step 2: 20 / 8 = 2.5
```

**Key Concepts:**
- `*` and `/` have equal precedence
- Equal precedence = evaluate left to right
- `20 / 4 * 2` = `(20 / 4) * 2` = `10.0`
- `20 / (4 * 2)` = `20 / 8` = `2.5`
- Use parentheses to avoid confusion

---

### Question 20
**Problem:** Write an expression to calculate: add 5 and 3, multiply the result by 4, then divide by 2. Use parentheses to ensure correct order.

**Solution Approach:**
- Break down the steps
- Use parentheses to control order
- Show the calculation step by step

**Complete Solution:**
```python
# Calculate with clear order using parentheses
result = ((5 + 3) * 4) / 2

print("Expression: ((5 + 3) * 4) / 2")
print("\nStep-by-step evaluation:")
print("Step 1: (5 + 3) = 8")
print("Step 2: 8 * 4 = 32")
print("Step 3: 32 / 2 = 16.0")
print(f"\nFinal result: {result}")

# Show what happens without enough parentheses
wrong_result = 5 + 3 * 4 / 2
print(f"\nWithout parentheses: 5 + 3 * 4 / 2 = {wrong_result}")
print("This gives wrong answer because * and / happen before +")

# Verify step by step
step1 = 5 + 3
step2 = step1 * 4
step3 = step2 / 2
print(f"\nVerification using variables:")
print(f"step1 (5 + 3) = {step1}")
print(f"step2 ({step1} * 4) = {step2}")
print(f"step3 ({step2} / 2) = {step3}")
```

**Output:**
```
Expression: ((5 + 3) * 4) / 2

Step-by-step evaluation:
Step 1: (5 + 3) = 8
Step 2: 8 * 4 = 32
Step 3: 32 / 2 = 16.0

Final result: 16.0

Without parentheses: 5 + 3 * 4 / 2 = 11.0
This gives wrong answer because * and / happen before +

Verification using variables:
step1 (5 + 3) = 8
step2 (8 * 4) = 32
step3 (32 / 2) = 16.0
```

**Key Concepts:**
- Parentheses control the order of operations
- Inner parentheses are evaluated first
- `((5 + 3) * 4) / 2` forces the correct sequence
- Without parentheses, PEMDAS would calculate differently
- Use parentheses liberally for clarity

---

## Complex Problems (Questions 21-25)

### Question 21
**Problem:** A store sells items for $19.99 each. Calculate the total cost of 7 items. Then calculate how much change you'd get from $150.

**Solution Approach:**
- Define price per item
- Calculate total for 7 items
- Calculate change from $150
- Display all values clearly

**Complete Solution:**
```python
# Given values
price_per_item = 19.99
quantity = 7
payment = 150

# Calculate total cost
total_cost = price_per_item * quantity

# Calculate change
change = payment - total_cost

# Display results
print("Store Purchase Calculation")
print("=" * 30)
print(f"Price per item: ${price_per_item}")
print(f"Quantity: {quantity}")
print(f"Total cost: ${total_cost}")
print(f"\nPayment: ${payment}")
print(f"Change: ${change}")
print(f"Change (rounded): ${change:.2f}")

# Verification
print(f"\nVerification:")
print(f"{quantity} items × ${price_per_item} = ${total_cost}")
print(f"${payment} - ${total_cost} = ${change:.2f}")
```

**Output:**
```
Store Purchase Calculation
==============================
Price per item: $19.99
Quantity: 7
Total cost: $139.93

Payment: $150
Change: $10.07
Change (rounded): $10.07

Verification:
7 items × $19.99 = $139.93
$150 - $139.93 = $10.07
```

**Key Concepts:**
- Multiplication for total: `price × quantity`
- Subtraction for change: `payment - total`
- Using descriptive variable names makes logic clear
- `.2f` formatting for currency display
- Breaking problem into clear steps

---

### Question 22
**Problem:** You have $500. You spend 30% on groceries and 45% on rent. How much money do you have left? Calculate each step separately.

**Solution Approach:**
- Start with initial amount
- Calculate groceries (30% of total)
- Calculate rent (45% of total)
- Subtract both to find remaining amount

**Complete Solution:**
```python
# Initial amount
starting_money = 500

# Calculate expenses
groceries_percent = 0.30  # 30%
rent_percent = 0.45       # 45%

groceries_cost = starting_money * groceries_percent
rent_cost = starting_money * rent_percent

# Calculate remaining money
total_spent = groceries_cost + rent_cost
money_left = starting_money - total_spent

# Display results
print("Budget Calculation")
print("=" * 40)
print(f"Starting money: ${starting_money}")
print()
print("Expenses:")
print(f"Groceries (30%): ${groceries_cost}")
print(f"Rent (45%): ${rent_cost}")
print(f"Total spent: ${total_spent}")
print()
print(f"Money remaining: ${money_left}")
print()
print("Percentage breakdown:")
print(f"Spent: {((total_spent/starting_money)*100):.0f}%")
print(f"Remaining: {((money_left/starting_money)*100):.0f}%")
```

**Output:**
```
Budget Calculation
========================================
Starting money: $500

Expenses:
Groceries (30%): $150.0
Rent (45%): $225.0
Total spent: $375.0

Money remaining: $125.0

Percentage breakdown:
Spent: 75%
Remaining: 25%
```

**Key Concepts:**
- Percentage as decimal: 30% = 0.30
- Calculate each expense: `amount * percentage`
- Total remaining: `start - total_spent`
- Can verify: 30% + 45% = 75% spent, 25% remaining
- Clear variable names document the calculation

---

### Question 23
**Problem:** Convert a temperature of 98.6°F to Celsius using the formula: C = (F - 32) × 5/9. Store the Fahrenheit value in a variable first.

**Solution Approach:**
- Store Fahrenheit temperature
- Apply conversion formula
- Use parentheses to ensure correct order
- Display both temperatures

**Complete Solution:**
```python
# Temperature in Fahrenheit
fahrenheit = 98.6

# Conversion formula: C = (F - 32) × 5/9
celsius = (fahrenheit - 32) * 5 / 9

# Display results
print("Temperature Conversion")
print("=" * 30)
print(f"Fahrenheit: {fahrenheit}°F")
print(f"Celsius: {celsius}°C")
print(f"Celsius (rounded): {celsius:.1f}°C")

# Show the calculation
print(f"\nCalculation:")
print(f"C = (F - 32) × 5/9")
print(f"C = ({fahrenheit} - 32) × 5/9")
print(f"C = {fahrenheit - 32} × 5/9")
print(f"C = {celsius:.1f}")

# Fun fact
print(f"\nFun fact: Normal body temperature")
print(f"98.6°F = {celsius:.1f}°C")
```

**Output:**
```
Temperature Conversion
==============================
Fahrenheit: 98.6°F
Celsius: 37.0°C
Celsius (rounded): 37.0°C

Calculation:
C = (F - 32) × 5/9
C = (98.6 - 32) × 5/9
C = 66.6 × 5/9
C = 37.0

Fun fact: Normal body temperature
98.6°F = 37.0°C
```

**Key Concepts:**
- Formula: `C = (F - 32) * 5 / 9`
- Parentheses crucial: `(fahrenheit - 32)` must happen first
- Without parentheses, order would be wrong
- `5 / 9` = `5/9` (division happens left to right with *)
- Could also write: `(fahrenheit - 32) * (5/9)`

---

### Question 24
**Problem:** Calculate compound interest: You invest $1000 at 5% interest for 3 years using the formula: A = P(1 + r)^t. Show your work step by step.

**Solution Approach:**
- Define principal (P), rate (r), time (t)
- Apply formula: A = P(1 + r)^t
- Calculate step by step
- Show final amount and interest earned

**Complete Solution:**
```python
# Investment parameters
principal = 1000      # P: Initial investment
rate = 0.05          # r: Interest rate (5% = 0.05)
time = 3             # t: Time in years

# Compound interest formula: A = P(1 + r)^t
# Step 1: Calculate (1 + r)
growth_factor = 1 + rate

# Step 2: Calculate (1 + r)^t
growth_multiplier = growth_factor ** time

# Step 3: Calculate final amount
final_amount = principal * growth_multiplier

# Calculate interest earned
interest_earned = final_amount - principal

# Display results
print("Compound Interest Calculation")
print("=" * 40)
print("Formula: A = P(1 + r)^t")
print()
print("Given values:")
print(f"Principal (P): ${principal}")
print(f"Rate (r): {rate} ({rate*100}%)")
print(f"Time (t): {time} years")
print()
print("Step-by-step calculation:")
print(f"Step 1: (1 + r) = (1 + {rate}) = {growth_factor}")
print(f"Step 2: (1 + r)^t = {growth_factor}^{time} = {growth_multiplier}")
print(f"Step 3: A = P × {growth_multiplier}")
print(f"        A = ${principal} × {growth_multiplier}")
print(f"        A = ${final_amount:.2f}")
print()
print("Results:")
print(f"Final amount: ${final_amount:.2f}")
print(f"Interest earned: ${interest_earned:.2f}")
print(f"Total growth: {((final_amount/principal - 1) * 100):.2f}%")
```

**Output:**
```
Compound Interest Calculation
========================================
Formula: A = P(1 + r)^t

Given values:
Principal (P): $1000
Rate (r): 0.05 (5.0%)
Time (t): 3 years

Step-by-step calculation:
Step 1: (1 + r) = (1 + 0.05) = 1.05
Step 2: (1 + r)^t = 1.05^3 = 1.157625
Step 3: A = P × 1.157625
        A = $1000 × 1.157625
        A = $1157.62

Results:
Final amount: $1157.62
Interest earned: $157.62
Total growth: 15.76%
```

**Key Concepts:**
- Compound interest formula: A = P(1 + r)^t
- Break formula into steps for clarity
- Use `**` operator for exponentiation
- Parentheses ensure (1 + r) is calculated first
- Interest earned = final - principal
- Breaking into steps makes complex formulas manageable

---

### Question 25
**Problem:** Create a program that calculates your age in months, days, and hours. Start with a variable `age_in_years = 20`. Show all calculations and use appropriate variable names. (Assume 365 days per year and 24 hours per day)

**Solution Approach:**
- Start with age in years
- Convert to months (years × 12)
- Convert to days (years × 365)
- Convert to hours (days × 24)
- Display all conversions clearly

**Complete Solution:**
```python
# Starting value
age_in_years = 20

# Conversion constants
MONTHS_PER_YEAR = 12
DAYS_PER_YEAR = 365
HOURS_PER_DAY = 24

# Calculate conversions
age_in_months = age_in_years * MONTHS_PER_YEAR
age_in_days = age_in_years * DAYS_PER_YEAR
age_in_hours = age_in_days * HOURS_PER_DAY

# Alternative: Calculate hours directly
age_in_hours_direct = age_in_years * DAYS_PER_YEAR * HOURS_PER_DAY

# Calculate some additional fun facts
age_in_minutes = age_in_hours * 60
age_in_seconds = age_in_minutes * 60

# Display results
print("Age Conversion Calculator")
print("=" * 50)
print(f"Your age: {age_in_years} years")
print()
print("Your age in different units:")
print(f"Months: {age_in_months:,} months")
print(f"Days: {age_in_days:,} days")
print(f"Hours: {age_in_hours:,} hours")
print()
print("Bonus conversions:")
print(f"Minutes: {age_in_minutes:,} minutes")
print(f"Seconds: {age_in_seconds:,} seconds")
print()
print("Calculation breakdown:")
print(f"Months: {age_in_years} years × {MONTHS_PER_YEAR} months/year = {age_in_months} months")
print(f"Days: {age_in_years} years × {DAYS_PER_YEAR} days/year = {age_in_days} days")
print(f"Hours: {age_in_days} days × {HOURS_PER_DAY} hours/day = {age_in_hours} hours")
print()
print(f"Fun fact: You've lived {age_in_hours:,} hours!")
print(f"That's {age_in_hours/1000:.1f} thousand hours!")
```

**Output:**
```
Age Conversion Calculator
==================================================
Your age: 20 years

Your age in different units:
Months: 240 months
Days: 7,300 days
Hours: 175,200 hours

Bonus conversions:
Minutes: 10,512,000 minutes
Seconds: 630,720,000 seconds

Calculation breakdown:
Months: 20 years × 12 months/year = 240 months
Days: 20 years × 365 days/year = 7300 days
Hours: 7300 days × 24 hours/day = 175200 hours

Fun fact: You've lived 175,200 hours!
That's 175.2 thousand hours!
```

**Key Concepts:**
- Constants in UPPERCASE (MONTHS_PER_YEAR)
- Descriptive variable names (age_in_months, age_in_days)
- Chain calculations: years → days → hours
- Use `:,` format for thousands separators
- Breaking complex conversions into clear steps
- Each conversion uses the previous result
- Shows the power of variables and basic math operations

---

## Summary of Key Patterns

Throughout these solutions, you've seen important problem-solving patterns:

1. **Break problems into steps** - Don't try to do everything at once
2. **Use descriptive variable names** - Code should be self-documenting
3. **Constants in UPPERCASE** - Shows values that shouldn't change
4. **Print intermediate results** - Helps verify your logic
5. **Use parentheses for clarity** - Even when not strictly needed
6. **Format output properly** - Use f-strings and format specifiers
7. **Comment your thinking** - Explain WHY, not just WHAT
8. **Verify your results** - Show calculations to prove correctness

These patterns will serve you well throughout your Python journey!