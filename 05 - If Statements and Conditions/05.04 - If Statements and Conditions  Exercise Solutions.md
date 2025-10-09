# Chapter 5: If Statements and Conditions - Solutions Guide

## Basic If Statements and Code Blocks (Questions 1-5)

### Question 1
**Problem:** Write a program that asks for a number and prints "Positive" if it's greater than 0. Include a print statement outside the if block that always displays "Program complete".

**Solution Approach:**
- Get a number from the user
- Check if number > 0 using an if statement
- The "Positive" message is INSIDE the code block (indented)
- The "Program complete" message is OUTSIDE the code block (same level as if)
- Outside statements always run, regardless of the condition

**Complete Solution:**
```python
# Get number from user
number = int(input("Enter a number: "))

# Check if positive
if number > 0:
    print("Positive")

# This line is outside the if block - always runs
print("Program complete")
```

**Sample Run (positive number):**
```
Enter a number: 5
Positive
Program complete
```

**Sample Run (non-positive number):**
```
Enter a number: -3
Program complete
```

**Key Concepts:**
- Code block is created by indentation after the colon
- Inside block: `print("Positive")` - only runs if condition is True
- Outside block: `print("Program complete")` - always runs
- The if statement does not need an else clause

---

### Question 2
**Problem:** Ask for a person's age and print "You can vote" if they are 18 or older. Make sure your code block includes TWO print statements that only run when the condition is true.

**Solution Approach:**
- Use >= operator to check if age is 18 or more
- Both print statements must have the same indentation (in the same code block)
- If age < 18, neither statement runs

**Complete Solution:**
```python
# Get age from user
age = int(input("Enter your age: "))

# Check voting eligibility
if age >= 18:
    print("You can vote")
    print("Remember to register!")
```

**Sample Run (eligible):**
```
Enter your age: 21
You can vote
Remember to register!
```

**Sample Run (not eligible):**
```
Enter your age: 16
```

**Key Concepts:**
- Both print statements are at the same indentation level (both in the code block)
- Code block can contain multiple statements
- If condition is False, entire code block is skipped
- No output for age < 18 (no else clause provided)

---

### Question 3
**Problem:** Create a program that checks if a password is correct. Use "python123" as the correct password. Print "Access granted" and "Welcome to the system" in the code block if correct. Print "Done checking" outside the block.

**Solution Approach:**
- Compare user input to the correct password string
- Two messages inside the if block (both indented)
- One message outside the if block (at same level as if)
- The outside message runs whether password is correct or not

**Complete Solution:**
```python
# Define correct password
correct_password = "python123"

# Get password from user
password = input("Enter password: ")

# Check password
if password == correct_password:
    print("Access granted")
    print("Welcome to the system")

# This always runs
print("Done checking")
```

**Sample Run (correct password):**
```
Enter password: python123
Access granted
Welcome to the system
Done checking
```

**Sample Run (incorrect password):**
```
Enter password: wrong
Done checking
```

**Key Concepts:**
- Use == for comparison (not = which is assignment)
- Strings are case-sensitive: "Python123" != "python123"
- The "Done checking" line runs in both cases
- Code block contains multiple related statements

---

### Question 4
**Problem:** Ask for a temperature and print "It's freezing" with "Wear a heavy coat" if the temperature is below 32. These should be in the same code block.

**Solution Approach:**
- Use < operator to check if temperature is below 32
- Both messages must be indented the same amount (same code block)
- If temperature >= 32, no output is produced

**Complete Solution:**
```python
# Get temperature from user
temperature = int(input("Enter temperature in Fahrenheit: "))

# Check if freezing
if temperature < 32:
    print("It's freezing")
    print("Wear a heavy coat")
```

**Sample Run (freezing):**
```
Enter temperature in Fahrenheit: 20
It's freezing
Wear a heavy coat
```

**Sample Run (not freezing):**
```
Enter temperature in Fahrenheit: 45
```

**Key Concepts:**
- The < operator checks "less than"
- 32°F is the freezing point of water
- Both statements must be indented to be in the code block
- No output if condition is False (could add else for this)

---

### Question 5
**Problem:** Write a program that checks if a number is even (use % operator). If even, print "Even number", "Divisible by 2", and "No remainder" - all in the same code block.

**Solution Approach:**
- Use modulo operator (%) to check remainder when dividing by 2
- If remainder is 0, the number is even
- All three print statements must be in the code block (same indentation)

**Complete Solution:**
```python
# Get number from user
number = int(input("Enter a number: "))

# Check if even
if number % 2 == 0:
    print("Even number")
    print("Divisible by 2")
    print("No remainder")
```

**Sample Run (even number):**
```
Enter a number: 8
Even number
Divisible by 2
No remainder
```

**Sample Run (odd number):**
```
Enter a number: 7
```

**Key Concepts:**
- `%` (modulo) returns the remainder after division
- `number % 2 == 0` means "remainder when divided by 2 equals 0"
- Even numbers have no remainder when divided by 2
- All three statements execute together when condition is True
- Multiple related statements can be in one code block

---

## If-Else Statements (Questions 6-10)

### Question 6
**Problem:** Ask for a number and print "Positive" if > 0, otherwise print "Not positive". Each branch should have TWO print statements.

**Solution Approach:**
- Use if-else structure for two mutually exclusive options
- If block runs when number > 0
- Else block runs when number <= 0
- Each block needs two print statements

**Complete Solution:**
```python
# Get number from user
number = int(input("Enter a number: "))

# Check if positive
if number > 0:
    print("Positive")
    print("The number is greater than zero")
else:
    print("Not positive")
    print("The number is zero or negative")
```

**Sample Run (positive):**
```
Enter a number: 5
Positive
The number is greater than zero
```

**Sample Run (not positive):**
```
Enter a number: -3
Not positive
The number is zero or negative
```

**Key Concepts:**
- If-else ensures ONE branch always executes
- Both blocks have the same indentation level relative to their keywords
- "Not positive" includes both zero and negative numbers
- Each branch can have multiple statements

---

### Question 7
**Problem:** Create a pass/fail system. If score >= 60, print "Pass" and "Congratulations", otherwise print "Fail" and "Study harder".

**Solution Approach:**
- Passing threshold is 60
- Use >= operator for the passing condition
- If score >= 60: pass messages
- Else: fail messages

**Complete Solution:**
```python
# Get score from user
score = int(input("Enter your score: "))

# Determine pass/fail
if score >= 60:
    print("Pass")
    print("Congratulations")
else:
    print("Fail")
    print("Study harder")
```

**Sample Run (passing):**
```
Enter your score: 75
Pass
Congratulations
```

**Sample Run (failing):**
```
Enter your score: 45
Fail
Study harder
```

**Key Concepts:**
- `>=` means "greater than or equal to"
- Score of exactly 60 is a pass
- Clear binary outcome: pass or fail
- Motivational messages in each branch

---

### Question 8
**Problem:** Check if a person can drive. If age >= 16, print "You can drive" and "Get your license", else print "Too young" and "Wait X years" (calculate X).

**Solution Approach:**
- Driving age is 16 in most places
- If age >= 16: can drive
- If age < 16: too young, calculate years to wait
- Years to wait = 16 - current_age

**Complete Solution:**
```python
# Get age from user
age = int(input("Enter your age: "))

# Check driving eligibility
if age >= 16:
    print("You can drive")
    print("Get your license")
else:
    years_to_wait = 16 - age
    print("Too young")
    print(f"Wait {years_to_wait} years")
```

**Sample Run (can drive):**
```
Enter your age: 18
You can drive
Get your license
```

**Sample Run (too young):**
```
Enter your age: 13
Too young
Wait 3 years
```

**Key Concepts:**
- Calculation can happen inside the else block
- Use f-string to display calculated value
- 16 - age gives years until eligible
- Each block provides specific, relevant information

---

### Question 9
**Problem:** Ask for a day number (1-7). If it's 6 or 7, print "Weekend", otherwise print "Weekday". Use if-else structure.

**Solution Approach:**
- Days 6 and 7 represent Saturday and Sunday
- Use OR operator to check if day is 6 OR 7
- If either condition is True: weekend
- Else: weekday

**Complete Solution:**
```python
# Get day number from user
day = int(input("Enter day number (1-7): "))

# Check if weekend
if day == 6 or day == 7:
    print("Weekend")
else:
    print("Weekday")
```

**Alternative approach:**
```python
# Get day number from user
day = int(input("Enter day number (1-7): "))

# Check if weekend using range
if day >= 6:
    print("Weekend")
else:
    print("Weekday")
```

**Sample Run (weekend):**
```
Enter day number (1-7): 6
Weekend
```

**Sample Run (weekday):**
```
Enter day number (1-7): 3
Weekday
```

**Key Concepts:**
- OR operator: at least one condition must be True
- `day == 6 or day == 7` is True when day is either 6 or 7
- Alternative: `day >= 6` works if 6-7 are the only weekend days
- Simple binary classification using if-else

---

### Question 10
**Problem:** Create a simple even/odd checker. Print "Even" with "Divisible by 2" for even numbers, print "Odd" with "Has remainder" for odd numbers.

**Solution Approach:**
- Even numbers: remainder of 0 when divided by 2
- Odd numbers: remainder of 1 when divided by 2
- Use modulo operator (%)
- Each branch has two print statements

**Complete Solution:**
```python
# Get number from user
number = int(input("Enter a number: "))

# Check even or odd
if number % 2 == 0:
    print("Even")
    print("Divisible by 2")
else:
    print("Odd")
    print("Has remainder")
```

**Sample Run (even):**
```
Enter a number: 10
Even
Divisible by 2
```

**Sample Run (odd):**
```
Enter a number: 7
Odd
Has remainder
```

**Key Concepts:**
- `number % 2 == 0`: even (no remainder)
- `number % 2 != 0`: odd (has remainder) - this is the else case
- If-else covers all integers (all numbers are either even or odd)
- Modulo is the standard way to check even/odd

---

## If-Elif-Else Chains (Questions 11-15)

### Question 11
**Problem:** Create a grade converter: 90-100 = A, 80-89 = B, 70-79 = C, 60-69 = D, below 60 = F. Print the grade with an appropriate message.

**Solution Approach:**
- Check from highest grade to lowest (most specific to least specific)
- Use >= operator for each threshold
- Once a condition matches, remaining elif blocks are skipped
- Order matters: check 90+ before 80+, etc.

**Complete Solution:**
```python
# Get score from user
score = int(input("Enter your score (0-100): "))

# Determine letter grade
if score >= 90:
    print("Grade: A")
    print("Excellent work!")
elif score >= 80:
    print("Grade: B")
    print("Good job!")
elif score >= 70:
    print("Grade: C")
    print("Satisfactory")
elif score >= 60:
    print("Grade: D")
    print("Needs improvement")
else:
    print("Grade: F")
    print("Please see instructor")
```

**Sample Run:**
```
Enter your score (0-100): 85
Grade: B
Good job!
```

**Key Concepts:**
- Order matters: check 90 before 80, 80 before 70, etc.
- If we checked 60 first, an 85 would incorrectly match (85 >= 60)
- Only ONE block executes - first True condition wins
- Else catches all scores below 60
- Each grade has a specific message

---

### Question 12
**Problem:** Build a BMI category system: <18.5 = Underweight, 18.5-24.9 = Normal, 25-29.9 = Overweight, 30+ = Obese. Ask for height and weight, calculate BMI, and categorize.

**Solution Approach:**
- BMI formula: weight (kg) / (height (m))²
- Or in pounds/inches: (weight / (height²)) × 703
- Check categories from lowest to highest
- Each elif adds the upper bound check

**Complete Solution:**
```python
# Get height and weight
height_inches = float(input("Enter height in inches: "))
weight_pounds = float(input("Enter weight in pounds: "))

# Calculate BMI
bmi = (weight_pounds / (height_inches ** 2)) * 703

# Display BMI
print(f"Your BMI: {bmi:.1f}")

# Categorize BMI
if bmi < 18.5:
    print("Category: Underweight")
    print("Consider consulting a nutritionist")
elif bmi < 25:
    print("Category: Normal weight")
    print("Maintain your healthy lifestyle")
elif bmi < 30:
    print("Category: Overweight")
    print("Consider diet and exercise")
else:
    print("Category: Obese")
    print("Consult with a healthcare provider")
```

**Sample Run:**
```
Enter height in inches: 68
Enter weight in pounds: 160
Your BMI: 24.3
Category: Normal weight
Maintain your healthy lifestyle
```

**Key Concepts:**
- BMI calculation requires floating-point division
- `**` operator raises to a power (height squared)
- Check boundaries from lowest to highest
- `bmi < 25` includes the range 18.5-24.9 (previous condition was False)
- Each elif implicitly includes the lower bound from previous conditions

---

### Question 13
**Problem:** Create a shipping cost calculator: 0-5 lbs = $5, 5-20 lbs = $10, 20-50 lbs = $20, over 50 lbs = $50. Ask for weight and display cost.

**Solution Approach:**
- Check weight ranges from lowest to highest
- Each range is mutually exclusive
- Use <= for upper bounds or < for strict less than
- Consider whether boundaries are inclusive (5 lbs in first or second category?)

**Complete Solution:**
```python
# Get package weight
weight = float(input("Enter package weight in pounds: "))

# Determine shipping cost
if weight <= 5:
    cost = 5
    print(f"Shipping cost: ${cost}")
    print("Standard ground shipping")
elif weight <= 20:
    cost = 10
    print(f"Shipping cost: ${cost}")
    print("Standard ground shipping")
elif weight <= 50:
    cost = 20
    print(f"Shipping cost: ${cost}")
    print("Heavy package rate")
else:
    cost = 50
    print(f"Shipping cost: ${cost}")
    print("Freight shipping required")
```

**Sample Run:**
```
Enter package weight in pounds: 15
Shipping cost: $10
Standard ground shipping
```

**Key Concepts:**
- Use <= to include the boundary value
- Exactly 5 lbs costs $5 (in first category)
- Each elif automatically excludes previous ranges
- Else handles anything over 50 lbs
- Store cost in variable for potential later use

---

### Question 14
**Problem:** Build a tax bracket calculator: $0-$10k = 10%, $10k-$40k = 12%, $40k-$85k = 22%, $85k+ = 24%. Ask for income and calculate tax owed.

**Solution Approach:**
- Check income brackets from lowest to highest
- Calculate tax as percentage of income
- Display both the rate and the amount owed
- Consider using float for precise calculations

**Complete Solution:**
```python
# Get annual income
income = float(input("Enter annual income: $"))

# Determine tax bracket and calculate tax
if income <= 10000:
    rate = 0.10
    tax = income * rate
    print(f"Tax bracket: 10%")
    print(f"Tax owed: ${tax:.2f}")
elif income <= 40000:
    rate = 0.12
    tax = income * rate
    print(f"Tax bracket: 12%")
    print(f"Tax owed: ${tax:.2f}")
elif income <= 85000:
    rate = 0.22
    tax = income * rate
    print(f"Tax bracket: 22%")
    print(f"Tax owed: ${tax:.2f}")
else:
    rate = 0.24
    tax = income * rate
    print(f"Tax bracket: 24%")
    print(f"Tax owed: ${tax:.2f}")

# Show take-home pay
take_home = income - tax
print(f"Take-home pay: ${take_home:.2f}")
```

**Sample Run:**
```
Enter annual income: $50000
Tax bracket: 22%
Tax owed: $11000.00
Take-home pay: $39000.00
```

**Key Concepts:**
- Use float for money calculations
- Store tax rate in a variable
- Format currency with `.2f` (2 decimal places)
- Calculate additional values (take-home) after determining bracket
- This is simplified - real tax brackets are more complex

---

### Question 15
**Problem:** Make a season detector: Ask for month number (1-12) and print which season it is (Winter: 12,1,2; Spring: 3,4,5; Summer: 6,7,8; Fall: 9,10,11).

**Solution Approach:**
- Use OR operators to check multiple months per season
- Could also use range checking (3 <= month <= 5)
- Winter is tricky: includes both December and January/February
- Order doesn't matter as much here (no overlapping categories)

**Complete Solution:**
```python
# Get month number
month = int(input("Enter month number (1-12): "))

# Determine season
if month == 12 or month == 1 or month == 2:
    print("Season: Winter")
    print("Bundle up!")
elif month == 3 or month == 4 or month == 5:
    print("Season: Spring")
    print("Flowers are blooming!")
elif month == 6 or month == 7 or month == 8:
    print("Season: Summer")
    print("Stay cool!")
elif month == 9 or month == 10 or month == 11:
    print("Season: Fall")
    print("Leaves are changing!")
else:
    print("Invalid month number")
```

**Alternative using range checking:**
```python
month = int(input("Enter month number (1-12): "))

if month in [12, 1, 2]:
    print("Season: Winter")
elif 3 <= month <= 5:
    print("Season: Spring")
elif 6 <= month <= 8:
    print("Season: Summer")
elif 9 <= month <= 11:
    print("Season: Fall")
else:
    print("Invalid month number")
```

**Sample Run:**
```
Enter month number (1-12): 7
Season: Summer
Stay cool!
```

**Key Concepts:**
- Multiple OR conditions check several values
- Winter spans year boundary (12, 1, 2)
- Range checking (3 <= month <= 5) is cleaner for consecutive months
- Else clause handles invalid input (month < 1 or month > 12)
- `in [list]` checks if value is in a list of options

---

## Compound Conditions with AND/OR (Questions 16-20)

### Question 16
**Problem:** Create a movie rating system. Person can watch if they're 17+ OR (13+ AND has parent permission). Ask for age and parent permission, then decide.

**Solution Approach:**
- Two ways to qualify: age >= 17 alone, OR age >= 13 with permission
- Use OR to connect the two conditions
- AND connects age and permission for younger viewers
- Parentheses make the logic clear

**Complete Solution:**
```python
# Get age and permission
age = int(input("Enter your age: "))
permission = input("Do you have parent permission? (yes/no): ")
has_permission = (permission.lower() == "yes")

# Check if can watch
if age >= 17 or (age >= 13 and has_permission):
    print("You can watch this movie")
    print("Enjoy the show!")
else:
    print("Sorry, you cannot watch this movie")
    if age < 13:
        print("Too young even with permission")
    else:
        print("You need parent permission")
```

**Sample Run (17+):**
```
Enter your age: 18
Do you have parent permission? (yes/no): no
You can watch this movie
Enjoy the show!
```

**Sample Run (13-16 with permission):**
```
Enter your age: 15
Do you have parent permission? (yes/no): yes
You can watch this movie
Enjoy the show!
```

**Sample Run (13-16 without permission):**
```
Enter your age: 15
Do you have parent permission? (yes/no): no
Sorry, you cannot watch this movie
You need parent permission
```

**Key Concepts:**
- OR: at least one condition must be True
- AND: both conditions must be True
- Parentheses group the AND condition
- `age >= 17` alone is sufficient (doesn't matter about permission)
- `(age >= 13 and has_permission)` is the alternative path
- Convert string input to boolean for clarity

---

### Question 17
**Problem:** Build a scholarship checker. Student qualifies if GPA >= 3.5 AND (income < $50k OR is first generation). Ask for all criteria and determine eligibility.

**Solution Approach:**
- Must have GPA >= 3.5 (required)
- Must also meet ONE of: income < 50k OR first generation
- Use AND to connect GPA with the OR condition
- Parentheses ensure correct evaluation order

**Complete Solution:**
```python
# Get student information
gpa = float(input("Enter GPA (0.0-4.0): "))
income = float(input("Enter family income: $"))
first_gen = input("Are you first generation college student? (yes/no): ")
is_first_gen = (first_gen.lower() == "yes")

# Check scholarship eligibility
if gpa >= 3.5 and (income < 50000 or is_first_gen):
    print("Congratulations! You qualify for the scholarship")
    print(f"GPA requirement met: {gpa:.2f} >= 3.5")
    if income < 50000:
        print("Income requirement met")
    if is_first_gen:
        print("First generation student status confirmed")
else:
    print("Sorry, you do not qualify for the scholarship")
    if gpa < 3.5:
        print(f"GPA requirement not met: {gpa:.2f} < 3.5")
    elif income >= 50000 and not is_first_gen:
        print("Must have income < $50k OR be first generation")
```

**Sample Run (qualifies):**
```
Enter GPA (0.0-4.0): 3.7
Enter family income: $60000
Are you first generation college student? (yes/no): yes
Congratulations! You qualify for the scholarship
GPA requirement met: 3.7 >= 3.5
First generation student status confirmed
```

**Key Concepts:**
- AND requires both sides to be True
- OR requires at least one side to be True
- Parentheses group the OR condition: `(income < 50000 or is_first_gen)`
- GPA is required AND one of the other conditions
- Detailed feedback shows which requirements were met

---

### Question 18
**Problem:** Make a loan approval system. Approve if credit score >= 700 AND (income > $50k OR has cosigner). Check all conditions.

**Solution Approach:**
- Credit score >= 700 is required
- Must also have high income OR a cosigner
- AND connects the two main requirements
- OR provides alternative ways to meet financial requirement

**Complete Solution:**
```python
# Get loan application information
credit_score = int(input("Enter credit score: "))
income = float(input("Enter annual income: $"))
cosigner = input("Do you have a cosigner? (yes/no): ")
has_cosigner = (cosigner.lower() == "yes")

# Determine loan approval
if credit_score >= 700 and (income > 50000 or has_cosigner):
    print("Loan APPROVED!")
    print(f"Credit score: {credit_score} (Excellent)")
    if income > 50000:
        print(f"Income: ${income:.2f} (Sufficient)")
    if has_cosigner:
        print("Cosigner: Yes (Approved)")
    print("\nProceed to loan agreement")
else:
    print("Loan DENIED")
    if credit_score < 700:
        print(f"Credit score: {credit_score} (Need 700+)")
    if income <= 50000 and not has_cosigner:
        print("Insufficient income and no cosigner")
```

**Sample Run (approved with cosigner):**
```
Enter credit score: 750
Enter annual income: $45000
Do you have a cosigner? (yes/no): yes
Loan APPROVED!
Credit score: 750 (Excellent)
Cosigner: Yes (Approved)

Proceed to loan agreement
```

**Key Concepts:**
- Credit score is the primary requirement (must be >= 700)
- Income OR cosigner provides financial security
- Compound condition: `credit_score >= 700 and (income > 50000 or has_cosigner)`
- Both AND and OR in one condition
- Parentheses ensure OR is evaluated before AND

---

### Question 19
**Problem:** Create a park entry validator. Free entry if age < 5 OR age >= 65 OR is resident. Otherwise charge $10. Use OR conditions properly.

**Solution Approach:**
- Three ways to get free entry (any one qualifies)
- Use OR to connect all three conditions
- All three conditions are at the same level (no AND needed)
- Else handles everyone who doesn't qualify for free entry

**Complete Solution:**
```python
# Get visitor information
age = int(input("Enter age: "))
resident = input("Are you a local resident? (yes/no): ")
is_resident = (resident.lower() == "yes")

# Determine entry fee
if age < 5 or age >= 65 or is_resident:
    print("Entry: FREE")
    if age < 5:
        print("Reason: Child admission")
    if age >= 65:
        print("Reason: Senior admission")
    if is_resident:
        print("Reason: Local resident")
    print("Welcome to the park!")
else:
    print("Entry: $10")
    print("Thank you for visiting!")
```

**Sample Run (child):**
```
Enter age: 3
Are you a local resident? (yes/no): no
Entry: FREE
Reason: Child admission
Welcome to the park!
```

**Sample Run (adult non-resident):**
```
Enter age: 35
Are you a local resident? (yes/no): no
Entry: $10
Thank you for visiting!
```

**Key Concepts:**
- Multiple OR conditions: any one being True makes entire condition True
- `age < 5 or age >= 65 or is_resident` - only need ONE to be True
- Can have multiple reasons for free entry (resident senior child would trigger all)
- Else handles the default case (pay full price)
- Three separate reasons, all equal priority

---

### Question 20
**Problem:** Build a restaurant reservation validator. Accept reservation if (party size <= 8 AND time between 5-9pm) OR has VIP status. Check both conditions.

**Solution Approach:**
- Two ways to get a reservation:
  1. Party size 8 or less AND time is 5-9pm
  2. VIP status (overrides other restrictions)
- Use OR to connect the two paths
- AND connects party size and time requirements

**Complete Solution:**
```python
# Get reservation details
party_size = int(input("Enter party size: "))
time = int(input("Enter reservation time (hour in 24h format, e.g., 17 for 5pm): "))
vip = input("Do you have VIP status? (yes/no): ")
is_vip = (vip.lower() == "yes")

# Check reservation validity
if (party_size <= 8 and 17 <= time <= 21) or is_vip:
    print("Reservation ACCEPTED!")
    if is_vip:
        print("VIP status confirmed - no restrictions")
    else:
        print(f"Party size: {party_size} (within limit)")
        print(f"Time: {time}:00 (prime dining hours)")
    print("\nWe look forward to serving you!")
else:
    print("Reservation DECLINED")
    if party_size > 8:
        print(f"Party size {party_size} exceeds limit of 8")
    if time < 17 or time > 21:
        print(f"Time {time}:00 outside dinner hours (5pm-9pm)")
    print("Please contact us for special arrangements")
```

**Sample Run (regular, valid):**
```
Enter party size: 6
Enter reservation time (hour in 24h format, e.g., 17 for 5pm): 19
Do you have VIP status? (yes/no): no
Reservation ACCEPTED!
Party size: 6 (within limit)
Time: 19:00 (prime dining hours)

We look forward to serving you!
```

**Sample Run (VIP, no restrictions):**
```
Enter party size: 12
Enter reservation time (hour in 24h format, e.g., 17 for 5pm): 14
Do you have VIP status? (yes/no): yes
Reservation ACCEPTED!
VIP status confirmed - no restrictions

We look forward to serving you!
```

**Key Concepts:**
- Two independent paths to approval
- `(party_size <= 8 and 17 <= time <= 21)` - both must be True
- `or is_vip` - provides alternative approval path
- VIP status bypasses normal restrictions
- Range checking: `17 <= time <= 21` checks if time is between 5pm and 9pm

---

## Nested If Statements (Questions 21-25)

### Question 21
**Problem:** Create a two-level authentication: First check username, then check password only if username is correct. Provide specific error messages for each level.

**Solution Approach:**
- First level: check username
- Second level (nested): check password only if username was correct
- Each failure point has its own error message
- Success requires both to be correct

**Complete Solution:**
```python
# Define correct credentials
correct_username = "admin"
correct_password = "secure123"

# Get user credentials
username = input("Enter username: ")
password = input("Enter password: ")

# Nested authentication
if username == correct_username:
    print("Username verified")
    
    # Only check password if username was correct
    if password == correct_password:
        print("Password verified")
        print("✓ LOGIN SUCCESSFUL")
        print("Welcome to the system!")
    else:
        print("✗ Incorrect password")
        print("Authentication failed at password check")
else:
    print("✗ Unknown username")
    print("Authentication failed at username check")
```

**Sample Run (correct username, wrong password):**
```
Enter username: admin
Enter password: wrong
Username verified
✗ Incorrect password
Authentication failed at password check
```

**Sample Run (wrong username):**
```
Enter username: user
Enter password: secure123
✗ Unknown username
Authentication failed at username check
```

**Key Concepts:**
- Outer if checks username first
- Inner if (nested) only runs if outer condition was True
- Each level of nesting adds one indentation
- Specific error messages at each failure point
- Password is never checked if username is wrong

---

### Question 22
**Problem:** Build a discount calculator: First check if customer is a member. If yes, check if purchase > $100 for additional discount. Non-members always pay full price. Calculate final price with appropriate discounts.

**Solution Approach:**
- First level: member or not
- Second level (nested): if member, check purchase amount
- Members get base discount, extra discount if > $100
- Calculate final price with appropriate reductions

**Complete Solution:**
```python
# Get purchase information
purchase_amount = float(input("Enter purchase amount: $"))
member = input("Are you a member? (yes/no): ")
is_member = (member.lower() == "yes")

# Apply discounts based on membership and amount
if is_member:
    print("Member discount applied!")
    
    # Check for additional discount based on purchase amount
    if purchase_amount > 100:
        discount_rate = 0.20  # 20% discount for members spending >$100
        discount = purchase_amount * discount_rate
        final_price = purchase_amount - discount
        print(f"Member purchase over $100: 20% discount")
        print(f"Discount amount: ${discount:.2f}")
        print(f"Final price: ${final_price:.2f}")
    else:
        discount_rate = 0.10  # 10% discount for members spending <=$100
        discount = purchase_amount * discount_rate
        final_price = purchase_amount - discount
        print(f"Member discount: 10% off")
        print(f"Discount amount: ${discount:.2f}")
        print(f"Final price: ${final_price:.2f}")
else:
    print("No membership discount")
    final_price = purchase_amount
    print(f"Final price: ${final_price:.2f}")
    print("(Join our membership program to save!)")
```

**Sample Run (member, large purchase):**
```
Enter purchase amount: $150
Are you a member? (yes/no): yes
Member discount applied!
Member purchase over $100: 20% discount
Discount amount: $30.00
Final price: $120.00
```

**Sample Run (non-member):**
```
Enter purchase amount: $150
Are you a member? (yes/no): no
No membership discount
Final price: $150.00
(Join our membership program to save!)
```

**Key Concepts:**
- Outer if determines membership status
- Inner if (nested in member block) checks purchase amount
- Non-members skip all discount logic (else block)
- Different discounts based on nested conditions
- Final price calculated differently in each path

---

### Question 23
**Problem:** Make a college admission system: First check if GPA >= 3.0. If yes, check if SAT >= 1200 OR has special talent. Provide specific feedback at each decision level.

**Solution Approach:**
- First requirement: minimum GPA
- Second requirement (only if GPA OK): SAT score OR special talent
- Use nested if with OR condition in the inner level
- Rejection can happen at either level

**Complete Solution:**
```python
# Get application information
gpa = float(input("Enter GPA (0.0-4.0): "))
sat_score = int(input("Enter SAT score: "))
talent = input("Do you have a special talent/skill? (yes/no): ")
has_talent = (talent.lower() == "yes")

# Evaluate admission
if gpa >= 3.0:
    print(f"✓ GPA requirement met: {gpa:.2f}")
    
    # Check secondary requirements
    if sat_score >= 1200 or has_talent:
        print("✓ ADMITTED!")
        if sat_score >= 1200:
            print(f"  - SAT score: {sat_score} (Excellent)")
        if has_talent:
            print("  - Special talent recognized")
        print("\nCongratulations! Welcome to our university!")
    else:
        print("✗ Admission denied")
        print(f"  - SAT score: {sat_score} (Need 1200+)")
        print("  - No special talent documented")
        print("Consider retaking the SAT or documenting special skills")
else:
    print(f"✗ GPA requirement not met: {gpa:.2f} < 3.0")
    print("Application rejected at initial screening")
    print("Focus on improving your GPA and reapply")
```

**Sample Run (admitted with SAT):**
```
Enter GPA (0.0-4.0): 3.5
Enter SAT score: 1300
Do you have a special talent/skill? (yes/no): no
✓ GPA requirement met: 3.5
✓ ADMITTED!
  - SAT score: 1300 (Excellent)

Congratulations! Welcome to our university!
```

**Sample Run (rejected at GPA):**
```
Enter GPA (0.0-4.0): 2.8
Enter SAT score: 1400
Do you have a special talent/skill? (yes/no): yes
✗ GPA requirement not met: 2.8 < 3.0
Application rejected at initial screening
Focus on improving your GPA and reapply
```

**Key Concepts:**
- Sequential evaluation: GPA first, then other criteria
- Inner condition uses OR (SAT or talent)
- SAT score isn't checked if GPA is too low
- Feedback specific to failure point
- Multiple paths to success in nested level

---

### Question 24
**Problem:** Create a game difficulty selector: Ask for experience level (1-3). If expert (3), ask if they want nightmare mode. If intermediate (2), ask if they want hard mode. Beginners (1) always get easy mode.

**Solution Approach:**
- Outer if-elif-else based on experience level
- Nested if statements for additional mode selection
- Different nesting in each branch of the outer structure
- Beginners have no nested choice (automatic easy mode)

**Complete Solution:**
```python
# Get experience level
print("Select your experience level:")
print("1 - Beginner")
print("2 - Intermediate")
print("3 - Expert")
experience = int(input("Enter level (1-3): "))

# Determine game difficulty
if experience == 3:
    print("\nExpert player detected!")
    nightmare = input("Do you want NIGHTMARE mode? (yes/no): ")
    
    if nightmare.lower() == "yes":
        print("⚠️  NIGHTMARE MODE ACTIVATED")
        print("Good luck... you'll need it!")
        difficulty = "Nightmare"
    else:
        print("Expert mode selected")
        print("Prepare for a challenge!")
        difficulty = "Expert"
        
elif experience == 2:
    print("\nIntermediate player detected!")
    hard_mode = input("Do you want HARD mode? (yes/no): ")
    
    if hard_mode.lower() == "yes":
        print("Hard mode activated")
        print("A good challenge awaits!")
        difficulty = "Hard"
    else:
        print("Normal mode selected")
        print("Balanced gameplay ahead!")
        difficulty = "Normal"
        
else:  # experience == 1 or any other value
    print("\nBeginner mode activated")
    print("Welcome! We'll start you off easy.")
    print("Learn the basics at your own pace.")
    difficulty = "Easy"

# Start game with selected difficulty
print(f"\n>>> Starting game on {difficulty} difficulty <<<")
```

**Sample Run (expert, nightmare):**
```
Select your experience level:
1 - Beginner
2 - Intermediate
3 - Expert
Enter level (1-3): 3

Expert player detected!
Do you want NIGHTMARE mode? (yes/no): yes
⚠️  NIGHTMARE MODE ACTIVATED
Good luck... you'll need it!

>>> Starting game on Nightmare difficulty <<<
```

**Sample Run (intermediate, normal):**
```
Select your experience level:
1 - Beginner
2 - Intermediate
3 - Expert
Enter level (1-3): 2

Intermediate player detected!
Do you want HARD mode? (yes/no): no
Normal mode selected
Balanced gameplay ahead!

>>> Starting game on Normal difficulty <<<
```

**Key Concepts:**
- Each experience level has different nested logic
- Expert branch has nested if for nightmare mode
- Intermediate branch has nested if for hard mode
- Beginner branch has no nesting (automatic easy)
- Different indentation levels show structure clearly

---

### Question 25
**Problem:** Build a comprehensive grading system: First check if student passed (>= 60). If passed, check if they made honor roll (>= 90). If honor roll, check if they made perfect score (100). Provide specific congratulatory messages at each achievement level.

**Solution Approach:**
- Three levels of achievement, each nested
- First level: pass or fail
- Second level (if passed): regular pass or honor roll
- Third level (if honor roll): honor roll or perfect score
- Each level has specific feedback

**Complete Solution:**
```python
# Get student score
score = int(input("Enter student score (0-100): "))

# Comprehensive grading with achievement levels
if score >= 60:
    print("✓ PASSED")
    
    # Check for honor roll
    if score >= 90:
        print("✓✓ HONOR ROLL!")
        
        # Check for perfect score
        if score == 100:
            print("✓✓✓ PERFECT SCORE!")
            print("OUTSTANDING ACHIEVEMENT")
            print("Absolute mastery of the material!")
            print("This is the highest possible achievement!")
            grade_level = "Perfect Score"
        else:
            print("Exceptional performance!")
            print("You're among the top students!")
            grade_level = "Honor Roll"
    else:
        print("Good work! You passed the course.")
        print("Keep up the steady effort!")
        grade_level = "Pass"
else:
    print("✗ FAILED")
    print("Score below passing threshold")
    print("Please review the material and consider tutoring")
    print(f"You need {60 - score} more points to pass")
    grade_level = "Fail"

# Summary
print(f"\n=== Final Grade: {grade_level} ===")
print(f"Score: {score}/100")
```

**Sample Run (perfect score):**
```
Enter student score (0-100): 100
✓ PASSED
✓✓ HONOR ROLL!
✓✓✓ PERFECT SCORE!
OUTSTANDING ACHIEVEMENT
Absolute mastery of the material!
This is the highest possible achievement!

=== Final Grade: Perfect Score ===
Score: 100/100
```

**Sample Run (honor roll, not perfect):**
```
Enter student score (0-100): 95
✓ PASSED
✓✓ HONOR ROLL!
Exceptional performance!
You're among the top students!

=== Final Grade: Honor Roll ===
Score: 95/100
```

**Sample Run (passed, not honor roll):**
```
Enter student score (0-100): 75
✓ PASSED
Good work! You passed the course.
Keep up the steady effort!

=== Final Grade: Pass ===
Score: 75/100
```

**Sample Run (failed):**
```
Enter student score (0-100): 45
✗ FAILED
Score below passing threshold
Please review the material and consider tutoring
You need 15 more points to pass

=== Final Grade: Fail ===
Score: 45/100
```

**Key Concepts:**
- Three levels of nesting show three tiers of achievement
- Each level only checks if the previous level was met
- Perfect score check (==100) only happens for honor roll students
- Honor roll check (>=90) only happens for passing students
- Specific, encouraging messages at each achievement level
- Indentation clearly shows the hierarchy: pass → honor → perfect
- Each nested level provides additional recognition

**Why this works:**
- We never check for honor roll unless student passed
- We never check for perfect score unless student made honor roll
- Each level builds on the previous achievement
- The nesting matches the logical progression of achievements
- Clear visual hierarchy through indentation

---

## Summary: Key Patterns and Concepts

### Code Block Fundamentals
```python
# Basic code block structure
if condition:
    statement1    # Inside block (indented)
    statement2    # Inside block (indented)
statement3        # Outside block (not indented)
```

### Decision Structures
```python
# Simple if
if condition:
    # code

# If-else (binary choice)
if condition:
    # option A
else:
    # option B

# If-elif-else (multiple options)
if condition1:
    # option 1
elif condition2:
    # option 2
elif condition3:
    # option 3
else:
    # default option
```

### Logical Operators
```python
# AND - both must be True
if age >= 18 and has_license:
    print("Can drive")

# OR - at least one must be True
if is_weekend or is_holiday:
    print("Day off")

# NOT - reverses condition
if not is_raining:
    print("No umbrella needed")

# Compound with parentheses
if (age >= 13 and age <= 19) or is_student:
    print("Teen or student")
```

### Nested If Patterns
```python
# Two-level authentication
if username_correct:
    if password_correct:
        print("Login successful")
    else:
        print("Wrong password")
else:
    print("Wrong username")

# Progressive checks
if meets_minimum:
    if meets_preferred:
        if meets_exceptional:
            print("Top tier")
        else:
            print("Preferred tier")
    else:
        print("Standard tier")
else:
    print("Does not qualify")
```

### Common Pitfalls to Avoid
1. **Using = instead of ==** - assignment vs comparison
2. **Wrong elif order** - check specific conditions before general ones
3. **Inconsistent indentation** - mixing spaces/tabs breaks code blocks
4. **Missing colons** - if, elif, else all need colons
5. **Unnecessary nesting** - use compound conditions when simpler

### Best Practices
- Keep code blocks clear with consistent 4-space indentation
- Check most specific conditions first in elif chains
- Use compound conditions (AND/OR) when appropriate
- Provide specific feedback at each decision point
- Limit nesting to 3 levels for readability
- Use meaningful variable names for boolean values
- Add comments to explain complex conditional logic