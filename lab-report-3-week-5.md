# Lab Report 3
## Researching Commands

Consider the command grep. It stands for "global regular expression print" and searches for the pattern within a given set of files. All of these commands are incredibly useful depending on what you are searching for in your files.

Find 3 interesting command-line options or alternate ways to use the command you chose. 

1. grep -

- grep -v : displays the lines not containing the pattern
```
grep -v '^#'
```
that command will return all the lines that do not begin with #, this is useful if you're trying look past certain lines of code that begin with the same characters

- grep -n : displays the lines containing the pattern and the line numbers
```
grep -n "hello"
```
that command will show you the lines containing the string "hello" as well as the line numbers

- grep -c : displays how many times the matching pattern is there
```
grep -c "hello"
```
that command will show you how many times the string "hello" appears in the file

2. grep “” 

- grep “^”:  displays the lines that begin with the following string
```
grep “^hello” 
```
that command searches the file for lines that begins with the string "hello" and returns the line

- grep "$": displays the lines that end with the following string
```
grep "hello$" 
```
that command does the opposite of ^ and searches for the lines in the file that end with the string "hello".

- grep "."
```
grep "^.$" file.txt
```
another example that will return the same output as the previous example, although it does not have the full string

3. grep “[]”

- grep "[a-d]"
```
grep "[a-d]"
```
that command searches for lines that contain any of the letters a, b, c, or d

- grep "[^]": 
```
grep "[^aeiou]"
```
that command will search for lines in the file that do not contain any vowels

- grep "[0-9]": displays the lines that start with the digit following
```
grep "[0-9]"
```
that command searches for lines that start with a digit following zero or more spaces
