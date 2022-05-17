# Lab Report 3 More on SSH

## Streamlining SSH Configuration

I added these 4 lines into the ```.ssh/config``` config file 
![SSH Config](./Lab%205%20SSH%20Config%20File.png)

The alias given to this was ```ieng6```
![SSH Config](./ieng6%20login.png)

Copying over the file can now be done like this
![Simplified SCP](./Lab%205%20Simplified%20SCP.png)

## Setup Github Access From ieng6

The public keys are stored in the settings pane of Github
![Github SSH Keys](./Lab%205%20Github%20SSH%20Key%20Location.png)

The Private key that is stored on my user account is in the ```.ssh``` folder in ```id_rsa```

![Server Private Keys](./Lab%205%20Private%20Key%20On%20Server%20Location.png)


Here, I Clone a repo from my Github Account to the Linux Server

![Repo Clone to Server](./Cloning%20Lab%20Report%203%20Repo%20on%20Server.png)

>If cloning with HTTPS make sure to set SSH to be able to commit with it

After making changes to ```test.java``` we want to commit and push them to Github

>Here to make it easier an pre-edited version of the ```test.java``` file was copied over to the server instead of updating the file on the server itself
  
We are now able to use git commands to commit and push to Github
![Commit From Servr Commands](./Lab%205%20Commit%20From%20Server.png)
>The same series of commands are done after using ```cd``` to enter the directory. We use ```git add``` to add files to our commit. ```git commit -m``` to commit the files with our update message. Finally we use ```git push origin main``` to push the commit to the Github repo   
[Commit to Github From Server](https://github.com/ShoumilSarkar/LabReport3/commit/b9d9463d5974eb2d7c04b4c63845cab5dfcd0910)


## Copy Whole Directory Recursively(```scp -r```)

### scp directory
This is what transferring using ```-r``` looks like
![Transferring Markdown 1](./Transferring%20Markdown%20Parse.png)
![Transferring Markdown 2](./Transferring%20Markdown%202.png)
>Lots of different files got copied over here. We can specifiy what files or filetypes we copy over when using the scp command. (done with the one line command later)

### Testing on the Server
Now that we have copied over the directory, we can run the tests after we ssh onto the server

![Running Tests on Server](./Lab%205%20Login%20into%20Server%20and%20Run.png)




### Streamlining Into One Line
We can copy the files we need over and run the tests in one line

![SCP and run one line](./Lab%205%20SCP%20and%20Run%20Tests%20Remotely%20in%20One%20Line.png)

>Here we copy over the current directory with files of type ```.java``` and ```.md``` and the ```lib``` folder. Then in the next command seperated by a semicolon we ssh into the server. Along with the ssh part of the one line command we use quotes to specify the commands to be done after we login to the server. These commands were to enter the ```markdown-parser``` folder we just copied over to, and then compiling and running the ```MarkdownParseTest.java``` file.
>>Note: After this completes you do not stay on the server