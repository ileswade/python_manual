# Chapter 2: Python Basics - Practice Questions

## Example Problems with Detailed Walkthroughs

### Example 1: Variable Creation and Type Checking
**Problem:** Create three variables: `student_count` with value 30, `average_grade` with value 87.5, and `school_name` with value "Lincoln High". Print each variable and its type.

**Detailed Solution:**

**Step 1: Understand what's being asked**
- We need to create 3 variables with specific names and values
- We need to display each variable's value
- We need to show what type each variable is

**Step 2: Identify the data types needed**
- `student_count = 30` → This is a whole number, so it's an **integer**
- `average_grade = 87.5` → This has a decimal, so it's a **float**
- `school_name = "Lincoln High"` → This is text, so it's a **string**

**Step 3: Create the variables**
Remember to use **snake_case** for variable names (all lowercase with underscores).

```python
student_count = 30
average_grade = 87.5
school_name = "Lincoln High"
```

**Step 4: Print the values and types**
Use `print()` to display values and `type()` to check their types.

```python
print(student_count)
print(type(student_count))

print(average_grade)
print(type(average_grade))

print(school_name)
print(type(school_name))
```

**Complete Solution:**
```python
# Create variables
student_count = 30
average_grade = 87.5
school_name = "Lincoln High"

# Print values and types
print(student_count)          # 30
print(type(student_count))    # <class 'int'>

print(average_grade)          # 87.5
print(type(average_grade))    # <class 'float'>

print(school_name)            # Lincoln High
print(type(school_name))      # <class 'str'>
```

**Why this approach works:**
- We followed Python naming conventions (snake_case)
- We matched the correct data type to each value
- We used built-in functions (`print()` and `type()`) to display information

---

### Example 2: Type Conversion Chain
**Problem:** Start with the string `"99.9"`. Convert it to a float, then to an integer, then back to a string. Print the result and type after each conversion. Explain what happens to the data.

**Detailed Solution:**

**Step 1: Understand the conversion chain**
We're doing a series of type conversions:
- String → Float → Integer → String

**Step 2: Predict what will happen**
- String to Float: `"99.9"` becomes `99.9` (the number)
- Float to Integer: `99.9` becomes `99` (LOSES the decimal - this is lossy!)
- Integer to String: `99` becomes `"99"` (text version)

**Step 3: Start with the original string**
```python
original = "99.9"
print(f"Original: {original}, Type: {type(original)}")
```

**Step 4: Convert string to float**
```python
as_float = float(original)
print(f"As float: {as_float}, Type: {type(as_float)}")
```

**Step 5: Convert float to integer (LOSSY!)**
```python
as_int = int(as_float)
print(f"As int: {as_int}, Type: {type(as_int)}")
```

**Step 6: Convert integer back to string**
```python
back_to_string = str(as_int)
print(f"Back to string: {back_to_string}, Type: {type(back_to_string)}")
```

**Complete Solution:**
```python
# Start with a string
original = "99.9"
print(f"Original: {original}, Type: {type(original)}")

# Convert to float
as_float = float(original)
print(f"As float: {as_float}, Type: {type(as_float)}")

# Convert to int (LOSES decimal!)
as_int = int(as_float)
print(f"As int: {as_int}, Type: {type(as_int)}")

# Convert back to string
back_to_string = str(as_int)
print(f"Back to string: {back_to_string}, Type: {type(back_to_string)}")

# Notice: We started with "99.9" and ended with "99" - data was lost!
```

**Output:**
```
Original: 99.9, Type: <class 'str'>
As float: 99.9, Type: <class 'float'>
As int: 99, Type: <class 'int'>
Back to string: 99, Type: <class 'str'>
```

**Key Insight:**
The float-to-int conversion is **lossy** - we permanently lost the `.9`. Even though we converted back to a string, we can never recover that lost decimal portion. This is why understanding type conversion is crucial!

---

### Example 3: Mathematical Expression with Order of Operations
**Problem:** Calculate the final price of an item that costs $50, has a 20% discount applied, and then has 5% tax added to the discounted price. Use the order of operations correctly and show each step.

**Detailed Solution:**

**Step 1: Break down the problem**
- Original price: $50
- Discount: 20% off (multiply by 0.80 to get 80% of the price)
- Tax: 5% added (multiply by 1.05 to add 5%)

**Step 2: Plan the calculation order**
1. Calculate discount: `price * 0.80`
2. Calculate tax on discounted price: `discounted_price * 1.05`

**Step 3: Could we do it in one expression?**
Yes! `50 * 0.80 * 1.05`

But let's do it step-by-step for clarity.

**Step 4: Create variables and calculate**
```python
# Original price
original_price = 50

# Apply 20% discount (keep 80% of price)
discount_rate = 0.20
price_after_discount = original_price * (1 - discount_rate)

# Apply 5% tax (multiply by 1.05)
tax_rate = 0.05
final_price = price_after_discount * (1 + tax_rate)
```

**Step 5: Display results with proper formatting**
```python
print(f"Original price: ${original_price}")
print(f"After 20% discount: ${price_after_discount}")
print(f"After 5% tax: ${final_price}")
```

**Complete Solution:**
```python
# Define the values
original_price = 50
discount_rate = 0.20  # 20% discount
tax_rate = 0.05       # 5% tax

# Step 1: Apply discount
price_after_discount = original_price * (1 - discount_rate)

# Step 2: Apply tax to discounted price
final_price = price_after_discount * (1 + tax_rate)

# Display results
print(f"Original price: ${original_price}")
print(f"After 20% discount: ${price_after_discount}")
print(f"After 5% tax: ${final_price}")

# Alternative: Calculate in one line
final_price_oneline = 50 * 0.80 * 1.05
print(f"\nOne-line calculation: ${final_price_oneline}")
```

**Output:**
```
Original price: $50
After 20% discount: $40.0
After 5% tax: $42.0

One-line calculation: $42.0
```

**Why this approach works:**
- We used parentheses to ensure correct order: `(1 - discount_rate)` calculates first
- We applied operations in the correct sequence: discount first, then tax
- We used descriptive variable names to make the code readable
- We stored intermediate results to see each step

---

## Practice Questions (25 Questions - Increasing Complexity)

### Variables and Data Types (Questions 1-5)

1. Create a variable called `my_age` and assign it your age. Print the variable and its type.

2. Create three variables: `item_name` (string), `item_price` (float), and `in_stock` (boolean). Print all three.

3. Create a variable `x` with value 10. Change it to 20, then to "twenty". Print it after each change along with its type.

4. Create a constant `MAX_SPEED` with value 120. Try to write it in the correct Python convention.

5. Create variables using both good and bad naming conventions. Identify which ones follow Python's snake_case convention correctly.

### Type Checking and Conversion (Questions 6-10)

6. Create a variable with value `"123"`. Check its type, convert it to an integer, then check the type again.

7. What happens when you try to convert `"12.5"` directly to an integer? Try it and explain the error.

8. Convert `"12.5"` to a float first, then to an integer. What value do you get and why?

9. Create a float `7.9` and convert it to an integer. Is this a lossy conversion? Why or why not?

10. Take the integer `100`, convert it to a float, then to a string. Print the result and all intermediate types.

### Basic Math Operations (Questions 11-15)

11. Calculate `23 + 45` and store it in a variable. Then calculate `23 - 45`. Compare the results.

12. What is `17 / 5`? What is `17 // 5`? What is `17 % 5`? Explain the difference between these three operations.

13. Calculate `2 ** 8` (2 to the power of 8). Then calculate `8 ** 2`. Are they the same?

14. Calculate the area of a rectangle with width `12.5` and height `8.3`. Store each dimension in a variable.

15. Use the formula for the area of a circle (πr²) to calculate the area of a circle with radius 7. Use `3.14159` for π.

### Order of Operations (Questions 16-20)

16. Calculate `5 + 3 * 2`. Then calculate `(5 + 3) * 2`. Explain why the results are different.

17. Evaluate `10 - 3 - 2`. Does this equal `10 - (3 - 2)`? Why or why not?

18. Calculate `2 ** 3 ** 2`. Then calculate `(2 ** 3) ** 2`. Compare the results and explain the order of operations for exponents.

19. Calculate `20 / 4 * 2`. Does this equal `20 / (4 * 2)`? Explain the left-to-right rule.

20. Write an expression to calculate: add 5 and 3, multiply the result by 4, then divide by 2. Use parentheses to ensure correct order.

### Complex Problems (Questions 21-25)

21. A store sells items for $19.99 each. Calculate the total cost of 7 items. Then calculate how much change you'd get from $150.

22. You have $500. You spend 30% on groceries and 45% on rent. How much money do you have left? Calculate each step separately.

23. Convert a temperature of 98.6°F to Celsius using the formula: C = (F - 32) × 5/9. Store the Fahrenheit value in a variable first.

24. Calculate compound interest: You invest $1000 at 5% interest for 3 years using the formula: A = P(1 + r)^t. Show your work step by step.

25. Create a program that calculates your age in months, days, and hours. Start with a variable `age_in_years = 20`. Show all calculations and use appropriate variable names. (Assume 365 days per year and 24 hours per day)

---

## Tips for Solving These Problems

1. **Read carefully**: Understand what the question asks before coding
2. **Plan your approach**: Think about what variables and operations you need
3. **Use descriptive names**: Variable names should explain what they store
4. **Test as you go**: Print intermediate results to verify your logic
5. **Check types**: Use `type()` when you're unsure about a variable's type
6. **Watch for lossy conversions**: Remember that float→int loses decimals
7. **Use parentheses**: When in doubt, use parentheses to clarify order of operations
8. **Comment your code**: Explain your thinking, especially for complex calculations