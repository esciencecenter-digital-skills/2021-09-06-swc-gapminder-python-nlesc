![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document Day 3

2021-09-06 Software Carpentry with Python.

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: [link](<url>)

Collaborative Document day 1: [link](https://hackmd.io/d87-fmTTSlqje0w8q2CbGA)

Collaborative Document day 2: [link](https://hackmd.io/dzeVERLjRwWSo4u7AF0kvg)

Collaborative Document day 3: [link](https://hackmd.io/XGvsAhpnS_aJZR73xe9n4w)

Collaborative Document day 4: [link](https://hackmd.io/9FvKiiWQTLqv36yJbbTf5w) 

## 👮Code of Conduct

* Participants are expected to follow those guidelines:
* Use welcoming and inclusive language
* Be respectful of different viewpoints and experiences
* Gracefully accept constructive criticism
* Focus on what is best for the community
* Show courtesy and respect towards other community members

For more details, see [here](https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html).

Want to report a Code of Conduct incident and you prefer to do it anonymously? You can do it [here](https://goo.gl/forms/KoUfO53Za3apOuOK2).
 
## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: [creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).

## 🙋Getting help

To ask a question, type `/hand` in the chat window.

To get help, type `/help` in the chat window.

You can ask questions in the document or chat window and helpers will try to help you.

## 🖥 Workshop website

[link](https://esciencecenter-digital-skills.github.io/2021-09-06-swc-gapminder-python-nlesc)

🛠 Setup

[link](https://esciencecenter-digital-skills.github.io/2021-09-06-swc-gapminder-python-nlesc/#setup)

Download files

* [data-shel.zip for shell lesson](http://swcarpentry.github.io/shell-novice/data/data-shell.zip)
* [python-novice-gapminder.zip for Python lesson](http://swcarpentry.github.io/python-novice-gapminder/files/python-novice-gapminder-data.zip)

## 👩‍🏫👩‍💻🎓 Instructors

Hanno Spreeuw (Monday), Jens Wehner (Tuesday), Dafne van Kuppevelt (Wednesday, Thursday)

## 🧑‍🙋 Helpers

Jaro Camphuijsen, Lieke de Boer  

## 👩‍💻👩‍💼👨‍🔬🧑‍🔬🧑‍🚀🧙‍♂️🔧 Roll Call
Name/ pronouns (optional) / job, role / social media (twitter, github, ...) / background or interests (optional) / city

(Deleted)

## 🗓️ Agenda
09:00	Welcome and icebreaker
09:15	Introduction to Programming in Python
10:15	Break
10:30	Introduction to Programming in Python (Continued)
11:30	Break
11:45	Introduction to Programming in Python (Continued)
12:45	Wrap-up
13:00	END

## 🧠 Collaborative Notes

### The jupyter interface
We work in the jupyter lab environment, and will write our program in a so called **Notebook**. This is a combination of human readable text and executable pieces of code.

Every separate piece in the notebook we call a **cell**. You can set the type of cell (plain text, markdown, code) in the top bar. You can execute or evaluate a cell by pressing **SHIFT + ENTER**. You can also press the "play" button in the top bar, but we like to use the keyboard as this is often faster.

The cells that are set to **markdown** will render just like this document after evaluating. The cells that are set to **code** will execute the code according to the language that you have specified in the top bar. We will use **Python 3**.

### First programming
Some of the simplest programs consist of just a mathematical expression. You can for example let your computer calculate the sum of 3 and 5 by entering the following formula in a cell that is marked as code and executing the cell (SHIFT + ENTER).

```python
3 + 5
```

It will output the answer just below the cell in a new "output" cell. 

We can also do several calculations in one cell, however jupyter will only show the last result. To explicitly tell python to show something we use the **print** statement.

```python
print(7 * 3)
print(2 + 1)
```
```
21
3
```

To store values in python we use the concept of a **variable**. We assign a variable using the equal sign:

```python
first_name = "Ahmed"
age = 43
```

Once the variable is defined, we can use it in the rest of the notebook.

```python
print("First name is", first_name, "age is", age)
```

Variables must be created before they are used so the following will give an error.
```python
print(last_name)
last_name = "Smith"
```

Variable names can be anything you like but ...
* can only contain letters, digits, and underscore _ (typically used to separate words in long variable names)
* cannot start with a digit
* are case sensitive (age, Age and AGE are three different variables)


If your variable is a number, you can use it in math equations. You can even update the variable like in the following example:
```python
age = age + 3
print(age)
```

Reassigning variables can be tricky and you must be careful when reusing variables.
```python
initial = 'left'
print('initial is:', initial)
position = initial
print('position is:', position, 'initial is:', initial)
initial = 'right'
print('position is:', position, 'initial is:', initial)
```

```
initial is: left
position is: left initial is: left
position is: left initial is: right
```

If our variable is text we can select a single character using a concept called **slicing**:
```python
atom_name = 'helium'
print(atom_name[0])
```
as in many programming languages we start counting at 0 instead of 1:

![](https://i.imgur.com/LWl2olS.png)

We can also select a larger part of the word using this slicing.
```python
print(atom_name[0:3]) # start at position 0 and end BEFORE position 3
```

### Types and conversions

This slicing does not work for all variables

```python
a = 123
a[1]
```
This gives an error because slicing is not defined for numbers.

Variables in python always are of a certain **type**. We can check this type as follows:

```python
type(atom_name)
type(a)
type(1.23)
```

```
string
integer
float
```

Since our variable "a" is a whole number without decimal point, we call it an **integer**. A number with decimal point we call a **float** and words, sentences, etc (anything we defined with the single or double quotes) is called a **string**. 

It is often possible to convert a variable of one type to another:

```python
str(a) #convert the integer "a" to a string
int(float("3.4")) 
```

In the second example we have defined a string "3.4", we convert that to float (3.4) and then convert it to an integer (3). Note that this conversion can remove information from your variable. Also often a conversion does not work because it is not clear what the result of such a conversion should be, for example `int("3.4")` or `float("hello")` will not work. 

### Built in functions and help

There are many built in functions that we can use in python.  We have seen some examples of built in functions already. The `print()`, `type` and the type conversions are all examples of built in functions.

Some others that will prove useful are:
```python
len("hello") # gives you the length of the string "hello", here: 5
max(1, 2, 3) # gives you the largest item in (1, 2, 3), here: 3
min(1, 2, 3) #gives you the smalles item in ('a', 'A', 0), here: 1
round(3.7123) # rounds the number to the nearest integer, here: 4
```

Functions always take zero or more arguments (the things we put in the brackets) and always return something.

To get more information about a function you can run the following command:

```python
help(round) #this works in any python environment
```
This gives you information about the function "round", with an explanation and a description of how to call it and what arguments it needs or can take.

In jupyter notebooks we can also run `round?` which shows similar result as the `help` function but marked up nicely.

From the output of this command, we see that round can take an additional argument, namely "ndigits". It has a default so is not required to execute the function, but it can be used to specify the number of digits you want to round to.

Functions can take another form that we will also work with. This notation makes use of the fact that some objects (like a string, or an integer) have their own functions.

```python
my_string = "Hello World!"
print(my_string.isupper())          # Not all the letters are uppercase
print(my_string.upper())            # This capitalizes all the letters
print(my_string.upper().isupper())  # Now all the letters are uppercase
```

In jupyter lab you can find which of these functions are available by typing `my_string.` and then press TAB. This shows you a list of possible functions that can be appended to this object using the dot notation. This tab-completion can also be used in other cases. If you type `m` and press TAB, you will get all possible entries (variables, functions, etc.) that are currently possible in your notebook. 

It might happen that you get an error message, this means something is not right in your program. Error messages give a lot of information that can be used to **debug** the program.

```python
print("hello"
```

Will give you a SyntaxError, it shows you where the error happened and will try to describe the problem. In this case it says "unexpected EOF while parsing", this means the line ends in a way that python does not expect (EOF stands for end of file). This is indeed the case since we forgot a bracket.


### Libraries
Use import to load a library module into a program’s memory.

```python
import math

print('pi is', math.pi)
print('cos(pi) is', math.cos(math.pi))
```

You can also use the help function, that we already know from before, to get information about a library, e.g. `help(math)`. This will print the documentation of the library. Most of the times you can also find it online.

You can also import specific items from a library and then use them without the library name:

```python
from math import cos, pi

print('cos(pi) is', cos(pi))
```

And you can specify an alias for the library name to make it easier to use in your code:

```python
import math as m

print('cos(pi) is', m.cos(m.pi))
```


### Start with Pandas
On the left side of your jupyter lab environment you can open up a sidebar with a file browser if you click on the folder icon.

![](https://i.imgur.com/J7QfDC8.png)


There you can browse through your system. Navigate to the downloaded data, if you are not already in that folder. This data is in csv (comma separated values) format. You can view this data in a nice table view in jupyter lab by a double click. It will open up a new tab where you can inspect the data.

We will however load the data in our (newly created) jupyter notebook "Data_with_pandas.ipynb".

```python
import pandas as pd

data = pd.read_csv('data/gapminder_gdp_oceania.csv') 
print(data)
```

The path that you need to input in `pd.read_csv` depends on where your data is located and where your jupyter notebook is located. So this can also be `'../data/gapminder_gdp_oceania.csv'`.

Use index_col to specify that a column’s values should be used as row headings.

```python
data = pd.read_csv('data/gapminder_gdp_oceania.csv', index_col='country')
print(data)
```

Use the DataFrame.info() method to find out more about a dataframe.

The DataFrame.columns variable stores information about the dataframe’s columns.

```python
print(data.columns)
```

Use DataFrame.T to transpose a dataframe. and `to_csv` to write to a new csv file.

```python
data_transposed = data.T
data_transposed.to_csv("data_transposed.csv") #will write our new data to the specified filename
```

Use `DataFrame.iloc[..., ...]` to select values by their (entry) position
Use `DataFrame.loc[..., ...]` to select values by their (entry) label.
Use `:` on its own to mean all columns or all rows.
Select multiple columns or rows using `DataFrame.loc` and a named slice.


```python
print(data.iloc[0, 0])
print(data.loc["Albania", "gdpPercap_1952"])
print(data.loc["Albania", :])
print(data.loc["Albania"]) #same as the one above
print(data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972'])
```

Result of slicing can be used in further operations.

```python
gdp_1952 = data.loc["gdpPercap_1952"].max()
```


## 🔧 Exercises

### Share something that you are proud of (work related, private, anything):
(Deleted)


### Ready to go? (conda installed and jupyter lab open)


### Math in Python

What is displayed when a Python cell in a notebook
that contains several calculations is executed?

### Predicting Values

What is the final value of `position` in the program below?
(Try to predict the value without running the program,
then check your prediction.)

~~~
initial = 'left'
position = initial
initial = 'right'
~~~


### Slicing concepts
 Given the string: `full_name = "James Bond"`
What would these lines return?
1. `full_name[7:10]`
2. `full_name[6:]`
3. `full_name[:4]`
4. `full_name[:]`
5. `full_name[2:-1]`
6. What happens when you choose a high value which is out of range? (i.e., `full_name[0:15]`)


### Challenge

If you assign `a = 123`,
what happens if you try to get the second digit of `a` via `a[1]`?



### Strings to Numbers

Where reasonable, `float()` will convert a string to a floating point number,
and `int()` will convert a floating point number to an integer:

~~~
print("string to float:", float("3.4"))
print("float to int:", int(3.4))
~~~

~~~
string to float: 3.4
float to int: 3
~~~

If the conversion doesn't make sense, however, an error message will occur.

~~~
print("string to float:", float("Hello world!"))
~~~

~~~
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
<ipython-input-5-df3b790bf0a2> in <module>
----> 1 print("string to float:", float("Hello world!"))

ValueError: could not convert string to float: 'Hello world!'
~~~

Given this information, what do you expect the following program to do?

What does it actually do?

Why do you think it does that?

~~~
print("fractional string to int:", int("3.4"))
~~~




### Arithmetic with Different Types

Which of the following will return the floating point number `2.0`?
Note: there may be more than one right answer.

~~~
first = 1.0
second = "1"
third = "1.1"
~~~

1. `first + float(second)`
2. `float(second) + float(third)`
3. `first + int(third)`
4. `first + int(float(third))`
5. `int(first) + int(float(third))`
6. `2.0 * second`




### What Happens When

1. Explain in simple terms the order of operations in the following program:
when does the addition happen, when does the subtraction happen,
when is each function called, etc.
2. What is the final value of `radiance`?

~~~
radiance = 1.0
radiance = max(2.1, 2.0 + min(radiance,  1.1 * radiance- 0.5))
~~~


### Locating the Right Module (Breakout exercise)

You want to select a random character from a string:

~~~
bases = 'ACTTGCTTGAC'
~~~

1. Which [standard library][(https://docs.python.org/3/library/)] module could help you?
2. Which function would you select from that module? Are there alternatives?
3. Try to write a program that uses the function.

Breakout room 1: import library random (import random) | random.choice(bases) | Alternative: import secrets |bases = 'ACTTGCTTGAC'| secrets.choice(bases) | More complicated alternative: position = int(random.uniform(0,len(bases)-1)) | subset = bases[position] | print(subset)

Breakout room 2: import random, then random.choice(bases) (refuse to look for alternatives)

Breakout room 3: import random, random.choice(bases)

Breakout room 4: import random library, random.choice(string), bases[random.randrange(0,len(bases)-1)]

Breakout room 5: import random | random.choice(bases)

Breakout room 6:



### There Are Many Ways To Import Libraries!

Match the following print statements with the appropriate library calls.

Print commands:

1. `print("sin(pi/2) =", sin(pi/2))`
2. `print("sin(pi/2) =", m.sin(m.pi/2))`
3. `print("sin(pi/2) =", math.sin(math.pi/2))`

Library calls:

1. `from math import sin, pi`
2. `import math`
3. `import math as m`
4. `from math import *`

Which statement do you find most easy to read?


### Can you load the data in jupyter notebook?



### Reading Other Data

Read the data in `gapminder_gdp_americas.csv`
(which should be in the same directory as `gapminder_gdp_oceania.csv`)
into a variable called `americas`
and display its summary statistics.


### Inspecting Data

After reading the data for the Americas,
use `help(americas.head)` and `help(americas.tail)`
to find out what `DataFrame.head` and `DataFrame.tail` do.

1.  What method call will display the first three rows of this data?
2.  What method call will display the last three columns of this data?
(Hint: you may need to change your view of the data.)


### Selection of Individual Values

Write an expression to find the Per Capita GDP of Serbia in 2007.


### Extent of Slicing

1.  Do the two statements below produce the same output?
2.  Based on this,
what rule governs what is included (or not) in numerical slices and named slices in Pandas?

~~~
print(df.iloc[0:2, 0:2])
print(df.loc['Albania':'Belgium', 'gdpPercap_1952':'gdpPercap_1962'])
~~~



## Feedback

### Top (what did you like most about today?)

- Very clear and easy to understand. 
- I like the way you instructors interact, its really organic and great how you help each other and keep check of the participants needs. (+1)
- clear and well organized
- I liked using the notebook as I could also take notes during the class, it will be very useful later. The lessons were clear, I particularly enjoyed the panda part.
I enjoyed the learning, pace was good, perfectly clear
- I really like this JupyterLab and how you get us familiar with it
- Nice and calm way to deal with issues
- Loved the hands-on instructions and pace
- new modules and functions
- I was looking forward to the python language and i have enjoyed the simplicity in coding
- I like the carpentry strategy of writing code together
- solving "individual" issues in breakout rooms is a good idea (+1)


### Tip (what could be improved?)
- would be nice if we can get your notebook or the terminal coding from the instructors, just in case

- Jupiter work a bit slow and my computer froze several times. bit slow and my computer froze several times. bit slow and my computer froze several times. bit slow and my computer froze several times. 
- more of such 'search the Jupyter/Python library'-exercises. Its scary how much is possible, and one needs to get the hang of it. (+1)
- Quite slow because not everybody has the necessary install (even though it should have been tested yesterday)
- Jupyter needs some "getting used to"
- It would be nice if persitent issues (system, downloads, etc) would be taken faster to a breakout room
- the instructor being interrupted while talking sometimes felt a bit uncomfortable
- Maybe a slighly longer trial run on the second day could help the lessons to go smoother, so not only how to open Jupyter but also  try to load some data etc. Or maybe as a homework between day 2 and 3?

## 📚 Resources

Zoom link of today https://us02web.zoom.us/j/88319621156?pwd=aWYyV29vK3JzS29Lb3AvbUJRUmRPdz09
Data for python https://swcarpentry.github.io/python-novice-gapminder/files/python-novice-gapminder-data.zip

[Notebooks Day 3](https://github.com/esciencecenter-digital-skills/2021-09-06-swc-gapminder-python-nlesc/tree/gh-pages/files/notebooks)