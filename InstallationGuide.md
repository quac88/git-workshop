# You'll Need / This Guide Includes
1. Some knowledge of Command Prompt Terminal (we'll show you some)
2. Version Control Software - Git (we use Git in this tutorial) 
3. Code Repository - GitHub (or Bitbucket, GitLab, etc)
4. Read the Best Practices Guide!! <link> 
5. Getting Started and Basic Commands 

# Before We Start 
    WINDOWS USERS: Please consider installing Linux based Command Prompt such as powershell, MinGW, or Cygwin. It is highly highly recommended. 

    You'll need to use the command prompt for almost all of these procedures (<link to command prompt tutorial and cheat sheet>). 
    You should get used to it because you'll see/use it sooner or later. 

# 2. Git 
Git is a version control software. There are other version control systems, we use Git in this tutorial. 

To install, please follow instructions from the official website: 
 https://git-scm.com/book/en/v2/Getting-Started-Installing-Git 

# 3. GitHub 
GitHub is a code repository. There are other code repositories such as Bitbucket and GitLab. Feel free to explore others, but we use GitHub in this tutorial. 

Ok, now create a GitHub account: 
https://github.com/ 

# 4. Read the Best Practices Guide 
<link> 

# 5. Getting Started and Basic Commands
(You must have Git installed before you can follow these steps.) 

** How to pull from remote directory (Github) to your local repository (laptop/PC) **

Steps:

a. Create a directory (folder) on your computer, where you would like all your project files to be.
Command line: 
    ```
    mkdir [name of folder] 
    ```
Example: 
    ```
    mkdir project1
    ```

b. Initialize Git by typing: 
    ```
    git init
    ```

This creates an empty local version control system a  in that folder you just created. To double check, you'll see a .git folder in your directory after you initialize git. (type: "ls -a" in command prompt to check, or just go to the folder)
For every project, you'll need to create a dedicated local directory (folder) for your project, and initialize Git, so Git can track your project versions at the directory. 

Some problems/troubleshootings: 
...

c. Change branch name from *master to main (more about branching later): 
    git branch -m main
    
Check branch name, you should see "main" as the branch name: 
    git branch 

Why change branch to main? Because... read this article if you're curious
https://www.zdnet.com/article/github-to-replace-master-with-main-starting-next-month/ 

d. Create a .gitignore and add it: 
    touch .gitignore

 You need to create this file to tell Git not to track some files you don't want to track, for security reasons. 
Inside the file, pick 1 method: 
i. List what you want to ignore: 
For example, you want to ignore these files: a.exe, .git, .htaccess; open the .gitignore file, then write: 
    a.exe
    .git
    .htaccess 

ii. Ignore everything, and then unignore: 
Same example, open the .gitignore file, then write: 
    # ignore everything by using "*"
    * 
        
    # unignore by using "!"
    !.gitignore
    !*.cpp
    !*.h
