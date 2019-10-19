### Zip
```
names = ['Jenny', 'Alexus', 'Sam', 'Grace']
dogs_names = ['Elphonse', 'Dr. Doggy DDS', 'Carter', 'Ralph']

names_and_dogs_names = zip(names, dogs_names)
list_of_names_and_dogs_names = list(names_and_dogs_names)
print(list_of_names_and_dogs_names)
```
Result:
```
[('Jenny', 'Elphonse'), ('Alexus', 'Dr. Doggy DDS'), ('Sam', 'Carter'), ('Grace', 'Ralph')]
```

### Append list
```
orders = ['daisies', 'periwinkle']
print(orders)

orders.append('tulips')

orders.append('roses')

print(orders)
```
```
last_semester_gradebook = [("politics", 80), ("latin", 96), ("dance", 97), ("architecture", 65)]

subjects = ['physics','calculus','poetry','history']
grades =[98,97,85,88]
subjects.append('computer science')
grades.append(100)
gradebook = list(zip(subjects,grades))
gradebook.append(('visual arts', 93)) #可以插入一对
print(gradebook)
full_gradebook = last_semester_gradebook + gradebook
```

### Growing a list
```
orders = ['daisy', 'buttercup', 'snapdragon', 'gardenia', 'lily']

# Create new orders here:
new_orders = orders + ['lilac' , 'iris']

broken_prices = [5, 3, 4, 5, 4] + [4]
```

### Range
```
>>> my_list = range(2, 9) #不包括9
>>> print(list(my_list))
[2, 3, 4, 5, 6, 7, 8]
```

### Slicing
```
suitcase = ['shirt', 'shirt', 'pants', 'pants', 'pajamas', 'books']

beginning = suitcase[0:4]
print(beginning)

middle = suitcase[2:4]

```
Result:
```
['shirt', 'shirt', 'pants', 'pants']
```

```
fruits = ['apple', 'banana', 'cherry', 'date']
print(fruits[:3])
```
```
['apple', 'banana', 'cherry']
```
```
print(fruits[2:])
```
```
['cherry' , 'date']
```
```
print(fruits[-3:])
```
```
print(fruits[-3:])
```

### Counting 
```
letters = ['m', 'i', 's', 's', 'i', 's', 's', 'i', 'p', 'p', 'i']
num_i = letters.count('i')
print(num_i)
```
```
4
```
```
votes = ['Jake', 'Jake', 'Laurie', 'Laurie', 'Laurie', 'Jake', 'Jake', 'Jake', 'Laurie', 'Cassie', 'Cassie', 'Jake', 'Jake', 'Cassie', 'Laurie', 'Cassie', 'Jake', 'Jake', 'Cassie', 'Laurie']

jake_votes = votes.count('Jake')

print(jake_votes)
```
```
9
```

### Sorting
```
names = ['Xander', 'Buffy', 'Angel', 'Willow', 'Giles']
names.sort()
print(names)
```
```
['Angel', 'Buffy', 'Giles', 'Willow', 'Xander']
```
```
sorted_names = names.sort() #不对，sorted_names不能被赋值
```
但是可以用：
```
games = ['Portal', 'Minecraft', 'Pacman', 'Tetris', 'The Sims', 'Pokemon']

games_sorted = sorted(games)
print(games, games_sorted)
```
```
['Portal', 'Minecraft', 'Pacman', 'Tetris', 'The Sims', 'Pokemon'] 
['Minecraft', 'Pacman', 'Pokemon', 'Portal', 'Tetris', 'The Sims']
```

### First character
```
my_string = "Whoa! A seesaw"
print(my_string[0])
print(my_string[2])
print(my_string[5])
```
```
"W"
"o"
" "
```

### List comprehension
```
original_list = [[1, 2], [3, 4],  [5, 6]]
new_list = [item1 + item2 for (item1, item2) in originalList]
```

Create a new list named first_only that contains the first element in each sub-list of nested_lists.
```
nested_lists = [[4, 8], [16, 15], [23, 42]]
first_only = [e1 for [e1, e2] in nested_lists]
```
```
a = [30, 42, 10]
b = [15, 16, 17]

greater_than = [i >= j for (i,j) in zip (a,b)]

print(greater_than)
```
```
[True, True, False]
```

### Lambda function
```
#Write your lambda function here
contains_a = lambda word: "a" in word

print contains_a("banana")
print contains_a("apple")
print contains_a("cherry")

```
```
add_or_subtract = lambda input_number: input_number - 1 if input_number >= 0 else input_number + 1
```
Add random
```
random.randint(a,b) will return an integer between a and b (inclusive).
```
