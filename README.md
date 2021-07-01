# Python-3-Bootcamp Notes

Python learning repo with code exercises and notes based on https://www.udemy.com/course/complete-python-bootcamp/
and https://github.com/Pierian-Data/Complete-Python-3-Bootcamp

Practical tasks:
Basic - http://codingbat.com/python  
Mathematical (and Harder) Practice - https://projecteuler.net/archives  
List of Practice Problems - http://www.codeabbey.com/index/task_list  
A SubReddit Devoted to Daily Practice Problems - https://www.reddit.com/r/dailyprogrammer  
A very tricky website with very few hints and touch problems (Not for beginners but still interesting) - http://www.pythonchallenge.com/  


---

## Environment:
Anaconda - https://www.anaconda.com/products/individual#windows  (Python and Jupiter Notebook editor are inside for local work, to run with bigger load in cloud - Google Collab Online Notebooks or Repl.it)

VSC - Visual Studio Code - https://code.visualstudio.com/download 

### Python code examples
https://linuxhint.com/python_scripts_beginners_guide/

---

### Python is Dynamic Typing  
We can reassign variables to different data types
```python
new_variable = ["A",3,3.141592,{"name":"Andrii","lastname":"Stepura"},{"a","b"},True]
type(new_variable), type(new_variable[0]), type(new_variable[1]), type(new_variable[2]), type(new_variable[3]), type(new_variable[4]), type(new_variable[5])
# resulted as:
# (list, str, int, float, dict, set, bool)
```

---

### Python Data Types:
```python
int  
float  
str  
list [789, "word", 3.1415] # ordered sequence of objects  
dict {"name":"Andrii","lastname":"Stepura"} # unordered key:value pairs  
tup (10,"word",3.1415) # ordered immutable sequence of objects  
set {"a","b"} # unordered collection of UNIQUE objects  
bool # True / False  
```

---

### Basic Arithmetic Notes:
```python
2 + 10 * 10 + 3 # Order of Operations followed in Python resulted in 105  
14/4  # Division - 3.5  
14//4 # Floor Division - 3  
2**3 # Powers - 8  
4**0.5 # Can also do roots this way - 2  
4**0.5 != 2 # False because 2 == 2.0
```

---

### Syntax:
PEP 8 -- Style Guide for Python Code - https://www.python.org/dev/peps/pep-0008/

Variables in lovercase and avoid "list", "str", etc. reserved words.

---

### Notes:
*Why doesn't 0.1+0.2-0.3 equal 0.0* - https://docs.python.org/2/tutorial/floatingpoint.html


---

# Strings manipulations:
```python
# string[start:stop:step]
word = "Hello World"
print(word[6:11]) # World
```

```python
# string multiplication
"z" * 3 # zzz

# string concatination
x = "Hello World" 
x = x + "!!!"

# Methods
x.upper() # HELLO WORLD!!!
x.lower() # 'hello world!!!'
x.split() # ['Hello', 'World']
x.split("o") # ['Hell', ' W', 'rld']
```

## Strings formatting
```python
print("FORMATTED %s!" %"string") # FORMATTED string
print("This is {} string {}".format("FORMATTED","example")) # This is FORMATTED string example
print("This is named var r as {r}, g {g} and b {b}".format(r="RED",g="green",b="blue")) # This is named var r as RED, g green and b blue
print("Original float - {r}, formatted - {r:1.3f}".format(r=22/7)) # Original float - 3.142857142857143, formatted - 3.143  
### or with variables insertion
name = "Andrew"
print(f"Name string - {name}") # Name string - Andrew

## Alignment, padding and precision with .format()
## Within the curly braces you can assign field lengths, left/right alignments, rounding parameters and more
## By default, `.format()` aligns text to the left, numbers to the right. You can pass an optional `<`,`^`, or `>` to set a left, center or right alignment:
print('{0:<8} | {1:^8} | {2:>8}'.format('Left','Center','Right'))
print('{0:<8} | {1:^8} | {2:>8}'.format(11,22,33))
#Left     |  Center  |    Right
#11       |    22    |       33

## padding character
print('{0:=<8} | {1:-^8} | {2:.>8}'.format('Left','Center','Right'))
print('{0:=<8} | {1:-^8} | {2:.>8}'.format(11,22,33))
#Left==== | -Center- | ...Right
#11====== | ---22--- | ......33
```

### Strings notes:
Are strings mutable? - Strings are not mutable! (meaning you can't use indexing to change individual elements of a string)

---
# Lists
```python
my_list = ["A",3,3.14]
len(my_list) #3
my_list.append("New element")
len(my_list) #4
my_list.pop() # New element printed and removed from end of list
my_list.pop(1) # New element printed and removed from 2nd position
len(my_list) #2
## Sort
new_list = [1, 3, 2] # [1, 3, 2]
new_list.sort() # [1, 3, 2] ==> [1, 2, 3]
new_list.reverse() # [1, 2, 3] ==> [3, 2, 1]

# Nested lists
nested_list = [1,10,[11,12,13],20]
nested_list[2][1] # 12
```
---

# Dictionaries
```python
my_dict = {"key1":"value1","key2":"value2"}
my_dict["key2"] #value2
# Revright or add value
my_dict["key3"] = "value3"

# Methods
my_dict.keys() # dict_keys(['key1', 'key2', 'key3'])
my_dict.values() # dict_values(['value1', 'value2', 'value3'])

# Nested dictionaries
nest_dict = {"key1":"value1","keyNest":{"kn1":"kv1","kn2":"kv2","kn3":"kv3"},"key3":["av1","av2","av3"]}
nest_dict["keyNest"]["kn2"] # kv2
nest_dict["key3"][1] # av2
```

### Dictionaries notes:
Dictionaries are mappings and do not retain order! If you do want the capabilities of a dictionary but you would like ordering as well, check out the ordereddict object

---

# Tuples
Similar to dictionaries, key difference - immutability

```python
my_t = ("a","c","b","a")
len(my_t) #4
my_t.count("a") #2
my_t.index("b") #2
my_t[0] = "NewValue" # TypeError: 'tuple' object does not support item assignment
```

---

# Set
Set - unordered collection of UNIQUE elements

```python
my_set = set()
my_set.add("a")
my_set.add("b")
len(my_set) #1
my_set.add("a")
len(my_set) #1
my_t = ("a","c","b","a") # or my_l = {"a","c","b","a"}
set(my_t) # Just unique values - {"a","b","c"}
```

### Set notes:
```python
set('Mississippi') #{'M', 'i', 'p', 's'}
```

---

# Files
## Write in file
```python
%%writefile myfile.txt
Hello in text file
second line
```

## Read from file
```python
my_file = open("myfile.txt") # or path open("C:\\path\\myfile.txt")
my_file # <_io.TextIOWrapper name='myfile.txt' mode='r' encoding='cp1251'>
my_file.read() # 'Hello in text file\nsecond line\n'
my_file.read() # '' !!! empty for next reading
type(my_file) # _io.TextIOWrapper

my_file.seek(0) # 0
my_file.read() # 'Hello in text file\nsecond line\n' - content available again

my_file.seek(0) # 0
my_file.readlines() # ['Hello in text file\n', 'second line\n']

# Close file - good practice!
my_file.close()

# it's embeded in construction:
with open("myfile.txt") as my_new_file:
    content = my_new_file.read()

# mode by default is r = READ
with open("myfile.txt",mode="r") as my_new_file:
    content = my_new_file.read()

# mode "r" - read only
# mode "w" - write only (will overwrite or create new file)
# mode "a" - append only (just to add new to file)
# mode "r+" - reading and writing 
# mode "w+" - writing and reading (overwrite or create new file)

# Write to file:
with  open("myfile.txt",mode="a") as f:
    f.write("\nnew added string")    
with open("myfile.txt") as f:
    content = f.read()
content # 'Hello in text file\nsecond line\nnew added string'

```

---

## Comparison operators and logical
```python
2 == 2.0 # True
2 != 3 # True
2 > 3 # Talse
2 >= 2 # True

# chaininig comparison
1 < 2 > 1.5 # True
1 < 2 > 3 # False
# or logical "and", "or", "not"
1 < 2 and 2 > 3 # False
1 < 2 and 2 < 3 # True
# same with ()
(1 < 2) and (2 > 3) # False
(1 == 2) or (2 < 3) # True - because False|True ==> True
not(1 == 1) # False - becasuse same as not(True) ==> False

```

---

## Flow control
```python
day = "Friday"
myStatus = "Maried"

if day == "Friday" and myStatus == "Single":
    print("Go to party")
elif day == "Friday" and myStatus == "Maried":
    print("Go to romantic dinner")
else:
    print("Think abou your life")
```

---

## Notes:
*Why doesn't 0.1+0.2-0.3 equal 0.0* - https://docs.python.org/2/tutorial/floatingpoint.html

Be careful with copy by link or value
```python
list_A = ["A",3,3.141592,{"name":"Andrii","lastname":"Stepura"},{"a","b"},True]
print("List A: ", list_A)

list_B = list_A
print("List B: ", list_B)

list_B[0] = "Changed element in list B"
print("List B: ", list_B)
print("\nBut, it's affects A also\n")
print("List A: ", list_A)
```