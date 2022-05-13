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

After making changes to ```test.java``` we want to commit and push them to Github

>Here to make it easier an pre-edited version of the ```test.java``` file was copied over to the server instead of updating the file on the server itself





We are now able to use git commands to commit and push to Github 
[Commit to Github From Server](https://github.com/ShoumilSarkar/LabReport3/commit/b9d9463d5974eb2d7c04b4c63845cab5dfcd0910)

## Copy Whole Directory Recursively(```scp -r```)

This is what transferring using ```-r``` looks like
![Transferring Markdown 1](./Transferring%20Markdown%20Parse.png)
![Transferring Markdown 2](./Transferring%20Markdown%202.png)



