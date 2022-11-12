# Lab Report 3
## Researching Commands

Consider the command grep. It stands for "global regular expression print" and searches for the pattern within a given set of files.

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

2. grep “^/$” 

- grep “^hello” 
```
grep “^hello” file.txt
```
that command searches the file for lines that begins with the string "hello" and returns the line

- grep
```
grep "hello$"
```

- grep
```
grep "lo$"
```

3. grep “[a-e]”

- grep
```
grep
```

- grep
```
grep
```

- grep
```
grep
```
