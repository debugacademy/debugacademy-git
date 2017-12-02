# Debug Academy - Git  
The free lesson you are reading is provided by Debug Academy. DebugAcademy offers career-changing, in-person, web development training in the Northern VA & Greater Washington D.C. area. Our primary focus is in Drupal, and our curriculum is entirely assembled by a certified Drupal Grand Master and employee of Acquia. Visit DebugAcademy.com for more information.  

This lesson is a subset of one of Debug Academy's git lessons.  

Git is a Version Control System, or 'VCS'. It takes snapshots of the state of files when changes are made. It is extremely beneficial and necessary on any large software project. It is a red flag if a software development company is not enforcing the use of version control.  

A practice assignment can be found in the repository under the name: git_assignment.md  

## Git Installation  
### Mac OS X  
Download Xcode from the Mac App Store. There is a program on your computer named 'App store' which you use to download Xcode.  

### Windows  
Use Git for Windows ( ```https://git-for-windows.github.io/``` ) (command line).  

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
Lists files and folders in the current directory.

#### Detail
- *Command:* ```ls```
- *Stands for:* List
- *Basic usage:* ```ls```
- *Common Flags:* To use flags, write a single dash, followed by each flag, with no spaces in-between the dash and each flag.
   - ```l``` Show detailed information, including filesize and permissions
   - ```a``` List all files, including hidden files
   - ```h``` Display output (such as filesize) in a human-friendly format
- *Advanced Usage:* ```ls [specific file or folder] -lah```
- *Typical frequency:* > Daily
- *Example:* ```ls sites/all/modules -lah```

### cd [relative path to folder]
Used for navigating to other folders.

#### Detail
- *Command:* ```cd```
- *Stands for:* Change directory
- *Basic usage:* ```cd [relative or absolute folder name]```
- *Advanced Usage:* 
  - ```cd ../``` navigate up 1 level from the current directory
  - ```cd ../../``` navigate up 2 levels from the current directory
  - ```cd sites``` navigate to the 'sites' folder within the current directory using relative path (path does not begin with a slash)
    - If the sites folder is within my current folder, I can use this relative path.
  - ```cd /Users/ashraf/sites``` navigate to the 'sites' folder within the user's home directory using absolute (entire) path
    - Using the absolute (entire) path, I can jump to the sites folder from whereever I am
- *Typical frequency:* > Daily
- *Examples:* ```cd ~/Desktop/debugacademy```

### * (asterisks)
- Asterisks means 'anything'.  
- In many commands, can be used as part of a filename to expand the command. For example:  
- Can be used to select all files in a folder  
 - `mv files/* files/ashraf/`  
- Can be used to move files based on a partial filename  
 - `mv files/*.pdf files/ashraf/`  
   - This moved everything in the 'files' folder whose name ends in '.pdf'.  
 - `mv files/a* files/ashraf/`  
   - This moved everything in the 'files' folder whose name starts with 'a'.  
 - `mv files/*tmp* files/trash`  
   - This moved everything in the 'files' folder whose name *contains* 'tmp'.  

### ../
- Used to denote 'up one level'  
- To change to the directory 'up one level':  
  - `cd ../`  
- Can be combined to go up multiple levels:  
  - `cd ../../`  
  - That takes you up two levels  

### ./
- Used to denote 'current directory'  
- Example: `mv files/file1.html ./`  
  - We moved a file from the 'files' folder into the folder we are currently in.  

## Git commands  
Below is a subset of the Debug Academy lesson on git commands. It covers the commands we will be using throughout this assignment.  

### git init
Creates a new git repository for the first time. This is done by adding the hidden .git/ directory to the current folder.

#### Detail
- *Command:* ```git init```  
- *Stands for:* Initiate git repository  
- *Basic usage:* ```git init```  
- *Typical frequency:* < Once a month  
*Example:*  
```  
cd sites/new-site  
git init  
touch README.md
git add README.md
git commit -m "My repository's first commit"  
```  
Now sites/new-site is a git repository, and it has one commit.  

### git clone [URL] [destination-name]
Copies (aka clones) a git repository and all of its contents from a specified URL to your computer.  

#### Detail
- *Command:* ```git clone```  
- *Stands for:* Clone a git repository  
- *Basic usage:* ```git clone [URL] [Destination]```  
- *Typical frequency:* < Weekly  
- *Example:* ```git clone https://github.com/debugacademy/course-drupal.git DA-drupal-course```  
  - That command copied the entire course-drupal repository (folder, subfolders, and files) into a folder named 'DA-drupal-course'  

### git add [file or folder]
Stages files for inclusion *in your next commit*. When you commit files, only the staged files will be included in your commit. Changes to files that were not 'add'ed will remain untracked by git.  

Filenames must be typed *exactly* and with extensions.

#### Detail
- *Command:* ```git add```  
- *Stands for:* Add files to the *next* commit  
- *Basic usage:* ```git add [file or folder]```  
- *Common Flags:* To use flags, write a single dash, followed by each flag, with no spaces in-between the dash and each flag.  
   - ```--all``` Stages file additions *and* removals for next commit. Includes all files  
   - ```-p``` Allows you to interactively choose portions of files to be 'git add'ed, as opposed to blindly git add'ing an entire file  
- *Typical frequency:* > Daily  
- *Example:*  
  - ```git add sites/all/modules/views```  
  - ```git add assignment1.md```  
  - ```git add -p assignment1.md```  

### git commit -m "[message]":
Stores the current version of all files that were added (staged) using 'git add'.  

- There should be a commit for *every* meaningful change.  
- There should be a short message describing what each commit is for.  

#### Detail
- *Command:* ```git commit```  
- *Stands for:* Commit files and/or folders to the git repository  
- *Basic usage:* ```git commit -m '[message]'```  
- *Common Flags:* To use flags, write a single dash, followed by each flag, with no spaces in-between the dash and each flag.  
   - ```m``` Pass the commit's message as an argument. Must be followed by a space, then a short string (words) in quotations.  
- *Advanced Usage:* ```git commit -m '[message]'```  
- *Typical frequency:* > Daily  
- *Example:*  
  - ```git add sites/all/modules/views/```  
  - ```git commit -m 'Added views module to repository'```  

### git checkout [branch]
Switches to the specified branch. This causes files on the current branch to be 'hidden' elsewhere, and files on the branch you are switching to to appear in the repository.

#### Detail
- *Command:* ```git checkout [branch]```  
- *Stands for:* Check out (go to) the branch named [branch]  
- *Basic usage:* ```git checkout [branch]```  
- *Typical frequency:* > Daily  
- *Example:*  
  - ```git checkout sitename-IssueNumber```  (now we are taken to the branch named sitename-IssueNumber, if it exists)  

### git checkout -b [new-branch] [branch]
Creates a new branch named [new-branch], which initially matches the branch named [branch] exactly.

#### Detail
- *Command:* ```git checkout -b [new-branch] [branch]```  
- *Stands for:* Create the branch [new-branch] to match the branch named [branch], then check out [new-branch] 
- *Basic usage:* ```git checkout -b [new-branch] [branch]```  
- *Typical frequency:* > Daily  
- *Example:*  
  - ```git checkout -b challies-435 master```  
    - This creates a branch named 'challies-435' based off of the master branch  
    - It then Checks out the new branch named challies-435  

### git remote add [alias] [url]
Adds a remote connection to a repository, which you can then push to or pull from. This is analogous to adding a contact to your phone's contact list which you can then call.  

#### Detail
- *Command:* ```git remote add [alias] [url]```  
- *Stands for:* Add an alias for interacting with a remote repostory.  
- *Basic usage:* ```git remote add [alias] [url]```  
- *Typical frequency:* > Monthly  
- *Example:*  
  - ```git remote add debugacademy https://github.com/debugacademy/course-drupal.git```  
    - Now we are connected to (can pull from) the 'debugacademy/course-drupal' repo.  
    - If we have the right privileges, we can also now push to the 'debugacademy/course-drupal' repo.  
    - e.g. ```git pull debugacademy master``` ## this command will now automatically pull from debugacademy/course-drupal.git  

### git remote
Shows the aliases, or nicknames, of the remote repositories whose URLs are referenced in your repository.

#### Detail
- *Command:* ```git remote```  
- *Stands for:* List remote repositories you are connected to  
- *Basic usage:* ```git remote -v```  
- *Common Flags:* To use flags, write a single dash, followed by each flag, with no spaces in-between the dash and each flag.  
   - ```v``` Stands for 'Verbose'. Lists the URLs each alias represents.  
- *Typical frequency:* > Daily  
- *Example:*  
  - ```git remote -v```  
    - The output for this may be:  
    - debugacademy   https://github.com/debugacademy/course-drupal.git (fetch)  
    - debugacademy   https://github.com/debugacademy/course-drupal.git (push)  
    - origin    https://github.com/[YOUR-USERNAME]/course-drupal.git (fetch)  
    - origin    https://github.com/[YOUR-USERNAME]/course-drupal.git (push)  

### git branch
Lists the branches that are on your computer. It places an asterisk next to the branch you are on.  

#### Detail
- *Command:* ```git branch```  
- *Stands for:* List the branches in your git repository  
- *Basic usage:* ```git branch```  
- *Common Flags:* To use flags, write a single dash, followed by each flag, with no spaces in-between the dash and each flag.  
   - ```--all``` *Multiple character flag*, so preceded by 2 dashes instead of 1  
     - Lists all branches you have downloaded (fetched), including remote branches  
- *Typical frequency:* > Daily  
- *Example:* ```git branch```  

### git push [remote alias] [local branch being pushed]
Used for sending commits from ```[branch]``` to ```[remote]/[same branch]```. Sends ALL committed work on ```[branch you are pushing]```.

#### Detail
- *Command:* ```git push```  
- *Stands for:* Push a specific branch from my repository to the specified remote.  
- *Basic usage:* ```git push [remote alias] [local branch being pushed]```  
- *Typical frequency:* > Daily  
- *Example:* ```git push myremote assignment2```  

### git fetch --all
Downloads ('fetches') all branches and tags from all connected remotes. Downloaded branches are saved locally with the following name structure: ```[remote alias]/[remote branch name]```

#### Detail
- *Command:* ```git fetch --all```  
- *Stands for:* Fetch (download) all branches from connected remotes  
- *Basic usage:* ```git fetch --all```  
- *Typical frequency:* > Daily  
- *Example:*  
  - ```git fetch --all```  
    - Downloaded branches are listed upon downloading  
    - Entire name (including `[remote alias]/`) must be used for any interaction with fetched branches  
  - 'Fetched' branches are *not* displayed by the `git branch` command  
    - To display fetched branches as well, run `git branch --all`  
    - Fetched branches will be displayed as: `remotes/[remote alias]/[branch name]`  
    - Do not include the `remotes/` portion of the name when interacting with the branch  

### git merge [branch name]
Merges work from [branch name] into the branch you currently have checked out.

#### Detail
- *Command:* ```git merge [branch name]```  
- *Stands for:* Merge commits from the specified branch into the currently checked-out branch  
- *Basic usage:* ```git merge [branch name]```  
- *Typical frequency:* > Daily  
- *Examples:*  
  - If I have branch2 and branch4 in my local repository and I want to bring the changes from branch4 into branch2:  
    - ```git checkout branch2```  
    - ```git merge branch4```  
  - If it says 'merge conflict', that means the two branches make changes to the same section of the same file  
    - Git will insert the changes from BOTH branches in the file  
    - Git will insert ```<<<``` within the file(s), before each conflict  
    - Git will insert ```>>>``` within the file(s), after each conflict  
    - It is your job to review what git has added to the files, then to remove what you do not want. Such as '<<<' and '>>>'.  
    - After resolving the conflict, it is your job to add and commit your changes.  
    - Following git workflows such as 'git flow' minimize messy merge conflicts.  

### git pull [remote] [branch name]
Immediately and automatically merges all new changes from ```[branch name]``` on ```[remote]``` to the branch you currently have checked out. When you git pull, make sure you have the branch you want to merge work into already checked out

#### Detail
- *Command:* ```git pull [remote] [branch name]```  
- *Stands for:* Pull (Fetch and then merge) work from [branch name] on [remote]  
- *Basic usage:* ```git pull [remote] [branch name]```  
- *Typical frequency:* > Daily  
- *Example:*  
  - For example, if I want to pull from debugacademy's 'master' branch into my 'branch2' branch  
    - `git checkout branch2`  
    - `git pull debugacademy master`  


## Good to know  
### Help! My command line is stuck.  
Sometimes, especially after a git merge or git commit, people find themselves seeing a bunch of text but being unable to type. If this happened to you, you likely are seeing the text editor 'vim'.  

vim is a popular, advanced command line editor.  
- Press ```escape``` to prepare for the subsequent commands  
- To enable typing, press ```i``` for 'Insert'  
- To save the file, press 'escape', then ```:```, then ```w``` (for write), then ```ENTER```  
- To exit a file and leave vim,  press 'escape', then ```:```, then ```q``` (for quit), then ```ENTER```  
  - You may need to press ```y``` if you have unsaved changed  
