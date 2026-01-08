# 3.4. Section 4 – Lists

---

## 3.4.6 `LAB` The basics of lists

#### Scenario
There once was a hat. The hat contained no rabbit, but a list of five numbers: `1`, `2`, `3`, `4`, and `5`.

Your task is to:

* write a line of code that prompts the user to replace the middle number in the list with an integer number entered by the user (Step 1)
* write a line of code that removes the last element from the list (Step 2)
* write a line of code that prints the length of the existing list (Step 3).

```python
hat_list = [1, 2, 3, 4, 5]  # This is an existing list of numbers hidden in the hat.

# Step 1: write a line of code that prompts the user
# to replace the middle number with an integer number entered by the user.

# Step 2: write a line of code that removes the last element from the list.

# Step 3: write a line of code that prints the length of the existing list.

print(hat_list)
```

Ready for this challenge?

#### Sample Solution
```python
hat_list = [1, 2, 3, 4, 5]  # This is an existing list of numbers hidden in the hat.

# Step 1: replace the middle number with an integer entered by the user
hat_list[2] = int(input("Enter an integer to replace the middle number: "))

# Step 2: remove the last element from the list
hat_list.pop()

# Step 3: print the length of the existing list
print(len(hat_list))

print(hat_list)
```

---

## 3.4.11 `LAB` The basics of lists ‒ the Beatles

#### Scenario
The Beatles were one of the most popular music groups of the 1960s, and the best-selling band in history. Some people consider them to be the most influential act of the rock era. Indeed, they were included in Time magazine's compilation of the 20th Century's 100 most influential people.

The band underwent many line-up changes, culminating in 1962 with the line-up of John Lennon, Paul McCartney, George Harrison, and Richard Starkey (better known as Ringo Starr).


Write a program that reflects these changes and lets you practice with the concept of lists. Your task is to:

* step 1: create an empty list named `beatles`;
* step 2: use the `append()` method to add the following members of the band to the list: `John Lennon`, `Paul McCartney`, and `George Harrison`;
* step 3: use the `for` loop and the `append()` method to prompt the user to add the following members of the band to the list: `Stu Sutcliffe`, and `Pete Best`;
* step 4: use the `del` instruction to remove `Stu Sutcliffe` and `Pete Best` from the list;
* step 5: use the `insert()` method to add `Ringo Starr` to the beginning of the list.

By the way, are you a Beatles fan? (The Beatles is one of Greg's favorite bands. But wait...who's Greg...?)

```python
# step 1
print("Step 1:", beatles)

# step 2
print("Step 2:", beatles)

# step 3
print("Step 3:", beatles)

# step 4
print("Step 4:", beatles)

# step 5
print("Step 5:", beatles)


# testing list length
print("The Fab", len(beatles))
```

#### Sample Solution
```python
# step 1
beatles = []
print("Step 1:", beatles)

# step 2
beatles.append("John Lennon")
beatles.append("Paul McCartney")
beatles.append("George Harrison")
print("Step 2:", beatles)

# step 3
for member in ["Stu Sutcliffe", "Pete Best"]:
    beatles.append(input(f"Add band member ({member}): "))
print("Step 3:", beatles)

# step 4
del beatles[-1]
del beatles[-1]
print("Step 4:", beatles)

# step 5
beatles.insert(0, "Ringo Starr")
print("Step 5:", beatles)

# testing list length
print("The Fab", len(beatles))
```