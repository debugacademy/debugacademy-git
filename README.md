# Debug Academy - Git  
The free lesson you are reading is provided by Debug Academy. DebugAcademy offers career-changing, in-person, web development training in the Northern VA & Greater Washington D.C. area. Our primary focus is in Drupal, and our curriculum is entirely assembled by a certified Drupal Grand Master and employee of Acquia. Visit DebugAcademy.com for more information.  

This lesson is a subset of one of Debug Academy's git lessons.  

Git is a Version Control System, or 'VCS'. It takes snapshots of the state of files when changes are made. It is extremely beneficial and necessary on any large software project. It is a red flag if a software development company is not enforcing the use of version control.  

A practice assignment can be found in the repository under the name: git_assignment.md  

## Git Installation  
### Mac OS X  
Use the Git OS X Installer ( ```http://code.google.com/p/git-osx-installer/``` ). If you use the Homebrew package manager, run ```brew install git```. You might want to install GitX (GUI).  

### Windows  
Use Git for Windows ( ```http://msysgit.github.io/``` ) (command line).  

### Ubuntu  
Use the command ```sudo apt-get install git-core``` to install Git using the command line.  

Follow the installation options that will be presented to you.  

## Post-Installation Setup  
Git keeps track of the history of files changed - including who made each change. Because of which, you are required to configure your name and e-mail address.  

To configure your name and e-mail address, enter the following 2 commands into the command line where you will be using git:  
`git config --global user.name "YOUR NAME"`    
`git config --global user.email "YOUR EMAIL ADDRESS"`    

## Command line basics  
If you are new to programming, you likely spend most of your computer-time using a GUI (pronounced gooey). A GUI is a user interface designed to hide the complexity behind applications. We will be using the terminal for portions of this Git lesson.  

Below you will find a *subset* of Debug Academy's command line basics lesson.  

### ls  
- ls => 'list'  
- Lists files and folders in the current directory  

### cd [relative path to folder]  
- 'cd' = >'Change Directory'  
- Used for navigating to other folders  
- Can use an *absolute (entire) path*: cd /Users/ashraf/Desktop/debugsociety/subfolder-name  
 - Absolute paths begin with a /  
- Can use a *relative path*:  
 - cd /Users/ashraf/Desktop  
   - Used an absolute path to get to the Desktop folder  
 - cd debugsociety  
   - Because the debugsociety folder is within my current folder, I can use a relative path.  
 - cd subfolder-name  
   - Because subfolder-name is in my current folder, I can use a relative path.  

### * (asterisks)  
- Asterisks means 'anything'.  
- In many commands, can be used as part of a filename to expand the command. For example:  
- Can be used to select all files in a folder  
 - mv files/* files/ashraf/  
- Can be used to move files based on a partial filename  
 - mv files/*.pdf files/ashraf/  
   - This moved everything in the 'files' folder whose name ends in '.pdf'.  
 - mv files/a* files/ashraf/  
   - This moved everything in the 'files' folder whose name starts with 'a'.  
 - mv files/*tmp* files/trash  
   - This moved everything in the 'files' folder whose name *contains* 'tmp'.  

### ../  
- Used to denote 'up one level'  
- To change to the directory 'up one level': cd ../  
- Can be combined to go up multiple levels:  
 - cd ../../  
 - That takes you up two levels  

### ./  
- Used to denote 'current directory'  
- Example: mv files/file1.html ./  
 - We moved a file from the 'files' folder into the folder we are currently in.  

## Git commands  
Below is a subset of the Debug Academy lesson on git commands. It covers the commands we will be using throughout this assignment.  

### git init:  
- For creating a new git repository.  
- It turns the current directory into a git repository.  
- For example:  
  - 'cd' into a non-git folder.  
  - Type 'git init'.  
  - Now the folder is a git repository.  

### git clone [URL] [destination-name]:  
- For copying (aka cloning) a repo (and all files in it) from a URL to your computer.  
- For example:  
  - "git clone https://github.com/debugacademy/debugacademy-git.git da-git"  
  - That will download a copy of the entire debugacademy-git repository into a local folder (on your computer) called 'da-git'  

### git add [file or folder]:  
- Includes the 'add'ed files *in your next commit*.  
- Changes to files that were not 'add'ed will remain untracked by git.  
- Filenames must be typed exactly and with extensions.  
  - For example, if you want to add a file named File1.html to your next commit:  
  - git add File1.html will work.  
    - 'git add File1' will NOT work.  
    - 'git add file1.html' will NOT work.  

### git commit -m "[message]":  
- Stores the current version of all files that were added using 'git add'.  
- There should be a commit for every meaningful change.  
- There should be a short message describing what the commit is for.  
  - For example: git commit -m "Updated git_commands.md"  
- If this message displayed: no changes added to commit, it means you did not 'git add' your changes before committing them.  

### git checkout [branch] :  
- Used to switch branches.  
  - For example:  
    - I am on the 'master' branch  
    - git checkout hello-world  
    - If it exists, I am taken to the branch named 'hello-world'  

### git checkout -b [new-branch] [branch]:  
- Used to create a new branch named [new-branch], which initially matches the branch named [branch] exactly  
  - For example:  
    - git checkout -b my-branch master  
    - The branch 'my-branch' is created based off of the 'master' branch  
    - Then I am taken to the new 'my-branch' branch  

### git remote add [alias] [url]:  
- Adds a remote connection to a repository.  
- For example:  
  - git remote add ds https://github.com/debugacademy/debugacademy-git.git  
  - Now we are connected to (can pull from) the 'debugacademy/debugacademy-git' repo.  
    - If we have the right privileges, we can also now push to the 'debugacademy/debugacademy-git' repo.  
  - i.e. git pull ds master ## this command will now automatically pull from debugacademy/debugacademy-git.git  

### git remote:  
- Shows the nicknames of the remote repositories that your repo is connected to.  
  - For example:  
  - git remote might display:  
    - origin  
    - ds  
- *Passing the -v flag shows more detail.*  
  - For example:  
  - git remote -v might display:  
    - da   https://github.com/debugacademy/debugacademy-git.git (fetch)  
    - da   https://github.com/debugacademy/debugacademy-git.git (push)  
    - origin    https://github.com/[YOUR-USERNAME]/debugacademy-git.git (fetch)  
    - origin    https://github.com/[YOUR-USERNAME]/debugacademy-git.git (push)  

### git branch:  
- Shows you the branches on your computer  
- Places an asterisk next to the branch you are on.  

### git push [remote] [branch you are pushing]:  
- Used for sending commits from [branch] to [remote]/[same branch]  
- Sends ALL committed work on [branch you are pushing]  

### git pull [remote] [branch name]:  
- Immediately/automatically merges all new changes from [remote]/[branch name] to the branch you currently have checked out.  
- When you git pull, make sure you have the branch you want to pull into checked out  
- For example, if I want to pull from debugacademy's 'master' branch into my 'branch2' branch  
    - git checkout branch2  
    - git pull debugacademy master  
