![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document Day 2

2021-09-06 Software Carpentry with Python.

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: [link]([<url>](https://hackmd.io/d87-fmTTSlqje0w8q2CbGA))

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
Hennie Dolfsma / she, her / Library systems administrator / Amstelveen

(Deleted)

## 🗓️ Agenda
09:00	Welcome and icebreaker
09:15	Version Control with Git
10:15	Break
10:30	Version Control with Git (Continued)
11:30	Break
11:45	Version Control with Git (Continued)
12:45	Wrap-up
13:00	END

## 🧠 Collaborative Notes

### About automated version control
Version control systems do all of the following:
* make new folders
* add description to Readme
* copy to public repository
* retrieve version from the history
* collect changes

![](https://i.imgur.com/frZTUzL.png)

Vocabulary:
* A project folder we call a **repository**
* A incremented change to the file is called a **commit**
* If the repository lives only on your own system, it is called **local repository**
* If you upload your commit to the online server it is called **push**
* If you download it to your local system again from the server it is called **pull**
* Combining two different changes to the same repository is called **merge**
* The history of changes is called the **commit history**
* The network of commits and versions is called the **tree**
* A line of commits that have 

### Setting up git
Open up a shell (Terminal, Git Bash).
```bash
git #brings up the "help" information of git
git --version #brings up the version of git
```

We will start with configuring git to our personal needs.
```bash
git config --list #brings up all current configurations
git config --global user.name "myname" # set your user name to "myname"
git config --global user.email "name@domain.ext" #set your email to name@domain.ext
```

Since different operating systems use different characters for line endings, we need to tell git which one we use so it can combine different users with different operating systems. How this exactly works is beyond the scope of this lesson but type one of the following according to your own operating system:
```bash
git config --global core.autocrlf true #windows
git config --global core.autocrlf input #macOS and Linux
```

You can set the default text editor you would like git to use to write your commit messages (the message you pass to every commit to describe the changes).

```bash
git config --global core.editor "nano -w"
```

If you have an older version of git you want to set the following:
```bash
git config --global init.defaultBranch main
```

### Creating a repository
Let's move to our Desktop folder(`cd ~/Desktop`) and create a new directory called "planets".

```bash
mkdir planets
cd planets/
```

now we will ask the program "git" to initialize (`init`) a new repository in this directory. It will create a hidden folder called ".git" that you can view wiht `ls -a`. It is used by git to store your history of changes and some configuration files.
```bash
git init
ls
ls -a
```

We use the `checkout` command to navigate to our main branch. 
```bash
git checkout -b main
git status
```

### Tracking changes
We will create a file called mars, and add some content to it.

```bash
nano mars.txt
```
Type the following text, so it will be the contents of `mars.txt`:
```
Cold and dry, but everything is my favorite color
```

As before you can use `CMD+X` or `CTRL+X` to save and exit nano.

We will inspect the contents of the file and the status of our git repository
```bash
cat mars.txt #shows the contents of mars.txt
git status #inspect the status of our git repository
```

As suggested by `git status` we will use add the file to our so called **staged** files. These are the files that we intent to **commit** to the history.
```bash
git add mars.txt
git status
```

We see that the status has changed again, and now we will commit the changes to the history. This will make our changes definite so, from then one they will be stored in the commit history. 

```bash
git commit -m "Start notes on Mars as a base"
```

The option `-m` (for message) adds the commit message to the commit. It is good practice to add clear and descriptive commit messages so you can easily navigate through your history.

We can inspect the changes in the log

```bash
git log
```

Let's make another change to our file with nano (see above). Add the text:
```
The two moons may be a problem for Wolfram
```

Running `git status` now shows that our file mars.txt is "modified".

We can again add this change to our changes that we intend to commit: 

```bash
git add mars.txt
```

We can inspect the difference with the git command `diff` (for difference).

```bash
git diff mars.txt
```

Just like with the first change we have to commit this new change so it will be added to our commit history. Again use a clear and descriptive message:

```bash
git commit -m "Add concerns about effects of Mars' moons on Wolfman"
```

This two stage workflow of adding and committing makes sure we can check our changes and commit multiple changes to multiple files at once that have a logical consistency (this often happens if you write code).

![](https://i.imgur.com/Kkzy2hy.png)

For example we can create a second document about venus and add a change to our old file.

To do:
* Add a new file with some content called venus.txt using nano
* Add a new line to mars.txt using nano

We can now add both changes of both files at once: 
```bash
git add mars.txt venus.txt
```

or in two commands

```bash
git add mars.txt
git add venus.txt
```

And we can now make even more changes, create new files etc. and once we are ready to commit we add this commit to the repository:

```bash
git commit -m "Solving the problems of a base on Mars by considering a new base on Venus"
```

### Exploring History

We are in our planets repository `cd ~/Desktop/planets`
Let's make a new change to our mars.txt file, for example `Jeff Bezos can help us get there`.
Let's not add and commit for now.

We know how to investigate the history:
```bash
git log
git diff mars.txt
```
In general, `git diff` will compare the current state with the currently checked out state in the commit history, which is called **HEAD** *(this comes from old magnetic tapes, where the reading head goes past the magnetic ribbon, the position of the reading head is where we currently read out information)*.
Currently this is just our latest commit, but it can change as we will see in a minute. 

We can also be more specific by which version we want to compare our current changes with:

```bash
git diff HEAD mars.txt #only show difference of the file mars.txt
git diff HEAD #show difference in all tracked files
```

This will give the same output as when you leave out the `HEAD`. The real strength is that you can compare with commits before the current `HEAD` position by using `~`

```bash
git diff HEAD~1 mars.txt 
```
This will compare the current status of your file `mars.txt` with the status of the file after the commit before your last commit. `~2` will go another commit down the line. Check `git log` to see the thread of commits.

You can also select a specific commit by entering the uniquely asociated **hash** that you can find in `git log` instead of counting back from HEAD.

```bash
git diff f22b25e3233b4645dabd0d81e651fe074bd8e73b mars.txt
git diff f22b25e mars.txt #the first 7 digits also work
```

In a similar manner you can show the information about a certain commit:

```bash
git show f22b25e
git show HEAD~3
```

And you can change the position of HEAD (so where we watching and working at the moment) to a certain commit with:

```bash
git checkout f22b25e
git checkout HEAD~3
git checkout main 
```
This last command will change the status of all files (so also with changes that have not been committed yet) to the status of the top of the `main` branch.
Again this can also be done for specific files by adding the file name at the end of the command. it will only change the state of the specified file.

```bash
git checkout f22b25e mars.txt
```

We can also undo a previous commit, however since it is bad practice to erase history, we will just create a new commit that reverts the changes of another commit. There is a special command for that:

```bash
git revert f22b25e
```

In the following example we make two changes but only add one to the commit. 

```bash
echo "Venus is beautiful and full of love" > venus.txt
git add venus.txt
echo "Venus is too hot to be suitable as a base." >> venus.txt
git commit -m "Comment on Venus as unsuitable base"
```

We can see that there are still untracked changes
```bash
git status
git diff venus.txt
```

These last changes can be undone by checking out the HEAD position 
```bash
git checkout HEAD #for all files
git checkout HEAD venus.txt #for a specific file
cat venus.txt
git status
```

### Remotes in GitHub

GitHub is an online server to share and work together on git repositories. You can access it by going to www.github.com.

After signing in or signing up (please do so with the email address that you used to setup git), you can create a new remote repository by clicking the green button. It might look slightly different in your account due to user specific settings.  ![](https://i.imgur.com/YsKW3eX.png)

Name the repository "planets" and create the repository. If you create it as being completely empty, you will get instructions how to push a local repository. 

Since Jens added a license file, this information will not show, but we can still work with the remote repository with a little extra tweaking.


First we tell git to add our github url as the **remote** for our local repository and we give it the name "origin".
```bash
git remote add origin https://github.com/YourUsername/planets.git
git remote -v #this will give us information about the remote that we connected
```

To download changes (the license file we added) online into our local repository, we tell git to **pull** from the remote that we called "origin", and we want to get the branch called "main".
```bash
git pull origin main
```

This gives a problem since we added the License file in the remote repository and the local repository didn't know about that. The histories do not match because they both have a different starting point. To solve this problem we pass an extra option to the pull command, that tells git to merge the remote repository with our local repository without bothering about the different histories. 

```bash
git pull origin main --allow-unrelated-histories
```

:::warning
To avoid this behavior:
\
Either... 
Don't add any files to the remote repository when you create it (so no license file).
You can then right away start with pushing your local repository into the remote (See below)



\
Or... 

Do not do any work (create folders, files, content) locally and instead use 
```bash
git clone https://github.com/YourUsername/planets.git
```
to copy the remote repository to your local computer. This remote CAN contain any files (like a license). 
You do not have to initialize a local repository first, it will just copy the whole remote repository with all files necessary to git onto your computer. It will name the local directory like the remote repository and it will contain the hidden ".git" directory. 
:::

:::info
Since our log is starting to get long and complicated with several branches, we add some options to our log command:
```bash
git log --oneline --graph
```

The --oneline option gives you less information per commit, so it will fit your screen better for long histories. The --graph option gives some visual information about which commits are connected. They can be used individually as well. 
:::

#### Push local changes to the remote
To upload our local changes to the remote online repository we use the **push** command
```bash
git push origin main
```
This tells git to push the contents of our "main" branch to the remote which we called "origin".
It asks for you login details to github (username and password). 

:::info
A while ago GitHub changed to use two factor authentication and since that moment the password you use to access github in the browser will not work. Instead you have to set up a so called **personal access token**.

You can do so via this link (requires signing into github):
https://github.com/settings/tokens

Create a new token and set it up as you like:
![](https://i.imgur.com/i7yfliC.png)
The token will expire in 30 days, the discription makes it easier to find out what it can be used for. It needs at least full controll over the repositories in you github account, the rest of the scope can be left unticked.

This will show you a very long line of characters that you should store somewhere safe and not share with anyone. Be sure to copy it, once you click away the screen, it will be gone.
:::

Now use your github username together with the personal access token instead of the password you just created to perform the first push:

```bash
git push origin main
```

If all went well, you can now inspect the files via the browser in your remote repository.

Since the remote repository is public, other can now clone it and if they have the proper access rights, also push their changes to it. In this way you can work together.


## 🔧 Exercises

### Icebreaker: What is the best advice you ever got?
(Deleted)

### Question: 
You wrote some code and it worked and you want to share it with a colleague. What do you do (infrastructure-wise)? What did you do if something went wrong, e.g. with versions?


### Can you open Git?
Type in your shell: `git --version`


### Can you run Git status
Run `git status`. On which branch are you?


### Committing Changes to Git
Which command(s) below would save the changes of `myfile.txt` to my local Git repository?

1.`$ git commit -m "my recent changes"`
2. 
    `$ git init myfile.txt` 
    `$ git commit -m "my recent changes"`
3.
`$ git add myfile.txt`
`$ git commit -m "my recent changes"`

4.`git commit -m myfile.txt "my recent changes"`



### Committing Multiple Files

The staging area can hold changes from any number of files that you want to commit as a single snapshot.

1.    Add some text to `mars.txt` noting your decision to consider Venus as a base
2.    Create a new file `venus.txt` with your initial thoughts about Venus as a base for you and your friends
3.    Add changes from both files to the staging area, and commit those changes.


### `bio` Repository

*    Create a new Git repository on your computer called bio.
*    Write a three-line biography for yourself in a file called me.txt, commit your changes
*    Modify one line, add a fourth line
*    Display the differences between its updated state and its original state.


### Recovering Older versions of a File

Jennifer has made changes to the Python script that she has been working on for weeks, and the modifications she made this morning “broke” the script and it no longer runs. She has spent ~ 1hr trying to fix it, with no luck…

Luckily, she has been keeping track of her project’s versions using Git! Which commands below will let her recover the last committed version of her Python script called `data_cruncher.py`?

1.   `$ git checkout HEAD`
2.    `$ git checkout HEAD data_cruncher.py`
3.    `$ git checkout HEAD~1 data_cruncher.py`
4.    `$ git checkout <unique ID of last commit> data_cruncher.py`
5.   `$ Both 2 and 4`


### Reverting a Commit

Jennifer is collaborating with colleagues on her Python script. She realizes her last commit to the project’s repository contained an error, and wants to undo it. Jennifer wants to undo correctly so everyone in the project’s repository gets the correct change. The command `git revert [erroneous commit ID]` will create a new commit that reverses the erroneous commit.

The command `git revert` is different from `git checkout [commit ID]` because `git checkout` returns the files not yet committed within the local repository to a previous state, whereas `git revert` reverses changes committed to the local and project repositories.

Below are the right steps and explanations for Jennifer to use git revert, what is the missing command?

1.   ` ________ # Look at the git history of the project to find the commit ID`
2.    Copy the ID (the first few characters of the ID, e.g. 0b1d055).
3.    `git revert [commit ID]`
4.    Type in the new commit message.
5.    Save and close


### Understanding Workflow and History

What is the output of the last command in
```bash
$ cd planets
$ echo "Venus is beautiful and full of love" > venus.txt
$ git add venus.txt
$ echo "Venus is too hot to be suitable as a base" >> venus.txt
$ git commit -m "Comment on Venus as an unsuitable base"
$ git checkout HEAD venus.txt
$ cat venus.txt #this will print the contents of venus.txt to the screen
```

1.Venus is too hot to be suitable as a base
2.Venus is beautiful and full of love
3.Venus is beautiful and full of love
  Venus is too hot to be suitable as a base
4.Error because you have changed venus.txt without committing the changes


### Can you login to github.com ?


### Did you manage to push changes to github?
With the command `git push --set-upstream origin main`



### Did you manage to install anaconda and open jupyter lab?



## Feedback

### Tops (what you liked)

* nice step-by-step guide that introduced concepts gradually (+1)
* i enjoyed the mode on instruction made it easy to follow
* nicely incremental 
* Very clear guide
* Nice problem solving!
* had a excellent learning session. Thank you.
*
*


### Tipps (what we can improve)

* maybe not for the course itself but as suppl. material, is there some info you could add on the different hosting systems (github, gitlab) to see what options are out there? Esp. info on  sharing with groups outside of your institute/data privacy/managing for larger groups would be interesting.
* a bit slow
* I think the content was sufficient for one day, but I would like more information. Maybe suppl. material as mentioned above or an extra day for this part would be nice.
* I felt today a a bit fast. I request if you could share the codes from the instructor (from git bash).
* if the codes can be shared with us, it would be easier for us to follow. because some time I was stucked somewhere, after I solved the problem, I found I missed part
*
*
*
*

## 📚 Resources
[Course material of yesterday](http://swcarpentry.github.io/shell-novice/)
[Courses by the eScience Center](https://esciencecenter-digital-skills.github.io/)