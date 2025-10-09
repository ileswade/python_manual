# Chapter 3: Input and Output - Solutions Guide

## Basic Input and Output (Questions 1-5)

### Question 1
**Problem:** Write a program that asks for the user's favorite color and prints "Your favorite color is [color]!"

**Solution Approach:**
- Use `input()` with a clear prompt
- Store the response in a variable
- Print the formatted message using an f-string

**Complete Solution:**
```python
# Get user's favorite color
favorite_color = input("What is your favorite color? ")

# Print the message
print(f"Your favorite color is {favorite_color}!")
```

**Sample Run:**
```
What is your favorite color? blue
Your favorite color is blue!
```

**Key Concepts:**
- `input()` always returns a string (perfect for text like colors)
- No type conversion needed for text responses
- F-strings make output formatting clean and readable
- Including punctuation in the prompt helps guide the user

---

### Question 2
**Problem:** Ask the user for two numbers and print them both. The program should just display the numbers, no calculations needed.

**Solution Approach:**
- Get two inputs from the user
- No conversion needed since we're just displaying
- Print both numbers

**Complete Solution:**
```python
# Get two numbers from user
number1 = input("Enter first number: ")
number2 = input("Enter second number: ")

# Display both numbers
print(f"First number: {number1}")
print(f"Second number: {number2}")
```

**Sample Run:**
```
Enter first number: 42
Enter second number: 17
First number: 42
Second number: 17
```

**Key Concepts:**
- Since we're only displaying (not calculating), no casting needed
- Even though user enters numbers, they're stored as strings
- This would NOT work if we tried to add them: "42" + "17" = "4217"
- Labels make output clear and professional

---

### Question 3
**Problem:** Get the user's first name and last name separately, then print their full name in the format "Last, First".

**Solution Approach:**
- Get first name
- Get last name
- Combine them in the requested format with comma and space

**Complete Solution:**
```python
# Get name components
first_name = input("Enter your first name: ")
last_name = input("Enter your last name: ")

# Print in "Last, First" format
print(f"{last_name}, {first_name}")
```

**Alternative using concatenation:**
```python
# Get name components
first_name = input("Enter your first name: ")
last_name = input("Enter your last name: ")

# Print using concatenation
print(last_name + ", " + first_name)
```

**Sample Run:**
```
Enter your first name: Alice
Enter your last name: Smith
Smith, Alice
```

**Key Concepts:**
- Order matters in output: last name comes first
- F-strings make formatting simple: `f"{last_name}, {first_name}"`
- With concatenation: need to manually add `", "` between names
- This format is common in formal documents and directories

---

### Question 4
**Problem:** Ask for a person's birth year, then print just that year back to them with the message "You were born in [year]".

**Solution Approach:**
- Get birth year from user
- No conversion needed (just displaying it back)
- Print the formatted message

**Complete Solution:**
```python
# Get birth year
birth_year = input("What year were you born? ")

# Display message
print(f"You were born in {birth_year}.")
```

**Sample Run:**
```
What year were you born? 2000
You were born in 2000.
```

**Key Concepts:**
- Even though it's a number, we don't need to convert it
- We're only displaying, not calculating with it
- If we needed to calculate age, THEN we'd need `int(birth_year)`
- F-strings work with any data type

---

### Question 5
**Problem:** Create a program that asks "What is your name?" and then prints three exclamation marks after the name (e.g., "Alice!!!").

**Solution Approach:**
- Get the user's name
- Print name followed by three exclamation marks
- Can use concatenation or f-string

**Complete Solution:**
```python
# Get user's name
name = input("What is your name? ")

# Print with three exclamation marks
print(f"{name}!!!")
```

**Alternative methods:**
```python
# Method 2: Using concatenation
print(name + "!!!")

# Method 3: Using commas (but adds unwanted space)
print(name, "!!!")  # This gives "Alice !!!" with a space

# Method 4: String repetition
print(f"{name}{'!' * 3}")
```

**Sample Run:**
```
What is your name? Alice
Alice!!!
```

**Key Concepts:**
- F-strings and concatenation both work well here
- Commas add unwanted space: `"Alice !!!"` instead of `"Alice!!!"`
- String repetition: `'!' * 3` creates `'!!!'`
- Choose the method that's clearest for your purpose

---

## Type Conversion with Input (Questions 6-10)

### Question 6
**Problem:** Ask the user for their age and print what their age will be in 5 years. (Remember to convert to int!)

**Solution Approach:**
- Get age as input (it's a string)
- Convert to integer using `int()`
- Add 5 to calculate future age
- Display the result

**Complete Solution:**
```python
# Get age and convert to integer
age = int(input("How old are you? "))

# Calculate age in 5 years
future_age = age + 5

# Display result
print(f"In 5 years, you will be {future_age} years old.")
```

**Sample Run:**
```
How old are you? 20
In 5 years, you will be 25 years old.
```

**Key Concepts:**
- **MUST** convert to int to do math
- Without conversion: `"20" + 5` causes a TypeError
- Convert immediately: `int(input(...))` in one line
- Then we can do arithmetic: `age + 5`

**What happens without conversion:**
```python
# WRONG - This will crash!
age = input("How old are you? ")
future_age = age + 5  # TypeError: can't add string and int
```

---

### Question 7
**Problem:** Get a decimal number from the user and print its value multiplied by 10.

**Solution Approach:**
- Get input from user
- Convert to float (for decimal numbers)
- Multiply by 10
- Display result

**Complete Solution:**
```python
# Get decimal number
number = float(input("Enter a decimal number: "))

# Multiply by 10
result = number * 10

# Display result
print(f"{number} multiplied by 10 is {result}")
```

**With formatting:**
```python
# Get decimal number
number = float(input("Enter a decimal number: "))

# Multiply by 10
result = number * 10

# Display with 2 decimal places
print(f"{number:.2f} multiplied by 10 is {result:.2f}")
```

**Sample Run:**
```
Enter a decimal number: 3.5
3.50 multiplied by 10 is 35.00
```

**Key Concepts:**
- Use `float()` for decimal numbers
- `int()` would fail on "3.5" - can't convert decimal string to int
- `:.2f` formats to 2 decimal places for cleaner output
- Multiplication works the same with floats as with ints

---

### Question 8
**Problem:** Ask for two integers and print their sum. Make sure to convert the inputs properly.

**Solution Approach:**
- Get two numbers from user
- Convert both to integers
- Add them together
- Display the result

**Complete Solution:**
```python
# Get two integers
num1 = int(input("Enter first number: "))
num2 = int(input("Enter second number: "))

# Calculate sum
sum_result = num1 + num2

# Display result
print(f"The sum of {num1} and {num2} is {sum_result}")
```

**Alternative - calculate directly in print:**
```python
# Get two integers
num1 = int(input("Enter first number: "))
num2 = int(input("Enter second number: "))

# Calculate and display in one line
print(f"{num1} + {num2} = {num1 + num2}")
```

**Sample Run:**
```
Enter first number: 15
Enter second number: 27
The sum of 15 and 27 is 42
```

**Key Concepts:**
- Both inputs must be converted to int
- Without conversion: `"15" + "27"` = `"1527"` (string concatenation!)
- With conversion: `15 + 27` = `42` (proper addition)
- Can do calculation directly in f-string: `{num1 + num2}`

**Common mistake:**
```python
# WRONG - This concatenates strings!
num1 = input("Enter first number: ")
num2 = input("Enter second number: ")
print(num1 + num2)  # "15" + "27" = "1527"
```

---

### Question 9
**Problem:** Get a temperature in Celsius from the user (as a float) and convert it to Fahrenheit using the formula F = C × 9/5 + 32.

**Solution Approach:**
- Get Celsius temperature (float for decimals)
- Apply conversion formula: F = C × 9/5 + 32
- Display both temperatures

**Complete Solution:**
```python
# Get Celsius temperature
celsius = float(input("Enter temperature in Celsius: "))

# Convert to Fahrenheit
fahrenheit = celsius * 9/5 + 32

# Display result
print(f"{celsius}°C is equal to {fahrenheit}°F")
```

**With formatted output:**
```python
# Get Celsius temperature
celsius = float(input("Enter temperature in Celsius: "))

# Convert to Fahrenheit
fahrenheit = celsius * 9/5 + 32

# Display with 1 decimal place
print(f"{celsius:.1f}°C is equal to {fahrenheit:.1f}°F")
```

**Sample Run:**
```
Enter temperature in Celsius: 25
25.0°C is equal to 77.0°F
```

**Key Concepts:**
- Formula: F = C × 9/5 + 32
- Order of operations: multiplication and division before addition
- Could also write: `(celsius * 9/5) + 32` (same result)
- Or: `celsius * (9/5) + 32` (clearer intent)
- `9/5` = `1.8`, so formula becomes: `celsius * 1.8 + 32`

---

### Question 10
**Problem:** Ask the user for a price and how many items they want. Calculate and display the total cost.

**Solution Approach:**
- Get price per item (float for decimals)
- Get quantity (int for whole items)
- Calculate total: price × quantity
- Display result

**Complete Solution:**
```python
# Get price and quantity
price = float(input("Enter price per item: $"))
quantity = int(input("How many items? "))

# Calculate total
total = price * quantity

# Display result
print(f"Total cost: ${total:.2f}")
```

**Sample Run:**
```
Enter price per item: $12.99
How many items? 3
Total cost: $38.97
```

**Key Concepts:**
- Price should be float (allows $12.99)
- Quantity should be int (can't buy 2.5 items usually)
- `:.2f` formats money to 2 decimal places
- Notice $ in prompt but user doesn't type it
- Result: clean currency display

---

## Different Print Formats (Questions 11-15)

### Question 11
**Problem:** Ask for a user's name and age. Print them using concatenation (with +), then print them using commas, then print them using an f-string.

**Solution Approach:**
- Get name (string) and age (keep as string for concatenation demo)
- Show all three printing methods
- Highlight differences between them

**Complete Solution:**
```python
# Get user input
name = input("What is your name? ")
age = input("What is your age? ")

# Method 1: Concatenation (requires all strings)
print("=== Using Concatenation ===")
print("Name: " + name + ", Age: " + age)

# Method 2: Commas (auto-converts, adds spaces)
print("\n=== Using Commas ===")
print("Name:", name, ", Age:", age)

# Method 3: F-strings (cleanest)
print("\n=== Using F-strings ===")
print(f"Name: {name}, Age: {age}")
```

**If age needs to be a number:**
```python
# Get user input
name = input("What is your name? ")
age = int(input("What is your age? "))

# Method 1: Concatenation (MUST cast age to string)
print("=== Using Concatenation ===")
print("Name: " + name + ", Age: " + str(age))

# Method 2: Commas (auto-converts - no casting needed)
print("\n=== Using Commas ===")
print("Name:", name, ", Age:", age)

# Method 3: F-strings (auto-converts - no casting needed)
print("\n=== Using F-strings ===")
print(f"Name: {name}, Age: {age}")
```

**Sample Run:**
```
What is your name? Alice
What is your age? 25

=== Using Concatenation ===
Name: Alice, Age: 25

=== Using Commas ===
Name: Alice , Age: 25

=== Using F-strings ===
Name: Alice, Age: 25
```

**Key Concepts:**

| Method | Pros | Cons |
|--------|------|------|
| Concatenation | Precise control | Must cast numbers, verbose |
| Commas | Auto-converts | Adds spaces (see ", Age:") |
| F-strings | Clean, no casting | None - use this! |

---

### Question 12
**Problem:** Get three favorite foods from the user and print them on the same line, separated by commas.

**Solution Approach:**
- Get three food inputs
- Print all on one line with commas between
- Multiple ways to accomplish this

**Complete Solution:**
```python
# Get three favorite foods
food1 = input("Enter your first favorite food: ")
food2 = input("Enter your second favorite food: ")
food3 = input("Enter your third favorite food: ")

# Print on one line, separated by commas
print(f"Your favorite foods are: {food1}, {food2}, {food3}")
```

**Alternative methods:**
```python
# Method 2: Using concatenation
print("Your favorite foods are: " + food1 + ", " + food2 + ", " + food3)

# Method 3: Using sep parameter
print("Your favorite foods are:", food1, food2, food3, sep=", ")

# Method 4: Join method (more advanced)
foods = [food1, food2, food3]
print("Your favorite foods are: " + ", ".join(foods))
```

**Sample Run:**
```
Enter your first favorite food: Pizza
Enter your second favorite food: Sushi
Enter your third favorite food: Tacos
Your favorite foods are: Pizza, Sushi, Tacos
```

**Key Concepts:**
- F-strings are cleanest: `f"{food1}, {food2}, {food3}"`
- `sep=", "` changes default separator in print
- All methods produce same output
- Choose based on readability

---

### Question 13
**Problem:** Ask for a number and print it with exactly 2 decimal places, then with 4 decimal places.

**Solution Approach:**
- Get number as float
- Use format specifiers to control decimal places
- `:.2f` for 2 decimals, `:.4f` for 4 decimals

**Complete Solution:**
```python
# Get number from user
number = float(input("Enter a number: "))

# Print with 2 decimal places
print(f"With 2 decimals: {number:.2f}")

# Print with 4 decimal places
print(f"With 4 decimals: {number:.4f}")
```

**Sample Run:**
```
Enter a number: 3.14159
With 2 decimals: 3.14
With 4 decimals: 3.1416
```

**Key Concepts:**
- Format specifier: `{value:.Xf}` where X is number of decimals
- `:.2f` rounds to 2 places (doesn't just truncate)
- `:.4f` rounds to 4 places
- If number has fewer decimals, zeros are added: `3.1` → `3.1000`
- This is called "fixed-point" notation (the `f` in `.2f`)

**Examples with different inputs:**
```python
# Input: 5
# Output: 5.00 and 5.0000

# Input: 2.7
# Output: 2.70 and 2.7000

# Input: 1.23456789
# Output: 1.23 and 1.2346 (rounds!)
```

---

### Question 14
**Problem:** Create a program that asks for length and width, then prints "The area is [area]" where the area is shown with 1 decimal place.

**Solution Approach:**
- Get length and width (floats)
- Calculate area = length × width
- Display with 1 decimal place using `:.1f`

**Complete Solution:**
```python
# Get dimensions
length = float(input("Enter the length: "))
width = float(input("Enter the width: "))

# Calculate area
area = length * width

# Display with 1 decimal place
print(f"The area is {area:.1f}")
```

**Sample Run:**
```
Enter the length: 12.5
Enter the width: 8.3
The area is 103.8
```

**Key Concepts:**
- `:.1f` formats to exactly 1 decimal place
- Even if calculation gives more decimals, it rounds
- Example: 103.75 → 103.8 (rounded)
- Format happens in the print, not in calculation
- Original value still stored with full precision

---

### Question 15
**Problem:** Get a large number from the user and display it with commas as thousands separators (e.g., 1,234,567).

**Solution Approach:**
- Get number from user
- Use `:,` format specifier to add thousands separators
- Works with both int and float

**Complete Solution:**
```python
# Get large number
number = int(input("Enter a large number: "))

# Display with thousands separators
print(f"Formatted number: {number:,}")
```

**For decimal numbers:**
```python
# Get number as float
number = float(input("Enter a large number: "))

# Display with commas and 2 decimal places
print(f"Formatted number: {number:,.2f}")
```

**Sample Run:**
```
Enter a large number: 1234567
Formatted number: 1,234,567
```

**With decimals:**
```
Enter a large number: 1234567.89
Formatted number: 1,234,567.89
```

**Key Concepts:**
- `:,` adds thousands separators
- `:,.2f` combines separators with decimal places
- Makes large numbers readable
- Works automatically regardless of number size
- Examples:
  - `1000` → `1,000`
  - `1000000` → `1,000,000`
  - `999` → `999` (no comma needed)

---

## Combined Calculations (Questions 16-20)

### Question 16
**Problem:** Create a simple tip calculator: get the bill amount and tip percentage, calculate the tip amount and total bill.

**Solution Approach:**
- Get bill amount (float)
- Get tip percentage (can enter as 15 or 0.15)
- Calculate tip amount
- Calculate total (bill + tip)
- Display all values

**Complete Solution:**
```python
# Get bill amount and tip percentage
bill_amount = float(input("Enter bill amount: $"))
tip_percent = float(input("Enter tip percentage (e.g., 15 for 15%): "))

# Convert percentage to decimal if needed
tip_rate = tip_percent / 100

# Calculate tip and total
tip_amount = bill_amount * tip_rate
total = bill_amount + tip_amount

# Display results
print(f"\nBill: ${bill_amount:.2f}")
print(f"Tip ({tip_percent}%): ${tip_amount:.2f}")
print(f"Total: ${total:.2f}")
```

**Sample Run:**
```
Enter bill amount: $45.50
Enter tip percentage (e.g., 15 for 15%): 20

Bill: $45.50
Tip (20.0%): $9.10
Total: $54.60
```

**Key Concepts:**
- Convert percentage to decimal: `tip_percent / 100`
- Tip = bill × rate
- Total = bill + tip
- Format all money values with `:.2f`
- Clear output shows breakdown

---

### Question 17
**Problem:** Ask for hours worked and hourly rate, then calculate and display the gross pay.

**Solution Approach:**
- Get hours worked (float for partial hours)
- Get hourly rate (float for decimal rates)
- Calculate gross pay = hours × rate
- Display formatted result

**Complete Solution:**
```python
# Get work information
hours_worked = float(input("Enter hours worked: "))
hourly_rate = float(input("Enter hourly rate: $"))

# Calculate gross pay
gross_pay = hours_worked * hourly_rate

# Display result
print(f"\nHours worked: {hours_worked}")
print(f"Hourly rate: ${hourly_rate:.2f}")
print(f"Gross pay: ${gross_pay:.2f}")
```

**Sample Run:**
```
Enter hours worked: 37.5
Enter hourly rate: $15.50

Hours worked: 37.5
Hourly rate: $15.50
Gross pay: $581.25
```

**Key Concepts:**
- Simple formula: pay = hours × rate
- Use float for hours (allows 37.5 hours)
- Use float for rate (allows $15.50)
- Format money with `:.2f`
- Shows all input values for verification

---

### Question 18
**Problem:** Build a miles-to-kilometers converter (1 mile = 1.60934 km). Get miles from user and display kilometers.

**Solution Approach:**
- Define conversion constant
- Get miles from user
- Convert to kilometers
- Display result

**Complete Solution:**
```python
# Conversion constant
KM_PER_MILE = 1.60934

# Get miles from user
miles = float(input("Enter distance in miles: "))

# Convert to kilometers
kilometers = miles * KM_PER_MILE

# Display result
print(f"{miles} miles is equal to {kilometers:.2f} kilometers")
```

**Sample Run:**
```
Enter distance in miles: 10
10.0 miles is equal to 16.09 kilometers
```

**Key Concepts:**
- Constant in UPPERCASE: `KM_PER_MILE`
- Simple multiplication for conversion
- `:.2f` formats to 2 decimal places
- Could also offer reverse conversion

**Bidirectional converter:**
```python
KM_PER_MILE = 1.60934

miles = float(input("Enter distance in miles: "))
kilometers = miles * KM_PER_MILE

print(f"{miles} miles = {kilometers:.2f} km")
print(f"{kilometers:.2f} km = {miles} miles")
```

---

### Question 19
**Problem:** Create a program that calculates BMI: get weight in kg and height in meters, then calculate BMI = weight / (height²).

**Solution Approach:**
- Get weight in kg (float)
- Get height in meters (float)
- Calculate BMI using formula
- Display result with interpretation

**Complete Solution:**
```python
# Get user measurements
weight = float(input("Enter your weight in kg: "))
height = float(input("Enter your height in meters: "))

# Calculate BMI
bmi = weight / (height ** 2)

# Display result
print(f"\nWeight: {weight} kg")
print(f"Height: {height} m")
print(f"BMI: {bmi:.1f}")
```

**With BMI categories:**
```python
# Get user measurements
weight = float(input("Enter your weight in kg: "))
height = float(input("Enter your height in meters: "))

# Calculate BMI
bmi = weight / (height ** 2)

# Display result
print(f"\nWeight: {weight} kg")
print(f"Height: {height} m")
print(f"BMI: {bmi:.1f}")

# Basic categories (simplified)
print("\nBMI Categories:")
print("Below 18.5: Underweight")
print("18.5-24.9: Normal weight")
print("25-29.9: Overweight")
print("30+: Obese")
```

**Sample Run:**
```
Enter your weight in kg: 70
Enter your height in meters: 1.75

Weight: 70.0 kg
Height: 1.75 m
BMI: 22.9
```

**Key Concepts:**
- Formula: BMI = weight / height²
- Use `**` for exponentiation: `height ** 2`
- Parentheses crucial: `weight / (height ** 2)`
- Without parentheses: wrong calculation
- Format BMI to 1 decimal: `:.1f`

---

### Question 20
**Problem:** Make a compound interest calculator: get principal, rate (as percentage), and years. Calculate final amount using A = P(1 + r/100)^t.

**Solution Approach:**
- Get principal amount (float)
- Get interest rate as percentage (float)
- Get time in years (int or float)
- Apply compound interest formula
- Display results

**Complete Solution:**
```python
# Get investment information
principal = float(input("Enter principal amount: $"))
rate_percent = float(input("Enter annual interest rate (%): "))
years = float(input("Enter number of years: "))

# Convert percentage to decimal
rate = rate_percent / 100

# Calculate final amount: A = P(1 + r)^t
final_amount = principal * ((1 + rate) ** years)

# Calculate interest earned
interest_earned = final_amount - principal

# Display results
print(f"\nInvestment Summary:")
print(f"Principal: ${principal:.2f}")
print(f"Interest rate: {rate_percent}%")
print(f"Time: {years} years")
print(f"Final amount: ${final_amount:.2f}")
print(f"Interest earned: ${interest_earned:.2f}")
```

**Sample Run:**
```
Enter principal amount: $1000
Enter annual interest rate (%): 5
Enter number of years: 3

Investment Summary:
Principal: $1000.00
Interest rate: 5.0%
Time: 3.0 years
Final amount: $1157.63
Interest earned: $157.63
```

**Key Concepts:**
- Formula: A = P(1 + r/100)^t
- Or with r as decimal: A = P(1 + r)^t
- Convert percentage: `rate = rate_percent / 100`
- Use `**` for exponentiation
- Parentheses ensure correct order: `(1 + rate) ** years`
- Interest earned = final - principal

---

## Complex Programs (Questions 21-25)

### Question 21
**Problem:** Create a "Mad Libs" program: ask for a noun, verb, adjective, and adverb, then create a funny sentence using all four words.

**Solution Approach:**
- Get four different word types from user
- Create a sentence template with blanks
- Insert the words into the template
- Display the funny result

**Complete Solution:**
```python
# Get words from user
print("Let's play Mad Libs!")
print("=" * 30)

noun = input("Enter a noun: ")
verb = input("Enter a verb: ")
adjective = input("Enter an adjective: ")
adverb = input("Enter an adverb: ")

# Create the mad lib story
print(f"\n=== YOUR MAD LIB STORY ===")
print(f"The {adjective} {noun} decided to {verb} {adverb}.")
print(f"Everyone was amazed by how {adverb} the {noun} could {verb}!")
```

**More elaborate version:**
```python
# Get words from user
print("=== MAD LIBS GAME ===")
noun1 = input("Enter a noun: ")
noun2 = input("Enter another noun: ")
verb1 = input("Enter a verb: ")
verb2 = input("Enter another verb: ")
adjective = input("Enter an adjective: ")
adverb = input("Enter an adverb: ")
place = input("Enter a place: ")

# Create the story
print(f"\n=== YOUR SILLY STORY ===")
print(f"Once upon a time, a {adjective} {noun1} went to {place}.")
print(f"There, it decided to {verb1} a {noun2} {adverb}.")
print(f"Everyone watched as the {noun1} continued to {verb2}.")
print(f"It was the most {adjective} thing anyone had ever seen!")
```

**Sample Run:**
```
=== MAD LIBS GAME ===
Enter a noun: penguin
Enter another noun: pizza
Enter a verb: dance
Enter another verb: sing
Enter an adjective: sparkly
Enter an adverb: quietly
Enter a place: moon

=== YOUR SILLY STORY ===
Once upon a time, a sparkly penguin went to moon.
There, it decided to dance a pizza quietly.
Everyone watched as the penguin continued to sing.
It was the most sparkly thing anyone had ever seen!
```

**Key Concepts:**
- All inputs are strings (no conversion needed)
- F-strings make sentence building easy
- Can create any story template you want
- Multiple sentences make it more interesting
- This is pure string manipulation - no math!

---

### Question 22
**Problem:** Build a pizza order calculator: ask for number of pizzas, price per pizza, and delivery fee. Calculate subtotal, add 8% tax, and show a formatted receipt with all values.

**Solution Approach:**
- Get order details (pizzas, price, delivery fee)
- Calculate subtotal = pizzas × price + delivery
- Calculate tax = subtotal × 0.08
- Calculate total = subtotal + tax
- Display formatted receipt

**Complete Solution:**
```python
# Get order information
print("=== PIZZA ORDER SYSTEM ===")
num_pizzas = int(input("How many pizzas? "))
price_per_pizza = float(input("Price per pizza: $"))
delivery_fee = float(input("Delivery fee: $"))

# Constants
TAX_RATE = 0.08  # 8% tax

# Calculate costs
pizza_cost = num_pizzas * price_per_pizza
subtotal = pizza_cost + delivery_fee
tax = subtotal * TAX_RATE
total = subtotal + tax

# Display receipt
print("\n" + "=" * 40)
print("           PIZZA RECEIPT")
print("=" * 40)
print(f"Pizzas: {num_pizzas} x ${price_per_pizza:.2f} = ${pizza_cost:.2f}")
print(f"Delivery Fee:              ${delivery_fee:.2f}")
print("-" * 40)
print(f"Subtotal:                  ${subtotal:.2f}")
print(f"Tax (8%):                  ${tax:.2f}")
print("=" * 40)
print(f"TOTAL:                     ${total:.2f}")
print("=" * 40)
```

**Sample Run:**
```
=== PIZZA ORDER SYSTEM ===
How many pizzas? 3
Price per pizza: $12.99
Delivery fee: $5.00

========================================
           PIZZA RECEIPT
========================================
Pizzas: 3 x $12.99 = $38.97
Delivery Fee:              $5.00
----------------------------------------
Subtotal:                  $43.97
Tax (8%):                  $3.52
========================================
TOTAL:                     $47.49
========================================
```

**Key Concepts:**
- Multiple calculation steps build to final total
- Format all currency with `:.2f`
- Use separators (`=`, `-`) for visual structure
- Constants (TAX_RATE) in uppercase
- Alignment makes receipt professional looking
- Shows breakdown so customer can verify

---

### Question 23
**Problem:** Create a grade calculator: ask for points earned and points possible, calculate the percentage, and display it formatted as "You earned XX.X%".

**Solution Approach:**
- Get points earned (float)
- Get points possible (float)
- Calculate percentage = (earned / possible) × 100
- Display with 1 decimal place

**Complete Solution:**
```python
# Get grade information
points_earned = float(input("Enter points earned: "))
points_possible = float(input("Enter points possible: "))

# Calculate percentage
percentage = (points_earned / points_possible) * 100

# Display result
print(f"\nYou earned {percentage:.1f}%")
```

**Enhanced version with letter grade:**
```python
# Get grade information
points_earned = float(input("Enter points earned: "))
points_possible = float(input("Enter points possible: "))

# Calculate percentage
percentage = (points_earned / points_possible) * 100

# Display result
print(f"\n=== GRADE REPORT ===")
print(f"Points earned: {points_earned}")
print(f"Points possible: {points_possible}")
print(f"Percentage: {percentage:.1f}%")

# Show letter grade ranges (info only at this stage)
print("\nLetter Grade Scale:")
print("90-100: A")
print("80-89: B")
print("70-79: C")
print("60-69: D")
print("Below 60: F")
```

**Sample Run:**
```
Enter points earned: 87
Enter points possible: 100

=== GRADE REPORT ===
Points earned: 87.0
Points possible: 100.0
Percentage: 87.0%
```

**Key Concepts:**
- Formula: percentage = (earned / possible) × 100
- Parentheses ensure division happens first
- `:.1f` formats to 1 decimal place
- Works for any point values (not just /100)
- Example: 43/50 = 86% works correctly

---

### Question 24
**Problem:** Make a currency converter: get amount in USD, ask for exchange rate, calculate equivalent in foreign currency, and show both amounts with proper formatting.

**Solution Approach:**
- Get USD amount (float)
- Get exchange rate (float)
- Calculate foreign amount = USD × rate
- Display both amounts formatted

**Complete Solution:**
```python
# Get conversion information
print("=== CURRENCY CONVERTER ===")
usd_amount = float(input("Enter amount in USD: $"))
currency_name = input("Enter target currency (e.g., EUR, GBP): ")
exchange_rate = float(input(f"Enter exchange rate (1 USD = ? {currency_name}): "))

# Calculate foreign currency amount
foreign_amount = usd_amount * exchange_rate

# Display results
print(f"\n=== CONVERSION RESULT ===")
print(f"${usd_amount:.2f} USD")
print(f"= {foreign_amount:.2f} {currency_name}")
print(f"\nExchange rate: 1 USD = {exchange_rate} {currency_name}")
```

**Sample Run:**
```
=== CURRENCY CONVERTER ===
Enter amount in USD: $100
Enter target currency (e.g., EUR, GBP): EUR
Enter exchange rate (1 USD = ? EUR): 0.85

=== CONVERSION RESULT ===
$100.00 USD
= 85.00 EUR

Exchange rate: 1 USD = 0.85 EUR
```

**Key Concepts:**
- Simple multiplication: foreign = USD × rate
- Getting currency name makes output more meaningful
- Format all money values with `:.2f`
- Could extend to handle reverse conversion
- Clear display shows the conversion calculation

---

### Question 25
**Problem:** Build a travel time calculator: ask for distance in miles and average speed in mph. Calculate time in hours (as decimal), then break it down into hours and minutes. Display both formats. (Hint: use // for hours and % for remaining minutes)

**Solution Approach:**
- Get distance and speed (both floats)
- Calculate time in hours (decimal) = distance / speed
- Convert to hours and minutes:
  - Hours = time // 1 (whole hours)
  - Minutes = (time % 1) × 60 (decimal part to minutes)
- Display both formats

**Complete Solution:**
```python
# Get travel information
print("=== TRAVEL TIME CALCULATOR ===")
distance = float(input("Enter distance in miles: "))
speed = float(input("Enter average speed in mph: "))

# Calculate time in hours (decimal)
time_hours = distance / speed

# Break down into hours and minutes
hours = int(time_hours)  # Whole hours
minutes = int((time_hours % 1) * 60)  # Decimal part to minutes

# Display results
print(f"\n=== TRAVEL TIME ===")
print(f"Distance: {distance} miles")
print(f"Speed: {speed} mph")
print(f"\nTime (decimal): {time_hours:.2f} hours")
print(f"Time (formatted): {hours} hours and {minutes} minutes")
```

**Alternative approach using // and %:**
```python
# Get travel information
print("=== TRAVEL TIME CALCULATOR ===")
distance = float(input("Enter distance in miles: "))
speed = float(input("Enter average speed in mph: "))

# Calculate total minutes
total_minutes = (distance / speed) * 60

# Break down into hours and minutes
hours = int(total_minutes // 60)
minutes = int(total_minutes % 60)

# Calculate decimal hours
time_hours = distance / speed

# Display results
print(f"\n=== TRAVEL TIME ===")
print(f"Distance: {distance} miles")
print(f"Speed: {speed} mph")
print(f"Time: {time_hours:.2f} hours")
print(f"Time: {hours} hours and {minutes} minutes")
```

**Sample Run:**
```
=== TRAVEL TIME CALCULATOR ===
Enter distance in miles: 175
Enter average speed in mph: 65

=== TRAVEL TIME ===
Distance: 175.0 miles
Speed: 65.0 mph
Time: 2.69 hours
Time: 2 hours and 41 minutes
```

**Key Concepts:**
- Basic formula: time = distance / speed
- Convert decimal hours to hours:minutes
- Method 1: 
  - Hours: `int(time_hours)` gets whole part
  - Minutes: `(time_hours % 1) * 60` converts decimal to minutes
- Method 2:
  - Convert everything to minutes first
  - Use `// 60` for hours, `% 60` for remaining minutes
- Both formats give users different perspectives on time

**Why the math works:**
- 2.69 hours means 2 hours + 0.69 hours
- 0.69 hours × 60 min/hour = 41.4 minutes ≈ 41 minutes
- `%` operator gets decimal part: `2.69 % 1 = 0.69`

---

## Summary: Key Patterns for Input/Output Problems

### Input Best Practices
1. **Always provide clear prompts**: Tell users what to enter
2. **Cast immediately**: `int(input(...))` or `float(input(...))`
3. **Remember input() returns strings**: Convert for calculations
4. **Use appropriate types**: 
   - Text → no conversion
   - Whole numbers → int
   - Decimals → float

### Output Best Practices
1. **Use f-strings** for modern, clean formatting
2. **Format numbers appropriately**:
   - Money: `{value:.2f}`
   - Percentages: `{value:.1f}%`
   - Thousands: `{value:,}`
3. **Add labels**: Don't just print numbers
4. **Structure output**: Use blank lines, separators

### Common Patterns
1. **Get input → Convert → Calculate → Display**
2. **Use constants for fixed values** (TAX_RATE, etc.)
3. **Show work**: Display input values for verification
4. **Format professionally**: Align values, use appropriate decimals
5. **Test with different inputs**: Try decimals, negatives, zeros

### Error Prevention
- **Casting issues**: Can't do `int("12.5")` - use float first
- **Concatenation**: Can't do `"Age: " + 25` - must use str(25) or f-string
- **Order of operations**: Use parentheses to be clear
- **Division by zero**: Will cause error (we'll handle this later with if statements)