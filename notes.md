# Intro to Python Bootcamp
A day-long bootcamp to build a solid foundation in Python, an excellent programming language known for its clean syntax and strength in data.

No prior programming experience is required.


# Instructor
- name: Henry Xie
- email: henry@simplefractal.com
- website: [simplefractal.com](http://simplefractal.com)

# What do you need?
- Download Anaconda 3.7 [here](https://www.anaconda.com/download/)
- Verify installation by:
    - On a Mac: Open Terminal and run `jupyter notebook`
    - On Windows: Search for Jupyter in your start menu and click the Jupyter icon
- Download CSV dataset [here](https://bit.ly/2jiFQlB)

# Topics
1. Data Types
2. Variables
3. Data Structures
    - Lists
    - Dictionaries
4. Control Flow
5. Functions
6. Problem-solving
7. Intermediate Techniques
    - List comprehensions
    - List sorting
    - List slicing
    - Lambda functions
    - Exception handling
8. Data Analysis on real dataset
    - Reading in CSV file into Python data structures
    - Dealing with unclean data
    - Applying techniques to answer questions an analyst might have

# The Basic Data Types
What are the basic data types?
- Integers, e.g. 1, 2, 3
- Floating point numbers, e.g 2.3, 3.782738
- String, e.g. "John Krasinski"
- Boolean, True or False
- None, which just corresponds to empty or null, if you've used other languages

Let's start with integers and floats.

Let's go into the python shell.
To do this, open up your terminal and type 'python' and then press Enter.

We can do math in the shell.
```python
>>> 2 + 2
4
>>> 2 * 3.5
7.0
>>> 7 / 2.0
3.5
```

Practice question - try these out in the shell:
```
1. 2 * 7 * 3.5
2. 3 + 5 - (2 * 6)
3. (3 + 5 - 2) * 6
4. 4 == 5
5. 5 == 5
6. 4 < 5
7. 5 >= 4
8. 9 != 9
9. 8 != 9
```

Explanations:
```
In 1., we learned that you can chain operations
In 2 and 3, we learned that order matters and you can use parentheses to indicate the order, as part of the usual mathematical order of operations.
In 4 and 5, we learned about the equality operator.
In 6 and 7, we learned about inequality comparions like less than or greater than equal to.
In 8 and 9, we learned about the not-equal-to operator.
```

Now let's talk variables. What's a variable? It's a placeholder for a value.
```python
>>> x = 5
>>> y = 2
>>> x + y
7
>>> x = 3
>>> x + y
5
```

Practice question:
Given x=10, y=2, predict the answers to the following and then try them out in the shell:
```
1. x + y
2. x * y
3. (x + 7) / y
4. (x + 7.0) / y
5. x == y
6. x != y
```

Now let's talk about Booleans.
Simply put, a boolean variable is either True or False, and every python object or data has a boolean value.
We can find out what the true-false value is by using bool()

Let's try it out:
```python
>>> bool(False)
False
>>> bool(True)
True
>>> bool(0)
False
>>> bool(7)
True
>>> bool(None)
False
>>> bool(7 == 0)
False
>>> 7 == 0
False
```
Last stop on our journey into basic data types: Strings
A string is a sequence of characters, for example "Hello" or "My id # is 1235!"
Let's try a few in our shell:
```python
>>> "Hello World!"
Hello World!
>>> "Hello" + " World!"
>>> 1 + "world"
```

Practice problem:
```
- Set a variable called `name` equal to your full name.
- Set a variable called `first_name` equal to your first name.
- Set a variable called `last_name` equal to your last name.
- Then combine `first_name` and `last_name` so that it equals your full name, and save this in a variable called `full_name`.
- Prove using the == operator that they are equal.
```

What if we wanted to prompt the user to set the variables as opposed to having them pre-defined? We can use `input` (Python 3+) or `raw_input` (Python 2.x) like so:

```python
>>> first_name = input("What is your first name? ")
>>> last_name = input("What is your last name? ")
>>> print("Your full name is: {} {}".format(first_name, last_name))
```

The above is an example of "string interpolation", a technique used for interpolating strings with variables.

# Lists
Lists is a super useful data type often used to store a multitude of similar things.
It's an ordered collection of items, which you can modify by adding or removing elements.

Let's learn the syntax of a list:
```python
>>> x = [1, 2, 3, 4, 5]
>>> len(x)
5
>>> # what's between the brackets is called the index
>>> x[0]
1
>>> x[1]
2
>>> x[4]
5
>>> x[6]
IndexError
>>> x.append("hello")
>>> len(x)
6
>>> x[5]
"Hello"
>>> # can remove elements, defaults to popping off the last one
>>> x.pop()
"Hello"
>>> print x
[1, 2, 3, 4, 5]
>>> # can specify the index
>> x.pop(2)
3
>>> print x
 [1, 2, 4, 5]
>>> # can do a boolean check if something is in the list
>>> 5 in x
True
>>> 3 in x
False
```

Practice problem:
```
- Create a list called `restaurants` consisting of the following elements in this order:
"Laut", "Random String", "Chipotle", "Eataly", "Sophie's Cuban", "Chop't", "Potbelly's"
- Get the third element of the list
- Add "Ootoya" to the end of the list
- Use .pop() to remove "Random String" from the list
- Print the list
- Check if 'Chipotle' is in the list
- Check if 'Dunkin Donuts' is in the list
- Get the length of the list
```

Let's learn about slicing:
```python
>>> y = [1, 2, 3, 4, 5, 6, 7, 8]
>>> y[2:]
[3, 4, 5, 6, 7, 8]
>>> y[:4]
[1, 2, 3, 4]
>>> y[1:3]
[2, 3]
>>> y[-3:]
[6, 7, 8]
```
- In the square brackets after the list, there is now a colon to indicate slicing.
- Slicing produces a new list that is a subsection of the original list.
- What comes before the colon is the first index we wish to include. It defaults to 0.
- The sliced list includes all element up until but not including the index specified after the colon. If you don't specify it, all elements through the last element of the list will be included in the sliced list.
- Negative indices are supported. `-3` refers to the third element from the end of the list.

# Dictionaries
Dictionaries are also massively useful. One use case is for storing several attributes or data points about the same thing. You can think of them as maps, between a set of keys and their corresponding values.
Let's look at one in the shell to better understand how they work and how they can be useful:

```python
>>> # Here's the syntax, `{}` with `key:value`, with `key` being a string.
>>> dog = {"name": "Lucky", "age": 12, "friends": ["Penny", "Pancho"]}
>>> # like for lists, we use the brackets to reference data inside but instead of the index, we provide the key name as a string
>>> dog["name"]
"Lucky"
>>> dog["friends"].append("Spot")
>>> len(dog["friends"])
3
>>> dog["random"]
KeyError
>>> dog["breed"] = "golden retriever"
>>> dog
{'friends': ['Penny', 'Pancho', 'Spot'], 'age': 12, 'name': 'Lucky', 'breed': 'Golden Retriever'}
>>> key = "age"
>>> dog[key] += 1
>>> dog
{'friends': ['Penny', 'Pancho', 'Spot'], 'age': 13, 'name': 'Lucky', 'breed': 'Golden Retriever'}
>>> del dog[key]
>>> dog
{'friends': ['Penny', 'Pancho', 'Spot'], 'name': 'Lucky', 'breed': 'Golden Retriever'}
>>> dog.keys()
dict_keys(['friends', 'name', 'breed'])
>>> dog.values()
dict_values([['Penny', 'Pancho', 'Spot'], 'Lucky', 'Golden Retriever'])
>>> dog.items()
dict_items([('friends', ['Penny', 'Pancho', 'Spot']), ('name', 'Lucky'), ('breed', 'Golden Retriever')])
>>> # check if a key exists in the dictionary
>>> "name" in dog
True
>>> "favorite_food" in dog
False
```
Practice problem:
```
Create a dictionary called `class_data` with the following keys:
- "course_name", which should correspond to "Intro to Python"
- "student_count", which should correspond to number of students, say 20
- "instructor", which should itself be a dictionary with the following keys
    - "name" ("Henry")
    - "gender" ("M")
    - "can_program" (True)
- get the student count from the dictionary
- get the instructor name from the dictionary
- delete the gender key under instructor
- change the instructor name to "Henry Xie"
```

# If/Else
If/else statements are blocks of our code that allow us to do different things based on some logical condition
Let's learn the syntax, note INDENTATION is important:
```python
>>> x = 5
>>> if x > 4:
        print("Hello")
    else:
        print("World")
Hello
>>> if x < 5:
        print("Less than five")
    else:
        print("Greater than or equal to five")
>>> if x == 1 or x == 2:
        print("Ha")
    elif x == 3:
        print("Hey")
    else:
        print("Hi")
```

Practice problem:
```
- Prompt the user for an integer between 0 and 100 using `input` or `raw_input`
- If the number is greater than 75, print "You picked a large number!"
- Else if the number is greater than 40, print "You picked a decently large number."
- Else if the number is greater than 10, print "Ok, that's still respectable."
- Else print "Wow, your number is really small."
```

# Loops
Loops let us pass through a set of values and do some operation on each.
There are different kinds of loops, for loops and while loops. They're quite similar, but let's look at the canonical loop, the for loop.

```python
>>> numbers = [1, 2, 8, 7, 9, 10]
>>> odds = []
>>> for number in numbers:
        if number % 2 == 1:
            odds.append(number)

>>> odds
[1, 7, 9]
```
- the `number` in the for loop syntax is a dummy variable that refers to the element in the list that we're passing through. The first time around, number refers to 1, the last time it refers to 10.
- we are going through this list and if the number is odd, we add it to the odds list that we initialized before the for loop.
- this technique/algorithm of initializing a variable (in this case as an empty list), and constructing it as we loop over data, is very common and useful.

Before we move on to some practice problems, here is a useful function:
```python
>>> range(10)
```

Practice problems:
```
- Construct a list of numbers between 0 and 1000 that are divisible by 33
- Given the following list
["Donald Duck", "Mickey Mouse", "Daffy Duck", "Goofy", "Minnie Mouse", "Pluto"]
Get the sum of all of the lengths of these strings.
- Given the above list, create a list of all of the elements that have the letter "d" or the letter "m" in them
```

# Functions
Functions are the heart and soul of python. Functions are blocks of code that take an input and based on some rules produce an output.

Let's learn the syntax of functions:

```python
>>> def add(a, b):
        return a + b
>>> z = add(3, 4)
>>> print(z)
7
```
a and b are variables that the function `add` takes, a.k.a. ARGUMENTS

Practice problems:
```
- create function `multiply` that takes two variables and returns their product
- create function `subtract` that takes two variables and returns their difference
```

Let's write a function that takes a variable, which is a list of numbers, and then returns just the ones that are divisible by 33.

```python
def div_by_33(numbers):
    by_33 = []
    for number in numbers:
        if number % 33 == 0:
            by_33.append(number)
    return by_33
```

Practice problem: Write a function that takes a list of numbers and returns True if the sum of the numbers is even and False otherwise.

# Methods
Methods are functions that are attached to things, or "objects" in programming-speak. These methods are accessed on the object using dot notation. Here is an example:

```python
>>> greeting = "Hello, World"
>>> print(greeting.lower())
hello, world!
```
- `greeting` is a variable that contains a string. All strings have the `lower` method, which when called, produces the lowercase value of the string it was called on.
- methods and functions are conceptually the same


# Lemonade Accounting

Prompt the user for how many lemonades he/she sold and over how many hours.
Use code to print out how much profit the user made, as well as the user's average hourly income.

Assume the following:
 - It takes 4 lemons to make a lemonade
 - Each lemon costs 50 cents
 - You charge $5 per lemonade
 - Cost of the lemonades is your only expense
 - When prompted, the user will input valid integer values

```python
def calc_profit(num_lemonades, num_hours):

    lemons_per_lemonade = 4
    price = 5
    lemon_cost = 0.5

    revenues = num_lemonades * price
    expenses = lemon_cost * num_lemonades * lemons_per_lemonade

    profit = revenues - expenses

    return "You made ${}, or ${} per hour.".format(profit, profit / num_hours)
```

## Python Exercises

1 - Write a function that prints all the even numbers between 1 and 10,000.

Solution:
```python
def print_evens():
    for x in xrange(10001):
        if x % 2 == 0:
           print x
```
This reviewed FOR LOOPS, IF CONDITIONS, and PRINTING

2 - Write a function that returns a list of the numbers between 1 and 10,000 that are divisible by 3.

Solution:
```python
def divisible_by_3():
    numbers = []
    for x in xrange(10001):
        if x % 3 == 0:
           numbers.append(x)
    return numbers
```
This reviews basic use of LISTS. Note: we use `xrange` instead of `range` because `range` loads the entire list into memory, while `xrange` just creates an iterator: https://mail.python.org/pipermail/python-list/2012-November/634509.html. If you have a really big list, `xrange` is way faster. In Python 3 `range` works the same way as `xrange`.

3 - The same as #2, but use Python list comprehensions.

Solution:
```python
def divisible_by_3():
    return [x for x in xrange(10001) if x % 3 == 0]
```
Note: List comprehensions are super useful. They allow you to iterate through lists and generate new lists on the fly with very little code.

4 - Write a function that takes a list of numbers and returns the max of those numbers, don't ues the max() function.

Solution:
```python
def get_max(numbers):
    max_number = numbers[0]
    for number in numbers:
        if number > max_number:
           max_number = number
    return max_number
```
Note: Here we just tested out our logic skills.

5 - Write a function that returns True if a number is odd or divisble by 7 and False otherwise.

Solution:
```python
def is_odd_or_div_by_7(number):
    return number % 2 == 1 or number % 7 == 0
```

6 - Use the function in #5 and list comprehensions to write a function that given a list of numbers returns a sublist of numbers
that are odd or divisible by 7.

Solution:
```python
def get_sublist_of_numbers_odd_or_div_by_7(numbers):
    return [number for number in numbers if is_odd_or_div_by(number)]
```
Note: Here we are combining our knowledge of list comprehensions with some conditional logic inside the list comprehension.

7 - Write a division function `divide(a, b)` that catch exceptions and return an error string if the arguments do not make sense.

Solution:
```python

def divide(a, b):
    try:
        result = a / b
    except TypeError:
        return "Both the numerator and denominator must be valid numbers."
    except ZeroDivisionError:
        return "The denominator cannot be zero."
    else:
        return result
```
Do not catch the general `Exception` since we won't know if some other error occurred.


8 - Given a list of food orders, write a function that takes the list and returns a dictionary with the different dishes as keys and the number of times they appear in the list as the values. For example,
```python
>>> tally(["burger", "fries", "burger", "tenders", "apple pie"])
{
   "burger": 2,
   "fries": 1,
   "tenders": 1,
   "apple pie": 1
}
```

Solution:
```python
def tally(order_list):
    orders_by_count = {}
    for order in order_list:
        # if we've already seen this order, increment the count
        if order in orders_by_count:
           orders_by_count[order] += 1
        # otherwise, this is the first time we're seeing it, so set its count to 1
        else:
           orders_by_count[order] = 1
    return orders_by_count
```

9 - Write a function that takes the same kind of input as in #8 but instead of returning a dictionary with the counts, it just returns a tuple: the dish that appears the most in the list and the number of times it appears in the list. So the output given the example would be ("burger", 2)

Solution:
```python
def get_most_popular_order_data(order_list):
    order_tally = tally(order_list)
    # the key is a function that tells `max` what to sort by
    # in this case, it's the second element of the tuple, e.g. 2 in ("burger", 2)
    # which is just the number of times it appears in the list of orders
    return max(order_tally.iteritems(), key=lambda x: x[1])
```
Note: for more on lambda functions, check this out http://www.diveintopython.net/power_of_introspection/lambda_functions.html


## Data Analysis
## Objectives
- use csv library to read in data
- use Python techniques to extract insights about the data

### Exercises

1 - Using csv library, read in data from https://raw.githubusercontent.com/suneel0101/data/master/classic-rock/classic-rock-song-list.csv.
NOTE: Make sure to open the file on the browser, highlight and copy the contents into your text editor and save. Otherwise, you'll get some errors when trying to read the file through the `csv` library.
HINT: Here's the relevant documentation on csv: https://docs.python.org/2/library/csv.html, use `DictReader`
```python
>>> import csv
>>> csvfile = open('rock.csv', 'rb')   # Use 'rU' for Python 3
>>> reader = csv.DictReader(csvfile)
>>> dir(reader)
>>> reader.fieldnames
```

2 - How many songs are from 1981?

Solution:
```python
print "# songs released in 1981 is: {}".format(
    len([row for row in rows if row["Release Year"] == "1981"])
)
```

3 - What is the earliest release year in the data?
HINT: You might have to account for/clean up dirty data

#### First pass
```python
>>> min([int(row['Release Year']) for row in rows if row['Release Year']])
ValueError: invalid literal for int() with base 10: 'SONGFACTS.COM'
```
`SONGFACTS.com` is not a valid year, so we'll have to clean up `Release Year` by ensuring we are dealing with integers.

#### Second pass
```python
def is_valid_year(string):
    try:
        year = int(string)
    except ValueError:
        return False
    else:
        return year

>>> release_years = [int(row['Release Year']) for row in rows if is_valid_year(row['Release Year'])]
>>> min(release_years)
1071
```

This doesn't make any sense! Exclude that!

#### Third pass
```python
def is_valid_year(string):
    try:
        year = int(string)
    except ValueError:
        return False
    else:
        return year > 1900


print "Earliest release year is: {}".format(
    min([row['Release Year'] for row in rows
        if is_valid_year(row['Release Year'])])
)
```

That makes much more sense!

4 - How many songs are from before 1984
```python
print "# songs released before 1984 is: {}".format(
    len([row for row in rows
        if is_valid_year(row["Release Year"])
        and int(row["Release Year"]) < 1984])
)
```

5 - What are the top 20 songs by play count
HINT: use builtin sorted() function
```python
print "The top 20 songs by play count are: {}".format(
    [(row['Song Clean'], row['PlayCount'])
    for row in sorted(
        rows,
        key=lambda row: int(row['PlayCount']),
        reverse=True)][:20])
```

6 - Who are the top 10 most prolific artists in the data along with the number of their songs that appear in the data?
```python
# ["Led Zeppelin", "Led Zeppelin", "Rolling Stones", ...]
artist_names = [row["ARTIST CLEAN"] for row in rows]

# {"Led Zeppelin": 69, "Rolling Stones": 56}
artist_tally = tally(artist_names)

# [("Led Zeppelin", 35), ...]
pairs = sorted(artist_tally.items(), key=lambda x: x[1], reverse=True)

print "Top 10 most prolific artists are: "
for pair in pairs[:10]:
    print pair
```

7 - How many different artists appear in the data?
```python
print "# different artists is: {}".format(
    len(set(artists))
)
```
NOTE: How is a Python set different from a list?

8 - How many songs does 'Rock'/'rock' appear in the title of?
```python
print "# songs with word rock (case insensitive) in title is: {}".format(
    len([row for row in rows if 'rock' in row['Song Clean'].lower()])
)
```

