#Using Git and Github with Xubuntu.

##Git Setup

###Git-User configuration

[git config --global user.name mucximilian
git config --global user.email mucximilian@gmail.com]

###GitHub SSH Configuration

This is essential to connect with Git-repositories from GitHub.

<source lang="bash">
ssh-keygen -t rsa -C "your@email.com"
</source>

Accept the default location for the key file (''~/.ssh/id_rsa'') and enter a password. 
Then add the entire content of the file ''~/.ssh/id_rsa.pub'' to your SSH Key list in your GitHub account settings.

##Creating a repository on Github

It is posible to create a new repository on the Github website or to create it from the console on your local machine.

<source lang="bash">
git remote add origin git@github.com:<USERNAME>/<REPOSITORY>.git 
</source>

##Setting up a local repository

###Download remote repository content

If you want the current directory to contain the data of your Github repository, it is necessary to mark the directory as Git-repository at first:

<source lang="bash">
git init
</source>

Now you can add your GitHub repository

<source lang="bash">
git remote add origin https://github.com/<USERNAME>/<REPOSITORY_NAME>.git
</source>

And pull down the content from the remote repository:

<source lang="bash">
git pull origin master
</source>

###Download remote repository directory

Execute this command to download the complete repository from GitHub in a new directory with the name of the repository.
<source lang="bash">
git clone git@github.com:<USERNAME>/<REPOSITORY_NAME>.git
</source>

==Workig with Git==

===Adding files===

If a new file is added locally it can be staged for commiting using

<source lang="bash">
git add <file>
</source>

You can also add all files in the directory

<source lang="bash">
git add .
</source>

or the files in a subdirectory

<source lang="bash">
git add directory/*
</source>

===Removing files===

A file can be removed from the local repository the same similar to how it is added:

<source lang="bash">
git rm <file>
</source>

===Resetting staged files===

<source lang="bash">
git reset
</source>

===Checking stage status===

<source lang="bash">
git status
</source>

===Upload===

Execute these commands in the project folder. The -u tells Git to remember the parameters.

<source lang="bash">
git commit -m 'Commit text'
git push -u origin master
</source>

===Branching===

Create a new branch and switch to it: 

<source lang="bash">
git branch new_branch
git checkout new_branch
</source>

===Ignoring files===

Create a file called '''.gitignore''' in your repository directory. To ignore a directory called ''dir'' and all ''.txt''-files you would add:

<source lang="bash">
dir/
*.txt
</source>

to your file.

[[Category:Linux]]
