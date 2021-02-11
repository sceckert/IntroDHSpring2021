# Introduction to the Command Line
Thursday, Feb 11, 2021

## Agenda

- Paul Bloomberg, "What is Code?""
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


In the [*Programming Historian* tutorial](https://programminghistorian.org/en/lessons/intro-to-bash) you learned the following commands.

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

---

### Creating text files and directories

1. Open up your terminal
2. Use `pwd` to tell us where we are
3. Use `mkdir` to create a directory (a folder) called "practice" inside of a directory called "workspace"
4. `cd` into that directory.
5. Use a new command, called **`touch`** to create a new file called greetings.txt in workspace
` touch ../an_empty_file.txt` 
6. Use `echo` and `>` to create a text file: 
``` 
echo """
Hello! 
Hi!
Hey!
Greetings, Intro DH!
""" > greetings.txt
````
7. `cat` our file to check inside
8. Now try 
``` 
echo """
Hello, again! 
Hi, again!
Hey, again!
Greetings (again) Intro DH!
""" >> greetings.txt
````
9. Check your file again with `cat greetings.txt`  What do we notice?
10. List the files we have in this directory using `ls`

---



### Working with files and texts ##

All Unix commands have **a syntax: transitive verb -> adverb ->  object**

1. Type `head -1 greetings.txt`  
	- *For Windows*, type `gc greetings.txt -head 1`
2. This command can be roughly parsed as "show me" (`head`) only the first line (`-1`) of my file "greetings.txt" (`greetings.txt`)


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

### Analyzing text files

#### Searching inside a text file (For Macs)###


**`grep "search term" [filename]`**: allows you to search for a `"search term"` in a file output lines that match a search term or pattern

1. Type `grep "Intro DH" greetings.txt`
2. Type `grep "Intro DH" -n greetings.txt`
	- The `-n` flag is one of many flags we can use to soup up our search. Here, this outputs the corresponding line numbers
2. Now try `grep "Intro DH" -B 1 -A 1 -n --color greetings.txt`
	- What just happened?
	- The `-B`  and `-A` flags will give the number of lines before (-B) or after (-A). Here, we said to display one line before and one line after our search term. This gives us the context (the 2 lines around a term). The `--color` flag highlighted our search term or search phrase.

What if we wanted to search for more than one term?

 **`grep -f`** allows us to search patterns from a file 

1. Use `echo` to make a list of words
```
echo"""  
hi
hey
""" >> list_of_words.txt
```
2. `cat list_of_words.txt` to make sure our words are there
3. Now, let's use that list to look for only the lines that contain "hi" or "hey" in our greetings file 
`grep -f list_of_words.txt -n --color filename.txt`
	- What happened?
4. Let's try again, this time, telling our search to ignore cases `grep -f list_of_words.txt -n -i --color filename.txt` 



#### Searching inside a text file (For Windows)###

`gc [filename] | Select-String -Pattern "search term"`: takes the `gc` command and pipes it to a command called `Select-String`, which searches for lines that include the search term. 

1. Type `gc  greetings.txt | Select-String -Pattern "Intro DH"`
2. Type `gc  greetings.txt | Select-String -Pattern "Intro DH" -AllMatches` 
	- The `-AllMatches` flag is one of many flags we can use to soup up our search. This makes sure that we catch any instances where our search term appears twice on a line
2. Now try `gc  greetings.txt | Select-String -Pattern "Intro DH" -Context 1,1` 
	- What just happened?
	- The `-Context [number, number]` flag will give the number of lines before and after the line with the search term. Here, we said to display one line before and one line after our search term. This gives us the context (the 2 lines around a term). 

What if we wanted to search for more than one term?

`gc [filename ]| Select-String -Pattern` can take a file as an input!

1. Use `echo` to make a list of words
```
echo"""  
hi
hey
""" >> list_of_words.txt
```
2. `cat list_of_words.txt` to make sure our words are there
3. Now, let's use that list to look for only the lines that contain "hi" or "hey" in our greetings file (we're not going to look for the contextual lines) `gc greetings.txt | Select-String -Pattern list_of_words.txt -AllMatches`:
4. Let's try again, this time, let's tell our search to be case sensitive `gc  greetings.txt | Select-String -Pattern "Intro DH" -AllMatches -caseSensitive`
	- What happened?



---

### Pipes (`|`),  Wildcards (`*`), and Redirects (`>`)

The command `|` is a pipe. It  takes the **output** of one command and passes it on as the input of another. It can be used to string together a series of commands.

#### For Macs:

1. Try `grep "Hello" greetings.txt  | wc -w`

The character **`*`** is a wildcard. It tells the program to search for all file paths in the current working directory.

2. Try `grep "Hello" *` 

We've already seen the redirect (`>`) and append (`>>`) characters. 

- The redirect command `>` takes the output of a command and puts it in a file. It an be used in conjunction with other commands, like `echo`, to take an input and write it to file. Eg `echo "Here is some text" > filename.txt` will create a new file called "filename" containing the enclosed phrase, or **overwrite** an existing file.
- The append command `>>` can be used in conjunction with other commands, like `echo`, to take an input and append it to a file. Eg `echo "Here is some text" >> filename.txt` will add the text "Here is some text" to the file filename.txt, or create a new file, if it does not already exist.

#### For Windows:

1. Try `grep "Hello" greetings.txt  | wc -w`

The character **`*`** is a wildcard. It tells the program to search for all file paths in the current working directory.

2. Try `grep "Hello" *` 


We've already seen the redirect (`>`) and append (`>>`) characters. 

- The redirect command `>` takes the output of a command and puts it in a file. It an be used in conjunction with other commands, like `echo`, to take an input and write it to file. Eg `echo "Here is some text" > filename.txt` will create a new file called "filename" containing the enclosed phrase, or **overwrite** an existing file.
- The append command `>>` can be used in conjunction with other commands, like `echo`, to take an input and append it to a file. Eg `echo "Here is some text" >> filename.txt` will add the text "Here is some text" to the file filename.txt, or create a new file, if it does not already exist.

---

## Any questions??

--
## In-Class Exercises

Open the [in-class exercises](https://github.com/sceckert/IntroDHSpring2021/blob/main/_week2/in-class-exercises.md) and work through them with your partner.