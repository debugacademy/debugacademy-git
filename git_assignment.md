# Intro to Command Line & Git  
In this assignment, we will learn git by using it.  

## Answering questions  
In this assignment, simply edit this homework file itself to answer the questions on it. You will be walked through everything during the assignment.  

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be in your own words**  

## Committing  
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Tasks  
Tasks are listed below.  

### Install Git  
#### Mac OS X  
- Open the command line  
  - This is the program named "Terminal"  
  - Unsure where to find it? Try Mac's spotlight search tool. Press:  
    - `command` + `space`  
    - Type: `Terminal`  
    - Press the `Enter` key  
- Run: ```git --version```  
  - If it displays a version number, git is already installed. You can skip to "Initial Git Configuration".  
  - If you receive an error or warning, git is not yet installed. Continue reading.  

Downloading *Xcode* via the program on your computer named 'App store' is ideal, but it is *very* large download. If you have not already downloaded Xcode before class, try this git alternative: https://git-scm.com/download/mac  

#### Windows  
Use Git for Windows ( ```https://git-for-windows.github.io/``` ) (command line).  

#### Ubuntu  
Use the command ```sudo apt-get install git-core``` to install Git using the command line.  

Follow the installation options that will be presented to you.  

### Github set up  
- Log in to github.com  
  - *You need to create an account on github.com first*  
- Visit:  ```https://github.com/debugacademy/debugacademy-git```  
- Press 'Fork' in the upper right corner of the page  
- You have just created a copy of this repository on your github account!  

### Local set up  
- Open the command line (where git is installed)  
- Run: ```git --version``` to confirm git is working  
  - If you receive an error, git was not installed correctly  
- ```cd``` to your Desktop  
  - Done using: `cd ~/Desktop`  
- Create a new folder named debugacademy within your Desktop:  
  - `mkdir debugacademy`  
- `cd` into that folder  
  - `cd debugacademy`  
    - There is more information on the ```cd``` command in this repository's README.md file.  
- Clone the git repository you are reading by running the following command in your command line:  
    - ```git clone https://github.com/debugacademy/debugacademy-git.git```  

This will create a copy of this repository on your computer, in a folder named debugacademy-git, which will be placed in the folder debugacademy on your desktop, because that is where you ran the ```git clone``` command.  

Wonderful! You now have cloned this repository twice. Once in your github.com account by clicking 'Fork', and once to your local computer using the git clone command. Let's proceed.  

### Create and switch to a new branch  
A branch is a version of your repository. By convention, we don't want to edit the 'master' branch, that version of your repository should continue to match that of Debug Academy's repository.  

- Create a new branch based off of the master branch  
  - ```git checkout -b [new-branch] [base-branch]```  
- Name the branch using the following common convention  
  - `TOPIC-TASK_NUMBER-YOUR_INITIALS`  

For example, Ashraf Abed would run the following command:  
```git checkout -b git-01-aa master```  

### Confirm you are on your new branch  
The ```git branch``` command lists all branches, and tells you what branch you are on by prefixing it with ```*```  

Simply run the ```git branch``` command and confirm you are where you expect to be.  

### Make your first commit  
Git is great for keeping the history of all edits on files. Let's try it out by editing the file you're reading right now!  

HEAD
Fill in your name after this colon: Kevin E. Post  

Optionally, write the company you are representing, if any: N/A

Check the appropriate boxes as they apply to you or the company you represent:  
[X] Interested in hearing about upcoming Debug Academy classes  
[ ] Interested in hiring Drupal developers  
[ ] Interested in discussing something else with Debug Academy  
[ ] None of the above  

You're not done quite yet - git did not save our changes to the history. Changes saved to the git history must be deliberate and explicit; git does not save every edit you do to the history automatically. Imagine how long the list would be if it did!  

Tell git you want this edit included in the next commit using git add:  
- ```git add git_assignment.md```    

Now, create your first commit, saving the change to your repository's history!  
- ```git commit -m '[my commit message]'```  

### Compare branches  
You just switched from the master branch to your new branch, then made an edit and committed it to your new branch. Because branches are versions of the repository, we now have two different versions of the same repository! What does that mean?  

It means that you can simply jump between ( ```git checkout [branch]``` ) your master branch and your new branch, and all of the files in your repository will automatically be updated to the appropriate version!  

Let's try it out. You committed your name above, let's see if it really is only on your new branch.  
- Look at this file and confirm your change really was made  
- Switch to the master branch by running: ```git checkout master```  
- Reload this file and look for the change you made  

What happened to it?  

### Merging work  
We've edited this very file on one branch. What if a coworker edited the same file on their computer, and we want to combine our work?  

In this example, our colleague has added a commit to another branch named git-02-aa and pushed (sent) it to the official Debug Academy repository. We are going to combine their branch with our branch.  

- Download all branches from all repositories.  
  - `git fetch --all`
  - This downloads hidden copies of all branches from all associated remotes.  

- The other branch is named `git-02-aa`, and it is stored on the remote nicknamed `origin`, by default.  

- Switch to your question 1 branch you would like to be combined:  
  - Run: `git checkout QUESTION_1_BRANCH_NAME`  
- Merge (combine) the changes from origin's git-02-aa branch into your current branch:  
  - Run: ```git merge origin/git-02-aa```  
  - You should see a 'merge conflict' error message. Return to editing this file.  

- Review this file - The edits you made to your branch and the edits were automatically combined!  
  - Notice the `<<<`, `===`, and `>>>`  
  - These are merge conflict indicators  
  - They let you know what section of the file needs manually updated, if any  

- You may remove the merge conflict indicators then save the file.  
  - Then, git add and commit the merge:
    - `git add git_assignment.md`  
    - `git commit -m 'Merged branch git-02-aa'`   

### Communicating with remotes  
You've made updates to your local, now you want to share them with teammates. This is where 'remotes' come in.  

Adding a remote is like adding an entry to your phone book. Instead of adding a name and phone number, you add a name and git URL. The concept and governing rules are essentially the same.  

Go to your github account, and click on the debugacademy-git repository which you forked.  
- Copy the ```HTTPS clone URL``` on the right of the page  
- Run the command: ```git remote add me [copied URL]```  
  - This command will add an entry in your 'phonebook', or list of remotes, with your github account's repository.  
  - This command uses `me` as the account nickname. Just like contacts in a phonebook, you could use a different nickname.  

Run ```git remote -v``` to see a list of all entries your repository has in its 'phone book'. Confirm that your github repository is listed.  

### Push work to your repository  
Let us now push one of the branches we have been working on to our Github accounts. After all, a primary point of git is to be able to collaborate.  

```git push me [question 1's branch name]```  

Using the remote ('contact') entry from the previous task, git will send the specified branch to the remote which has the specified nickname in your contacts list.  

### Create a pull request  
Now that you've pushed your work to your github repository, it's time to submit your work from your github repository to the main debugacademy repository.  

Because you don't have permission to push your work to debugacademy's account, you must instead ask debugacademy to pull the work from your account. This is called creating a 'Pull Request', and it is a feature on github.com .  

Once you've pushed your branch to your github repository, visit your github repository, and click 'Create Pull Request' or 'Pull Requests'.  

Review the pull request you are about to create, and confirm its creation. The folks at debugacademy will receive a notification, review your pull request, and merge in the work you have submitted! This is how collaboration on software projects works.  
