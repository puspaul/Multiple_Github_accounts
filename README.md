# Multiple_Github_accounts
How to use multiple github accounts in VS code to push and pull from repositories
Ex : first account is in : user1@gmail.com
     second account is in : user2@gmail.com
## Step-1 : Terminal
Open the terminal from the start bar.

## Step-2 : SSH
Move to shell using : ```cd ~/.ssh```


The cd ~/.ssh command is used to change the current working directory to the .ssh directory that is located in the user's home directory.

The tilde ~ in the command is a shorthand notation for the user's home directory, so ~/.ssh refers to the .ssh directory that is located in the home directory.

The .ssh directory is used for storing SSH-related files, such as public and private keys, known hosts, and configuration files. When you run the cd ~/.ssh command, you are changing the current working directory to this directory, which allows you to perform operations on these SSH-related files, such as generating or managing SSH keys, configuring SSH connections, and so on.

## Step-3: Command to create ssh key
```ssh-keygen -t rsa -b 4096 -C "user1@gmail.com"```
```ssh-keygen -t rsa -b 4096 -C "user2@gmail.com"```
## Step-4: Enter file in which to save the key
While doing the third step you have to enter the rsa file name in which you wish to save the key.
We are renaming it to different names for the different accounts.
Set file name for user 1 = ```id_rsa_user1.pub```
Set file name for user 2 = ```id_rsa_user2.pub```
## Step-5: Get the Public Key for both the accounts
```cat id_rsa_user2.pub```

Copy this public key and paste in the github account SSH Key section.
Do this for both the accounts

## Step-6:  Create the config file
```nano config```

```
# Personal account - default config
Host github.com
   HostName github.com
   User git
   IdentityFile ~/.ssh/id_rsa_user1
# Practise account
Host github.com-user2
   HostName github.com
   User git
   IdentityFile ~/.ssh/id_rsa_user2
```

## Step-7:  Clone the repo using the SSH option from the Code section of the repository
If you are cloning using your default config id then you just simply need to copy the link and do git clone.
```git clone git@github.com:puspaul/twitter-the-algorithm.git```

If you want to use your secondary account to clone then just add the user2 id after github.com with the name we changed in the config file.

```git clone git@github.com-user2:puspaul/twitter-the-algorithm.git```

## Step-8: Add, Commit, Push
The add, commit and push functionalities remain same as before. The cloned repositories know from backend which id is pushing or adding and we dont need to add the identifiers at every step, just do it once during cloning and you are done.