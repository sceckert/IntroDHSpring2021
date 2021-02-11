# Cheatsheet for Command Line Basics 



***Always remember to name your files and directories in a way that does not include white-spaces or special characters!***

***When in doubt, double-check your spelling!***

- [Command Line Cheatsheet for Mac/Linux](#for-maclinux)
- [Command Line Cheatsheet for Windows](#for-windows)


## For Mac/Linux

### Getting oriented

`pwd`:  path of working directory. This is the "tell me what folder I am in right now" 

`cd [filepath]`: change directory, move into the folder called "filepath" 

`cd ..`: change directory by moving up one level in the folder structure to a parent directory

`cd [filepath]` change directory to that one

`ls`: list the files and folders in your current directory

`man [commandname]`: manual. This is the help function. Type man command and it will tell you what that command does

### Making and viewing files and directories

`touch [filename]`: create a file

`echo "Some text here"`: prints the enclosed phrase. The `echo` command be used to display text with line breaks if you use three sets of quotation marks, like `echo """
Item 1
Item 2
Some additional text
"""`

`mkdir [directoryname]`: make a director called "directory-name"

`cp [original-filename] [copied-filename]`: copy file

`rm [filename]`: remove file:

`mv [original-filename] [new-filename]`: move or rename a file or folder

`cat [filename]`: show all the contents of a file, eg cat filename

`less [filename]`: show a snippet of a file that allows you to scroll through

`head[filename]`: shows you the first 10 lines. Can be used with a flag and a number to show the first however many lines (eg `head -50 [filename]` to show the first 50 lines)

`tail`: shows you the last 10 lines. Can be used with a flag and a number to show the last however many lines (eg `tail -50 [filename]`)

### Analyzing text files

`wc -w -l [filename]` : outputs the word and line count of a file. The command `wc` can be used the flag `-w` to output the workout, or with the flag `-l` to output the line count. (It can also output the character count with `-m`  and the byte count with `-c`).

`grep “search term” [filename] or [filepath]` searches for lines that include the search term in the file. 
Can be used with the flag following flags: `-n` gives the corresponding line numbers, `-f` searches for a pattern by reading in a file, `-A [number]` prints the number of lines of context after the match, `-B [number]` prints the number of lines of context after a match, `-i` ignores case, `-r` recursively search subdirectories, or `--color`  to highlight the search term. For instance, `grep -n "search term" [filename]` will output the lines that include the search term, along with the corresponding line numbers.

### Operators for chaining commands together

`*`  = wildcard. Can be used to search all existing files in a specified directory, or to replace part of a search query. Eg `*.txt` says look for all files that end in .txt file extension.

`|` : The pipe command takes the **output** of one command and passes it on as the input of another. It can be used to string together a series of commands.

`> [filename]` (redirect). The redirect command takes the output of a command and puts it in a file. It an be used in conjunction with other commands, like `echo`, to take an input and write it to file. Eg `echo "Here is some text" > filename.txt` will create a new file called "filename" containing the enclosed phrase, or **overwrite** an existing file.

`>> [filename]`  (redirect and append): The append command can be used in conjunction with other commands, like `echo`, to take an input and append it to a file. Eg `echo "Here is some text" >> filename.txt` will add the text "Here is some text" to the file filename.txt, or create a new file, if it does not already exist.

### SHORTCUTS

`Tab` Auto-complete files and folder names

`Up Arrow`:  Lets you scroll up through your previous commands

`:q` Exit

`CTRL + C`: kill the current process


##  FOR WINDOWS

### Getting oriented

`pwd`:  path of working directory. This is the "tell me what folder I am in right now" 

`cd [filepath]`: change directory, move into the folder called "filepath" 

`cd ..`: change directory by moving up one level in the folder structure to a parent directory

`ls`: list the files and folders in your current directory

`help [commandname]`: manual. This is the help function. Type `help` and the name of the command and it will tell you what that command does

### Making and viewing files and directories

`ni [filename]`: make a file called "file-name"

`echo "Some text here"`: prints the enclosed phrase. The `echo` command be used to display text with line breaks if you use three sets of quotation marks, like `echo """
Item 1
Item 2
Some additional text
"""`

`mkdir [directoryname]`: make a director called "directory-name"

`cp [original-filename] [copied-filename]`: copy file

`rm [filename]`: remove file:

`move [original-filename] [new-filename]`: move or rename a file or folder

`cat [filename]`: show all the contents of a file, eg cat filename

`more [filename]`: show a snippet of a file that allows you to scroll through

`gc [filename] -head 10`:  `gc` stands for "get content". This command shows you the first 10 lines. Can be used with a flag and a number  to show the first however many lines (eg `gc [filename] -head 50`, which shows the first 50 lines)

`gc [filename] -tail 10`: shows you the last 10 lines. Can be used with a flag and a number  to show the last however many lines (eg `gc [filename] -tail 50`, which shows the last 50 lines)

### Analyzing text files

`gc [filename] | Measure-Object -Word –Line`  takes the `gc` command and pipes it to another command called `Measure-Object`, which outputs the word and line count of a file. The `-Word` flag outputs the number of words in the file, the `-Line` flag outputs the number of lines.

`gc [filename] | Select-String -Pattern "search term"`: takes the `gc` command and pipes it to a command called `Select-String`, which searches for lines that include the search term. Matches are not case sensitive by default. This command can be used with the following flags: `-Pattern "search term"` or `-Pattern [file-with-list-of-search-terms]` will allow you to search for a term, or load a separate file with a list of words to search for, `-AllMatches` highlights all search terms, `-caseSensitive` makes your search case sensitive, the `-Context [number, number]` flag allows you to the number of lines **before**  and **after** the line with your matching search term --- eg `gc [filename] | Select-String -Pattern "search term" -Context 1,1` will search a filename for your search term and return the lines before and after it. 

`Select-String -Path [filepath] -Pattern "search term"`: This is another way to use the `Seelct-String` command. You can `-Path` flag and the wildcard character `*` to search all files in a specified directory, eg; `Select-String -Path .\*  -Pattern "search term"` will search all files

### Operators for chaining commands together

`|` : The pipe command takes the **output** of one command and passes it on as the input of another. It can be used to string together a series of commands.

`> [filename]` (redirect). The redirect command takes the output of a command and puts it in a file. It an be used in conjunction with other commands, like `echo`, to take an input and write it to file. Eg `echo "Here is some text" > filename.txt` will create a new file called "filename" containing the enclosed phrase, or **overwrite** an existing file.

`>> [filename]`  (redirect and append): The append command can be used in conjunction with other commands, like `echo`, to take an input and append it to a file. Eg `echo "Here is some text" >> filename.txt` will add the text "Here is some text" to the file filename.txt, or create a new file, if it does not already exist.

`*`  = wildcard. Can be used to search all existing files in a specified directory, or to replace part of a search query. Eg `*.txt` says look for all files that end in .txt file extension.

### SHORTCUTS

`Tab` Auto-complete files and folder names

`Up Arrow`:  Lets you scroll up through your previous commands

`exit` Exit

`CTRL + C`: kill the current process