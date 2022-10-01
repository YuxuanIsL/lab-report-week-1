# CSE 15L week 1 lab report

## Installing VSCode
VSCode is a powerful tool for you to learn coding. If you don't have it installed in your computer, go and follow the instruction in the link to install VSCode:
[Instruction on VSCode](https://code.visualstudio.com/)

When it is installed, you should be able to open a window that looks like this (it might have different colors, or a different menu bar, depending on your system and settings):

![image](https://github.com/YuxuanIsL/lab-report-week-1/blob/main/vscode%E6%89%93%E5%BC%80%E9%A1%B5%E9%9D%A2.png)

Then you can create new files or open an existing file and do a lot of creative works there!

## Remotely Connecting

Sometimes we want to do some work on the another computer without physically being there. 
`ssh` is a helpful command for us to do so. By using it we can log into a remote computer and access to files in that computer.

In this step, we are using VSCode to open us a terminal and type in some useful commands in it.

Firstly open VScode and find the button Terminal, then open a new terminal.

Try out this command in terminal: `$ ssh cs15lfa22lr@ieng6.ucsd.edu`

This seeming "email address" is the account of the remote computer you want to log in. For me, my account is cs15lfa22lr@ieng6.ucsd.edu

If you are login first time, it will ask you to enter the password, which should be set before.

After entering the correct password, you will be successfully logged into the remote computer. Now, we call this the *server*, and our local computer is the *client*. 

You will see something like this: ![image](https://github.com/YuxuanIsL/lab-report-week-1/blob/main/ssh%20%E9%A1%B5%E9%9D%A2.png)

## Trying Some Commands

Now you have been in the remote computer and can now try some useful commands here. Try running the commands `cd`, `ls`, `pwd`, `mkdir`, and `cp` a few times in different ways, both on your computer, and on the remote computer after ssh-ing. 

Here is a short demo for using command: ![image](https://github.com/YuxuanIsL/lab-report-week-1/blob/main/Try%20running%20some%20cmd%20.png)
