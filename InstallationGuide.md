# You'll Need / This Guide Includes
1. Some knowledge of Command Prompt Terminal (we'll show you some)
2. Version Control Software - Git (we use Git in this tutorial) 
3. Code Repository - GitHub (or Bitbucket, GitLab, etc)
4. Read the Best Practices Guide!! <link> 
5. Getting Started and Basic Commands 

# Before We Start 
- WINDOWS USERS: Please consider installing Linux based Command Prompt such as powershell, MinGW, or Cygwin. It is highly highly recommended. 

- You'll need to use the command prompt for almost all of these procedures (<link to command prompt tutorial and cheat sheet>). You should get used to it because you'll see/use it sooner or later. 

# 2. Git 
Git is a version control software. There are other version control systems, we use Git in this tutorial. 

To install, please follow instructions from the official website: 
 https://git-scm.com/book/en/v2/Getting-Started-Installing-Git 

# 3. GitHub 
GitHub is a code repository. There are other code repositories such as Bitbucket and GitLab. Feel free to explore others, but we use GitHub in this tutorial. 

## Ok, now create a GitHub account: 
https://github.com/ 

## CREATE A GITHUB REPOSITORY 
Github repository is a remote repository, this is for when you want to start a project. 
 1. Click on the "+"/"Create new..." sign on the top right corner

 2. Click on "New repository"

 3. Choose public or private 

 4. You can choose to add a README file and add a .gitignore file, but we'll show you how to create them later from your Command Prompt. 

 IMPORTANT: if you have created a README.md and/or .gitignore files in your local repostory already, you shouldn't create another ones from clicking these buttons. 

5. Click "Create repository". You have created a remote repository. 
 Note the SSH key tab, you'll need to copy that later to add your remote repository to your local repository (click on the SSH tab, and copy link)

6. Now, you will see a screen that says "Quick setup - if you've done this kind of thing before ... "
 - IF YOU HAVE NEVER HAD GITHUB BEFORE: you will need to set up a SSH key to connect Github to push/pull from your local repository, you'll only need to do this once per Github account. 
 - SKIP this step if you have done this or you know what you're doing.
 - To set up GitHub push with SSH keys, OPEN A DIFFERENT BROWSER TAB, then please follow these instructions, and SKIP step 1 because we just created a repository, and STOP after you have tested the SSH key (DO NOT do 'git remote ...'): 

 https://gist.github.com/xirixiz/b6b0c6f4917ce17a90e00f9b60566278 

 #### Notes: 
 - Use the Command Prompt
 - Use your email
 - You skip the file name step by accepting the default by pressing enter
 - You can skip at the passphrase stepp by pressing enter twice 
 - When you do the test key step, you can ignore the warning, and choose yes 
 - If the test works, you'll see: "Hi [your username]" message

7. To push your local repository to remote repository, please see step 5 below, PART III: HOW TO PUSH EXISTING LOCAL REPOSITORY FROM THE COMMAND LINE

# 4. Read the Best Practices Guide 

https://github.com/quac88/git-workshop/blob/main/docs/commits.md 

https://github.com/quac88/git-workshop/blob/main/docs/contributing.md 

# 5. Getting Started and Basic Commands
(You must have Git installed before you can follow these steps.) 

## PART I: HOW TO SET UP A LOCAL REPOSITORY (LAPTOP/PC) 

 Steps:

### 1. Create a directory (folder) on your computer, where you would like all your project files to be. 

In Command Prompt: 
```
mkdir [name of folder] 
```

Example:
```
mkdir project1 
```

### 2. Initialize Git by typing: 
```
git init
```
 This creates an empty local version control system a  in that folder you just created. To double check, you'll see a .git folder in your directory after you initialized git. (type: "ls -a" in command prompt to check, or just go to the folder). 

 For every project, you'll need to create a dedicated local directory (folder) for your project, and initialize Git, so Git can track your project versions at the directory. 

### 3. Change branch name from *master to main (more about branching later): 
```
git branch -m main
```
    
Check branch name, you should see "main" as the branch name: 

``` 
git branch 
```

 #### Why change branch to main? 
 Because... read this article if you're curious: 
 https://www.zdnet.com/article/github-to-replace-master-with-main-starting-next-month/ 

### 4. Create a .gitignore: 
``` 
touch .gitignore 
``` 

 You need to create this file to tell Git not to track some files you don't want to track, for security reasons. This step is VERY IMPORTANT, because if you accidentally forget to ignore a file (for example, a file that contains user passwords) and let it to be in a repository, it's there forever! 

 #### Inside the file, pick 1 method: 

 ##### i. List what you want to ignore and add it: 

 For example, you want to ignore these files: a.exe, .git, .htaccess; open the .gitignore file, then write: 

   ```
    # ignore everything by typing out files names 

    a.exe
    .git
    .htaccess 
   ```

 ##### ii. Ignore everything, and then unignore: 

 Same example, open the .gitignore file, then write: 
   ```
    # ignore everything by using "*"
    * 
        
    # unignore by using "!"
    !.gitignore
    !*.cpp
    !*.h 
   ```

### 5. Add a file before committing
 You need to 'git add' files to your version control before you can commit them. We can add the .gitignore file we just created: 
```
git add .gitignore
```

You can add multiple files, such as: 
```
git add .gitignore main.cpp function.cpp 
``` 

### 6. Check file status: 
``` 
git status 
``` 

### 7. Commit files: 
```
git commit -m "comment" 
``` 

 Commit locks in the changes you made. Please please KNOW BEST PRACTICES for committing changes. You should commit small, often, and smart. You should write detailed/reasonable comments, please remember that your teammates and even you may want to go back and understand what you did as well. 

 You can double check by entering: 
```
git status
```

 or: 

```
git ls-files
```

Same process if you would like to create a README.md file or any files. 

**Congratulations!** You have set up your local repository :D 


## PART II: HOW TO PULL REMOTE REPOSITORY (GITHUB) TO YOUR LOCAL REPOSITORY (DIRECTORY IN YOUR PC) 

 ### In your local repository, to add the remote repository to your local repository, enter: 
``` 
git remote add origin [your SSH key from your "Quick setup - ...", which is the Github repository page]
``` 

 Example: 
```
git remote add origin git@github.com:ak-iqmulus/test.git
``` 
 
 Now you can pull it to your local directory/repository: 
```
git pull origin main 
```

## PART III: HOW TO PUSH EXISTING LOCAL REPOSITORY FROM THE COMMAND LINE  
 BEFORE YOU PUSH, please check your branch name first, make sure you push to the correct branch. 
``` 
git branch 
``` 

 Change *master branch name to main if necessary: 
```
git branch -M main 
``` 
 
 Now you can push your files to the main branch: 
```
git push -u origin main 
``` 

 This means you push your committed work from 'origin', which is your local repository, to the main branch of the remote repository. You know it works when you see your added/updated work/files in your Github repository. 

 HOWEVER, it is best practice to create your own branch to push to, then, when your team is happy with your work, you merge it with the development branch, then finally, you can merge it with the main branch (please see Best Practices Guide, i.e. contributing.md doc) 

 To create a branch, following the angular-style format: 
```
your-name/type-of-commit/few-words-about-what-you-did 
``` 
 
 Example: 
```
git checkout -b quac/docs/installation-guide 
``` 

 To check branches, you can even see which branch you're at: 
```
git branch 
``` 

 To change to a different branch, for example, you want to go to the development branch: 
```
git checkout development 
``` 

 For more information: https://github.com/quac88/NitDestroyer/blob/main/docs/contributing.md 