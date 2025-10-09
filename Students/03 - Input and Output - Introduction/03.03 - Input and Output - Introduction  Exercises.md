# Chapter 3: Input and Output - Practice Questions

## Example Problems with Detailed Walkthroughs

### Example 1: Simple User Greeting with Name and Age
**Problem:** Create a program that asks the user for their name and age, then prints a personalized greeting that tells them how old they'll be next year. Use f-strings for the output.

**Detailed Solution:**

**Step 1: Understand what we need**
- Get user's name (string) - no conversion needed
- Get user's age (integer) - MUST convert from string
- Calculate age next year (add 1)
- Display a formatted message

**Step 2: Identify the input types**
- `input()` ALWAYS returns a string
- Name can stay as string
- Age needs to be converted to int for calculation

**Step 3: Get the inputs**
```python
name = input("What is your name? ")
age_string = input("What is your age? ")
```

**Step 4: Convert age to integer**
Remember: We MUST cast to int to do math!
```python
age = int(age_string)
```

Or combine steps 3 and 4:
```python
age = int(input("What is your age? "))
```

**Step 5: Calculate next year's age**
```python
age_next_year = age + 1
```

**Step 6: Display the result using f-strings**
```python
print(f"Hello {name}! Next year you will be {age_next_year} years old.")
```

**Complete Solution:**
```python
# Get user input
name = input("What is your name? ")
age = int(input("What is your age? "))

# Calculate next year's age
age_next_year = age + 1

# Display greeting with f-string
print(f"Hello {name}! Next year you will be {age_next_year} years old.")
```

**Sample Run:**
```
What is your name? Alice
What is your age? 25
Hello Alice! Next year you will be 26 years old.
```

**Why this approach works:**
- We used clear prompts in `input()` so user knows what to type
- We converted age to int immediately after input
- We used f-strings for clean, readable output
- We calculated the result before printing

**Common Mistake to Avoid:**
```python
# WRONG - will cause error!
age = input("What is your age? ")
age_next_year = age + 1  # ERROR! Can't add int to string
```

---

### Example 2: Rectangle Calculator with Multiple Outputs
**Problem:** Create a program that asks the user for the width and height of a rectangle (both can be decimals), then calculates and displays: the area, the perimeter, and whether it's a square. Use proper formatting with 2 decimal places for the results.

**Detailed Solution:**

**Step 1: Understand the problem**
- Get width and height (floats for decimal values)
- Calculate area = width × height
- Calculate perimeter = 2 × (width + height)
- Check if it's a square (width equals height)

**Step 2: Decide on data types**
- Width: float (can have decimals)
- Height: float (can have decimals)
- Area: float (result of multiplication)
- Perimeter: float (result of calculation)
- Is square: boolean (True/False)

**Step 3: Get user input and convert**
```python
width = float(input("Enter the width: "))
height = float(input("Enter the height: "))
```

Why float? Because user might enter "12.5" and we need decimals.

**Step 4: Calculate area and perimeter**
```python
area = width * height
perimeter = 2 * (width + height)
```

Note: Parentheses in perimeter ensure we add first, then multiply.

**Step 5: Check if it's a square**
```python
is_square = (width == height)
```

The `==` operator checks equality and returns True or False.

**Step 6: Display results with formatting**
```python
print(f"\nRectangle Properties:")
print(f"Width: {width}")
print(f"Height: {height}")
print(f"Area: {area:.2f}")
print(f"Perimeter: {perimeter:.2f}")
print(f"Is it a square? {is_square}")
```

The `:.2f` formats floats to 2 decimal places.

**Complete Solution:**
```python
# Get dimensions from user
print("Rectangle Calculator")
print("-" * 20)
width = float(input("Enter the width: "))
height = float(input("Enter the height: "))

# Calculate properties
area = width * height
perimeter = 2 * (width + height)
is_square = (width == height)

# Display results
print(f"\nRectangle Properties:")
print(f"Width: {width}")
print(f"Height: {height}")
print(f"Area: {area:.2f}")
print(f"Perimeter: {perimeter:.2f}")
print(f"Is it a square? {is_square}")
```

**Sample Run 1 (Rectangle):**
```
Rectangle Calculator
--------------------
Enter the width: 12.5
Enter the height: 8.3

Rectangle Properties:
Width: 12.5
Height: 8.3
Area: 103.75
Perimeter: 41.60
Is it a square? False
```

**Sample Run 2 (Square):**
```
Rectangle Calculator
--------------------
Enter the width: 10
Enter the height: 10

Rectangle Properties:
Width: 10.0
Height: 10.0
Area: 100.00
Perimeter: 40.00
Is it a square? True
```

**Key Insights:**
- We used `float()` because dimensions can have decimals
- Parentheses in `2 * (width + height)` ensure correct order
- `==` operator compares values and returns boolean
- `:.2f` formatting makes output professional
- Adding section headers makes output readable

---

### Example 3: Price Calculator with Tax and Multiple Print Techniques
**Problem:** Create a program that takes an item price and quantity from the user, calculates the subtotal, applies 5% tax, and displays a formatted receipt. Show the calculation using different output methods (concatenation, commas, and f-strings) to demonstrate all techniques.

**Detailed Solution:**

**Step 1: Plan the calculations**
- Get price (float)
- Get quantity (integer)
- Calculate subtotal = price × quantity
- Calculate tax = subtotal × 0.05
- Calculate total = subtotal + tax

**Step 2: Understand output requirements**
- Demonstrate concatenation (must cast numbers)
- Demonstrate comma separation (auto-converts)
- Demonstrate f-strings (best practice)

**Step 3: Get user input**
```python
item_name = input("Enter item name: ")
price = float(input("Enter price per item: $"))
quantity = int(input("Enter quantity: "))
```

Notice: We can put the $ in the prompt so user doesn't type it.

**Step 4: Perform calculations**
```python
TAX_RATE = 0.05  # 5% tax (constant)

subtotal = price * quantity
tax = subtotal * TAX_RATE
total = subtotal + tax
```

**Step 5: Display using CONCATENATION**
```python
print("\n=== METHOD 1: Concatenation ===")
print("Item: " + item_name)
print("Price: $" + str(price))  # MUST cast to string!
print("Quantity: " + str(quantity))
print("Subtotal: $" + str(subtotal))
print("Tax: $" + str(tax))
print("Total: $" + str(total))
```

**Step 6: Display using COMMAS**
```python
print("\n=== METHOD 2: Commas ===")
print("Item:", item_name)
print("Price: $", price)  # No casting needed!
print("Quantity:", quantity)
print("Subtotal: $", subtotal)
print("Tax: $", tax)
print("Total: $", total)
```

**Step 7: Display using F-STRINGS (recommended)**
```python
print("\n=== METHOD 3: F-Strings (Best!) ===")
print(f"Item: {item_name}")
print(f"Price: ${price:.2f}")
print(f"Quantity: {quantity}")
print(f"Subtotal: ${subtotal:.2f}")
print(f"Tax (5%): ${tax:.2f}")
print(f"Total: ${total:.2f}")
```

**Complete Solution:**
```python
# Constants
TAX_RATE = 0.05

# Get user input
print("Receipt Generator")
print("=" * 40)
item_name = input("Enter item name: ")
price = float(input("Enter price per item: $"))
quantity = int(input("Enter quantity: "))

# Calculate totals
subtotal = price * quantity
tax = subtotal * TAX_RATE
total = subtotal + tax

# Method 1: Concatenation (requires str() for numbers)
print("\n=== METHOD 1: Concatenation ===")
print("Item: " + item_name)
print("Price: $" + str(price))
print("Quantity: " + str(quantity))
print("Subtotal: $" + str(subtotal))
print("Tax: $" + str(tax))
print("Total: $" + str(total))

# Method 2: Commas (auto-converts, adds spaces)
print("\n=== METHOD 2: Commas ===")
print("Item:", item_name)
print("Price: $", price)
print("Quantity:", quantity)
print("Subtotal: $", subtotal)
print("Tax: $", tax)
print("Total: $", total)

# Method 3: F-strings (cleanest, most flexible)
print("\n=== METHOD 3: F-Strings (Best!) ===")
print(f"Item: {item_name}")
print(f"Price: ${price:.2f}")
print(f"Quantity: {quantity}")
print(f"Subtotal: ${subtotal:.2f}")
print(f"Tax (5%): ${tax:.2f}")
print(f"Total: ${total:.2f}")
```

**Sample Run:**
```
Receipt Generator
========================================
Enter item name: Widget
Enter price per item: $12.99
Enter quantity: 3

=== METHOD 1: Concatenation ===
Item: Widget
Price: $12.99
Quantity: 3
Subtotal: $38.97
Tax: $1.9485
Total: $40.9185

=== METHOD 2: Commas ===
Item: Widget
Price: $ 12.99
Quantity: 3
Subtotal: $ 38.97
Tax: $ 1.9485
Total: $ 40.9185

=== METHOD 3: F-Strings (Best!) ===
Item: Widget
Price: $12.99
Quantity: 3
Subtotal: $38.97
Tax (5%): $1.95
Total: $40.92
```

**Key Comparisons:**

| Method | Pros | Cons |
|--------|------|------|
| Concatenation | Explicit control | Must cast numbers, verbose |
| Commas | Auto-converts | Adds unwanted spaces around $ |
| F-strings | Clean, flexible, formatting | None - use this! |

**Why F-strings are best:**
- No casting needed
- Formatting built in (:.2f)
- Most readable
- Can include expressions: `{price * quantity}`
- Modern Python standard

---

## Practice Questions (25 Questions - Increasing Complexity)

### Basic Input and Output (Questions 1-5)

1. Write a program that asks for the user's favorite color and prints "Your favorite color is [color]!"

2. Ask the user for two numbers and print them both. The program should just display the numbers, no calculations needed.

3. Get the user's first name and last name separately, then print their full name in the format "Last, First".

4. Ask for a person's birth year, then print just that year back to them with the message "You were born in [year]".

5. Create a program that asks "What is your name?" and then prints three exclamation marks after the name (e.g., "Alice!!!").

### Type Conversion with Input (Questions 6-10)

6. Ask the user for their age and print what their age will be in 5 years. (Remember to convert to int!)

7. Get a decimal number from the user and print its value multiplied by 10.

8. Ask for two integers and print their sum. Make sure to convert the inputs properly.

9. Get a temperature in Celsius from the user (as a float) and convert it to Fahrenheit using the formula F = C × 9/5 + 32.

10. Ask the user for a price and how many items they want. Calculate and display the total cost.

### Different Print Formats (Questions 11-15)

11. Ask for a user's name and age. Print them using concatenation (with +), then print them using commas, then print them using an f-string.

12. Get three favorite foods from the user and print them on the same line, separated by commas.

13. Ask for a number and print it with exactly 2 decimal places, then with 4 decimal places.

14. Create a program that asks for length and width, then prints "The area is [area]" where the area is shown with 1 decimal place.

15. Get a large number from the user and display it with commas as thousands separators (e.g., 1,234,567).

### Combined Calculations (Questions 16-20)

16. Create a simple tip calculator: get the bill amount and tip percentage, calculate the tip amount and total bill.

17. Ask for hours worked and hourly rate, then calculate and display the gross pay.

18. Build a miles-to-kilometers converter (1 mile = 1.60934 km). Get miles from user and display kilometers.

19. Create a program that calculates BMI: get weight in kg and height in meters, then calculate BMI = weight / (height²).

20. Make a compound interest calculator: get principal, rate (as percentage), and years. Calculate final amount using A = P(1 + r/100)^t.

### Complex Programs (Questions 21-25)

21. Create a "Mad Libs" program: ask for a noun, verb, adjective, and adverb, then create a funny sentence using all four words.

22. Build a pizza order calculator: ask for number of pizzas, price per pizza, and delivery fee. Calculate subtotal, add 8% tax, and show a formatted receipt with all values.

23. Create a grade calculator: ask for points earned and points possible, calculate the percentage, and display it formatted as "You earned XX.X%".

24. Make a currency converter: get amount in USD, ask for exchange rate, calculate equivalent in foreign currency, and show both amounts with proper formatting.

25. Build a travel time calculator: ask for distance in miles and average speed in mph. Calculate time in hours (as decimal), then break it down into hours and minutes. Display both formats. (Hint: use // for hours and % for remaining minutes)

---

## Tips for Solving These Problems

### Input Best Practices
1. **Always include prompts** - Tell users what to enter
2. **Cast immediately** - Convert input right away if you need to do math
3. **Use descriptive variable names** - `price` not `p`
4. **Remember input() always returns string** - Convert for calculations

### Output Best Practices
1. **Use f-strings** - They're the cleanest and most powerful
2. **Format numbers appropriately** - Use `:.2f` for money
3. **Add labels to output** - "Total: $50" not just "50"
4. **Use blank lines** - `print()` adds spacing for readability

### Common Pitfalls
1. **Forgetting to cast input** - `age = input()` gives you a string!
2. **Casting in wrong order** - Can't do `int("12.5")` - use float first
3. **Concatenation without str()** - Can't do `"Age: " + 25`
4. **Forgetting decimal formatting** - `1/3` looks messy without `:.2f`

### Problem-Solving Process
1. **Read carefully** - What inputs are needed? What output is expected?
2. **Plan data types** - String? Int? Float?
3. **Write input section** - Get all data from user
4. **Do calculations** - Process the data
5. **Format output** - Make it look professional
6. **Test with different inputs** - Try decimals, negatives, zeros