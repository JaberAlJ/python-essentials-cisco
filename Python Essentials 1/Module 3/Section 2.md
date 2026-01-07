# 3.2. Section 2 – Loops in Python

---

## 3.2.4 `LAB` Guess the secret number

#### Scenario
A junior magician has picked a secret number. He has hidden it in a variable named `secret_number`. He wants everyone who runs his program to play the Guess the secret number game, and guess what number he has picked for them. Those who don't guess the number will be stuck in an endless loop forever! Unfortunately, he does not know how to complete the code.

Your task is to help the magician complete the code in the editor in such a way so that the code:

* will ask the user to enter an integer number;
* will use a `while` loop;
* will check whether the number entered by the user is the same as the number picked by the magician. If the number chosen by the user is different than the magician's secret number, the user should see the message `"Ha ha! You're stuck in my loop!"` and be prompted to enter a number again. If the number entered by the user matches the number picked by the magician, the number should be printed to the screen, and the magician should say the following words: `"Well done, muggle! You are free now."`

The magician is counting on you! Don't disappoint him.

> [!IMPORTANT]
> By the way, look at the `print()` function. The way we've used it here is called multi-line printing. You can use triple quotes to print strings on multiple lines in order to make text easier to read, or create a special text-based design. Experiment with it.

```python
secret_number = 777

print(
"""
+================================+
| Welcome to my game, muggle!    |
| Enter an integer number        |
| and guess what number I've     |
| picked for you.                |
| So, what is the secret number? |
+================================+
""")
```

#### Sample Solution
```python
secret_number = 777

print(
"""
+================================+
| Welcome to my game, muggle!    |
| Enter an integer number        |
| and guess what number I've     |
| picked for you.                |
| So, what is the secret number? |
+================================+
""")

guess = int(input("Enter your guess: "))

while guess != secret_number:
    print("Ha ha! You're stuck in my loop!")
    guess = int(input("Enter your guess: "))

print(guess)
print("Well done, muggle! You are free now.")
```

---

## 3.2.7 `LAB` Essentials of the for loop – counting mississippily

#### Scenario
Do you know what Mississippi is? Well, it's the name of one of the states and rivers in the United States. The Mississippi River is about 2,340 miles long, which makes it the second longest river in the United States (the longest being the Missouri River). It's so long that a single drop of water needs 90 days to travel its entire length!

The word Mississippi is also used for a slightly different purpose: to count mississippily.

If you're not familiar with the phrase, we're here to explain to you what it means: it's used to count seconds.

The idea behind it is that adding the word Mississippi to a number when counting seconds aloud makes them sound closer to clock-time, and therefore "one Mississippi, two Mississippi, three Mississippi" will take approximately an actual three seconds of time! It's often used by children playing hide-and-seek to make sure the seeker does an honest count.

Your task is very simple here: write a program that uses a `for` loop to "count mississippily" to five. Having counted to five, the program should print to the screen the final message `"Ready or not, here I come!"`

Use the skeleton we've provided in the editor.

> [!IMPORTANT]
> Note that the code in the editor contains two elements which may not be fully clear to you at this moment: the `import time` statement, and the `sleep()` method. We're going to talk about them soon.
>
> For the time being, we'd just like you to know that we've imported the `time` module and used the `sleep()` method to suspend the execution of each subsequent `print()` function inside the `for` loop for one second, so that the message outputted to the console resembles an actual counting. Don't worry - you'll soon learn more about modules and methods.

```python
import time

# Write a for loop that counts to five.
    # Body of the loop - print the loop iteration number and the word "Mississippi".
    # Body of the loop - use: time.sleep(1)

# Write a print function with the final message.
```

#### Expected output
```
1 Mississippi
2 Mississippi
3 Mississippi
4 Mississippi
5 Mississippi
Ready or not, here I come!
```

#### Sample Solution
```python
import time

# Write a for loop that counts to five.
for i in range(1, 6):
    # Body of the loop - print the loop iteration number and the word "Mississippi".
    print(f"{i} Mississippi")
    # Body of the loop - use: time.sleep(1)
    time.sleep(1)

# Write a print function with the final message.
print("Ready or not, here I come!")
```

---

## 3.2.9 `LAB` The break statement – Stuck in a loop

#### Scenario
The `break` statement is used to exit/terminate a loop.

Design a program that uses a `while` loop and continuously asks the user to enter a word unless the user enters `"chupacabra"` as the secret exit word, in which case the message `"You've successfully left the loop."` should be printed to the screen, and the loop should terminate.

Don't print any of the words entered by the user. Use the concept of conditional execution and the `break` statement.

#### Sample Solution
```python
while True:
    word = input("Enter a word: ")
    if word == "chupacabra":
        print("You've successfully left the loop.")
        break
```

---

## 3.2.10 `LAB` The continue statement – the Ugly Vowel Eater

#### Scenario
The `continue` statement is used to skip the current block and move ahead to the next iteration, without executing the statements inside the loop.

It can be used with both the while and for loops.

Your task here is very special: you must design a vowel eater! Write a program that uses:

* a `for` loop;
* the concept of conditional execution (if-elif-else)
* the `continue` statement.

Your program must:

* ask the user to enter a word;
* use `user_word = user_word.upper()` to convert the word entered by the user to upper case; we'll talk about **string methods** and the `upper()` method very soon – don't worry;
* use conditional execution and the `continue` statement to "eat" the following vowels A, E, I, O, U from the inputted word;
* print the uneaten letters to the screen, each one of them on a separate line.

```python
# Prompt the user to enter a word
# and assign it to the user_word variable.

for letter in user_word:
    # Complete the body of the for loop.
```

Test your program with the data we've provided for you.

#### Sample I/O
```
Sample input:
Gregory
-------------
Expected output:
G
R
G
R
Y
```
```
Sample input:
abstemious
-------------
Expected output:
B
S
T
M
S
```
```
Sample input:
IOUEA
-------------
Expected output:
 
```

#### Sample Solution
```python
# Prompt the user to enter a word
# and assign it to the user_word variable.
user_word = input("Enter a word: ")
user_word = user_word.upper()

for letter in user_word:
    # Complete the body of the for loop.
    if letter == "A":
        continue
    elif letter == "E":
        continue
    elif letter == "I":
        continue
    elif letter == "O":
        continue
    elif letter == "U":
        continue
    else:
        print(letter)
```
```python
# Prompt the user to enter a word
# and assign it to the user_word variable.
user_word = input("Enter a word: ")
user_word = user_word.upper()

for letter in user_word:
    # Complete the body of the for loop.
    if letter in "AEIOU":
        continue
    else:
        print(letter)
```

---

## 3.2.11 `LAB` The continue statement – the Pretty Vowel Eater

#### Scenario
Your task here is even more special than before: you must redesign the (ugly) vowel eater from the previous lab and create a better, upgraded (pretty) vowel eater! Write a program that uses:

* a `for` loop;
* the concept of conditional execution (if-elif-else)
* the `continue` statement.

Your program must:

* ask the user to enter a word;
* use `user_word = user_word.upper()` to convert the word entered by the user to upper case; we'll talk about **string methods** and the `upper()` method very soon - don't worry;
* use conditional execution and the `continue` statement to "eat" the following vowels A, E, I, O, U from the inputted word;
* assign the uneaten letters to the `word_without_vowels` variable and print the variable to the screen.

Look at the code in the editor. We've created `word_without_vowels` and assigned an empty string to it. Use concatenation operation to ask Python to combine selected letters into a longer string during subsequent loop turns, and assign it to the `word_without_vowels` variable.

```python
word_without_vowels = ""

# Prompt the user to enter a word
# and assign it to the user_word variable.


for letter in user_word:
    # Complete the body of the loop.

# Print the word assigned to word_without_vowels.
```

Test your program with the data we've provided for you.

#### Test Data
| Sample input | Expected output |
| ------------ | --------------- |
| Gregory | GRGRY |
| abstemious | BSTMS |
| IOUEA |   |

#### Sample Solution
```python
word_without_vowels = ""

# Prompt the user to enter a word
# and assign it to the user_word variable.
user_word = input("Enter a word: ")
user_word = user_word.upper()

for letter in user_word:
    # Complete the body of the loop.
    if letter in "AEIOU":
        continue
    else:
        word_without_vowels += letter

# Print the word assigned to word_without_vowels.
print(word_without_vowels)
```

---

## 3.2.14 `LAB` Essentials of the while loop

#### Scenario
Listen to this story: a boy and his father, a computer programmer, are playing with wooden blocks. They are building a pyramid.

Their pyramid is a bit weird, as it is actually a pyramid-shaped wall – it's flat. The pyramid is stacked according to one simple principle: each lower layer contains one block more than the layer above.


The figure illustrates the rule used by the builders:

<img src="./rule used by the builders.png" alt="rule used by the builders" />

Your task is to write a program which reads the number of blocks the builders have, and outputs the height of the pyramid that can be built using these blocks.

> [!NOTE]
> The height is measured by the number of **fully completed layers** – if the builders don't have a sufficient number of blocks and cannot complete the next layer, they finish their work immediately.

```python
blocks = int(input("Enter the number of blocks: "))

#
# Write your code here.
#	

print("The height of the pyramid:", height)
```

Test your code using the data we've provided.

#### Test Data
| Sample input | Expected output |
| ------------ | --------------- |
| 6 | The height of the pyramid: 3 |
| 20 | The height of the pyramid: 5 |
| 1000 | The height of the pyramid: 44 |
| 2 | The height of the pyramid: 1 |

#### Sample Solution
```python
blocks = int(input("Enter the number of blocks: "))

height = 0
needed = 1

while blocks >= needed:
    blocks -= needed
    height += 1
    needed += 1

print("The height of the pyramid:", height)
```

---

## 3.2.15 `LAB` Collatz's hypothesis

#### Scenario
In 1937, a German mathematician named Lothar Collatz formulated an intriguing hypothesis (it still remains unproven) which can be described in the following way:

1. take any non-negative and non-zero integer number and name it `c0`;
2. if it's even, evaluate a new `c0` as `c0 ÷ 2`;
3. otherwise, if it's odd, evaluate a new `c0` as `3 × c0 + 1`;
4. if `c0 ≠ 1`, go back to point 2.

The hypothesis says that regardless of the initial value of `c0`, it will always go to 1.

Of course, it's an extremely complex task to use a computer in order to prove the hypothesis for any natural number (it may even require artificial intelligence), but you can use Python to check some individual numbers. Maybe you'll even find the one which would disprove the hypothesis.

Write a program which reads one natural number and executes the above steps as long as `c0` remains different from 1. We also want you to count the steps needed to achieve the goal. Your code should output all the intermediate values of `c0`, too.

> [!TIP]
> The most important part of the problem is how to transform Collatz's idea into a `while` loop – this is the key to success.

Test your code using the data we've provided.

#### Sample I/O
```
Sample input:
15
-------------
Expected output:
46
46
70
35
106
53
160
80
40
20
10
5
16
8
4
2
1
steps = 17
```
```
Sample input:
16
-------------
Expected output:
8
4
2
1
steps = 4
```
```
Sample input:
1023
-------------
Expected output:
3070
1535
4606
2303
6910
3455
10366
5183
15550
7775
23326
11663
34990
17495
52486
26243
78730
39365
118096
59048
29524
14762
7381
22144
11072
5536
2768
1384
692
346
173
173
260
130
65
196
98
49
148
74
37
37
56
28
14
7
22
11
34
17
52
26
13
40
20
10
5
16
8
4
2
steps = 62
```

#### Sample Solution
```python
c0 = int(input())

steps = 0

while c0 != 1:
    if c0 % 2 == 0:
        c0 //= 2
    else:
        c0 = 3 * c0 + 1

    print(c0)
    steps += 1

print("steps =", steps)
```