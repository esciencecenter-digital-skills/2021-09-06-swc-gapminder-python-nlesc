![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document Day 1

2021-09-06 Software Carpentry with Python.

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.
For help with markdown press the little question mark (?) in the white top bar.



----------------------------------------------------------------------------

This is the Document for today: [link](https://hackmd.io/d87-fmTTSlqje0w8q2CbGA)

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

* [shell-lesson-data.zip for shell lesson](https://swcarpentry.github.io/shell-novice/data/shell-lesson-data.zip )
* [python-novice-gapminder.zip for Python lesson](http://swcarpentry.github.io/python-novice-gapminder/files/python-novice-gapminder-data.zip)

## 👩‍🏫👩‍💻🎓 Instructors

Hanno Spreeuw (Monday), Jens Wehner (Tuesday), Dafne van Kuppevelt (Wednesday, Thursday)

## 🧑‍🙋 Helpers

Jaro Camphuijsen, Lieke de Boer  

## 👩‍💻👩‍💼👨‍🔬🧑‍🔬🧑‍🚀🧙‍♂️🔧 Roll Call

Name / pronouns (optional) / job / social media (twitter, github, ...) / interest / city

(Deleted)

## 🗓️ Agenda
Day 1, Mo Sept 6th
09:00	Welcome and icebreaker
09:15	Automating Tasks with the Unix Shell
10:15	Break
10:30	Automating Tasks with the Unix Shell (Continued)
11:30	Break
11:45	Automating Tasks with the Unix Shell (Continued)
12:45	Wrap-up
13:00	END

## 🧠 Collaborative Notes

### icebreaker: If you could eat only one dish for breakfast for the rest of your life, what would it be?
(Deleted)

### Feedback
#### Top (what went well):
* I like that I could learn new details about some things that I already knew a bit from
* liked the session. I am new to this but catching up
* very clear, speed is ok, on interuption, new learining
* Clearly explained, especially for dummies, how to install and download files is also very clear
* Exercices are nice, speed is too slow
* Learned new tricks in bash good to see different options (subcommands) and try them with exercises
* The chat Q&A worked really well!
* Nice interactive questions and exercises
* Nice set of example material that gives teh opportunity to try out things on our own after the course
* clearly explained! thanks
* very live exercises!
* 

#### Tip (what can be improved):
*     Can you make the exercises available?
* A notebook with explanations, examples and excercises would be very nice
* The The The The
* If instrctor can share the commands shown in class
* Zoom is better than Eventbrite
* it would nice to have homeworks? so whoever that wants to practice can do it independently :) It would be nice also to have a "book" so we can review things
* early on you describe the directory structure as a tree, maybe give a visual explanation immediately, because it may be rather vague without something like that
* In giving the answers to excercises, sometimes it is too easy to see what others have already come up with, meaning you really have to force yourself to not take the easy way (just glancing at it is already a bit too easy)
* Course speed a bit fast esp. if one tries to take notes and test the code in the terminal at the same time. Maybe giving some material to follow would be helpful
* 
* 

## 🔧 Exercises

#### Can you open the shell?


#### a) What does `ls -l` do? And `ls -lh`?


#### c)Starting from /Users/amanda/data, which of the following commands could Amanda use to navigate to her home directory, which is /Users/amanda?

    cd .
    cd /
    cd /home/amanda
    cd ../..
    cd ~
    cd home
    cd ~/data/..
    cd
    cd ..
 

#### d) Using the filesystem diagram below, if pwd displays /Users/thing, what will ls -F ../backup display?

    1) ../backup: No such file or directory
    2) 2012-12-01 2013-01-08 2013-01-27
    3) 2012-12-01/ 2013-01-08/ 2013-01-27/
    4) original/ pnas_final/ pnas_sub/


```
Users
│
└───thing
│       │   
│       └───backup
│             │  
│             └───2012-12-01
│             │ 
│             └───2013-01-08
│             │
│             └───2013-01-27
│   
└─backup
     │  
     └───original
     │ 
     └───pnas_final
     │
     └───pnas_sub
```


#### g) After running the following commands, Jamie realizes that she put the files sucrose.dat and maltose.dat into the wrong folder. The files should have been placed in the raw folder.
```
$ ls -F
 analyzed/ raw/
$ ls -F analyzed
fructose.dat glucose.dat maltose.dat sucrose.dat
$ cd analyzed
```
Fill in the blanks to move these files to the raw/ folder (i.e. the one she forgot to put them in)
```
mv sucrose.dat maltose.dat ____/____
```



#### h) Suppose that you created a plain-text file in your current directory to contain a list of the statistical tests you will need to do to analyze your data, and named it: statstics.txt

After creating and saving this file you realize you misspelled the filename! You want to correct the mistake, which of the following commands could you use to do so?
```
1) cp statstics.txt statistics.txt
2) mv statstics.txt statistics.txt
3) mv statstics.txt .
4) cp statstics.txt .
```


#### o) Breakout rooms
You’re starting a new experiment and would like to duplicate the directory structure from your previous experiment so you can add new data.

Assume that the previous experiment is in a folder called ‘2016-05-18’, which contains a data folder that in turn contains folders named raw and processed that contain data files. The goal is to copy the folder structure of the 2016-05-18-data folder into a folder called 2016-05-20 so that your final directory structure looks like this:
```
2016-05-20/
└── data
    ├── processed
    └── raw
```
Which of the following set of commands would achieve this objective? What would the other commands do?
```
$ mkdir 2016-05-20
$ mkdir 2016-05-20/data
$ mkdir 2016-05-20/data/processed
$ mkdir 2016-05-20/data/raw
```
```
$ mkdir 2016-05-20
$ cd 2016-05-20
$ mkdir data
$ cd data
$ mkdir raw processed
```
```
$ mkdir 2016-05-20/data/raw
$ mkdir 2016-05-20/data/processed
```
```
$ mkdir -p 2016-05-20/data/raw
$ mkdir -p 2016-05-20/data/processed
```
```
$ mkdir 2016-05-20
$ cd 2016-05-20
$ mkdir data
$ mkdir raw processed
```

Please put your group answers in the proper line:
* Breakout room nr 1: Options 1,2,4 work, 3 gives an error because 2016-05-20 doesn't exist yet, 5 puts raw and processed on the same level as data
* Breakout room nr 2: Options 1, 2 and 4 works but not 3 or 5
* Breakout room nr 3: option 2, I guess?
* Breakout room nr 4: $ mkdir -p 2016-05-20/data/raw ; $ mkdir -p 2016-05-20/data/processed (most efficient, 1 and 2 also work)
* Breakout room nr 5 | Options 1, 2 and 4 (the most efficient way) work.



#### s) In our current directory, we want to find the 3 files which have the least number of lines. Which command listed below would work?
```
1) wc -l * > sort -n > head -n 3
2) wc -l * | sort -n | head -n 1-3
3) wc -l * | head -n 3 | sort -n
4) wc -l * | sort -n | head -n 3
```


#### t) A file called animals.txt (in the shell-lesson-data/data folder) contains the following data:
```
2012-11-05,deer
2012-11-05,rabbit
2012-11-05,raccoon
2012-11-06,rabbit
2012-11-06,deer
2012-11-06,fox
2012-11-07,rabbit
2012-11-07,bear
```
What text passes through each of the pipes and the final redirect in the pipeline below?
```
$ cat animals.txt | head -n 5 | tail -n 3 | sort -r > final.txt
```
Hint: build the pipeline up one command at a time to test your understanding



#### u) For the file animals.txt from the previous exercise, consider the following command:
```
$ cut -d , -f 2 animals.txt
```
The `cut` command is used to remove or ‘cut out’ certain sections of each line in the file, and `cut` expects the lines to be separated into columns by a Tab character. A character used in this way is a called a delimiter. In the example above we use the `-d` option to specify the comma as our delimiter character. We have also used the `-f` option to specify that we want to extract the second field (column). This gives the following output:
```
deer
rabbit
raccoon
rabbit
deer
fox
rabbit
bear
```
The `uniq` command filters out adjacent matching lines in a file. How could you extend this pipeline (using `uniq` and another command) to find out what animals the file contains (without any duplicates in their names)?




#### v) The file animals.txt contains 8 lines of data formatted as follows:
```
2012-11-05,deer
2012-11-05,rabbit
2012-11-05,raccoon
2012-11-06,rabbit
...
```
The uniq command has a -c option which gives a count of the number of times a line occurs in its input. Assuming your current directory is shell-lesson-data/data/, what command would you use to produce a table that shows the total count of each type of animal in the file?
```
1) sort animals.txt | uniq -c
2) sort -t, -k2,2 animals.txt | uniq -c
3) cut -d, -f 2 animals.txt | uniq -c
4) cut -d, -f 2 animals.txt | sort | uniq -c
5) cut -d, -f 2 animals.txt | sort | uniq -c | wc -l
```





### Command log / Notes

#### Navigating the shell
Commands to show information about your location (which we call "working directory") are `pwd` for "print working directory" and `ls` for "list".
```bash
pwd # tells you where you are
ls  #shows the contents of your directory
ls -F #same as previous but with information about type of content
ls --help # shows you all the option of the command "ls"
man ls # similar to "ls --help"
```
```bash
ls -t #list the files in the directory sorted by modification time
ls -r #reverses the order in which the files in a directory are sorted
```


```bash
ls -l # gives you even more information about the contents of your current working directory
```
This returns a long list with information about the permissions, owner, size and last edit date of the files.

You can also add a directory path to the command `ls`. 

```bash
ls /Users/Hanno/Desktop #shows the content of "/Users/Hanno/Desktop"
```


The command that is used to go to a different directory is `cd` which is short for "change directory". 

```bash
cd #without a specified directory this will bring you back to your home directory
cd ~ # also brings you to your home directory
cd - # brings you to the previous location, where you were before you used "cd" the last time
cd . # brings you to the current working directory, so does not do anything 
cd .. # brings you to the directory above your current working directory
cd Desktop #brings you to the directory called "Desktop" if it lives in your current working directory
```

If you start typing the first characters of a sub-directory after `cd` you can use the TAB key to automatically complete the sub-directory name. 

You can also combine directory and sub-directory names to quickly navigate.

```bash
cd ../creatures
```
is the same as:
```bash
cd ..
cd creatures
```

The following command will bring you to the "shell-lesson-data" directory in your "Desktop" directory which lives in your home directory
```bash
cd ~/Desktop/shell-lesson-data 
```


#### Working with files and directories

Let’s go back to our "shell-lesson-data" directory on the Desktop and make a new directory

```bash
pwd 
```
```
/Users/Hanno/Desktop/shell-lesson-data
```

We can make a new directory with the command `mkdir` which stands for "make directory"
```bash
mkdir Discovery_of_the_Higgs_boson
```

and another subdirectory in this newly created one

```bash
mkdir Discovery_of_the_Higgs_boson/first_measurements
```
If the parent directory (Discovery_of_the_Higgs_boson) does not exist, it will raise an error.

We can do this in one go for a new project using the -p option. This creates any required parent directories without errors.

```bash
mkdir -p Discovery_of_the_dark_matter/first_measurements
```
Let's navigate into this new subdirectory
```bash
cd Discovery_of_the_dark_matter/first_measurements
```
here we can create a new file by opening the text editor called "nano" and add a non existing file name to the command:

```bash
nano first_thoughts.txt
```

Here we can type any contents and then exit (with saving) using CMD + X.

Another way to create new files is using the `touch` command:

```bash
touch second_thoughts.txt
```
This creates an empty file.

If we now want to **copy** this file to another location we can use the command `cp` from "copy".
```bash
cp first_thoughts.txt ../../Discovery_of_the_Higgs_boson
```

In this way `cp` can only copy single files. We can use the -r option (from "recursive") to copy whole directories with their contents.

```bash
cd ../../Discovery_of_the_Higgs_boson
cp -r first_measurements second_measurements 
```


We can use the `rm` command (from "remove") to **remove** a file. 
:::info
BE CAREFUL!!! THERE IS NO WAY TO RECOVER YOUR FILE!!!
:::

```bash
rm first_thoughts.txt # removes the first_thoughts.txt file in the current working directory
```

Also `rm` has a -r option, to remove complete folders. Use this with much caution! You can destroy very important files without any warning!

```bash
rm -r second_measurements #will remove the complete "second_measurements" directory
```

The command to **move** a file to a different place in the file tree is `mv` from "move". but it can also be used to only change a file's name:

```bash
mv first_thoughts.txt first_considerations.txt # changes the name first_thoughts.txt file 
```

```bash
mv first_considerations.txt ../first_thoughts.txt  # moves the first_thoughts.txt file name to the parent directory 
```
We can also do operations on multiple files at once. We can make use of so called **wildcards**.
```bash
cd 
ls *.txt # shows all files that end with ".txt"
ls *Z.txt # shows all files that end with "Z.txt"
ls *[AB].txt # shows all files that end with "A.txt" or "B.txt"
touch d.txt # make a file that is called "d.txt."
ls ?.txt # show all files that have a name of only one character followed by ".txt"
```

\* is a wildcard, which matches zero or more characters. Let’s consider the shell-lesson-data/molecules directory: *.pdb matches ethane.pdb, propane.pdb, and every file that ends with ‘.pdb’. On the other hand, p*.pdb only matches pentane.pdb and propane.pdb, because the ‘p’ at the front only matches filenames that begin with the letter ‘p’.

? is also a wildcard, but it matches exactly one character. So ?ethane.pdb would match methane.pdb whereas *ethane.pdb matches both ethane.pdb, and methane.pdb.

Wildcards can be used in combination with each other e.g. `???ane.pdb` matches three characters followed by ane.pdb, giving cubane.pdb ethane.pdb octane.pdb.

#### Pipes and filters

Let's move back to the shell-lesson-data directory and go into the molecules sub-directory.

```bash=
cd ~/Desktop/shell-lesson-data
cd molecules/
ls
```

We now introduce a new command to count lines, words and characters in your files. We use `wc` for "word count":

```bash
wc * #shows a list of all files preceded with counts of the number of lines, words and characters respectively
```

Another useful command is `cat` (short for concatenate) can be used to show the contents of a file.

```bash
cat methane.txt
```

Now we will change where the output of the command will go with a `>` which redirects the output of the command on the left to a file that we specify on the right.

```bash
wc * > these_are_number_of_lines_words_and_characters_of_these_files.txt
```

Now the word count results are stored in a new file, that we can view with `cat`.

```bash
cat these_are_number_of_lines_words_and_characters_of_these_files.txt
```

Another useful command is `sort` which will do as the name suggests, sort the contents of its input. These kinds of commands are called **filters**, because they transform a stream of input into a stream of output. So if we run it on a file:

```bash
sort numbers.txt #sorts the lines of numbers.txt in alpha-numerical order, it will assume 2 is larger than 10 as it starts with a character that is higher (2 > 1) 
sort -n numbers #sorts the lines of numbers.txt in numerical order, so it understands 10 is larger than 2
```

Again we can redirect the output into a file instead of displaying in the terminal. 
```bash
sort -n numbers.txt > sorted_numbers.txt
```

Another way to manipulate where the output of a command goes is with `|` which is called a "pipe". It will take the output of what is on the left and use it as input for what is on the right.

```bash
sort -n numbers.txt | head -n 3
```
This will sort the contents of numbers.txt in numerical order and pass this as output to `head -n 3` which returns only the first three lines of this output.


Let us now investigate another dataset, which we will use to explore pipelines.
```bash
cd ../data
ls
cat animals.txt
```

We explore the behaviour of the following pipelines in **exercise t, u and v**:
```bash
cat animals.txt | head -n 5 | tail -n 3 | sort -r > final.txt
cut -d, -f 2 animals.txt | sort | uniq -c
```


## 📚 Resources
[How to customize your git-bash shell](https://blog.devgenius.io/how-to-customize-the-git-bash-shell-prompt-336f6aefcf3f)