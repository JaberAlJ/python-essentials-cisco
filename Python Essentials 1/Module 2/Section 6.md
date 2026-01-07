# 2.6. Section 6 – Interaction with the user

---

## 2.6.9 `LAB` Simple input and output

#### Scenario
Your task is to complete the code in order to evaluate the results of four basic arithmetic operations.

The results have to be printed to the console.

You may not be able to protect the code from a user who wants to divide by zero. That's okay, don't worry about it for now.

Test your code ‒ does it produce the results you expect?

We won't show you any test data ‒ that would be too simple.

```python
# input a float value for variable a here
# input a float value for variable b here

# output the result of addition here
# output the result of subtraction here
# output the result of multiplication here
# output the result of division here

print("\nThat's all, folks!")
```

#### Sample Solution
```python
a = float(input("Enter first value: "))
b = float(input("Enter second value: "))

print("Addition:", a + b)
print("Subtraction:", a - b)
print("Multiplication:", a * b)
print("Division:", a / b)

print("\nThat's all, folks!")
```

---

## 2.6.10 `LAB` Operators and expressions

#### Scenario

Your task is to complete the code in order to evaluate the following expression:

<img src="./Math expression.png" alt="Math expression" />
The result should be assigned to y. Be careful ‒ watch the operators and keep their priorities in mind. Don't hesitate to use as many parentheses as you need.

You can use additional variables to shorten the expression (but it's not necessary). Test your code carefully.

```python
x = float(input("Enter value for x: "))

# Write your code here.

print("y =", y)
```

#### Test Data
| Sample input | Expected output |
| ------------ | --------------- |
| 1 | y = 0.6000000000000001 |
| 10 | y = 0.09901951266867294 |
| 100 | y = 0.009999000199950014 |
| -5 | y = -0.19258202567760344 |

#### Sample Solution
```python
x = float(input("Enter value for x: "))
y = 1./(x + 1./(x + 1./(x + 1./x)))
print("y =", y)
```

---

## 2.6.11 `LAB` Operators and expressions – 2


#### Scenario
Your task is to prepare a simple code able to evaluate the **end time** of a period of time, given as a number of minutes (it could be arbitrarily large). The start time is given as a pair of hours (0..23) and minutes (0..59). The result has to be printed to the console.

For example, if an event starts at **12:17** and lasts **59 minutes**, it will end at **13:16**.

Don't worry about any imperfections in your code ‒ it's okay if it accepts an invalid time ‒ the most important thing is that the code produces valid results for valid input data.

Test your code carefully. Hint: using the `%` operator may be the key to success.

```python
hour = int(input("Starting time (hours): "))
mins = int(input("Starting time (minutes): "))
dura = int(input("Event duration (minutes): "))

# Write your code here.
```

#### Sample I/O
```
Sample input:
12
17
59
----------------
Expected output:
13:16
```
```
Sample input:
23
58
642
----------------
Expected output:
10:40
```
```
Sample input:
0
1
2939
----------------
Expected output:
1:0
```

#### Sample Solution
```python
hour = int(input("Starting time (hours): "))
mins = int(input("Starting time (minutes): "))
dura = int(input("Event duration (minutes): "))
mins = mins + dura # find a total of all minutes
hour = hour + mins // 60 # find a number of hours hidden in minutes and update the hour
mins = mins % 60 # correct minutes to fall in the (0..59) range
hour = hour % 24 # correct hours to fall in the (0..23) range
print(hour, ":", mins, sep='')
```