# Lab Report 4
## Part One
Task: Changing the name of the start parameter and its uses to base

In terminal type: vim TestDocSearch.java

Move cursor to 10, ( j to go down, l to go right)

Put cursor on 0 use x key to delete it

Use i to enter insert mode, add the correct numbers (391)

Click Escape to exit insert mode

Type :wq! to exit and save vim

In terminal type: DocSearchServer.java

Then type: :%s/start/base/g to find and replace all instances of start with base in the whole file

Type :wq! to exit and save vim

## Part Two
SCP vs VIM
* Editing file in vsc, copying it over to the remote, running bash test.sh, 22.33 seconds
* Using vim in the remote to edit and save the file, then running bash test.sh, 10.15 seconds

Both ways had no issues, but vim saves much more time.

**Which of these two styles would you prefer using if you had to work on a program that you were running remotely, and why?**
I would prefer to work with vsc and scp because I don't know all the vim commands yet and feel like it would just be more difficult for me to use vim, since we've just learned it.

**What about the project or task might factor into your decision one way or another? (If nothing would affect your decision, say so and why!)**
If I was worried about time, I would change my decision and use vim since it is more efficient. However, if time is not a concern nothing would affect my decision considering i am more comfortable with vsc adn scp.
