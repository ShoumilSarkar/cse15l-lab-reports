[Lab Report 1](lab-report-1-week-2.html)
[Lab Report 1](https://shoumilsarkar.github.io/cse15l-lab-reports/lab-report-1-week-2.html)


# Remote Access Tutorial

## Step 1: Downloading VSCode
Head over to the website down below and download the version of VSCode for your operating system.

[VSCode Download](https://code.visualstudio.com/)

Once installed the page should open up to this
![image](./VSCode%20Start%20Page.png)

## Step 2: Connecting to the Remote Server

First open up a terminal window and enter in

`ssh <Your-Username>@ieng6.ucsd.edu`

> Before the `@` is the account name and after it is the server name.

It will then prompt you to enter in your password. The account password should be entered here.

> For security it will not show anything being typed.

After typing in your password you will be greeted by a screen showing that you have logged in.
![image](./SSH%20Login.png)


## Step 3: Trying Some Commands

After logging in, there are a multitude of Linux commands that an be used.

>`pwd` Prints the working directory 

>`ls` Lists all the files in the current directory including a directory after will list the files in that directory
>>`-l`,`-a`,`-t` modifiers like this can be added as parameters to these commands  
>>>`-l` include extra information such as permissions  
>>>`-a` show all files including hidden  
>>>`-t` sorts by date and time  
>>`-lat` they can also be combined into one command that does them all together

>`cd` Follow this command by another directory to go into that directory and make it your current working directory  
>>`..` refers to the previous directory and can be used in conjunction with cd to go to the parent directory

These are some of the commands that can be used to traverse a remote server through terminal.

## Step 4: Moving Files with scp

`scp` Is a command taht secure copys files from one directory to another usually from server to local or vice versa.

## Step 5: Setting an SSH Key
## Step 6: Optimizing Remote Running

