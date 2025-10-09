# Introduction to Python Programming
## Problem Set 01 - Exercise - Conditional Logic

### Instructions

These 25 problems are designed to progressively challenge your understanding of if statements, from simple conditions to complex nested logic. Work through them in order - they get more difficult as you go!

**How to use this problem set:**
- Try to solve each problem on your own first
- Test your code with different inputs
- If you get stuck, review the relevant sections in Chapter 4
- There's a separate solution guide available when you need it
- The goal is to see how far you can get - struggling is part of learning!

---

## Level 1: Basic If Statements (Problems 1-5)

### Problem 1: Positive Number Checker
Write a program that asks the user for a number. If the number is positive (greater than 0), print "That's a positive number!"

### Problem 2: Voting Eligibility
Ask the user for their age. If they are 18 or older, print "You are eligible to vote."

### Problem 3: Password Length
Ask the user to enter a password. If the password is longer than 8 characters, print "Password is long enough."

### Problem 4: Temperature Warning
Ask for the temperature in Celsius. If it's above 30 degrees, print "It's hot outside! Stay hydrated."

### Problem 5: Discount Eligibility
Ask the user for their age. If they are 65 or older, print "You qualify for a senior discount!"

---

## Level 2: If-Else Statements (Problems 6-10)

### Problem 6: Even or Odd
Ask the user for a number. Print whether the number is "Even" or "Odd".
(Hint: Use the modulus operator %)

### Problem 7: Pass or Fail
Ask for a test score (0-100). If the score is 50 or higher, print "Pass". Otherwise print "Fail".

### Problem 8: Positive or Negative
Ask the user for a number. Print "Positive" if it's greater than 0, otherwise print "Not positive".

### Problem 9: Adult or Minor
Ask for age. Print "Adult" if 18 or older, otherwise print "Minor".

### Problem 10: Hot or Cold
Ask for temperature. If it's above 25 degrees, print "Hot". Otherwise print "Cold".

---

## Level 3: If-Elif-Else (Problems 11-15)

### Problem 11: Letter Grade
Ask for a test score (0-100). Print the letter grade:
- 90-100: A
- 80-89: B
- 70-79: C
- 60-69: D
- Below 60: F

### Problem 12: Age Category
Ask for age and categorize:
- Under 13: Child
- 13-19: Teenager
- 20-64: Adult
- 65+: Senior

### Problem 13: Shipping Cost
Ask for order total. Calculate shipping:
- Orders over $100: Free shipping
- Orders $50-$100: $5 shipping
- Orders under $50: $10 shipping
Print the shipping cost.

### Problem 14: Traffic Light
Ask the user for a traffic light color (red, yellow, or green). Print:
- Red: "Stop"
- Yellow: "Slow down"
- Green: "Go"
- Any other input: "Invalid color"

### Problem 15: BMI Category
Ask for weight (kg) and height (meters). Calculate BMI = weight / (height * height).
Categorize:
- BMI < 18.5: Underweight
- BMI 18.5-24.9: Normal weight
- BMI 25-29.9: Overweight
- BMI >= 30: Obese

---

## Level 4: Compound Conditions with AND/OR (Problems 16-19)

### Problem 16: Movie Ticket Pricing
Ask for age and whether it's a weekend (yes/no).
- Child (under 12) on weekend: $10
- Child on weekday: $8
- Adult (12+) on weekend: $15
- Adult on weekday: $12

### Problem 17: Loan Approval
Ask for credit score and annual income.
Approve the loan if:
- Credit score is 700 or higher AND income is $30,000 or more
Otherwise, deny the loan.

### Problem 18: Park Entry
Ask for age and height (in cm).
Allow entry to the ride if:
- Age is 12 or older AND height is 140cm or more
OR
- Age is under 12 AND height is 150cm or more
Otherwise, deny entry.

### Problem 19: Password Validator
Ask for a password and check if it meets these criteria:
- Length is 10 or more characters AND
- Contains at least one digit (you can ask the user if it contains a digit)
Print "Strong password" or "Weak password".

---

## Level 5: Basic Nesting (Problems 20-22)

### Problem 20: Restaurant Seating
Ask if the restaurant is open (yes/no).
If open, ask party size.
- Party size 1-4: "Table for your party"
- Party size 5-8: "Large table for your party"
- Party size 9+: "We'll need to combine tables"
If closed, print "Sorry, we're closed"

### Problem 21: Store Discount
Ask for membership status (yes/no) and purchase amount.
If they're a member:
- Purchases over $100 get 20% discount
- Purchases $50-$100 get 10% discount
- Purchases under $50 get 5% discount
If not a member:
- No discount
Calculate and print final price.

### Problem 22: Grade with Bonus
Ask for base score (0-100) and if they did extra credit (yes/no).
If they did extra credit, add 5 points (max score stays 100).
Then determine letter grade (A, B, C, D, F) and print both the final score and grade.

---

## Level 6: Advanced Nesting and Complex Logic (Problems 23-25)

### Problem 23: Insurance Premium Calculator
Ask for: age, whether they smoke (yes/no), and whether they exercise regularly (yes/no).

Calculate base premium = $100

Apply these rules in order:
- If age is under 25: add $50
- If age is 25-60: no change
- If age is over 60: add $100

Then:
- If they smoke: double the current premium
- If they exercise regularly: reduce premium by 20%

Print the final premium.

### Problem 24: College Admission
Ask for: GPA (0.0-4.0), SAT score (400-1600), and extracurricular activities (yes/no).

Admission rules:
- If GPA >= 3.5:
  - If SAT >= 1200 OR has extracurriculars: Accepted
  - Otherwise: Waitlisted
- If GPA is 3.0-3.49:
  - If SAT >= 1300 AND has extracurriculars: Accepted
  - If SAT >= 1300 OR has extracurriculars: Waitlisted
  - Otherwise: Rejected
- If GPA < 3.0:
  - If SAT >= 1400 AND has extracurriculars: Waitlisted
  - Otherwise: Rejected

Print the admission decision.

### Problem 25: Complex Shipping and Tax Calculator
Ask for: item price, item weight (kg), destination (domestic/international), and customer status (premium/regular).

Calculate shipping cost:
- If domestic:
  - Weight under 1kg: $5
  - Weight 1-5kg: $10
  - Weight over 5kg: $20
- If international:
  - Weight under 1kg: $15
  - Weight 1-5kg: $30
  - Weight over 5kg: $50

Apply premium discount:
- If customer is premium:
  - If item price > $100: Free shipping
  - Otherwise: 50% off shipping

Calculate tax:
- If domestic: 10% of item price
- If international: No tax

Calculate total = item price + shipping + tax

Print itemized breakdown:
- Item price
- Shipping cost
- Tax amount
- Total cost

---

## Reflection

After completing these problems (or getting as far as you can):

1. **Which problem was the first one that really challenged you?** That's your current skill level!

2. **What patterns did you notice?** 
   - How does nesting change the logic?
   - When is AND vs OR more appropriate?
   - How does order of conditions matter?

3. **Where did you get stuck?**
   - Understanding the problem?
   - Translating logic to code?
   - Nested conditions?
   - Boolean operators?

4. **What strategies helped you solve problems?**
   - Drawing flowcharts?
   - Writing pseudocode first?
   - Testing with different inputs?

Remember: The goal isn't to solve all 25 perfectly on your first try. The goal is to:
- Practice applying what you've learned
- Identify what you understand well
- Discover what needs more practice
- Build confidence with increasingly complex logic

**If you got stuck, that's good!** It shows you where to focus your learning. Review the chapter sections related to where you struggled, then come back and try again.
