[Lab Report 1](lab-report-1-week-2.html)
[Lab Report 1](https://shoumilsarkar.github.io/cse15l-lab-reports/lab-report-1-week-2.html)


# Remote Access Tutorial

## Step 1: Downloading VSCode
Head over to the website down below and download the version of VSCode for your operating system.

[VSCode Download](https://code.visualstudio.com/)

Once installed the start up page should open up to this
![image](./VSCode%20Start%20Page.png)

## Step 2: Connecting to the Remote Server

First open up a terminal window and enter in

`ssh <Your-Username>@ieng6.ucsd.edu`

> Before the `@` is the account name and after it is the server name.

It will then prompt you to enter in your password. The account password should be entered here.

> For security it will not show anything being typed.

After typing in your password you will be greeted by a screen showing that you have logged in.
![image](./SSH%20Login.png)

**Note: SSH keys were already setup here so no password was requested**


## Step 3: Trying Some Commands

After logging in, there are a multitude of Linux commands that an be used. Here are some important ones.

>`pwd` Prints the working directory 

>`ls` Lists all the files in the current directory including a directory after will list the files in that directory
>>`-l`,`-a`,`-t` modifiers like this can be added as parameters to these commands  
>>>`-l` include extra information such as permissions  
>>>`-a` show all files including hidden  
>>>`-t` sorts by date and time  
>>`-lat` they can also be combined into one command that does them all together

>`cd` Follow this command by another directory to go into that directory and make it your current working directory  
>>`..` refers to the previous directory and can be used in conjunction with cd to go to the parent directory

These are some of the commands that can be used to traverse a remote server through the terminal.

Here is an example:
1. `ls` is see what files are in the directory
2. `cd` is used to change the current working directory to Documents
3. In Documents `ls` is used again to see what is inside however it is empty so nothing shows/
4. `cd ..` is then used to go back to the previous directory
5. finally, pwd is used to print the working directory which in this case is the home directory of my account.

![image](./Command%20Test.png)


## Step 4: Moving Files with scp

`scp` Is a command that securely copies files from one directory to another usually from a server to local or vice versa.

The full command syntax is

`scp <file> <server>:<directory>`

`cd` is used to go to the folder Lab 1 which contains the WhereAmI.java file we would like to copy over. Then we use the scp command with the file we are copying over, the server that we are sending to and after the colon, the directory of the server we want it to be in. It requests the password of the server. Once entered it starts copying over the file showing transfer status of the file as it copies.

![image](./SCP%20Screenshot.png)

## Step 5: Setting an SSH Key
It becomes inefficient to constantly have to type in the server password each time a login or a command like scp is done. Therefore we can create SSH keys which is a set of public and local keys that allows a passwordless connection between the server and the local computer being used.

To set this up, enter `ssh-keygen` in the terminal of the local computer. It will generate the keys and then request the location of where the keys should be saved. We put it into the `.ssh` folder in a file called `id_rsa`. It will then request a passphrase to be used, do not enter a password and just press enter(This will mean there is no passphrase). It will then double check the passphrase so only press enter there as well. Finally, it will show the key's fingerprint and a randomart image that was generated.

![image](./SSH%20Keygen.png)

The next step is to copy the public key from the pair we generated to the server.

As done in step 4, we will login and use `scp`, but first we need to create a `.ssh` directory on the server. The command for this is `mkdir`. So here we will do `mkdir .ssh`.

![image](./mkdir%20Screenshot.png)

Then we use `scp` to copy the public key(using .pub of the ida_rsa file) into the authorized_keys.

![image](./SCP%20SSH%20Keys%20.png)

Now a password is not required to login and run commmands.


## Step 6: Optimizing Remote Running

There are two main tools that can be used to optimize running files remotely.

> 1. We can run commands at the end of an `ssh` login by enclosing them in quotes.
> 2. Multiple commands can be run in the same line by seperating them with semicolons.

We can actually put these two together to login and run multiple commands all in one line.

 **Example:**

![image](./Optimized%20Commands%20Screenshot.png)

Here we login to cs15lsp22ajg, compile the `WhereAmI.java` file and then run it, all in one line.


**Note: Some steps done were connecting to a personal ucsd ieng6 account instead of the correct class username, however, the same steps apply.**