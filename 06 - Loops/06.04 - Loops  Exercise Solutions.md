# Chapter 6: Loops - Solutions Guide

## Basic For Loops with Range (Questions 1-5)

### Question 1
**Problem:** Print numbers from 0 to 10 using a for loop with range.

**Solution Approach:**
- Range starting at 0 (default) going to 11 (to include 10)
- Or use explicit: range(0, 11)
- Remember: stop value is NOT included

**Complete Solution:**
```python
# Method 1: Using default start
for i in range(11):
    print(i)

# Method 2: Explicit start and stop
for i in range(0, 11):
    print(i)
```

**Output:**
```
0
1
2
3
4
5
6
7
8
9
10
```

**Key Concepts:**
- `range(11)` produces 0, 1, 2, ..., 10
- Stop value (11) is not included, so last number printed is 10
- Default start is 0 when not specified
- Loop variable `i` takes each value from range

---

### Question 2
**Problem:** Print numbers from 5 to 15 (inclusive) using range.

**Solution Approach:**
- Start at 5
- Stop at 16 (to include 15)
- Use range(5, 16)

**Complete Solution:**
```python
# Print from 5 to 15
for num in range(5, 16):
    print(num)
```

**Output:**
```
5
6
7
8
9
10
11
12
13
14
15
```

**Key Concepts:**
- `range(5, 16)` starts at 5, stops before 16
- To include 15, we use 16 as stop value
- Second parameter is always excluded
- Variable naming: use meaningful names like `num` instead of just `i`

---

### Question 3
**Problem:** Print even numbers from 0 to 20 using range with a step parameter.

**Solution Approach:**
- Start at 0 (first even number)
- Stop at 21 (to include 20)
- Step by 2 (to get every second number)
- range(0, 21, 2)

**Complete Solution:**
```python
# Print even numbers using step
for even in range(0, 21, 2):
    print(even)
```

**Alternative without step:**
```python
# Without using step (less efficient)
for i in range(21):
    if i % 2 == 0:
        print(i)
```

**Output:**
```
0
2
4
6
8
10
12
14
16
18
20
```

**Key Concepts:**
- Step parameter (third argument) determines increment
- `range(0, 21, 2)` gives 0, 2, 4, 6, ..., 20
- Using step is more efficient than checking each number
- Step of 2 skips odd numbers automatically

---

### Question 4
**Problem:** Count from 20 down to 10 (inclusive) using a for loop with negative step.

**Solution Approach:**
- Start at 20
- Stop at 9 (to include 10, since stop is excluded)
- Step by -1 to count down
- range(20, 9, -1)

**Complete Solution:**
```python
# Count down from 20 to 10
for count in range(20, 9, -1):
    print(count)
```

**Output:**
```
20
19
18
17
16
15
14
13
12
11
10
```

**Key Concepts:**
- Negative step makes range count backwards
- Stop value still excluded: stop at 9 to include 10
- `range(20, 9, -1)` produces 20, 19, 18, ..., 10
- Must use negative step for counting down

---

### Question 5
**Problem:** Ask the user for a number N and print "Hello" exactly N times using a for loop.

**Solution Approach:**
- Get N from user
- Use range(N) to loop N times
- Loop variable not needed for the task (use _ convention)

**Complete Solution:**
```python
# Get number of times to print
n = int(input("How many times should I say hello? "))

# Print hello N times
for i in range(n):
    print("Hello")

# Show count
print(f"\nSaid hello {n} times!")
```

**Alternative with counter display:**
```python
n = int(input("How many times should I say hello? "))

for i in range(n):
    print(f"Hello #{i + 1}")
```

**Sample Run:**
```
How many times should I say hello? 3
Hello
Hello
Hello

Said hello 3 times!
```

**Key Concepts:**
- `range(n)` creates a sequence of n numbers (0 to n-1)
- Loop runs exactly n times
- Even though range starts at 0, it still loops n times
- Can use loop variable for counting if needed

---

## Accumulator Pattern (Questions 6-10)

### Question 6
**Problem:** Calculate the sum of numbers from 1 to 100 using a for loop.

**Solution Approach:**
- Initialize sum to 0
- Loop from 1 to 100 (inclusive)
- Add each number to sum (accumulation)
- Display final sum

**Complete Solution:**
```python
# Initialize accumulator
total = 0

# Add numbers 1 to 100
for number in range(1, 101):
    total = total + number

# Display result
print(f"Sum of 1 to 100: {total}")

# Verify with formula: n(n+1)/2
formula_result = 100 * 101 // 2
print(f"Formula verification: {formula_result}")
```

**Output:**
```
Sum of 1 to 100: 5050
Formula verification: 5050
```

**Key Concepts:**
- **Accumulator pattern**: variable that collects values over iterations
- Initialize before loop: `total = 0`
- Update inside loop: `total = total + number` (or `total += number`)
- Sum of 1 to n formula: n(n+1)/2 = 100(101)/2 = 5050
- Accumulator starts at appropriate value (0 for sum, 1 for product)

---

### Question 7
**Problem:** Ask for 5 numbers from the user and calculate their average.

**Solution Approach:**
- Loop 5 times to get input
- Accumulate the sum
- Calculate average = sum / count
- Count is known (5), so use for loop

**Complete Solution:**
```python
# Initialize sum
total = 0

# Get 5 numbers
print("Enter 5 numbers:")
for i in range(5):
    number = float(input(f"Number {i + 1}: "))
    total = total + number

# Calculate average
average = total / 5
print(f"\nTotal: {total}")
print(f"Average: {average:.2f}")
```

**Sample Run:**
```
Enter 5 numbers:
Number 1: 10
Number 2: 20
Number 3: 30
Number 4: 15
Number 5: 25

Total: 100.0
Average: 20.00
```

**Key Concepts:**
- Loop exactly 5 times: `range(5)`
- Accumulate sum inside loop
- Use loop variable for display: `i + 1` (humans count from 1)
- Average = sum / count
- Use float for decimal inputs

---

### Question 8
**Problem:** Count how many even numbers exist between 1 and 50.

**Solution Approach:**
- Initialize counter to 0
- Check each number from 1 to 50
- If even (% 2 == 0), increment counter
- Display count

**Complete Solution:**
```python
# Initialize counter
even_count = 0

# Check each number from 1 to 50
for number in range(1, 51):
    if number % 2 == 0:
        even_count = even_count + 1

# Display result
print(f"Even numbers between 1 and 50: {even_count}")

# Verify: should be 25 (2, 4, 6, ..., 50)
```

**Alternative using step:**
```python
# More efficient: just count the even numbers directly
even_count = len(range(2, 51, 2))
print(f"Even numbers between 1 and 50: {even_count}")

# Or calculate directly
even_count = 50 // 2
print(f"Even numbers between 1 and 50: {even_count}")
```

**Output:**
```
Even numbers between 1 and 50: 25
```

**Key Concepts:**
- Counter accumulator: increments by 1 for each match
- Modulo operator checks even: `number % 2 == 0`
- Could use range with step for efficiency: `range(2, 51, 2)`
- Mathematical approach: there are n/2 even numbers from 1 to n

---

### Question 9
**Problem:** Ask the user for a number and calculate its factorial (n! = n × (n-1) × ... × 1).

**Solution Approach:**
- Factorial requires multiplication
- Initialize product to 1 (not 0!)
- Multiply by each number from 1 to n
- 5! = 5 × 4 × 3 × 2 × 1 = 120

**Complete Solution:**
```python
# Get number
n = int(input("Enter a number to find factorial: "))

# Initialize product accumulator
factorial = 1

# Multiply by each number from 1 to n
for i in range(1, n + 1):
    factorial = factorial * i

# Display result
print(f"{n}! = {factorial}")
```

**With step-by-step display:**
```python
n = int(input("Enter a number to find factorial: "))

factorial = 1
print(f"\nCalculating {n}!:")

for i in range(1, n + 1):
    factorial = factorial * i
    print(f"After multiplying by {i}: {factorial}")

print(f"\n{n}! = {factorial}")
```

**Sample Run:**
```
Enter a number to find factorial: 5

Calculating 5!:
After multiplying by 1: 1
After multiplying by 2: 2
After multiplying by 3: 6
After multiplying by 4: 24
After multiplying by 5: 120

5! = 120
```

**Key Concepts:**
- **Product accumulator** starts at 1 (not 0)
- Multiply each iteration: `factorial = factorial * i`
- Range is 1 to n+1 to include n
- Factorial grows very quickly (10! = 3,628,800)
- 0! = 1 by mathematical definition

---

### Question 10
**Problem:** Find the sum of all numbers from 1 to 100 that are divisible by 3.

**Solution Approach:**
- Check each number from 1 to 100
- If divisible by 3 (% 3 == 0), add to sum
- Accumulate the sum

**Complete Solution:**
```python
# Initialize sum
total = 0

# Check each number
for number in range(1, 101):
    if number % 3 == 0:
        total = total + number

# Display result
print(f"Sum of numbers divisible by 3: {total}")
```

**More efficient using step:**
```python
# Use step to only get multiples of 3
total = 0

for number in range(3, 101, 3):
    total = total + number

print(f"Sum of numbers divisible by 3: {total}")
```

**Output:**
```
Sum of numbers divisible by 3: 1683
```

**Verification:**
Numbers divisible by 3: 3, 6, 9, ..., 99
This is 33 numbers (100/3 = 33.33, so 33 complete multiples)
Sum = 3 + 6 + 9 + ... + 99 = 1683

**Key Concepts:**
- Conditional accumulation: only add if condition met
- `number % 3 == 0` checks divisibility
- More efficient: `range(3, 101, 3)` gives only multiples of 3
- Combining filtering with accumulation

---

## Basic While Loops (Questions 11-15)

### Question 11
**Problem:** Create a countdown from 10 to 1 using a while loop, then print "Liftoff!".

**Solution Approach:**
- Initialize counter at 10
- Loop while counter > 0
- Print counter, then decrement
- After loop, print "Liftoff!"

**Complete Solution:**
```python
# Initialize countdown
count = 10

# Countdown loop
print("Countdown starting...")
while count > 0:
    print(count)
    count = count - 1

# Liftoff!
print("Liftoff! 🚀")
```

**Output:**
```
Countdown starting...
10
9
8
7
6
5
4
3
2
1
Liftoff! 🚀
```

**Key Concepts:**
- While loop checks condition before each iteration
- Must update counter inside loop or it runs forever
- `count = count - 1` makes progress toward exit condition
- Condition `count > 0` becomes False when count reaches 0

---

### Question 12
**Problem:** Keep asking the user for a password until they enter "secret". Count the number of attempts.

**Solution Approach:**
- Initialize attempt counter
- Loop while password is not "secret"
- Increment counter each attempt
- Display number of attempts

**Complete Solution:**
```python
# Initialize
attempts = 0
correct_password = "secret"

# Keep asking until correct
password = input("Enter password: ")
attempts = attempts + 1

while password != correct_password:
    print("Incorrect password. Try again.")
    password = input("Enter password: ")
    attempts = attempts + 1

# Success
print(f"Access granted!")
print(f"It took you {attempts} attempt(s)")
```

**Sample Run:**
```
Enter password: hello
Incorrect password. Try again.
Enter password: test
Incorrect password. Try again.
Enter password: secret
Access granted!
It took you 3 attempt(s)
```

**Key Concepts:**
- Priming read: get first input before loop
- Loop continues while condition is True
- Get next input at end of loop
- Counter tracks all attempts (including first)

---

### Question 13
**Problem:** Ask for positive numbers and sum them. Stop when the user enters a negative number or zero.

**Solution Approach:**
- Initialize sum to 0
- Get first number
- While number is positive, add and get next
- Display total

**Complete Solution:**
```python
# Initialize sum
total = 0

# Get first number
print("Enter positive numbers (0 or negative to stop)")
number = float(input("Enter number: "))

# Sum while positive
while number > 0:
    total = total + number
    number = float(input("Enter number: "))

# Display result
print(f"\nTotal sum: {total}")
```

**Sample Run:**
```
Enter positive numbers (0 or negative to stop)
Enter number: 10
Enter number: 20
Enter number: 15
Enter number: 0

Total sum: 45.0
```

**Key Concepts:**
- Sentinel value: 0 or negative stops the loop
- Condition `number > 0` ensures only positive numbers summed
- Priming read pattern
- Loop exits immediately when non-positive entered

---

### Question 14
**Problem:** Create a doubling program: start with 1, keep doubling until the number exceeds 1000. Print each value.

**Solution Approach:**
- Start with 1
- While number <= 1000, print and double
- Stop when exceeds 1000

**Complete Solution:**
```python
# Start with 1
number = 1

# Keep doubling while <= 1000
print("Doubling sequence:")
while number <= 1000:
    print(number)
    number = number * 2

print(f"\nStopped at {number} (exceeds 1000)")
```

**Output:**
```
Doubling sequence:
1
2
4
8
16
32
64
128
256
512
1024

Stopped at 1024 (exceeds 1000)
```

**Key Concepts:**
- Geometric progression (doubling)
- Condition checks at start of each iteration
- 1024 is first value exceeding 1000
- Number grows exponentially (powers of 2)

---

### Question 15
**Problem:** Keep asking for numbers until the sum exceeds 100. Display how many numbers were needed.

**Solution Approach:**
- Track sum and count
- Get numbers while sum <= 100
- Count each number entered

**Complete Solution:**
```python
# Initialize
total = 0
count = 0

# Keep asking until sum exceeds 100
print("Enter numbers (will stop when sum exceeds 100)")

while total <= 100:
    number = float(input(f"Number {count + 1}: "))
    total = total + number
    count = count + 1
    print(f"Current sum: {total}")

# Display results
print(f"\nSum exceeded 100!")
print(f"Final sum: {total}")
print(f"Numbers entered: {count}")
```

**Sample Run:**
```
Enter numbers (will stop when sum exceeds 100)
Number 1: 30
Current sum: 30.0
Number 2: 40
Current sum: 70.0
Number 3: 35
Current sum: 105.0

Sum exceeded 100!
Final sum: 105.0
Numbers entered: 3
```

**Key Concepts:**
- Condition based on accumulated value
- Count tracks number of inputs
- Loop exits when condition no longer met
- Shows progress with current sum

---

## Break Statement (Questions 16-20)

### Question 16
**Problem:** Find the first number between 1 and 100 that is divisible by both 7 and 13. Stop searching once found.

**Solution Approach:**
- Loop through 1 to 100
- Check if divisible by both 7 AND 13
- When found, print and break
- If divisible by both, also divisible by 91 (7×13)

**Complete Solution:**
```python
# Search for number divisible by both 7 and 13
print("Searching for number divisible by both 7 and 13...")

for number in range(1, 101):
    if number % 7 == 0 and number % 13 == 0:
        print(f"Found: {number}")
        break
else:
    print("No number found")

# Note: 7 × 13 = 91, so 91 is the answer
```

**Output:**
```
Searching for number divisible by both 7 and 13...
Found: 91
```

**Key Concepts:**
- Break exits loop immediately
- AND condition requires both divisibilities
- LCM of 7 and 13 is 91 (7×13, since they're prime)
- Else clause on for loop runs if no break occurred

---

### Question 17
**Problem:** Create a simple number guessing game. The secret number is 42. Break when the user guesses correctly. Limit to 5 attempts.

**Solution Approach:**
- Secret number is 42
- Loop up to 5 times
- Get guess each iteration
- Break if correct
- Track attempts

**Complete Solution:**
```python
# Secret number
secret = 42
max_attempts = 5

print("Guess the number (1-100)")
print(f"You have {max_attempts} attempts")

# Guessing loop
for attempt in range(1, max_attempts + 1):
    guess = int(input(f"\nAttempt {attempt}: "))
    
    if guess == secret:
        print(f"🎉 Correct! You guessed it in {attempt} attempts!")
        break
    elif guess < secret:
        print("Too low!")
    else:
        print("Too high!")
else:
    print(f"\n😞 Out of attempts! The number was {secret}")
```

**Sample Run (win):**
```
Guess the number (1-100)
You have 5 attempts

Attempt 1: 50
Too high!

Attempt 2: 25
Too low!

Attempt 3: 40
Too low!

Attempt 4: 42
🎉 Correct! You guessed it in 4 attempts!
```

**Key Concepts:**
- Break exits immediately on correct guess
- For-else: else runs if loop completes without break
- Provides hints (too high/low)
- Tracks attempt number using loop variable

---

### Question 18
**Problem:** Print numbers from 1 to 50, but stop (break) when you reach a number divisible by both 3 and 7.

**Solution Approach:**
- Loop 1 to 50
- Print each number
- Check if divisible by both 3 and 7
- Break when condition met

**Complete Solution:**
```python
# Print until divisible by both 3 and 7
for number in range(1, 51):
    print(number, end=" ")
    
    if number % 3 == 0 and number % 7 == 0:
        print(f"\n\nStopped at {number} (divisible by both 3 and 7)")
        break
```

**Output:**
```
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 

Stopped at 21 (divisible by both 3 and 7)
```

**Key Concepts:**
- LCM of 3 and 7 is 21
- Break immediately upon finding match
- Print with `end=" "` keeps numbers on one line
- Check condition after printing the number

---

### Question 19
**Problem:** Ask for numbers and add them to a list. Break when the user enters 'done'. Then display all numbers and their sum.

**Solution Approach:**
- Use while True for infinite loop
- Get input as string
- Check if 'done', then break
- Otherwise convert to number and add to list

**Complete Solution:**
```python
# Initialize list
numbers = []

print("Enter numbers (type 'done' to finish)")

# Input loop
while True:
    user_input = input("Enter number: ")
    
    # Check for done
    if user_input.lower() == 'done':
        break
    
    # Convert and add to list
    try:
        number = float(user_input)
        numbers.append(number)
    except:
        print("Invalid input, try again")

# Display results
if len(numbers) > 0:
    print(f"\nNumbers entered: {numbers}")
    print(f"Count: {len(numbers)}")
    print(f"Sum: {sum(numbers)}")
    print(f"Average: {sum(numbers)/len(numbers):.2f}")
else:
    print("No numbers entered")
```

**Sample Run:**
```
Enter numbers (type 'done' to finish)
Enter number: 10
Enter number: 20
Enter number: 30
Enter number: done

Numbers entered: [10.0, 20.0, 30.0]
Count: 3
Sum: 60.0
Average: 20.00
```

**Key Concepts:**
- While True creates infinite loop
- Break provides exit
- Try-except handles invalid input
- Process data after loop completes

---

### Question 20
**Problem:** Search for the first prime number greater than 100. Use break when you find it.

**Solution Approach:**
- Start checking from 101
- For each number, check if prime
- Prime: only divisible by 1 and itself
- Break when first prime found

**Complete Solution:**
```python
# Search for first prime > 100
print("Searching for first prime number greater than 100...")

# Start from 101
number = 101

# Keep searching
while True:
    # Check if prime
    is_prime = True
    
    for divisor in range(2, number):
        if number % divisor == 0:
            is_prime = False
            break  # Not prime, stop checking divisors
    
    # If prime, we found it
    if is_prime:
        print(f"First prime > 100: {number}")
        break  # Exit main loop
    
    # Try next number
    number = number + 1
```

**More efficient version:**
```python
import math

# Search for first prime > 100
for number in range(101, 200):
    is_prime = True
    
    # Only check up to square root
    for divisor in range(2, int(math.sqrt(number)) + 1):
        if number % divisor == 0:
            is_prime = False
            break
    
    if is_prime:
        print(f"First prime > 100: {number}")
        break
```

**Output:**
```
First prime > 100: 101
```

**Key Concepts:**
- Nested break: inner break exits divisor check, outer break exits search
- 101 is prime (only divisible by 1 and 101)
- Efficiency: only check divisors up to sqrt(number)
- Two levels of break for different purposes

---

## Continue Statement (Questions 21-25)

### Question 21
**Problem:** Print numbers from 1 to 20, but skip (don't print) multiples of 3 using continue.

**Solution Approach:**
- Loop 1 to 20
- Check if divisible by 3
- If yes, continue (skip print)
- Otherwise, print number

**Complete Solution:**
```python
# Print numbers except multiples of 3
print("Numbers from 1 to 20 (skipping multiples of 3):")

for number in range(1, 21):
    if number % 3 == 0:
        continue  # Skip multiples of 3
    print(number, end=" ")

print()  # New line at end
```

**Output:**
```
Numbers from 1 to 20 (skipping multiples of 3):
1 2 4 5 7 8 10 11 13 14 16 17 19 20 
```

**Key Concepts:**
- Continue skips rest of loop body, goes to next iteration
- Multiples of 3 (3, 6, 9, 12, 15, 18) are skipped
- Print statement never reached for multiples of 3
- More concise than if-else for skipping logic

---

### Question 22
**Problem:** Ask for 10 numbers. Sum only the positive ones (skip negative using continue).

**Solution Approach:**
- Loop 10 times
- Get number each iteration
- If negative or zero, continue (skip)
- Add positive numbers to sum

**Complete Solution:**
```python
# Initialize sum
total = 0

print("Enter 10 numbers (only positive will be summed)")

# Get 10 numbers
for i in range(10):
    number = float(input(f"Number {i + 1}: "))
    
    # Skip non-positive
    if number <= 0:
        print("  (Skipped - not positive)")
        continue
    
    # Add positive numbers
    total = total + number
    print(f"  (Added - running total: {total})")

# Display result
print(f"\nSum of positive numbers: {total}")
```

**Sample Run:**
```
Enter 10 numbers (only positive will be summed)
Number 1: 10
  (Added - running total: 10.0)
Number 2: -5
  (Skipped - not positive)
Number 3: 20
  (Added - running total: 30.0)
Number 4: 0
  (Skipped - not positive)
Number 5: 15
  (Added - running total: 45.0)
...

Sum of positive numbers: 45.0
```

**Key Concepts:**
- Continue skips the addition for non-positive numbers
- Total only accumulates positive values
- Feedback shows which numbers were skipped
- Conditional summing with continue

---

### Question 23
**Problem:** Print numbers from 1 to 30. Skip numbers that are divisible by both 2 and 3 (divisible by 6).

**Solution Approach:**
- Loop 1 to 30
- Check if divisible by 6 (divisible by both 2 and 3)
- If yes, continue (skip)
- Otherwise print

**Complete Solution:**
```python
# Print numbers except those divisible by 6
print("Numbers from 1 to 30 (skipping multiples of 6):")

for number in range(1, 31):
    # Skip multiples of 6
    if number % 6 == 0:
        continue
    print(number, end=" ")

print()  # New line
```

**Alternative checking both:**
```python
print("Numbers from 1 to 30 (skipping multiples of both 2 and 3):")

for number in range(1, 31):
    # Skip if divisible by both 2 and 3
    if number % 2 == 0 and number % 3 == 0:
        continue
    print(number, end=" ")

print()
```

**Output:**
```
Numbers from 1 to 30 (skipping multiples of 6):
1 2 3 4 5 7 8 9 10 11 13 14 15 16 17 19 20 21 22 23 25 26 27 28 29 
```

**Key Concepts:**
- Divisible by both 2 and 3 means divisible by 6
- Continue used to skip specific values
- Keeps rest of loop code simple
- Multiples of 6: 6, 12, 18, 24, 30 are skipped

---

### Question 24
**Problem:** Create a grade processor: ask for 5 test scores. Skip any score above 100 or below 0 (use continue), and calculate the average of valid scores only.

**Solution Approach:**
- Loop 5 times
- Check if score is valid (0-100)
- If invalid, continue (skip)
- Track sum and count of valid scores
- Calculate average of valid scores

**Complete Solution:**
```python
# Initialize trackers
total = 0
valid_count = 0

print("Enter 5 test scores (0-100):")

# Get 5 scores
for i in range(5):
    score = float(input(f"Score {i + 1}: "))
    
    # Validate score
    if score < 0 or score > 100:
        print("  Invalid score (must be 0-100) - skipped")
        continue
    
    # Process valid score
    total = total + score
    valid_count = valid_count + 1
    print(f"  Valid score recorded")

# Calculate and display average
print(f"\n=== Results ===")
print(f"Valid scores: {valid_count}")
print(f"Invalid scores: {5 - valid_count}")

if valid_count > 0:
    average = total / valid_count
    print(f"Average of valid scores: {average:.2f}")
else:
    print("No valid scores entered")
```

**Sample Run:**
```
Enter 5 test scores (0-100):
Score 1: 85
  Valid score recorded
Score 2: 120
  Invalid score (must be 0-100) - skipped
Score 3: 90
  Valid score recorded
Score 4: -10
  Invalid score (must be 0-100) - skipped
Score 5: 78
  Valid score recorded

=== Results ===
Valid scores: 3
Invalid scores: 2
Average of valid scores: 84.33
```

**Key Concepts:**
- Continue skips invalid data
- Separate counters for total and valid count
- Only valid scores affect average
- Input validation with continue
- Average calculated from valid scores only

---

### Question 25
**Problem:** FizzBuzz variation: Print numbers 1-50. For multiples of 3, print "Fizz" and continue (skip the number). For multiples of 5, print "Buzz" and continue. For multiples of both, print "FizzBuzz" and continue. Otherwise, print the number.

**Solution Approach:**
- Check multiples of 15 (both 3 and 5) first
- Then check multiples of 3
- Then check multiples of 5
- Use continue after each to skip number printing

**Complete Solution:**
```python
# FizzBuzz with continue
print("FizzBuzz (1-50):")

for number in range(1, 51):
    # Check multiples of both (15)
    if number % 15 == 0:
        print("FizzBuzz", end=" ")
        continue
    
    # Check multiples of 3
    if number % 3 == 0:
        print("Fizz", end=" ")
        continue
    
    # Check multiples of 5
    if number % 5 == 0:
        print("Buzz", end=" ")
        continue
    
    # Print the number
    print(number, end=" ")

print()  # New line at end
```

**Output:**
```
FizzBuzz (1-50):
1 2 Fizz 4 Buzz Fizz 7 8 Fizz Buzz 11 Fizz 13 14 FizzBuzz 16 17 Fizz 19 Buzz Fizz 22 23 Fizz Buzz 26 Fizz 28 29 FizzBuzz 31 32 Fizz 34 Buzz Fizz 37 38 Fizz Buzz 41 Fizz 43 44 FizzBuzz 46 47 Fizz 49 Buzz 
```

**Key Concepts:**
- Continue after each print prevents number from printing
- Check multiples of 15 first (both 3 and 5)
- Order matters: most specific condition first
- Classic programming interview problem
- Continue makes logic cleaner than nested if-else

---

## Summary: Key Loop Patterns

### Range Patterns
```python
# Count up
range(10)           # 0-9
range(5, 16)        # 5-15
range(0, 21, 2)     # 0, 2, 4, ..., 20

# Count down
range(10, 0, -1)    # 10, 9, 8, ..., 1
range(20, 9, -1)    # 20, 19, 18, ..., 10
```

### Accumulator Patterns
```python
# Sum accumulator
total = 0
for i in range(n):
    total += value

# Product accumulator  
product = 1
for i in range(n):
    product *= value

# Counter accumulator
count = 0
for item in items:
    if condition:
        count += 1
```

### While Loop Patterns
```python
# Countdown
count = 10
while count > 0:
    print(count)
    count -= 1

# Input validation
while input_invalid:
    get_new_input()

# Sentinel value
while value != sentinel:
    process(value)
    value = get_next()

# Infinite with break
while True:
    if exit_condition:
        break
```

### Break and Continue
```python
# Break - exit immediately
for i in range(100):
    if found:
        break

# Continue - skip to next
for i in range(100):
    if skip_this:
        continue
    process(i)
```

### Common Combinations
```python
# Find first occurrence
for i in range(n):
    if condition:
        result = i
        break

# Skip unwanted values
for item in items:
    if unwanted:
        continue
    process(item)

# Input until valid
while True:
    value = get_input()
    if valid(value):
        break
    show_error()
```