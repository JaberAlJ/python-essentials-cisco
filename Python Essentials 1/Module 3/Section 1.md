# 3.1. Section 1 – Making decisions in Python

---

## 3.1.6 `LAB` Variables ‒ Questions and answers

#### Scenario
Using one of the comparison operators in Python, write a simple two-line program that takes the parameter `n` as input, which is an integer, and prints `False` if `n` is less than `100`, and `True` if `n` is greater than or equal to `100`.

Don't create any `if` blocks (we're going to talk about them very soon). Test your code using the data we've provided for you.

#### Test Data
| Sample input | Expected output |
| ------------ | --------------- |
| 55 | False |
| 99 | False |
| 100 | True |
| 101 | True |
| -5 | False |
| +123 | True |

#### Sample Solution
```python
n = int(input("Enter a number: "))
print(n >= 100)
```

---

## Example 3

It's time to complicate the code – let's find the largest of three numbers. Will it enlarge the code? A bit.

We assume that the first value is the largest. Then we verify this hypothesis with the two remaining values.

Look at the code below:
```python
# Read three numbers
number1 = int(input("Enter the first number: "))
number2 = int(input("Enter the second number: "))
number3 = int(input("Enter the third number: "))
 
# We temporarily assume that the first number
# is the largest one.
# We will verify this soon.
largest_number = number1
 
# We check if the second number is larger than the current largest_number
# and update the largest_number if needed.
if number2 > largest_number:
    largest_number = number2
 
# We check if the third number is larger than the current largest_number
# and update the largest_number if needed.
if number3 > largest_number:
    largest_number = number3
 
# Print the result
print("The largest number is:", largest_number)
```

This method is significantly simpler than trying to find the largest number all at once, by comparing all possible pairs of numbers (i.e., first with second, second with third, third with first). Try to rebuild the code for yourself.

#### Sample Solution
```python
# Read three numbers from the user
number1 = int(input("Enter the first number: "))
number2 = int(input("Enter the second number: "))
number3 = int(input("Enter the third number: "))

# Assume the first number is the largest
largest_number = number1

# Check the second number
if number2 > largest_number:
    largest_number = number2

# Check the third number
if number3 > largest_number:
    largest_number = number3

# Display the result
print("The largest number is:", largest_number)
```

---

## 3.1.10 `LAB` Comparison operators and conditional execution


#### Scenario
`Spathiphyllum`, more commonly known as a peace lily or white sail plant, is one of the most popular indoor houseplants that filters out harmful toxins from the air. Some of the toxins that it neutralizes include benzene, formaldehyde, and ammonia.

Imagine that your computer program loves these plants. Whenever it receives an input in the form of the word `Spathiphyllum`, it involuntarily shouts to the console the following string: `"Spathiphyllum is the best plant ever!"`

Write a program that utilizes the concept of conditional execution, takes a string as input, and:

* prints the sentence `"Yes - Spathiphyllum is the best plant ever!"` to the screen if the inputted string is `"Spathiphyllum"` (upper-case)
* prints `"No, I want a big Spathiphyllum!"` if the inputted string is `"spathiphyllum"` (lower-case)
* prints `"Spathiphyllum! Not [input]!"` otherwise. Note: `[input]` is the string taken as input.

Test your code using the data we've provided for you. And get yourself a Spathiphyllum, too!

#### Test Data
| Sample input | Expected output |
| ------------ | --------------- |
| spathiphyllum | No, I want a big Spathiphyllum! |
| pelargonium | Spathiphyllum! Not pelargonium! |
| Spathiphyllum | Yes - Spathiphyllum is the best plant ever! |

#### Sample Solution
```python
plant = input("Enter the plant name: ")

if plant == "Spathiphyllum":
    print("Yes - Spathiphyllum is the best plant ever!")
elif plant == "spathiphyllum":
    print("No, I want a big Spathiphyllum!")
else:
    print("Spathiphyllum! Not", plant + "!")
```

---

## 3.1.11 `LAB` Essentials of the if-else statement


#### Scenario
Once upon a time there was a land – a land of milk and honey, inhabited by happy and prosperous people. The people paid taxes, of course – their happiness had limits. The most important tax, called the Personal Income Tax (PIT for short) had to be paid once a year, and was evaluated using the following rule:

* if the citizen's income was not higher than 85,528 thalers, the tax was equal to 18% of the income minus 556 thalers and 2 cents (this was what they called tax relief)
* if the income was higher than this amount, the tax was equal to 14,839 thalers and 2 cents, plus 32% of the surplus over 85,528 thalers.

Your task is to write a tax calculator.

* It should accept one floating-point value: the income.
* Next, it should print the calculated tax, rounded to full thalers. There's a function named `round()` which will do the rounding for you – you'll find it in the skeleton code in the editor.

Note: this happy country never returned any money to its citizens. If the calculated tax was less than zero, it would only mean no tax at all (the tax was equal to zero). Take this into consideration during your calculations.

Look at the code in the editor – it only reads one input value and outputs a result, so you need to complete it with some smart calculations.

```python
income = float(input("Enter the annual income: "))

if income < 85528:
	tax = income * 0.18 - 556.02
# Write the rest of your code here.

tax = round(tax, 0)
print("The tax is:", tax, "thalers")
```

Test your code using the data we've provided.

#### Test Data
| Sample input | Expected output |
| ------------ | --------------- |
| 10000 | The tax is: 1244.0 thalers |
| 100000 | The tax is: 19470.0 thalers |
| 1000 | The tax is: 0.0 thalers |
| -100 | The tax is: 0.0 thalers |

#### Sample Solution
```python
income = float(input("Enter the annual income: "))

if income < 85528:
	tax = income * 0.18 - 556.02
else:
	tax = (income - 85528) * 0.32 + 14839.02

if tax < 0.0:
	tax = 0.0

tax = round(tax, 0)
print("The tax is:", tax, "thalers")
```

---

## 3.1.12 `LAB` Essentials of the if-elif-else statement

#### Scenario
As you surely know, due to some astronomical reasons, years may be leap or common. The former are 366 days long, while the latter are 365 days long.

Since the introduction of the Gregorian calendar (in 1582), the following rule is used to determine the kind of year:

* if the year number isn't divisible by four, it's a common year;
* otherwise, if the year number isn't divisible by 100, it's a leap year;
* otherwise, if the year number isn't divisible by 400, it's a common year;
* otherwise, it's a leap year.

Look at the code in the editor – it only reads a year number, and needs to be completed with the instructions implementing the test we've just described.


The code should output one of two possible messages, which are `Leap year` or `Common year`, depending on the value entered.

It would be good to verify if the entered year falls into the Gregorian era, and output a warning otherwise: `Not within the Gregorian calendar period`. Tip: use the `!=` and `%` operators.

```python
year = int(input("Enter a year: "))

if year < 1582:
	print("Not within the Gregorian calendar period")
else:
    #  Write the if-elif-elif-else block here.
```

Test your code using the data we've provided.

#### Test Data
| Sample input | Expected output |
| ------------ | --------------- |
| 2000 | Leap year |
| 2015 | Common year |
| 1999 | Common year |
| 1996 | Leap year |
| 1580 | Not within the Gregorian calendar period |

#### Sample Solution
```python
year = int(input("Enter a year: "))

if year < 1582:
	print("Not within the Gregorian calendar period")
else:
	if year % 4 != 0:
		print("Common year")
	elif year % 100 != 0:
		print("Leap year")
	elif year % 400 != 0:
		print("Common year")
	else:
		print("Leap year")
```