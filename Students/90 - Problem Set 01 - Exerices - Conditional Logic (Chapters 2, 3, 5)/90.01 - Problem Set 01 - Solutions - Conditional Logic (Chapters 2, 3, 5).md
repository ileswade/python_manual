# Introduction to Python Programming
## Problem Set 01 - Solutions - Conditional Logic

### How to Use This Guide

- Try solving each problem yourself first before looking at the solution
- Read the "Thinking Process" to understand the logic
- Study the code to see how the logic translates to Python
- Pay attention to new concepts introduced - they build on each other
- Later solutions assume you understand concepts from earlier problems

---

## Level 1: Basic If Statements (Problems 1-5)

### Problem 1: Positive Number Checker

**Thinking Process:**
The problem asks us to check ONE condition: is the number positive (greater than 0)? If yes, we print something. If no, we do nothing. This is the simplest form of an if statement - just checking one condition.

**Solution:**
```python
number = float(input("Enter a number: "))

if number > 0:
    print("That's a positive number!")
```

**Key Points:**
- We use `float()` instead of `int()` to handle decimal numbers
- The condition `number > 0` evaluates to True or False
- If True, the indented code runs
- If False, nothing happens and the program ends

---

### Problem 2: Voting Eligibility

**Thinking Process:**
Similar to Problem 1, we check one condition: age >= 18. The >= operator means "greater than OR equal to" - so 18 counts as eligible.

**Solution:**
```python
age = int(input("Enter your age: "))

if age >= 18:
    print("You are eligible to vote.")
```

**Key Points:**
- Notice we use `>=` not just `>` because 18 should qualify
- The pattern is the same: check condition, do something if True

---

### Problem 3: Password Length

**Thinking Process:**
We need to check if a string's length is greater than 8. Python has a built-in `len()` function that returns the number of characters in a string.

**Solution:**
```python
password = input("Enter a password: ")

if len(password) > 8:
    print("Password is long enough.")
```

**Key Points:**
- `len(password)` counts the characters
- We compare that count to 8
- Note: "greater than 8" means 9 or more characters

---

### Problem 4: Temperature Warning

**Thinking Process:**
Check if temperature > 30. Straightforward single condition check.

**Solution:**
```python
temperature = float(input("Enter temperature in Celsius: "))

if temperature > 30:
    print("It's hot outside! Stay hydrated.")
```

---

### Problem 5: Discount Eligibility

**Thinking Process:**
Check if age >= 65 for senior discount. Same pattern as before.

**Solution:**
```python
age = int(input("Enter your age: "))

if age >= 65:
    print("You qualify for a senior discount!")
```

---

## Level 2: If-Else Statements (Problems 6-10)

### Problem 6: Even or Odd

**Thinking Process:**
Now we have TWO possible outcomes - the number is either even OR odd (not both, not neither). This requires if-else. 

To check if even: use modulus operator (%). If `number % 2` equals 0, it's even (divides evenly by 2). Otherwise, it's odd.

**Solution:**
```python
number = int(input("Enter a number: "))

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

**Key Points:**
- `%` gives the remainder after division
- `number % 2` gives 0 (even) or 1 (odd)
- We use `==` to check equality (not `=` which is assignment!)
- One of the two blocks will ALWAYS run

---

### Problem 7: Pass or Fail

**Thinking Process:**
Two outcomes: Pass (>= 50) or Fail (< 50). When you have exactly two mutually exclusive outcomes, use if-else.

**Solution:**
```python
score = int(input("Enter test score: "))

if score >= 50:
    print("Pass")
else:
    print("Fail")
```

**Key Points:**
- The else handles everything NOT covered by the if
- If score is NOT >= 50, it must be < 50

---

### Problem 8: Positive or Negative

**Thinking Process:**
Two outcomes based on whether number > 0. Note: the problem says "Not positive" for else, which includes 0 and negative numbers.

**Solution:**
```python
number = float(input("Enter a number: "))

if number > 0:
    print("Positive")
else:
    print("Not positive")
```

---

### Problem 9: Adult or Minor

**Solution:**
```python
age = int(input("Enter age: "))

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

---

### Problem 10: Hot or Cold

**Solution:**
```python
temperature = float(input("Enter temperature: "))

if temperature > 25:
    print("Hot")
else:
    print("Cold")
```

---

## Level 3: If-Elif-Else (Problems 11-15)

### Problem 11: Letter Grade

**Thinking Process:**
Now we have MORE than two outcomes (A, B, C, D, F). We use elif to check multiple conditions in order. 

**Critical thinking point:** Order matters! We check from highest grade down. If we checked >= 60 first, a score of 95 would print "D" and stop!

**Solution:**
```python
score = int(input("Enter test score: "))

if score >= 90:
    print("A")
elif score >= 80:
    print("B")
elif score >= 70:
    print("C")
elif score >= 60:
    print("D")
else:
    print("F")
```

**Key Points:**
- Check most specific condition first (highest score)
- Once one condition is True, the rest are skipped
- The else catches everything below 60

---

### Problem 12: Age Category

**Thinking Process:**
Four categories, so we need three conditions plus else. Again, order matters - check specific ranges carefully.

**Solution:**
```python
age = int(input("Enter age: "))

if age < 13:
    print("Child")
elif age <= 19:
    print("Teenager")
elif age <= 64:
    print("Adult")
else:
    print("Senior")
```

**Key Points:**
- First condition catches under 13
- Second condition only runs if age >= 13, so we only need to check <= 19
- Each elif only runs if previous conditions were False

---

### Problem 13: Shipping Cost

**Thinking Process:**
Three shipping tiers based on order total. We need to check from highest to lowest or organize conditions carefully.

**Solution:**
```python
order_total = float(input("Enter order total: "))

if order_total > 100:
    shipping = 0
    print("Free shipping")
elif order_total >= 50:
    shipping = 5
    print("Shipping cost: $5")
else:
    shipping = 10
    print("Shipping cost: $10")
```

**Key Points:**
- We check > 100 first (free shipping)
- Then >= 50 (which we know is also <= 100 because the first condition failed)
- Else handles everything under 50

---

### Problem 14: Traffic Light

**Thinking Process:**
We're checking a string value against specific options. Need to handle invalid input too.

**Solution:**
```python
color = input("Enter traffic light color: ").lower()

if color == "red":
    print("Stop")
elif color == "yellow":
    print("Slow down")
elif color == "green":
    print("Go")
else:
    print("Invalid color")
```

**Key Points:**
- `.lower()` converts input to lowercase so "Red", "RED", "red" all work
- We use `==` to check string equality
- The else catches any input that's not red, yellow, or green

---

### Problem 15: BMI Category

**Thinking Process:**
First calculate BMI, THEN categorize it. This introduces the idea of doing calculations before making decisions.

**Solution:**
```python
weight = float(input("Enter weight in kg: "))
height = float(input("Enter height in meters: "))

bmi = weight / (height * height)

if bmi < 18.5:
    print("Underweight")
elif bmi < 25:
    print("Normal weight")
elif bmi < 30:
    print("Overweight")
else:
    print("Obese")
```

**Key Points:**
- Calculate first, decide second
- We can use `< 25` for the second condition because we already know BMI >= 18.5 (first condition failed)
- Order matters: check from lowest to highest threshold

---

## Level 4: Compound Conditions with AND/OR (Problems 16-19)

### Problem 16: Movie Ticket Pricing

**Thinking Process:**
Now we're checking TWO factors: age AND day of week. We have FOUR possible combinations:
- Child on weekend
- Child on weekday  
- Adult on weekend
- Adult on weekday

We use AND to check both conditions together.

**Solution:**
```python
age = int(input("Enter age: "))
is_weekend = input("Is it a weekend? (yes/no): ").lower()

if age < 12 and is_weekend == "yes":
    print("Ticket price: $10")
elif age < 12 and is_weekend == "no":
    print("Ticket price: $8")
elif age >= 12 and is_weekend == "yes":
    print("Ticket price: $15")
else:  # age >= 12 and weekday
    print("Ticket price: $12")
```

**Key Points:**
- AND means BOTH conditions must be True
- `age < 12 and is_weekend == "yes"` - both parts must be True
- We check all four combinations explicitly
- The final else catches the last combination

---

### Problem 17: Loan Approval

**Thinking Process:**
Loan approval needs BOTH conditions: good credit (>= 700) AND sufficient income (>= 30000). If EITHER is missing, deny the loan. This is a perfect use of AND.

**Solution:**
```python
credit_score = int(input("Enter credit score: "))
income = float(input("Enter annual income: "))

if credit_score >= 700 and income >= 30000:
    print("Loan approved!")
else:
    print("Loan denied.")
```

**Key Points:**
- Both conditions must be True for approval
- If credit_score is 750 but income is 25000: denied (AND requires BOTH)
- The else handles all cases where at least one condition fails

---

### Problem 18: Park Entry

**Thinking Process:**
This is trickier - we have TWO different ways to qualify:
- Way 1: Age >= 12 AND height >= 140
- Way 2: Age < 12 AND height >= 150

If EITHER way works, allow entry. This requires OR to connect the two possibilities.

**Solution:**
```python
age = int(input("Enter age: "))
height = int(input("Enter height in cm: "))

if (age >= 12 and height >= 140) or (age < 12 and height >= 150):
    print("Entry allowed")
else:
    print("Entry denied")
```

**Key Points:**
- Parentheses group the two ways to qualify
- OR means "if this way works OR that way works"
- If EITHER condition in parentheses is True, entry is allowed
- This is combining AND and OR - powerful but requires careful thinking!

---

### Problem 19: Password Validator

**Thinking Process:**
Password must meet BOTH requirements: length >= 10 AND contains a digit. Both must be True for "Strong password".

**Solution:**
```python
password = input("Enter password: ")
has_digit = input("Does it contain a digit? (yes/no): ").lower()

if len(password) >= 10 and has_digit == "yes":
    print("Strong password")
else:
    print("Weak password")
```

**Key Points:**
- We use AND because both conditions are required
- If password is 15 characters but no digit: Weak (need BOTH)
- If password has digit but only 8 characters: Weak (need BOTH)

---

## Level 5: Basic Nesting (Problems 20-22)

### Problem 20: Restaurant Seating

**Thinking Process:**
This introduces NESTING - checking a condition INSIDE another condition. 

First question: Is restaurant open?
- If NO: Tell them it's closed (we're done)
- If YES: Now ask about party size (second level of decision)

We only care about party size IF the restaurant is open. That's nesting!

**Solution:**
```python
is_open = input("Is the restaurant open? (yes/no): ").lower()

if is_open == "yes":
    party_size = int(input("Enter party size: "))
    
    if party_size <= 4:
        print("Table for your party")
    elif party_size <= 8:
        print("Large table for your party")
    else:
        print("We'll need to combine tables")
else:
    print("Sorry, we're closed")
```

**Key Points:**
- The inner if-elif-else is INSIDE the outer if
- Inner block only runs if outer condition is True
- Notice the extra indentation for the nested part
- We only ask for party_size if restaurant is open

---

### Problem 21: Store Discount

**Thinking Process:**
First check: Are they a member?
- If YES: Calculate discount based on purchase amount (nested decision)
- If NO: No discount

The discount calculation only happens for members - that's why it's nested inside.

**Solution:**
```python
is_member = input("Are you a member? (yes/no): ").lower()
purchase = float(input("Enter purchase amount: "))

if is_member == "yes":
    if purchase > 100:
        discount = 0.20
        final_price = purchase * 0.80
        print(f"20% discount applied")
    elif purchase >= 50:
        discount = 0.10
        final_price = purchase * 0.90
        print(f"10% discount applied")
    else:
        discount = 0.05
        final_price = purchase * 0.95
        print(f"5% discount applied")
    
    print(f"Final price: ${final_price:.2f}")
else:
    print(f"No discount. Final price: ${purchase:.2f}")
```

**Key Points:**
- Entire discount structure is nested inside the member check
- Non-members skip all the discount logic
- We calculate final_price differently based on discount tier
- The `.2f` in f-string formats to 2 decimal places

---

### Problem 22: Grade with Bonus

**Thinking Process:**
First, handle the extra credit (if applicable). Then determine grade. This shows nesting can also be used for sequential decisions that affect each other.

**Solution:**
```python
score = int(input("Enter base score (0-100): "))
extra_credit = input("Did extra credit? (yes/no): ").lower()

if extra_credit == "yes":
    score = score + 5
    if score > 100:
        score = 100
    print(f"Bonus applied! New score: {score}")

# Now determine grade based on final score
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
elif score >= 60:
    grade = "D"
else:
    grade = "F"

print(f"Final score: {score}")
print(f"Grade: {grade}")
```

**Key Points:**
- First if handles bonus points
- Nested if caps the score at 100
- Second if-elif-else determines grade (uses the potentially modified score)
- These are sequential, not deeply nested - both run

---

## Level 6: Advanced Nesting and Complex Logic (Problems 23-25)

### Problem 23: Insurance Premium Calculator

**Thinking Process:**
This requires SEQUENTIAL decision making where each decision affects the next:
1. Start with base premium
2. Adjust for age
3. Adjust for smoking (affects current premium)
4. Adjust for exercise (affects current premium)

Each step builds on the previous result.

**Solution:**
```python
age = int(input("Enter age: "))
smokes = input("Do you smoke? (yes/no): ").lower()
exercises = input("Do you exercise regularly? (yes/no): ").lower()

premium = 100

# Age adjustment
if age < 25:
    premium = premium + 50
elif age > 60:
    premium = premium + 100

# Smoking adjustment (applies to current premium)
if smokes == "yes":
    premium = premium * 2

# Exercise adjustment (applies to current premium)
if exercises == "yes":
    premium = premium * 0.80

print(f"Your insurance premium is: ${premium:.2f}")
```

**Key Points:**
- We modify premium progressively
- Each if statement operates on the current value of premium
- Order matters: smoking doubles the current premium (which might already be adjusted for age)
- Exercise reduces the current premium (which might already be doubled for smoking)
- This is sequential logic, not deeply nested

---

### Problem 24: College Admission

**Thinking Process:**
This is COMPLEX NESTED logic - decisions within decisions within decisions. Let's break it down:

1. First level: What's the GPA range?
2. Second level: Based on GPA, what are the SAT/extracurricular requirements?
3. Use AND/OR to check multiple conditions

The key is to translate the rules exactly as given, using proper nesting.

**Solution:**
```python
gpa = float(input("Enter GPA (0.0-4.0): "))
sat = int(input("Enter SAT score (400-1600): "))
extracurriculars = input("Extracurricular activities? (yes/no): ").lower()

if gpa >= 3.5:
    # High GPA path
    if sat >= 1200 or extracurriculars == "yes":
        print("Accepted")
    else:
        print("Waitlisted")
        
elif gpa >= 3.0:
    # Medium GPA path
    if sat >= 1300 and extracurriculars == "yes":
        print("Accepted")
    elif sat >= 1300 or extracurriculars == "yes":
        print("Waitlisted")
    else:
        print("Rejected")
        
else:
    # Low GPA path
    if sat >= 1400 and extracurriculars == "yes":
        print("Waitlisted")
    else:
        print("Rejected")
```

**Key Points:**
- Three main branches based on GPA (first level)
- Each GPA branch has its own logic (second level)
- Notice the different requirements for each GPA tier
- High GPA: OR makes it easier (need one or the other)
- Medium GPA: Different rules for Accept vs Waitlist
- Low GPA: Very strict (need both, and even then just waitlisted)
- This mirrors real-world decision trees

---

### Problem 25: Complex Shipping and Tax Calculator

**Thinking Process:**
This is the MOST COMPLEX problem - it combines:
- Nested conditions (domestic/international, then weight tiers)
- Sequential calculations (shipping, then premium discount, then tax)
- Multiple variables to track
- Conditional logic that affects calculations

Break it down into steps:
1. Determine base shipping cost (nested: first domestic/international, then weight)
2. Apply premium discount to shipping if applicable (affects shipping)
3. Calculate tax (conditional on domestic/international)
4. Calculate total

**Solution:**
```python
price = float(input("Enter item price: "))
weight = float(input("Enter weight in kg: "))
destination = input("Destination (domestic/international): ").lower()
customer = input("Customer status (premium/regular): ").lower()

# Step 1: Calculate base shipping cost
if destination == "domestic":
    if weight < 1:
        shipping = 5
    elif weight <= 5:
        shipping = 10
    else:
        shipping = 20
else:  # international
    if weight < 1:
        shipping = 15
    elif weight <= 5:
        shipping = 30
    else:
        shipping = 50

# Step 2: Apply premium customer discount to shipping
if customer == "premium":
    if price > 100:
        shipping = 0
        print("Premium customer: Free shipping!")
    else:
        shipping = shipping * 0.5
        print("Premium customer: 50% off shipping!")

# Step 3: Calculate tax
if destination == "domestic":
    tax = price * 0.10
else:
    tax = 0

# Step 4: Calculate total
total = price + shipping + tax

# Step 5: Print itemized breakdown
print(f"\n--- Order Summary ---")
print(f"Item price: ${price:.2f}")
print(f"Shipping cost: ${shipping:.2f}")
print(f"Tax: ${tax:.2f}")
print(f"Total: ${total:.2f}")
```

**Key Points:**
- **First nested section:** Domestic/international splits into weight tiers (2 levels deep)
- **Sequential logic:** Premium discount applies to shipping (already calculated)
- **Conditional tax:** Only domestic orders have tax
- **Building up:** Each calculation uses previous values
- **Three levels of nesting** in first section (destination → weight tiers)
- **Multiple conditions affect same variable** (shipping gets calculated, then potentially modified)

**Common mistakes to avoid:**
- Calculating tax before shipping is finalized
- Forgetting that premium discount affects shipping (not price)
- Not handling both domestic and international in tax calculation
- Mixing up the order of operations

**This problem combines everything:**
- Nested if statements (3 levels)
- Sequential calculations (order matters)
- Multiple variables
- Complex business logic
- AND/OR conditions

If you solved this correctly, you've mastered Chapter 4 concepts!

---

## Key Takeaways from Solutions

### Progression of Complexity:

1. **Problems 1-5:** Single conditions - if this, then that
2. **Problems 6-10:** Two outcomes - if-else
3. **Problems 11-15:** Multiple outcomes - if-elif-else, order matters
4. **Problems 16-19:** Compound conditions - AND/OR logic, combining conditions
5. **Problems 20-22:** Basic nesting - decisions inside decisions (2 levels)
6. **Problems 23-25:** Advanced logic - deep nesting (3 levels), sequential calculations, complex business rules

### Common Patterns:

- **Range checking:** Always check most specific condition first (Problem 11)
- **AND requires ALL:** Both/all conditions must be True (Problem 17)
- **OR requires ONE:** At least one condition must be True (Problem 18)
- **Nesting for dependent decisions:** Only check B if A is true (Problem 20)
- **Sequential calculations:** Each step builds on previous results (Problem 23)
- **Complex business logic:** Combine nesting, AND/OR, sequential logic (Problem 25)

### Debugging Tips:

1. **Test boundary cases:** What happens at exactly 18? Exactly 100? Exactly 0?
2. **Trace through logic:** On paper, follow your code with a specific input
3. **Check order:** Are you checking specific conditions before general ones?
4. **Verify operators:** Is it > or >=? Does it matter?
5. **Print intermediate values:** Add print statements to see what's happening
6. **Check indentation:** Is your nesting correct?

---

## What If You're Still Stuck?

**If you struggled with:**

- **Problems 1-10:** Review basic if and if-else statements. Practice translating "if this, then that" statements into code.

- **Problems 11-15:** Focus on elif and order of conditions. Practice identifying ranges and which condition should be checked first.

- **Problems 16-19:** Study AND/OR logic truth tables. Practice writing out "both conditions must be true" vs "at least one must be true."

- **Problems 20-22:** Draw flowcharts for nested logic. Practice identifying when one decision depends on another.

- **Problems 23-25:** Break complex problems into smaller steps. Solve each piece, then combine them. Practice reading complex requirements and translating to code structure.

**Remember:** Programming is a skill that improves with practice. These problems are designed to challenge you - struggling means you're learning!
