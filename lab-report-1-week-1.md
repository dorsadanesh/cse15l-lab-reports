# Lab Report 1: How to log into a course-specific account on ieng6
## Installing Visual Studio Code
* I already had VS Code installed, so I did not need to do this step
* The website to install is https://code.visualstudio.com/, and it has all the installation instructions
* Once installed, opening VSC will lead to this:
* <img width="536" alt="Screen Shot 2022-09-30 at 6 57 37 PM" src="https://user-images.githubusercontent.com/114564837/193378642-99e7d564-7810-4b2b-8e9e-512ed01a2d30.png">
# Remotely Connecting
* Once installed, open a terminal so we can connect to a remote computer
* First you have to type in the ssh command into the terminal
* In this specific lab, the command we entered was: ssh cs15lfa22zz@ieng6.ucsd.edu (replacing zz with our specific account letter)
* I've reset my password four times now, and am still unable to log in to my specific account so for this lab I'll be using a ta5 account until I figure out how to fix this
* You'll be given a message that looks like this (respond yes) and prompted to enter your password
* <img width="663" alt="Screen Shot 2022-09-30 at 7 18 09 PM" src="https://user-images.githubusercontent.com/114564837/193379235-1871517b-75f1-46a5-b0d8-dccc2e14817c.png">
* After that, you've logged in and are now connected to another computer
## Trying Some Commands
* A couple commands we were given to try in lab were:
* cd ~
* cd
* ls -lat
* ls -a
* cp /home/linux/ieng6/cs15lfa22/public/hello.txt ~/
* cat /home/linux/ieng6/cs15lfa22/public/hello.txt
* example of ls -a:
* <img width="617" alt="Screen Shot 2022-09-30 at 9 11 18 PM" src="https://user-images.githubusercontent.com/114564837/193390826-32e48392-08eb-4aff-9fd1-d3894ed165df.png">
## Moving Files with scp
* Now we're gonna copy files over, so begin by creating a file, such as the following, and compile it with javac and java commands
* <img width="1016" alt="Screen Shot 2022-09-30 at 8 33 09 PM" src="https://user-images.githubusercontent.com/114564837/193385814-da1c5f7f-c12d-49db-8fd2-b4dff8ce0e25.png">
* Then, run this command: scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/ (again substituting zz with your specific account letter), where you will need to enter your password again
* Now, log back into ieng6 with the ssh command and use ls to find that the WhereAmI java file is in the home directory
## Setting an SSH Key
* An ssh key is a way to log on without having to enter a password everytime
* To set it up, type ssh-keygen into the terminal, click enter twice for the passphrase
* To make sure it worked, you will see the a random art image and the terminal looks like this
* <img width="670" alt="Screen Shot 2022-09-30 at 9 12 51 PM" src="https://user-images.githubusercontent.com/114564837/193391461-b677fb95-1ddf-4aef-8a80-7a4fdf96a80f.png">
* Then again, the command: ssh cs15lfa22zz@ieng6.ucsd.edu
## Optimizing Remote Running
*
