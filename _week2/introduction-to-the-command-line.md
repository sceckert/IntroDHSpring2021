# Introduction to the Command Line
Thursday, Feb 11, 2021

## Agenda

- What is Code?
- What is the Command Line?
- Practicing the command line
	- Creating text files
	- Working with text files
	- Analyzing text files
- In-Class Exercises 

---

## What is the Command Line? ## 

AKA bash, terminal, shell

- A UNIX-based, text-based way of interacting with your computer!
- It's written in *plain text*, which makes the commands human readable.
- The command line is one lightweight way of learning how to interact with files, run scripts, and practice working with the syntax of programming languages.


## Let's practice command line commands!


In the [*Programming Historian* tutorial]() you learned the following commands.

FOR MACS: 
- `pwd`:  path of working directory. This is the "tell me what folder I am in right now" 
- `cd [filepath]`: change directory, move into the folder called "filepath" 
- `cd ..`: change directory by moving up one level in the folder structure to a parent directory
- `ls`: list the files and folders in your current directory 
- `mkdir [directoryname]`: make a director called "directory-name"
- `man [commandname]`: manual. This is the help function. Type man command and it will tell you what that command does
- `cp [original-filename] [copied-filename]`: copy file
- `rm [filename]`: remove file:
- `mv [original-filename] [new-filename]`: move or rename a file or folder
- `cat [filename]`: show all the contents of a file, eg cat filename
- `head[filename]`: shows you the first 10 lines. Can be used with a flag and a number to show the first however many lines (eg `head -50 [filename]` to show the first 50 lines)
- `tail`: shows you the last 10 lines. Can be used with a flag and a number to show the last however many lines (eg `tail -50 [filename]`)


FOR WINDOWS

- `gc [filename] -head 10`: shows you the first 10 lines. Can be used with a flag and a number  to show the first however many lines (eg `gc [filename] -head 50`, which shows the first 50 lines)
- `gc [filename] -tail 10`: shows you the last 10 lines. Can be used with a flag and a number  to show the last however many lines (eg `gc [filename] -tail 50`, which shows the last 50 lines)

### Creating files and directories

1. Open up your terminal
2. Use `pwd` to tell us where we are
2. Use `mkdir` to create a directory (a folder) called "practice" inside of a directory called "workspace"
3. `cd` into that directory.
4. Use a new command, called **`touch`** to create a new file called greetings.txt in workspace
` touch ../a_nice_file.txt` 
5. Use `echo` and `>` to create a text file: 
``` 
echo """
Hello! 
Hi!
Greetings, Intro DH!
""" > greetings.txt
````
6. `cat` our file to check inside
7. Now try 
``` 
echo """
Hello! 
Hi!
Greetings, Intro DH!
""" >> greetings.txt
````
8. Check your file again. What do we notice?
9. List the files we have using `ls`

---



### Working with files and texts ##

All Unix command have **a syntax: transitive verb > adverb >  object**

1. Try  `head -1 greetings.txt` can be roughly parsed as "show me" (`head`) only the first line (`-1`) of my file "greetings.txt" (`greetings.txt`)


#### Count words, lines, and characters (For Macs) 

 `wc` is a command that allows you to count words and lines in a text file. It can be used with flags.

1. Use  `wc -w greetings.txt` to count the number of words in `greetings.txt`.
	-  In the statement above, `wc` is our verb, while the flag `-w` is our adverb and `greetings.txt`  is the object
2. Use `wc -l` to count the number of lines in `greetings.txt`


####  Count words, lines, and characters (For Windows)

The command `gc` used with the command `Measure-Object` allows you to count words and lines in a text file (We'll explain that `|` in a minute!)

1. Use `gc greetings.txt | Measure-Object -Word` to count the number of words in `greetings.txt`
2. Now use the `-Line` flag with the command above count the number of lines in `greetings.txt`

---

### Searching inside a text file ###


`grep -wc "search term" filename.txt`: allows you to search for and output lines that match a search term or pattern

`grep -wc "search term" filename.txt`

Combine with the -B and -A flags will give the number of lines before (-B) or after (-A). This gives us the context (the 4 lines around a term):

`grep "search term" -B 2 -A 2 -n --color filename.txt`


 `grep -f` will obtain patterns from a file 

So if you had a text file with a list of words to look for, you could use that:

`grep -f listOfWords.txt -B 2 -A 2 -n --color filename.txt`

#### Pipes and Wildcards

The command `|` is a pipe. It  takes the **output** of one command and passes it on as the input of another. It can be used to string together a series of commands.

For Macs:

1. Try `grep "Hello" greetings.txt  | wc -w`

The character **`*`** is a wildcard. It tells the program to search for all file paths in the current working directory.

2. Try `grep "Hello" *` 

For Windows:

1. Try `grep "Hello" greetings.txt  | wc -w`

The character **`*`** is a wildcard. It tells the program to search for all file paths in the current working directory.

2. Try `grep "Hello" *` 


## Any questions??

## In-Class Exercises

Open the [in-class exercises](https://github.com/sceckert/IntroDHSpring2021/blob/main/_week2/in-class-exercises.md) and work through them with your partner.