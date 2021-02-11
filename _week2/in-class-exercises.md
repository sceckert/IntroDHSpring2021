# In-Class Exercises

Thursday, Feb 11, 2021


Guidelines for pair-work:

- The important thing is not to finish first, but to work together. 
- Take turns with each step of the exercise.
- If you know the answer, give your partner a chance to work it out for themselves.
- If neither of you know the answer, look back over the materials and ask Prof. Eckert  

For each other exercises below, **record the command that you input.**

## Exercise 1: Looking for apples

- Open [the command line cheat sheet](https://github.com/sceckert/IntroDHSpring2021/blob/main/_week2/command-line-cheat-sheet.md)
- Make a directory called "my_lists"
-  In that directory, create a file called "grocery_list.txt", containing the following list
```
apple
broccoli
broccoli
carrot
apple
apple
apple
orange
orange
kiwi
```
- In the same directory, create a file called "tech_companies.txt", containing the following list
```
Google
Apple
Facebook
Amazon
Alphabet
```
- Finally, in the same directory, create a file called "favorite_things", containing a list of your five favorite things
- Search inside your "my_lists" directory for all instances of the word "apple"
- Then, search for all instances of the word "apple", **ignoring case**


✨*HINT*✨:
 Remember to include the path to the directory. If you're in a directory that contains a subdirectory (a directory within a directory) with text files you would like to perform commands on, you don't have to move into the directory to perform commands on the text files -- just include the path in your command:

Macs: `grep "search term" directoryname/filename.txt` or `grep "search term" directoryname/*` if you want to use a wildcard to search *all* the files in that directory

Windows: ` gc .\directoryname\filename.txt | Select-String -Pattern "search term"` or  `gc .\directoryname\*| Select-String -Pattern "search term"` if you want to use a wildcard to search all the files in that directory 
`

## Exercise 2: Imagining "America," Part 1

Download and unzip the **revised** corpus of [US Inaugural Addresses](https://github.com/sceckert/IntroDHSpring2021/blob/main/_week2/US_Inaugural_Addresses.zip?raw=true) and complete the following exercises on the command line (*NOTE: you must use this folder, not the previously shared link*)

1. Count the number of words in Biden's recent inaugural address
2. Search inside Biden's inaugural address for all instances of the term "America"  and display the results with the corresponding line numbers and your search term highlighted
3. Now, search for the term "America" in Biden's address and return the number of lines the term appears on.
 
## Exercise 3: Imagining "America," Part 2

1. Use a single command to search inside the folder of ["US_Inaugural_Addresses"](https://github.com/sceckert/IntroDHSpring2021/blob/main/_week2/US_Inaugural_Addresses.zip?raw=true) for **all** instances of the term "America" in all 59 speeches and print the results with the search term highlighted
2. Output the results of your keyword search to a text file
3. Make a second search, but this time include 1 additional line of context **before** and **after** the line that your term appears in.
4. Generate a second text file that contains the output of your new keyword search above.


*If you finish early, practice using some of the commands you just learned on this corpus!* 