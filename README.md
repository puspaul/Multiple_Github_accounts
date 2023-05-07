# Multiple_Github_accounts
How to use multiple github accounts in VS code to push and pull from repositories

## Step-1 : Terminal
Open the terminal from the start bar.

## Step-2 : SSH
Move to shell using : ```cd ~/.ssh```


The cd ~/.ssh command is used to change the current working directory to the .ssh directory that is located in the user's home directory.

The tilde ~ in the command is a shorthand notation for the user's home directory, so ~/.ssh refers to the .ssh directory that is located in the home directory.

The .ssh directory is used for storing SSH-related files, such as public and private keys, known hosts, and configuration files. When you run the cd ~/.ssh command, you are changing the current working directory to this directory, which allows you to perform operations on these SSH-related files, such as generating or managing SSH keys, configuring SSH connections, and so on.

## Step-3: Command to create ssh key
```ssh-keygen -t rsa -b 4096 -C "your_email@gmail.com"```
## Step-4: Enter file in which to save the key
While doing the third step you have to enter the rsa file name in which you wish to save the key.
We are renaming it to different names for the different accounts.
public key = ```id_rsa_identifier.pub```
## Step-5: Get the Public Key for both the accounts
cat publickey.pub

Copy this public key and paste in the github account SSH Key section.

Step4.  Create the config file
nano config