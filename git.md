#Using Git and Github with Xubuntu

##Git Setup

###Git-User configuration

    git config --global user.name mucximilian
    git config --global user.email mucximilian@gmail.co

###GitHub SSH Configuration

This is essential to connect with Git-repositories from GitHub.

    ssh-keygen -t rsa -C "your@email.com"

Accept the default location for the key file (_~/.ssh/id\_rsa_) and enter a password. 
Then add the entire content of the file _~/.ssh/id\_rsa.pub_ to your SSH Key list in your GitHub account settings.

##Creating a repository on Github

It is posible to create a new repository on the Github website or to create it from the console on your local machine.

    git remote add origin git@github.com:<USERNAME>/<REPOSITORY>.git 

##Setting up a local repository

###Download remote repository content

If you want the current directory to contain the data of your Github repository, it is necessary to mark the directory as Git-repository at first:

    git init

Now you can add your GitHub repository

    git remote add origin https://github.com/<USERNAME>/<REPOSITORY_NAME>.git

And pull down the content from the remote repository:

    git pull origin master

###Download remote repository directory

Execute this command to download the complete repository from GitHub in a new directory with the name of the repository.

    git clone git@github.com:<USERNAME>/<REPOSITORY_NAME>.git

##Workig with Git

###Adding files

If a new file is added locally it can be staged for commiting using

    git add <file>

You can also add all files in the directory

    git add .

or the files in a subdirectory

    git add directory/*

####Removing files

A file can be removed from the local repository the same similar to how it is added:

    git rm <file>
    
###Resetting staged files

    git reset

###Checking stage status

    git status

####Upload

Execute these commands in the project folder. The -u tells Git to remember the parameters.

    git commit -m 'Commit text'
    git push -u origin master

###Branching

Create a new branch and switch to it: 

    git branch new_branch
    git checkout new_branch

###Ignoring files

Create a file called **.gitignore** in your repository directory. To ignore a directory called _dir_ and all _.txt_-files you would add:

   dir/
   *.txt

to your file.
