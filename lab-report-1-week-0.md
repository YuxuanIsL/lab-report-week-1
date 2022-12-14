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

## Moving Files with `scp`

So far we???ve seen how we can do some work on local and remote computers. One key step in working remotely is being able to copy files back and forth between the computers. We???ll see now another way to copy a file (or many files!) from your computer to a remote computer. The command is called `scp`, and we will always run it from the client (that means from your computer, not logged into `ieng6`). 

To demonstrating this, we will create a new jave file in VSCode called `WhereAmI.java`
![image](https://github.com/YuxuanIsL/lab-report-week-1/blob/main/where%20am%20i.png)

Then compile and run the java file using
`javac WhereAmI.java`
`java WhereAmI`

Then, in the terminal from the directory where you made this file, run this command 
`scp WhereAmI.java cs15lfa22lr@ieng6.ucsd.edu:~/`
where `scp` means secure copy, what follows is the file you want to copy and the server account. **Enter the password**. You are now having `WhereAmI.java` in the remote computer. 

To verify that, try `ls` command. Then you'll see the file is successfully copied! 
![image](https://github.com/YuxuanIsL/lab-report-week-1/blob/main/ls.png)

## Setting an SSH Key

So far, we???ve seen how to log in, run commands, and copy files to a remote server with `ssh` and `scp`. Every time we log in or run scp, we have to type (or copy-paste) our password. This is frustrating, time consuming, and interrupts whatever task we were trying to do. Naturally, we should look into if there are ways to avoid this repetitive, frustrating task with a configuration or program.

In this case, there is a great solution ??? `ssh` keys. Here???s what you should run to set this up:
`ssh-keygen`

You will see this:
![image](https://github.com/YuxuanIsL/lab-report-week-1/blob/main/ssh.png)
This created two new files on your system; the private key (in a file `id_rsa`) and the public key (in a file `id_rsa.pub`), stored in the `.ssh` directory on your computer.

Now we need to copy the **public** (not the private) key to the `.ssh` directory of your user account on the server.

**On client:**
`$ ssh cs15lfa22zz@ieng6.ucsd.edu
<Enter Password>`

**On server:**
`$ mkdir .ssh
$ <logout>`

**On client:**
`$ scp /Users/joe/.ssh/id_rsa.pub cs15lfa22@ieng6.ucsd.edu:~/.ssh/authorized_keys`
(Make sure to use your own username)

Once those are done, you are free of entering password when using `ssh` and `scp`.

![image](https://github.com/YuxuanIsL/lab-report-week-1/blob/main/ssh%20showup.png)

## Optimizing Remote Running

This section will display what part becomes easier after setting up this key.

We will be using `WhereAmI.java`

![image](https://github.com/YuxuanIsL/lab-report-week-1/blob/main/demo.png)
![image](https://github.com/YuxuanIsL/lab-report-week-1/blob/main/demo%5C.png)

By implementing the key, we will skip over the step that asks entering password.

We could input command at the end of `ssh`command.

![image](https://github.com/YuxuanIsL/lab-report-week-1/blob/main/optimiing.png)

