# 4.3. Section 3 – Returning a result from a function

---

## 4.3.4 `LAB` A leap year: writing your own functions

#### Scenario
Your task is to write and test a function which takes one argument (a year) and returns `True` if the year is a leap year, or `False` otherwise.

The seed of the function is already shown in the skeleton code in the editor.

Note: we've also prepared a short testing code, which you can use to test your function.

The code uses two lists ‒ one with the test data, and the other containing the expected results. The code will tell you if any of your results are invalid.

```python
def is_year_leap(year):
    #
    # Write your code here.
    #

test_data = [1900, 2000, 2016, 1987]
test_results = [False, True, True, False]
for i in range(len(test_data)):
    yr = test_data[i]
    print(yr,"->",end="")
    result = is_year_leap(yr)
    if result == test_results[i]:
        print("OK")
    else:
        print("Failed")
```

#### Sample Solution
```python
def is_year_leap(year):
    if year % 4 != 0:
        return False
    elif year % 100 != 0:
        return True
    elif year % 400 != 0:
        return False
    else:
        return True

test_data = [1900, 2000, 2016, 1987]
test_results = [False, True, True, False]
for i in range(len(test_data)):
    yr = test_data[i]
    print(yr,"-> ",end="")
    result = is_year_leap(yr)
    if result == test_results[i]:
        print("OK")
    else:
        print("Failed")
```

---

## 4.3.5 `LAB` How many days: writing and using your own functions

#### Scenario
Your task is to write and test a function which takes two arguments (a year and a month) and returns the number of days for the given year-month pair (while only February is sensitive to the `year` value, your function should be universal).

The initial part of the function is ready. Now, convince the function to return `None` if its arguments don't make sense.

Of course, you can (and should) use the previously written and tested function (LAB 4.3.1.6). It may be very helpful. We encourage you to use a list filled with the months' lengths. You can create it inside the function ‒ this trick will significantly shorten the code.

We've prepared a testing code. Expand it to include more test cases.

```python
def is_year_leap(year):
    #
    # Your code from the previous LAB.
    #

def days_in_month(year, month):
    #
    # Write your new code here.
    #

test_years = [1900, 2000, 2016, 1987]
test_months = [2, 2, 1, 11]
test_results = [28, 29, 31, 30]
for i in range(len(test_years)):
    yr = test_years[i]
    mo = test_months[i]
    print(yr, mo, "->", end="")
    result = days_in_month(yr, mo)
    if result == test_results[i]:
        print("OK")
    else:
        print("Failed")
```

#### Sample Solution
```python
def is_year_leap(year):
    if year % 4 != 0:
        return False
    elif year % 100 != 0:
        return True
    elif year % 400 != 0:
        return False
    else:
        return True

def days_in_month(year,month):
    if year < 1582 or month < 1 or month > 12:
        return None
    days = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    res  = days[month - 1]
    if month == 2 and is_year_leap(year):
        res = 29
    return res

test_years = [1900, 2000, 2016, 1987]
test_months = [ 2, 2, 1, 11]
test_results = [28, 29, 31, 30]
for i in range(len(test_years)):
    yr = test_years[i]
    mo = test_months[i]
    print(yr,mo,"-> ",end="")
    result = days_in_month(yr, mo)
    if result == test_results[i]:
        print("OK")
    else:
        print("Failed")
```

---

## 4.3.6   `LAB`   Day of the year: writing and using your own functions

#### Scenario
Your task is to write and test a function which takes three arguments (a year, a month, and a day of the month) and returns the corresponding day of the year, or returns `None` if any of the arguments is invalid.

Use the previously written and tested functions. Add your own test cases to the code.

```python
def is_year_leap(year):
    #
    # Your code from the previous LAB.
    #

def days_in_month(year, month):
    #
    # Your code from the previous lab.
    #

def day_of_year(year, month, day):
    #
    # Write your new code here.
    #

print(day_of_year(2000, 12, 31))
```

#### Sample Solution
```python
def is_year_leap(year):
    if year % 4 != 0:
        return False
    elif year % 100 != 0:
        return True
    elif year % 400 != 0:
        return False
    else:
        return True

def days_in_month(year, month):
    if year < 1582 or month < 1 or month > 12:
        return None
    days = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    res  = days[month - 1]
    if month == 2 and is_year_leap(year):
        res = 29
    return res

def day_of_year(year, month, day):
    days = 0
    for m in range(1, month):
        md = days_in_month(year, m)
        if md == None:
            return None
        days += md
    md = days_in_month(year, month)
    if day >= 1 and day <= md:
        return days + day
    else:
        return None

print(day_of_year(2000, 12, 31))
```

---

## 4.3.7   `LAB`   Prime numbers ‒ how to find them

#### Scenario
*A natural number is **prime** if it is greater than 1 and has no divisors other than 1 and itself.*

Complicated? Not at all. For example, 8 isn't a prime number, as you can divide it by 2 and 4 (we can't use divisors equal to 1 and 8, as the definition prohibits this).

On the other hand, 7 is a prime number, as we can't find any legal divisors for it.

Your task is to write a function checking whether a number is prime or not.

The function:

* is called `is_prime`;
* takes one argument (the value to check)
* returns `True` if the argument is a prime number, and `False` otherwise.

> [!TIP]
> Try to divide the argument by all subsequent values (starting from 2) and check the remainder ‒ if it's zero, your number cannot be a prime; think carefully about when you should stop the process.

If you need to know the square root of any value, you can utilize the `**` operator. Remember: the square root of x is the same as x0.5

Complete the code in the editor.

Run your code and check whether your output is the same as ours.

```python
def is_prime(num):
    #
    # Write your code here.
    #

for i in range(1, 20):
    if is_prime(i + 1):
        print(i + 1, end=" ")
print()
```

#### Expected output
```
2 3 5 7 11 13 17 19
```

#### Sample Solution
```python
def is_prime(num):
    for i in range(2, int(1 + num ** 0.5)):
        if num % i == 0:
            return False
    return True

for i in range(1, 20):
    if is_prime(i + 1):
        print(i + 1, end=" ")
print()
```

---

## 4.3.8   `LAB`   Converting fuel consumption

#### Scenario
A car's fuel consumption may be expressed in many different ways. For example, in Europe, it is shown as the amount of fuel consumed per 100 kilometers.

In the USA, it is shown as the number of miles traveled by a car using one gallon of fuel.

Your task is to write a pair of functions converting l/100km into mpg, and vice versa.

The functions:

* are named `liters_100km_to_miles_gallon` and `miles_gallon_to_liters_100km` respectively;
* take one argument (the value corresponding to their names)

Complete the code in the editor and run it to check whether your output is the same as ours.

Here is some information to help you:

* 1 American mile = 1609.344 metres;
* 1 American gallon = 3.785411784 litres.

```python
def liters_100km_to_miles_gallon(liters):
    #
    # Write your code here.
    #

def miles_gallon_to_liters_100km(miles):
    #
    # Write your code here.
    #

print(liters_100km_to_miles_gallon(3.9))
print(liters_100km_to_miles_gallon(7.5))
print(liters_100km_to_miles_gallon(10.))
print(miles_gallon_to_liters_100km(60.3))
print(miles_gallon_to_liters_100km(31.4))
print(miles_gallon_to_liters_100km(23.5))
```

#### Expected output:
```
60.31143162393162
31.36194444444444
23.52145833333333
3.9007393587617467
7.490910297239916
10.009131205673757
```

#### Sample Solution
```python
# 1 American mile = 1609.344 metres
# 1 American gallon = 3.785411784 litres

def liters_100km_to_miles_gallon(litres):
    gallons = litres / 3.785411784
    miles = 100 * 1000 / 1609.344
    return miles / gallons

def miles_gallon_to_liters_100km(miles):
    km100 = miles * 1609.344 / 1000 / 100
    litres = 3.785411784
    return litres / km100

print(liters_100km_to_miles_gallon(3.9))
print(liters_100km_to_miles_gallon(7.5))
print(liters_100km_to_miles_gallon(10.))
print(miles_gallon_to_liters_100km(60.3))
print(miles_gallon_to_liters_100km(31.4))
print(miles_gallon_to_liters_100km(23.5))
```