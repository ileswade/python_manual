# Chapter 5: If Statements and Conditions - Practice Questions

## Example Problems with Detailed Walkthroughs

### Example 1: Age Category Classifier with Proper Code Block Structure
**Problem:** Create a program that asks for a person's age and classifies them into categories: Child (under 13), Teenager (13-19), Adult (20-64), or Senior (65+). The program should also provide age-appropriate messages for each category.

**Detailed Solution:**

**Step 1: Understanding the requirements**
- We need to check multiple conditions (4 age ranges)
- Each condition should trigger a different code block
- Only ONE category should be selected per person
- We need proper indentation to define code blocks

**Step 2: Recognize the decision structure**
This is a perfect case for if-elif-else because:
- We have multiple mutually exclusive categories
- Once we find the right category, we don't need to check others
- Order matters - we need to check from most specific to least specific

**Step 3: Plan the condition order**
Since we're using elif, order is critical. Should we check youngest to oldest or oldest to youngest?

Consider: If we check `age >= 13` first, a 70-year-old would match (70 >= 13 is True) and we'd never get to check if they're a senior!

**Correct order: Check most specific conditions first**
1. Senior (age >= 65)
2. Adult (age >= 20)
3. Teenager (age >= 13)
4. Else (must be child)

**Step 4: Understanding code block indentation**
```python
if age >= 65:
    # Everything indented here is IN the senior block
    statement1
    statement2
elif age >= 20:
    # This block only runs if first condition was False
    statement1
else:
    # This block only runs if all above were False
    statement1
```

**Step 5: Implement with proper code blocks**

**Complete Solution:**
```python
# Get user's age
age = int(input("Enter your age: "))

# Classify age into categories (order matters!)
if age >= 65:
    print("You are a senior")
    print("Senior discounts may apply")
    print("Enjoy your golden years!")
elif age >= 20:
    print("You are an adult")
    print("Full responsibilities apply")
    print("Welcome to adulthood!")
elif age >= 13:
    print("You are a teenager")
    print("Student discounts available")
    print("Enjoy these formative years!")
else:
    print("You are a child")
    print("Child admission rates apply")
    print("Have fun being young!")

# This line is OUTSIDE all code blocks - always runs
print("Thank you for visiting!")
```

**Sample Output (age = 70):**
```
Enter your age: 70
You are a senior
Senior discounts may apply
Enjoy your golden years!
Thank you for visiting!
```

**Sample Output (age = 16):**
```
Enter your age: 16
You are a teenager
Student discounts available
Enjoy these formative years!
Thank you for visiting!
```

**Key Concepts:**
- **Code blocks are defined by indentation** - all lines with the same indentation level belong to the same block
- **Order matters with elif** - conditions are checked top to bottom, first True condition wins
- **Only ONE block executes** - once a condition is True, all remaining elif/else blocks are skipped
- **Use elif, not separate ifs** - separate ifs would check every condition (inefficient and potentially incorrect)
- **Lines outside the if structure** (same indentation as the if) always run regardless of conditions

**Why this works:**
- Each age category has its own code block (multiple print statements)
- The "Thank you" line is at the same indentation as `if`, so it's outside all blocks
- By checking age >= 65 first, we ensure seniors aren't incorrectly categorized as adults

---

### Example 2: Compound Conditions with AND/OR Logic
**Problem:** Create a movie ticket pricing system. Admission is $15 for adults, but there are discounts: Students get $10 tickets, Seniors (65+) get $8 tickets, and children under 12 get $7 tickets. Students who are also seniors get the better discount. Handle the logic properly.

**Detailed Solution:**

**Step 1: Identify all conditions**
- Age (for child and senior discounts)
- Student status
- Default adult price

**Step 2: Understand logical operators**
- **AND**: Both conditions must be True
  - Example: `age >= 65 and is_student` (both must be True)
- **OR**: At least one condition must be True  
  - Example: `age < 12 or age >= 65` (either can be True)

**Step 3: Plan the decision structure**
What discounts are available?
- Child (age < 12): $7
- Senior (age >= 65): $8
- Student (any age): $10
- Adult (default): $15

**Step 4: Handle overlapping conditions**
Problem: A senior student could match multiple conditions!
- They're a senior (age >= 65) → $8
- They're a student → $10

Which should we give them? The **better discount** ($8).

**Solution: Check most beneficial discounts first**

**Step 5: Consider using compound conditions**
We could check: "Is this person a child OR a senior OR a student?"

```python
if age < 12 or age >= 65 or is_student:
    # Apply some discount
```

But this doesn't tell us WHICH discount! We need separate checks.

**Complete Solution:**
```python
# Get information
age = int(input("Enter your age: "))
student_response = input("Are you a student? (yes/no): ")
is_student = (student_response.lower() == "yes")

# Determine ticket price (check best discounts first)
if age < 12:
    price = 7
    print("Child ticket: $7")
elif age >= 65:
    price = 8
    print("Senior ticket: $8")
elif is_student:
    price = 10
    print("Student ticket: $10")
else:
    price = 15
    print("Adult ticket: $15")

# Show final price
print(f"Total: ${price}")

# Additional validation with compound conditions
if age < 0 or age > 120:
    print("Warning: Age seems invalid!")
```

**Alternative approach with explicit compound conditions:**
```python
age = int(input("Enter your age: "))
student_response = input("Are you a student? (yes/no): ")
is_student = (student_response.lower() == "yes")

# Using AND to check multiple conditions together
if age < 12 and is_student:
    price = 7  # Child price (student status doesn't improve it)
    print("Child ticket: $7 (student rate doesn't apply)")
elif age < 12:
    price = 7
    print("Child ticket: $7")
elif age >= 65 and is_student:
    price = 8  # Senior gets better rate than student
    print("Senior ticket: $8 (better than student rate)")
elif age >= 65:
    price = 8
    print("Senior ticket: $8")
elif is_student:
    price = 10
    print("Student ticket: $10")
else:
    price = 15
    print("Adult ticket: $15")

print(f"Total: ${price}")
```

**Sample Run:**
```
Enter your age: 67
Are you a student? (yes/no): yes
Senior ticket: $8 (better than student rate)
Total: $8
```

**Key Concepts:**
- **AND requires both conditions True**: `age >= 65 and is_student` - person must be BOTH senior AND student
- **OR requires at least one True**: `age < 12 or age >= 65` - person can be EITHER child OR senior
- **Operator precedence**: Comparisons happen before logical operators (and, or)
- **Truth tables matter**: Understanding how AND/OR work prevents logic errors
- **Order still matters**: Check best discounts first to avoid giving worse deals

**Why this works:**
- By checking child first, we give the lowest price to those under 12
- Senior checked before student ensures seniors get their better rate
- The elif structure ensures only ONE price is assigned
- Compound conditions let us handle overlapping cases explicitly

---

### Example 3: Nested If Statements for Complex Logic
**Problem:** Create a login system that checks username AND password. If the username is correct, check the password. If the password is also correct, check if the user has admin privileges for a special message. Show appropriate error messages for each failure point.

**Detailed Solution:**

**Step 1: Understand nested decision logic**
We have layers of decisions:
1. Is username correct?
   - If NO → error message
   - If YES → check password
2. Is password correct?
   - If NO → error message
   - If YES → check admin status
3. Is user an admin?
   - If YES → special admin message
   - If NO → regular user message

**Step 2: Recognize when to use nesting**
Use nested if statements when:
- You need to check a second condition ONLY if the first is true
- Each level of decision depends on the previous one
- You want to provide specific feedback at each decision point

**Step 3: Plan the indentation levels**
```python
if username_correct:           # Level 0 (no indent)
    if password_correct:       # Level 1 (one indent) - only checked if username OK
        if is_admin:          # Level 2 (two indents) - only checked if both OK
            # admin code       # Level 3 (three indents)
        else:
            # regular code     # Level 3 (three indents)
    else:
        # wrong password      # Level 2 (two indents)
else:
    # wrong username          # Level 1 (one indent)
```

**Step 4: Understand code block scope**
Each nested level creates a new code block:
- The password check only runs if username is correct
- The admin check only runs if both username AND password are correct
- Each level can have multiple statements in its code block

**Complete Solution:**
```python
# Define correct credentials
correct_username = "admin"
correct_password = "secret123"
admin_users = ["admin", "superuser"]

# Get user input
username = input("Enter username: ")
password = input("Enter password: ")

# Nested authentication logic
if username == correct_username:
    print("Username accepted")
    
    # Only check password if username was correct
    if password == correct_password:
        print("Password accepted")
        print("Login successful!")
        
        # Only check admin status if login succeeded
        if username in admin_users:
            print("*** ADMIN ACCESS GRANTED ***")
            print("You have administrative privileges")
            print("Welcome to the admin panel")
        else:
            print("Standard user access granted")
            print("Welcome to the system")
    else:
        print("Incorrect password")
        print("Access denied")
else:
    print("Username not found")
    print("Access denied")

print("Login attempt completed")
```

**Visualization of nested execution:**
```
username correct? 
    YES → "Username accepted"
          password correct?
              YES → "Password accepted"
                    is admin?
                        YES → admin messages
                        NO → regular user messages
              NO → "Incorrect password"
    NO → "Username not found"
```

**Sample Run (successful admin login):**
```
Enter username: admin
Enter password: secret123
Username accepted
Password accepted
Login successful!
*** ADMIN ACCESS GRANTED ***
You have administrative privileges
Welcome to the admin panel
Login attempt completed
```

**Sample Run (wrong password):**
```
Enter username: admin
Enter password: wrong
Username accepted
Incorrect password
Access denied
Login attempt completed
```

**Alternative: Combining conditions vs nesting:**
```python
# This approach uses compound conditions instead of nesting
username = input("Enter username: ")
password = input("Enter password: ")

if username == correct_username and password == correct_password:
    print("Login successful!")
    if username in admin_users:
        print("Admin access granted")
    else:
        print("Standard user access")
elif username == correct_username:
    print("Username correct but password wrong")
elif password == correct_password:
    print("Password correct but username wrong")
else:
    print("Both username and password incorrect")
```

**Key Concepts:**
- **Each level of nesting adds one indentation** - visually shows decision hierarchy
- **Inner blocks only execute if outer conditions are True** - this is the power of nesting
- **You can have multiple statements in each block** - all at the same indentation level
- **Nesting shows dependency** - password check depends on username being correct
- **Avoid excessive nesting** - more than 3 levels becomes hard to read
- **Alternative: Compound conditions** - sometimes `and` is cleaner than nesting

**Why this works:**
- We never check the password unless the username is correct (efficient and logical)
- Each failure point provides specific feedback
- The nested structure matches the logical flow of authentication
- Indentation makes the decision hierarchy clear

**When to use nesting vs compound conditions:**
- **Use nesting when**: You want to execute different code at each decision level
- **Use compound conditions when**: You just need to check if all conditions are True together

---

## Practice Questions (25 Questions - Increasing Complexity)

### Basic If Statements and Code Blocks (Questions 1-5)

1. Write a program that asks for a number and prints "Positive" if it's greater than 0. Include a print statement outside the if block that always displays "Program complete".

2. Ask for a person's age and print "You can vote" if they are 18 or older. Make sure your code block includes TWO print statements that only run when the condition is true.

3. Create a program that checks if a password is correct. Use "python123" as the correct password. Print "Access granted" and "Welcome to the system" in the code block if correct. Print "Done checking" outside the block.

4. Ask for a temperature and print "It's freezing" with "Wear a heavy coat" if the temperature is below 32. These should be in the same code block.

5. Write a program that checks if a number is even (use % operator). If even, print "Even number", "Divisible by 2", and "No remainder" - all in the same code block.

### If-Else Statements (Questions 6-10)

6. Ask for a number and print "Positive" if > 0, otherwise print "Not positive". Each branch should have TWO print statements.

7. Create a pass/fail system. If score >= 60, print "Pass" and "Congratulations", otherwise print "Fail" and "Study harder".

8. Check if a person can drive. If age >= 16, print "You can drive" and "Get your license", else print "Too young" and "Wait X years" (calculate X).

9. Ask for a day number (1-7). If it's 6 or 7, print "Weekend", otherwise print "Weekday". Use if-else structure.

10. Create a simple even/odd checker. Print "Even" with "Divisible by 2" for even numbers, print "Odd" with "Has remainder" for odd numbers.

### If-Elif-Else Chains (Questions 11-15)

11. Create a grade converter: 90-100 = A, 80-89 = B, 70-79 = C, 60-69 = D, below 60 = F. Print the grade with an appropriate message.

12. Build a BMI category system: <18.5 = Underweight, 18.5-24.9 = Normal, 25-29.9 = Overweight, 30+ = Obese. Ask for height and weight, calculate BMI, and categorize.

13. Create a shipping cost calculator: 0-5 lbs = $5, 5-20 lbs = $10, 20-50 lbs = $20, over 50 lbs = $50. Ask for weight and display cost.

14. Build a tax bracket calculator: $0-$10k = 10%, $10k-$40k = 12%, $40k-$85k = 22%, $85k+ = 24%. Ask for income and calculate tax owed.

15. Make a season detector: Ask for month number (1-12) and print which season it is (Winter: 12,1,2; Spring: 3,4,5; Summer: 6,7,8; Fall: 9,10,11).

### Compound Conditions with AND/OR (Questions 16-20)

16. Create a movie rating system. Person can watch if they're 17+ OR (13+ AND has parent permission). Ask for age and parent permission, then decide.

17. Build a scholarship checker. Student qualifies if GPA >= 3.5 AND (income < $50k OR is first generation). Ask for all criteria and determine eligibility.

18. Make a loan approval system. Approve if credit score >= 700 AND (income > $50k OR has cosigner). Check all conditions.

19. Create a park entry validator. Free entry if age < 5 OR age >= 65 OR is resident. Otherwise charge $10. Use OR conditions properly.

20. Build a restaurant reservation validator. Accept reservation if (party size <= 8 AND time between 5-9pm) OR has VIP status. Check both conditions.

### Nested If Statements (Questions 21-25)

21. Create a two-level authentication: First check username, then check password only if username is correct. Provide specific error messages for each level.

22. Build a discount calculator: First check if customer is a member. If yes, check if purchase > $100 for additional discount. Non-members always pay full price. Calculate final price with appropriate discounts.

23. Make a college admission system: First check if GPA >= 3.0. If yes, check if SAT >= 1200 OR has special talent. Provide specific feedback at each decision level.

24. Create a game difficulty selector: Ask for experience level (1-3). If expert (3), ask if they want nightmare mode. If intermediate (2), ask if they want hard mode. Beginners (1) always get easy mode.

25. Build a comprehensive grading system: First check if student passed (>= 60). If passed, check if they made honor roll (>= 90). If honor roll, check if they made perfect score (100). Provide specific congratulatory messages at each achievement level.

---

## Tips for Solving These Problems

### Understanding Code Blocks
1. **Indentation creates code blocks** - all lines with the same indentation belong together
2. **Code blocks execute as a unit** - all statements in a block run when the condition is True
3. **Four spaces is standard** - use consistent indentation (VS Code helps with this)
4. **The colon (:) starts a block** - if, elif, else all end with colons
5. **Blocks can be nested** - each level adds another indentation

### Working with If-Elif-Else
1. **Order matters with elif** - conditions checked top to bottom
2. **First True condition wins** - remaining elif/else blocks are skipped
3. **Only ONE block executes** - never multiple blocks in same if-elif-else chain
4. **Check specific before general** - put most specific conditions first
5. **Else is the catchall** - runs when all other conditions are False

### Compound Conditions Strategy
1. **AND - both must be True**
   - Use when you need ALL conditions satisfied
   - Example: `age >= 21 and has_id`
2. **OR - at least one must be True**
   - Use when ANY condition being True is sufficient
   - Example: `is_weekend or is_holiday`
3. **NOT - reverses the condition**
   - Use to check for absence or negation
   - Example: `not is_raining`
4. **Use parentheses for clarity** - `(a and b) or c` is clearer than `a and b or c`

### Nested If Statements Tips
1. **Use when checking depends on previous check** - password only matters if username is correct
2. **Each level adds one indent** - visualizes the decision hierarchy
3. **Limit nesting depth** - more than 3 levels gets confusing
4. **Consider alternatives** - sometimes compound conditions (AND) are cleaner
5. **Provide feedback at each level** - tell user which check failed

### Common Patterns
```python
# Pattern 1: Simple validation
if condition:
    # do something
    # multiple statements in block
print("This always runs")

# Pattern 2: Binary choice
if condition:
    # option A
else:
    # option B

# Pattern 3: Multiple categories
if condition1:
    # category 1
elif condition2:
    # category 2
elif condition3:
    # category 3
else:
    # default category

# Pattern 4: Compound conditions
if condition1 and condition2:
    # both must be True

if condition1 or condition2:
    # either can be True

# Pattern 5: Nested decisions
if outer_condition:
    # outer block
    if inner_condition:
        # inner block - only if outer was True
    else:
        # inner else
else:
    # outer else
```

### Problem-Solving Strategy
1. **Read carefully** - what conditions need to be checked?
2. **Identify structure** - simple if, if-else, if-elif-else, or nested?
3. **Plan condition order** - most specific to least specific for elif
4. **Draw it out** - sketch the decision tree if complex
5. **Consider edge cases** - what if inputs are negative, zero, or extreme?
6. **Test incrementally** - verify each condition works before adding more

### Debugging Tips
1. **Check indentation** - inconsistent spacing breaks code blocks
2. **Verify condition logic** - use print to see what's True/False
3. **Test each branch** - make sure every code block can be reached
4. **Watch for = vs ==** - assignment vs comparison
5. **Trace execution** - follow the path your code takes with given input