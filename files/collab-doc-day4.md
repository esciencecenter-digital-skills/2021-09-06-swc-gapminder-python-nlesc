![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document Day 4

2021-09-06 Software Carpentry with Python.

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: [link](https://hackmd.io/9FvKiiWQTLqv36yJbbTf5w)

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

[post-workshop survey](https://carpentries.typeform.com/to/UgVdRQ?slug=2021-09-06-swc-gapminder-python-nlesc)

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
09:15	Plotting and Programming in Python
10:15	Break
10:30	Plotting and Programming in Python (Continued)
11:30	Break
11:45	Plotting and Programming in Python (Continued)
12:30	Wrap-up
12:45	Post-workshop Survey
13:00	END

## Icebreaker

What is your favourite Youtube/TV/Netflix/Amazon Prime/HBO/Hulu/Disney show?
(Deleted)


## 🧠 Collaborative Notes

When to use loc: when you need more than one column. 

Import the data: 

```python=
import pandas as pd

data_europe = 
pd.read_csv('data/gapminder_gdp_europe.csv', 
index_col='country')

data_europe.head()
```
Let's make a subset:

```python=
subset = data_europe.loc('Italy': 'Poland', 'gdpPercap_1962': 'gdpPercap_1972')
subset
```

Let's see in which country within the subset, the gdp is larger than 10,000

```python=
subset > 10000
```

This will return `True` or `False` for each element in the subset, depending on whether it is greater than 10,000. We can save those trues and falses in a mask to select the data in the subset where the value is above 10,000. 

```python=
mask = subset > 10000
subset[mask]
```

We can use `describe` to check this subsetted dataset:

```python=
masked_subset = subset[mask]

masked_subset.describe()
```

Comparing it to the original subset:

```python=
subset.describe()
```

This describes the entire subset, without having masked it. 

#### Plotting

Matplotlib is the most common plotting library in Python. It can do a lot of complicated things, and one of its strengths is that you can use it with pandas. But we can also use it without pandas:

```python=
import matplotlib.pyplot as plt

time = [0, 1, 2, 3]
position = [0, 100, 200, 300]

plt.plot(time, position)
plt.xlabel('Time (hr)')
plt.ylabel('Position (km)')
```

If you do not specify which plot this applies to, Matplotlib always automatically changes the latest plot that was created with the code that is written. 

Let's plot some data!

```python=
data = pd.read_csv('data/gapminder_gdp_oceania.csv', index_col='country')

data
```

We would like our x-values to be the year in the column names, and our y-values to be the GDPs in the table.

In order to do that, we need to convert the column name string into a number. 

```python=
years = data.columns.str.strip('gdpPercap_')
years
```

Only doing this only strips the non-numeric characters from the string, but it is still a string. If we want to treat it like a number, we need to convert it to one. Luckily, pandas can do this for us. 

```python=
years_num = years.astype(int)
```

Now we have our years converted to numbers! Let's make sure we assign these to our column names.

```python=
data.columns = years_num
data
```

We did a lot of work, but now we can plot our data with a single line of code.

```python=
data.loc['Australia'].plot()
```

This plots the column names on the x-axis, and the gdp values on the y-axis. 

You may want to treat both countries at the same time, and think that this is what does it:

```python=
data.plot()
```

But unfortunately, it plots the axes the wrong way around! You first need to transpose the data. 

By default, the rows will be treated as x-values. If you do not want the rows as x-values, you need to transpose your data. 

```python=
data.T.plot()
```

This gives us the plot we wanted. 

We can change the styles in different ways! One example is to make it look like ggplot in R. 

```python=
plt.style.use('ggplot')
data.T.plot(kind = 'bar')
plt.ylabel('GDP per capita')
```

Let's plot Australia only:

```python=
years = data.columns
gdp_australia = data.loc['Australia']
plt.plot(years, gdp_australia)
```

It remembers that we used the ggplot style now! 

If we wanted to make the same plot without pandas, this is what you would do:

```python=
gdp_nz = data.loc['New Zealand']

plt.plot(years, gdp_australia, label='Australia')
plt.plot(years, gdp_nz, label='New Zealand')

plt.xlabel('Year')
plt.ylabel('GDP per cap')
plt.legend(loc='upper left')
```

we can also create a scatterplot:

```python=
plt.scatter(gdp_australia, gdp_nz)
```

This creates the GDPs of NZ against the GDPs of Australia for each corresponding year

```python=
data.T.plot.scatter(x = 'Australia' y = 'New Zealand')
```

Exercise plotting the max and min:

```python=
data_asia = pd.read_csv('data/gapminder_gdp_asia.csv', index_col = 'country')

data_asia.T.min()

```
This gives the minimum for each country over all years. 

```python=
data_asia.min()
```
This gives the minimum for all countries for all years. 


#### Lists

Lists can do a lot, let's explore their functionality.

```python=
pressures = [0.392, 0.275, 0.277, 0.299]
pressures
```

Strings are interpreted very similarly to lists. 

```python=
len(pressures) # this should output 4
```

```python=
pressures[0] #slicing first element
pressures[:2] #slicing everything up to third element
pressures[0] = 0.292 # replacing the first value with a new value

pressures #inspect the result
```
Lists have methods attached to them. This is how you can expand them:

```python=
pressures.append(0.288)
pressures #this will have appended a new value

pressures.extend([0.268, 0.298]) #adds a list to a list
```
You can also remove items from a list

```python=
del pressures[1]
pressures # this will have removed the second element from the list above

```

Sometimes, we want to initiate a variable with an empty list:

```python=
empty_list = []
empty_list
```
Solution to the fill in the blanks exercise:

```python=
values = []
values.append(1)
values.append(3)
values.append(5)
print('first time:', values)
values = values[1:]
print(values)
```

We can also combine different types of data in a list:

```python=
combined_list = ['a', 0.456, 100]
combined_list
```

One type of data that can be part of a list, is a list:

```python=
nested_list = [100, 120, ['a', 'b', 300]]
nested_list
```

Extending lists. If you use append and give it a list, the new list will include the appended list as an element in the list:

```python=
a = [1, 2, 3]
a.append([4, 5])
a
```

You cannot change the content of a string, but you can change the content of a list:

```python=
my_string = 'abcd'
my_string[0] = 'A' #this will throw an error. 
```

Stepping through a list

```python=
my_list = [0, 1, 2, 3, 4, 5]
print(my_list[::2]) # this will print the first, third, and fifth element
my_list[::-1] #this prints out the list in reverse
my_list[::-2] # this prints out every second elemtns in reverse
```

#### For loops

We can write a for loop to do something for each element in the list. The for loop will have an loop variable, which will take on the identity of each element of your list one by one. 

```python=
for element in my_list:
    print(element)

```

This will print each element of the list, one by one

```python=
element
```

`element` took on 6 different values throughout the loop. After the loop is done, it still exists, and has the value of the last iteration of the loop. 

```python=
primes = [3,5,7]
for p in primes:
    squared = p ** 2 #double asterisks means "to the power of"
    cubed = p ** 3 
    print(p, squared, cubed)
```

The loop goes through the list, and for each element calculate the squared and the cubed element. Then, it will print the number, the squared number, and the cubed number for each element. 

Often you do not want to type out the list of numbers you want to loop over. The function `range` can be useful for this. 

```python=
range(0, 6)

for number in range(0, 6):
    print('Number is:' number)
```

This will print each value in the range, after `Number is:`

Note that 6 is not included in the range. The range will be between 0 and 5. 

Sometimes we may want to sum all the values in the list. 

```python=
my_sum = 0
for number in range(10):
    my_sum = my_sum + number
    
print(my_sum) # this gets executed after the loop, because of the indentation
```

We did not output anything inside the loop, but it is working, and it does add all the numbers between 0 and 10. 

Exercise answer:

```python=
original = "tin"
result = ""
for char in original:
    result = char + result # this builds n i t over 3 iterations
print(result)
```

#### `if` statements

```python=
mass = 3.54
if mass > 3.0:
    print('Mass is large')
```
The code indented after `if` is only executed if the condition `mass > 3.0` is met. 

```python=
masses = [3.56, 2.64, 4.53, 1.24]
for mass in masses:
    if mass > 3.0:
        print(mass)
```

Here a loop and an if are combined. The loop goes over each element of masses and only prints it if the element is greater than 3. 

```python=
for mass in masses
    if mass > 3.0:
        print ('Large mass:' mass)
    else:
        print('Small mass:' mass)
```

This displays different information for the different masses, depending on whether the masses meet the condition set after `if`.

We can make use of more than 2 options (not just `if` and `else`). For that we use `elif`:

```python=
masses = [3.354, 2.345, 1.234, 9.235, 3.7]
    for mass in masses:
        if mass > 9.0:
            print('Huge mass:', mass)
        elif mass > 3.0:
            print('Large mass:', mass)
        else:
            print('Small mass:', mass) 
```

Exercise filling in the blanks with `if`

```python=
original = [-1.5, 0.2, 0.4, 0.0, -1.3, 0.4]
result = []
for value in original:
    if value < 0:
        result.append(0)
    else:
        result.append(1)
print(result)
```
This will output a 0 for negative numbers and a 1 for the rest. 

## 🔧 Exercises

### Breakout exercise: Practice with Selection

Assume Pandas has been imported and the Gapminder GDP data for Europe has been loaded.
Write an expression to select each of the following:

1.  GDP per capita for all countries in 1982.
2.  GDP per capita for Denmark for all years.
3.  GDP per capita for all countries for years *after* 1985.
4.  GDP per capita for each country in 2007 as a multiple of GDP per capita for that country in 1952.

#### Answers

Room 1: 
1) import pandas as pd
europe = pd.read_csv ('data/gapminder_gdp_europe.csv', index_col = "country"
) | europe.T.loc["gdpPercap_1982"].T
2) europe.loc["Denmark"]
3) europe.loc[:, "gdpPercap_1987":]
4) europe["gdpPercap_2007"] / europe["gdpPercap_1952"]



Room 2:
1) data_europe.loc[: ,"gdpPercap_1982"]
2) data_europe.loc["Denmark", :]
3) data_europe.loc[:,"gdpPercap_1985":]
4) data_europe.loc[:, "gdpPercap_2007"]/data_europe.loc[:, "gdpPercap_1952"]

Room 3: 1. data_europe['gdpPercap_1982']| 2. data_europe.loc['Denmark']|3. data_europe.loc[:, 'gdpPercap_1985':] | 4. data_europe.loc[:, 'gdpPercap_2007'] / data_europe.loc[:, 'gdpPercap_1952'] (data_europe["gdpPercap_2007"] / data_europe["gdpPercap_1952"] gives the same result)

Room 4:1. europe.loc[:,'gdpPercap_1982']|2. europe.loc['Denmark',:]|3.europe.loc[:,'gdpPercap_1985':]|4. europe.loc[:,"gdpPercap_2007"] / europe.loc[:,"gdpPercap_1952"]


#### Bonus exercise:

Python includes a `dir()` function that can be used to display all of the available methods (functions) that are built into a data object.  In Episode 4, we used some methods with a string. But we can see many more are available by using `dir()`:

~~~
my_string = 'Hello world!'   # creation of a string object
dir(my_string)
~~~

This command returns:

~~~
['__add__',
...
'__subclasshook__',
'capitalize',
'casefold',
'center',
...
'upper',
'zfill']
~~~

You can use `help()` or <kbd>Shift</kbd>+<kbd>Tab</kbd> to get more information about what these methods do.

Assume Pandas has been imported and the Gapminder GDP data for Europe has been loaded as `data`.  Then, use `dir()`
to find the function that prints out the median per-capita GDP across all European countries for each year that information is available.
room1:

#### Answers

Room 1: data.median()

Room 2: data_europe.median


Room 3:data_europe.median()


Room 4: data.median()


### Breakout exercise: Minima and Maxima

Fill in the blanks below to plot the minimum GDP per capita over time
for all the countries in Europe.
Modify it again to plot the maximum GDP per capita over time for Europe.

~~~
data_europe = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
data_europe.____.plot(label='min')
data_europe.____
plt.legend(loc='best')
plt.xticks(rotation=90)
~~~

Room 1: data_europe = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
data_europe.min().plot(label='min')
data_europe.max().plot(label='max')
plt.legend(loc='best')
plt.xticks(rotation=90)


Room 2: 
data_europe.min().plot(label='min')
data_europe.max().plot(label='max')
plt.legend(loc='best')
plt.xticks(rotation=90)
plt.show()

Room 3: 
data_europe = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
data_europe.min().plot(label='min')
data_europe.max().plot(label='max')
plt.legend(loc='best')
plt.xticks(rotation=90)

Room 4
data_europe = pd.read_csv('data/gapminder_gdp_europe.csv', index_col='country')
data_europe.min().plot(label='min')
data_europe.max().plot(label='max')
plt.legend(loc='best')
plt.xticks(rotation=90)

### Breakout exercise: Correlations

Modify the code of the scatter plot to create a scatter plot showing the relationship between the minimum and maximum GDP per capita among the countries in Asia for each year in the data set.
What relationship do you see (if any)?

**Room 1:** plt.scatter(data_asia.T.min(), data_asia.T.max())
plt.xlabel('minimum gdp')
plt.ylabel('maximum gdp')

or: plt.scatter(x=data_asia.T.min(), y = data_asia.T.max())

positive correlation
Room 2: 
plt.scatter(x = data_asia.T.min(), y = data_asia.T.max())
plt.title("Min GDP vs Max GDP in asian countries")
plt.xlabel("Minimum GDP")
plt.ylabel("Maximum GDP") 
|To get precisely what is asked for, the data should not be transposed, so no '.T'!|

Room 3: asia = pd.read_csv("data/gapminder_gdp_asia.csv", index_col="country")
plt.scatter(x=asia.min(), y=asia.max())

Room 4: plt.scatter(x = asia.T.min(), y = asia.T.max())
plt.xlabel("minimum GDP")
plt.ylabel("maximum GDP")


### Fill in the Blanks

Fill in the blanks so that the program below produces the output shown.

~~~
values = ____
values.____(1)
values.____(3)
values.____(5)
print('first time:', values)
values = values[____]
print('second time:', values)
~~~

~~~
first time: [1, 3, 5]
second time: [3, 5]
~~~

 #### Stepping Through a List

What does the following program print?

~~~
element = 'fluorine'
print(element[::2])
print(element[::-1])
~~~

If we write a slice as `low:high:stride`, what does `stride` do?


### Breakout exercises loops

#### Reversing a String

Fill in the blanks in the program below so that it prints "nit"
(the reverse of the original character string "tin").

~~~
original = "tin"
result = ____
for char in original:
    result = ____
print(result)
~~~

Room 1: original = "tin"
result = ""
for char in original:
    result = char + result
print(result)

Room 2: original = "tin"
result = ""
for char in original:
    result = char + result
print(result)

Room 3: first gap: "" | second gap: char + result

Room 4: original = "tin"
result = original
for char in original:
    result = original[::-1]
print(result)

#### Practice Accumulating

Fill in the blanks in each of the programs below
to produce the indicated result.

~~~
# Total length of the strings in the list: ["red", "green", "blue"] => 12
total = 0
for word in ["red", "green", "blue"]:
       ____ = ____ + len(word)
print(total)
~~~

~~~
# List of word lengths: ["red", "green", "blue"] => [3, 5, 4]
lengths = ____
for word in ["red", "green", "blue"]:
    lengths.____(____)
print(lengths)
~~~

~~~
# Concatenate all words: ["red", "green", "blue"] => "redgreenblue"
words = ["red", "green", "blue"]
result = ____
for ____ in ____:
    ____
print(result)
~~~

Room 1: 
total | total
[0,0,0] |

total = 0
for word in ["red", "green", "blue"]:
       total = total + len(word)
print(total)

----- 

lengths = []
for word in ["red", "green", "blue"]:
    lengths.append(len(word))
print(lengths)




Room 2: # Total length of the strings in the list: ["red", "green", "blue"] => 12
total = 0
for word in ["red", "green", "blue"]:
    total = total + len(word)
print(total)

 # List of word lengths: ["red", "green", "blue"] => [3, 5, 4]
lengths = []
for word in ["red", "green", "blue"]:
    lengths.append(len(word))
print(lengths)

Room 3: original = "tin"
result = ""
for char in original:
    result = char + result
print(result)

List of word lengths: ["red", "green", "blue"] => [3, 5, 4]
lengths = []
for word in ["red", "green", "blue"]:
    lengths.append(len(word))
print(lengths)

Total length of the strings in the list: ["red", "green", "blue"] => 12
total = 0
for word in ["red", "green", "blue"]:
       total = total + len(word)
print(total)
~~~

~~~
# List of word lengths: ["red", "green", "blue"] => [3, 5, 4]
lengths = []
for word in ["red", "green", "blue"]:
    lengths.append(len(word))
print(lengths)
~~~

~~~
# Concatenate all words: ["red", "green", "blue"] => "redgreenblue"
words = ["red", "green", "blue"]
result = ""
for word in words:
    result = result + word
print(result)

Room 4: 
|total = 0
for word in ["red", "green", "blue"]:
    total = total + len(word)
print(total)
|
lengths = []
for word in ["red", "green", "blue"]:
    lengths.append(len(word))
print(lengths)
|
words = ["red", "green", "blue"]
result = ""
for word in words:
    result = result + word
print(result)

# Tracing execution

What does this program print? Try to guess first before running the code.

~~~
pressure = 71.9
if pressure > 50.0:
    pressure = 25.0
elif pressure <= 50.0:
    pressure = 0.0
print(pressure)
~~~


### Trimming Values

Fill in the blanks so that this program creates a new list
containing zeroes where the original list's values were negative
and ones where the original list's values were positive.


~~~
original = [-1.5, 0.2, 0.4, 0.0, -1.3, 0.4]
result = ____
for value in original:
    if ____:
         result.append(0)
    else:
        ____
print(result)
~~~

~~~
[0, 1, 1, 1, 0, 1]
~~~


## Feedback

#### Tops(what you liked)
* You are all working so well together!!! 
* It's easy and comfortable to ask questions and interact with instructors as well as participants
* nice session and having more breakout rooms was useful to discuss ideas. Thanks, I learned a lot!
* very clear with good examples
* I like the coding together approach!
* Power of Python data tools
#### Tips (what we can improve)
* ;-) don't restrain Jens' jokes too much. <not written by Jens>
* May be seperate the Unix/ Git part from the Pythonpart 
* Would be nice to find a better alternative to the shared document. It becomeas way to caotic at times. (+1)
* may be git should have been after the python, because we all code with examples?
* Separate workshop on the Python data tools

## 📚 Resources
[Notebooks Day 3 and 4](https://github.com/esciencecenter-digital-skills/2021-09-06-swc-gapminder-python-nlesc/tree/gh-pages/files/notebooks)
[Lesson Material Python](http://swcarpentry.github.io/python-novice-gapminder/)

[matplotlib styles](https://matplotlib.org/stable/gallery/style_sheets/style_sheets_reference.html )
[matplotlib gallery](https://matplotlib.org/stable/gallery/index.html)
zoom link: https://us02web.zoom.us/j/88319621156?pwd=aWYyV29vK3JzS29Lb3AvbUJRUmRPdz09#success
[post-workshop survey](https://carpentries.typeform.com/to/UgVdRQ?slug=2021-09-06-swc-gapminder-python-nlesc)