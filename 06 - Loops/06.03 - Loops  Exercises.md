# Chapter 6: Loops - Practice Questions

## Example Problems with Detailed Walkthroughs

### Example 1: Understanding Range and For Loop Mechanics
**Problem:** Create a program that prints a countdown from 10 to 1, then prints "Blastoff!". Use range() with appropriate parameters to count backwards. Show the index values as you go.

**Detailed Solution:**

**Step 1: Understand what range produces**
We need to count DOWN from 10 to 1. Let's think about range parameters:
- `range(stop)` - starts at 0, goes up to (not including) stop
- `range(start, stop)` - starts at start, goes up to (not including) stop
- `range(start, stop, step)` - starts at start, goes up/down by step

**Step 2: Plan for counting backwards**
To count from 10 down to 1:
- Start: 10
- Stop: We want to include 1, so stop at 0 (remember, stop is NOT included)
- Step: -1 (negative to count down)

So: `range(10, 0, -1)` produces: 10, 9, 8, 7, 6, 5, 4, 3, 2, 1

**Step 3: Understand the for loop variable**
```python
for i in range(10, 0, -1):
    # i takes on each value: 10, then 9, then 8, etc.
```

The variable `i` is just a temporary container that holds the current number from the range.

**Step 4: Verify our range**
Let's manually check:
- Start at 10: ✓
- Next is 10 + (-1) = 9: ✓
- Next is 9 + (-1) = 8: ✓
- Continue until we reach 0 (not included): ✓
- Last value printed will be 1: ✓

**Complete Solution:**
```python
# Countdown using range with negative step
print("Countdown starting...")

for count in range(10, 0, -1):
    print(f"T-minus {count}")

print("Blastoff! 🚀")
```

**Output:**
```
Countdown starting...
T-minus 10
T-minus 9
T-minus 8
T-minus 7
T-minus 6
T-minus 5
T-minus 4
T-minus 3
T-minus 2
T-minus 1
Blastoff! 🚀
```

**Alternative with visualization:**
```python
# Show what range produces
print("Range produces:", list(range(10, 0, -1)))
print()

# Countdown
for count in range(10, 0, -1):
    print(count, end=" ")
print("\nBlastoff!")
```

**Output:**
```
Range produces: [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]

10 9 8 7 6 5 4 3 2 1 
Blastoff!
```

**Key Concepts:**
- **Range with negative step** counts backwards: `range(10, 0, -1)`
- **Stop value is NOT included**: range(10, 0, -1) goes down to 1, not 0
- **Loop variable changes each iteration**: `count` is 10, then 9, then 8, etc.
- **After the loop**: code after the loop runs once loop is complete
- **Default vs explicit**: `range(10)` starts at 0, `range(10, 0, -1)` is explicit

**Why this works:**
- Negative step makes range count down instead of up
- Stop at 0 ensures 1 is included (since stop is exclusive)
- The loop variable automatically takes each value from the range
- Code after the loop runs exactly once when loop finishes

---

### Example 2: While Loop with Input Validation and Accumulation
**Problem:** Create a program that keeps asking the user for numbers and adds them to a running total. Stop when the user enters 0. Display the count of numbers entered and the average (excluding the 0).

**Detailed Solution:**

**Step 1: Understand the requirements**
- Keep asking for numbers (unknown quantity = while loop)
- Stop when user enters 0
- Track: total sum, count of numbers
- Calculate: average = total / count

**Step 2: Recognize the while loop pattern**
We don't know how many numbers the user will enter. We need to loop "while the number is not 0":
```python
while number != 0:
    # process the number
```

**Step 3: Handle the first input**
Problem: We need a number to check before entering the loop!
```python
number = int(input("Enter a number: "))  # Get first number
while number != 0:
    # process
    number = int(input("Enter a number: "))  # Get next number
```

This pattern is called "read-process-read" or "priming read".

**Step 4: Track accumulation**
We need to accumulate (collect) values:
- `total` - starts at 0, add each number
- `count` - starts at 0, add 1 for each number

```python
total = 0
count = 0

while number != 0:
    total = total + number  # Accumulate sum
    count = count + 1       # Count numbers
```

**Step 5: Handle edge cases**
What if user enters 0 immediately? Count would be 0, and we'd divide by zero!
```python
if count > 0:
    average = total / count
else:
    # Handle no numbers entered
```

**Complete Solution:**
```python
# Initialize tracking variables
total = 0
count = 0

# Get first number
print("Enter numbers to sum (0 to stop)")
number = int(input("Enter a number: "))

# Keep asking while not zero
while number != 0:
    # Add to total
    total = total + number
    
    # Increment count
    count = count + 1
    
    # Get next number
    number = int(input("Enter a number: "))

# Display results
print(f"\n=== Results ===")
print(f"Numbers entered: {count}")
print(f"Total sum: {total}")

if count > 0:
    average = total / count
    print(f"Average: {average:.2f}")
else:
    print("No numbers were entered")
```

**Sample Run:**
```
Enter numbers to sum (0 to stop)
Enter a number: 10
Enter a number: 20
Enter a number: 30
Enter a number: 0

=== Results ===
Numbers entered: 3
Total sum: 60
Average: 20.00
```

**Tracing execution:**
```
Initial: total=0, count=0
Input: 10
  Loop iteration 1: total=10, count=1
  Input: 20
  Loop iteration 2: total=30, count=2
  Input: 30
  Loop iteration 3: total=60, count=3
  Input: 0
  Loop condition (0 != 0) is False → exit loop
Calculate: average = 60/3 = 20.0
```

**Key Concepts:**
- **While loop for unknown iterations**: We don't know how many numbers ahead of time
- **Priming read pattern**: Get first input before loop, get next input at end of loop
- **Accumulator pattern**: Variables that collect values (total, count)
- **Loop exit condition**: `number != 0` means loop continues while number is not 0
- **Edge case handling**: Check count > 0 before calculating average
- **The sentinel value**: 0 is our "sentinel" - special value that signals stop

**Why this works:**
- First input before loop lets us check the condition
- Input at end of loop gets next number for next condition check
- Total and count accumulate correctly because they start at 0
- Checking count prevents division by zero error

---

### Example 3: Break and Continue in a Menu System
**Problem:** Create a number classification program with a menu that runs until the user chooses to quit. For each number, classify it as: positive/negative/zero, even/odd (skip this for zero), and prime (skip for negative). Use break to exit and continue to skip unnecessary checks.

**Detailed Solution:**

**Step 1: Understand control flow statements**
- **break**: Exit the loop completely
- **continue**: Skip rest of current iteration, go to next iteration

**Step 2: Design the menu structure**
```python
while True:  # Infinite loop
    # Show menu
    # Get choice
    if choice == 'quit':
        break  # Exit loop
    # Process other choices
```

**Step 3: Plan the classification logic**
For each number:
1. Classify as positive/negative/zero
2. If zero → skip even/odd and prime (use continue? or just structure)
3. Check even/odd
4. If negative → skip prime check
5. If positive → check if prime

**Step 4: Understand when to use continue**
Continue is useful when we want to skip remaining code in the loop:
```python
if number == 0:
    print("Zero")
    continue  # Skip even/odd and prime checks
# Even/odd check here (skipped if number was 0)
# Prime check here (also skipped if number was 0)
```

**Step 5: Plan prime checking**
A number is prime if it's only divisible by 1 and itself:
- 2 is prime (special case)
- Check if any number from 2 to number-1 divides evenly
- If found a divisor → not prime

**Complete Solution:**
```python
print("=== Number Classifier ===")
print("Analyzes numbers for various properties")
print()

while True:
    # Show menu
    print("\n--- Menu ---")
    print("Enter a number to analyze")
    print("Type 'quit' to exit")
    
    # Get user input
    user_input = input("\nYour choice: ")
    
    # Check for quit
    if user_input.lower() == 'quit':
        print("Thank you for using Number Classifier!")
        break  # Exit the loop
    
    # Convert to number
    try:
        number = int(user_input)
    except:
        print("Invalid input. Please enter a number or 'quit'")
        continue  # Skip to next iteration
    
    # Classification begins
    print(f"\n=== Analyzing {number} ===")
    
    # Step 1: Positive/Negative/Zero
    if number > 0:
        print("✓ Positive number")
    elif number < 0:
        print("✓ Negative number")
    else:
        print("✓ Zero (neither positive nor negative)")
        continue  # Skip even/odd and prime checks for zero
    
    # Step 2: Even/Odd (only for non-zero)
    if number % 2 == 0:
        print("✓ Even number")
    else:
        print("✓ Odd number")
    
    # Step 3: Prime check (only for positive numbers)
    if number < 0:
        print("✓ Prime check skipped (negative number)")
        continue  # Skip prime check
    
    # Check if prime (for positive numbers only)
    if number == 1:
        print("✓ Not prime (1 is not considered prime)")
    elif number == 2:
        print("✓ Prime number (2 is the only even prime)")
    else:
        is_prime = True
        for i in range(2, number):
            if number % i == 0:
                is_prime = False
                break  # Found a divisor, stop checking
        
        if is_prime:
            print("✓ Prime number")
        else:
            print("✓ Not prime (composite number)")
```

**Sample Run:**
```
=== Number Classifier ===
Analyzes numbers for various properties

--- Menu ---
Enter a number to analyze
Type 'quit' to exit

Your choice: 17

=== Analyzing 17 ===
✓ Positive number
✓ Odd number
✓ Prime number

--- Menu ---
Enter a number to analyze
Type 'quit' to exit

Your choice: 0

=== Analyzing 0 ===
✓ Zero (neither positive nor negative)

--- Menu ---
Enter a number to analyze
Type 'quit' to exit

Your choice: -8

=== Analyzing -8 ===
✓ Negative number
✓ Even number
✓ Prime check skipped (negative number)

--- Menu ---
Enter a number to analyze
Type 'quit' to exit

Your choice: quit
Thank you for using Number Classifier!
```

**Key Concepts:**
- **while True creates infinite loop**: Must have break to exit
- **break exits the loop**: Used when user types 'quit'
- **continue skips to next iteration**: Used for zero (skip even/odd/prime)
- **Nested break**: Break inside prime check loop only exits that loop
- **Try-except for error handling**: Catches invalid input
- **Logical flow with continue**: Skips unnecessary checks based on number properties

**Why this works:**
- while True ensures menu keeps running
- break provides the only exit point (quit command)
- continue lets us skip irrelevant checks efficiently
- Each continue goes back to start of while loop (menu)
- Break in prime check only exits the inner for loop

---

## Practice Questions (25 Questions - Increasing Complexity)

### Basic For Loops with Range (Questions 1-5)

1. Print numbers from 0 to 10 using a for loop with range.

2. Print numbers from 5 to 15 (inclusive) using range.

3. Print even numbers from 0 to 20 using range with a step parameter.

4. Count from 20 down to 10 (inclusive) using a for loop with negative step.

5. Ask the user for a number N and print "Hello" exactly N times using a for loop.

### Accumulator Pattern (Questions 6-10)

6. Calculate the sum of numbers from 1 to 100 using a for loop.

7. Ask for 5 numbers from the user and calculate their average.

8. Count how many even numbers exist between 1 and 50.

9. Ask the user for a number and calculate its factorial (n! = n × (n-1) × ... × 1).

10. Find the sum of all numbers from 1 to 100 that are divisible by 3.

### Basic While Loops (Questions 11-15)

11. Create a countdown from 10 to 1 using a while loop, then print "Liftoff!".

12. Keep asking the user for a password until they enter "secret". Count the number of attempts.

13. Ask for positive numbers and sum them. Stop when the user enters a negative number or zero.

14. Create a doubling program: start with 1, keep doubling until the number exceeds 1000. Print each value.

15. Keep asking for numbers until the sum exceeds 100. Display how many numbers were needed.

### Break Statement (Questions 16-20)

16. Find the first number between 1 and 100 that is divisible by both 7 and 13. Stop searching once found.

17. Create a simple number guessing game. The secret number is 42. Break when the user guesses correctly. Limit to 5 attempts.

18. Print numbers from 1 to 50, but stop (break) when you reach a number divisible by both 3 and 7.

19. Ask for numbers and add them to a list. Break when the user enters 'done'. Then display all numbers and their sum.

20. Search for the first prime number greater than 100. Use break when you find it.

### Continue Statement (Questions 21-25)

21. Print numbers from 1 to 20, but skip (don't print) multiples of 3 using continue.

22. Ask for 10 numbers. Sum only the positive ones (skip negative using continue).

23. Print numbers from 1 to 30. Skip numbers that are divisible by both 2 and 3 (divisible by 6).

24. Create a grade processor: ask for 5 test scores. Skip any score above 100 or below 0 (use continue), and calculate the average of valid scores only.

25. FizzBuzz variation: Print numbers 1-50. For multiples of 3, print "Fizz" and continue (skip the number). For multiples of 5, print "Buzz" and continue. For multiples of both, print "FizzBuzz" and continue. Otherwise, print the number.

---

## Tips for Solving These Problems

### Understanding Range
1. **range(stop)** - Starts at 0, goes up to (not including) stop
   - `range(5)` → 0, 1, 2, 3, 4
2. **range(start, stop)** - Starts at start, goes up to (not including) stop
   - `range(2, 7)` → 2, 3, 4, 5, 6
3. **range(start, stop, step)** - Starts at start, increases by step
   - `range(0, 10, 2)` → 0, 2, 4, 6, 8
   - `range(10, 0, -1)` → 10, 9, 8, 7, 6, 5, 4, 3, 2, 1

### For vs While Decision Tree
- **Known iterations**: Use for loop
  - "Print numbers 1 to 10" → for loop
  - "Ask for 5 numbers" → for loop
- **Unknown iterations**: Use while loop
  - "Until user enters 0" → while loop
  - "Until sum exceeds 100" → while loop
  - "Keep asking until valid" → while loop

### Accumulator Pattern
```python
# Initialize before loop
total = 0
count = 0

# Accumulate inside loop
for i in range(10):
    total = total + i  # or total += i
    count = count + 1  # or count += 1

# Use after loop
average = total / count
```

### While Loop Patterns

**Pattern 1: Countdown**
```python
count = 10
while count > 0:
    print(count)
    count = count - 1
```

**Pattern 2: Input validation**
```python
password = ""
while password != "correct":
    password = input("Enter password: ")
```

**Pattern 3: Sum until sentinel**
```python
total = 0
number = int(input("Number (0 to stop): "))
while number != 0:
    total += number
    number = int(input("Number (0 to stop): "))
```

**Pattern 4: Infinite loop with break**
```python
while True:
    choice = input("Enter choice (q to quit): ")
    if choice == 'q':
        break
    # Process choice
```

### Break and Continue Usage

**Break - Exit loop immediately:**
```python
for i in range(100):
    if i == 50:
        break  # Stop loop at 50
    print(i)
# Prints 0 to 49
```

**Continue - Skip to next iteration:**
```python
for i in range(10):
    if i % 2 == 0:
        continue  # Skip even numbers
    print(i)
# Prints 1, 3, 5, 7, 9
```

**In while loops:**
```python
while True:
    number = int(input("Enter number: "))
    if number == 0:
        break  # Exit loop
    if number < 0:
        continue  # Skip negative, ask again
    print(f"Processing {number}")
```

### Common Patterns

**Find first occurrence:**
```python
for i in range(100):
    if condition_met:
        print(f"Found at {i}")
        break
```

**Skip unwanted values:**
```python
for i in range(20):
    if should_skip:
        continue
    # Process i
```

**Validate input:**
```python
while True:
    value = int(input("Enter 1-10: "))
    if 1 <= value <= 10:
        break
    print("Invalid, try again")
```

### Problem-Solving Strategy
1. **Identify loop type**: Known iterations (for) or condition-based (while)?
2. **Determine range parameters**: Start, stop, step needed?
3. **Initialize accumulators**: What values do you need to track?
4. **Plan loop body**: What happens each iteration?
5. **Consider exit conditions**: When does the loop stop?
6. **Check edge cases**: Empty input, zero values, etc.

### Debugging Tips
1. **Print loop variable**: See what values it takes
   ```python
   for i in range(5):
       print(f"i is now: {i}")
   ```
2. **Check range output**: Use list() to see what range produces
   ```python
   print(list(range(10, 0, -1)))
   ```
3. **Trace accumulator**: Print after each update
   ```python
   total = 0
   for i in range(5):
       total += i
       print(f"After adding {i}, total is {total}")
   ```
4. **Verify conditions**: Print boolean values
   ```python
   while count < 10:
       print(f"count={count}, condition={count < 10}")
   ```
5. **Watch for infinite loops**: Ensure while condition eventually becomes False