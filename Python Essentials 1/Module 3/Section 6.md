# 3.6. Section 6 – Operations on lists

---

## 3.6.6 `LAB` Operating with lists ‒ basics

#### Scenario
Imagine a list ‒ not very long, not very complicated, just a simple list containing some integer numbers. Some of these numbers may be repeated, and this is the clue. We don't want any repetitions. We want them to be removed.

Your task is to write a program which removes all the number repetitions from the list. The goal is to have a list in which all the numbers appear not more than once.

> [!NOTE]
> Assume that the source list is hard-coded inside the code ‒ you don't have to enter it from the keyboard. Of course, you can improve the code and add a part that can carry out a conversation with the user and obtain all the data from her/him.

> [!TIP]
> We encourage you to create a new list as a temporary work area ‒ you don't need to update the list in situ.

We've provided no test data, as that would be too easy. You can use our skeleton instead.

```python
my_list = [1, 2, 4, 4, 1, 4, 2, 6, 2, 9]
#
# Write your code here.
#
print("The list with unique elements only:")
print(my_list)
```

#### Sample Solution
```python
my_list = [1, 2, 4, 4, 1, 4, 2, 6, 2, 9]

unique_list = []

for number in my_list:
    if number not in unique_list:
        unique_list.append(number)

my_list = unique_list

print("The list with unique elements only:")
print(my_list)
```

---

> [!WARNING]
> If you have a list `list_1`, then the following assignment: `list_2 = list_1` does not make a copy of the `list_1` list, but makes the variables `list_1` and `list_2` **point to one and the same list in memory**. 

**For example:**
```python
vehicles_one = ['car', 'bicycle', 'motor']
print(vehicles_one) # outputs: ['car', 'bicycle', 'motor']

vehicles_two = vehicles_one
del vehicles_one[0] # deletes 'car'
print(vehicles_two) # outputs: ['bicycle', 'motor']
```