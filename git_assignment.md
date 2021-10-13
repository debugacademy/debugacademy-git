# Intro to Git  
In this assignment, we will learn git by using it.  

## Answering questions  
In this assignment, you will fork (and clone, if you haven't already) this repository (da-assignments), then edit this file itself (git.md) to answer the questions within the assignment. Below, we will walk you through the steps for obtaining the file. Your answers will be submitted as a pull request on github.   

### Global Git configuration -- Let Git know your name and email 
- Open the command line (Windows: Git bash, Mac: Terminal)  
    - *Important*: Windows users should *always* explicitly run Git bash as administrator.  
- Run: `git --version` to confirm git is working 
    - If you receive an error, git was not installed correctly  
- After replacing `[YOUR NAME]` with your name, run: `git config --global user.name "[YOUR NAME]"`  
- After replacing `[YOUR EMAIL]` with your public e-mail, run: `git config --global user.email "[YOUR EMAIL]"`  
- Windows users only: Prevent windows from converting characters by running `git config --global core.autocrlf false` in your command line. 

### Git configuration for our development project
- cd into your drupal folder  
  - `cd ~/Desktop/debugacademy/drupal`  
- After replacing `[YOUR NAME]` with your name, run: `git config user.name "[YOUR NAME]"`  
- After replacing `[YOUR EMAIL]` with your e-mail, run: `git config user.email "[YOUR EMAIL]"`  

### Assignments repository set up
**If you have already cloned the da-assignments folder into debugacademy, skip this step.**
- `cd` to the debugacademy folder:  
    - `cd ~/Desktop/debugacademy`  
- Clone the da-assignments repository that contains our assignments by running the following command in your command line:  
    - `git clone https://github.com/debugacademy/da-assignments.git`  

This will create a copy of the da-assignments repository on your computer, which will be placed where you ran the `git clone` command.  

Outside of the command line, confirm that the da-assignments folder now exists at ~/Desktop/debugacademy/da-assignments .  

You have now cloned this repository twice. Once in your github.com account, and once to your local computer. Let's proceed.  

### Create and switch to a new branch  
A branch is a version of your repository. Just like on a real gitflow-based project, we never want to edit the 'main' or 'develop' branches directly. Those versions of your repository should continue to match that of Debug Academy's repository for the entire project.  

- `cd` into the da-assignments folder
- Ensure you have the latest branches downloaded:
  - `git fetch --all`  
- Create a new branch based off of the *develop* branch, which is our base branch using the gitflow workflow  
  - `git checkout -b [new branch name] [base branch name]`  
- Name the branch using the following common convention  
  - [Topic]-[Task Number]-[Your initials]  

For example, Ashraf Abed would run the following command:  
  -`git checkout -b git-003-aa origin/develop`  

### Confirm you are on your new branch  
The `git branch` command lists all branches, and tells you what branch you are on by denoting it with `*`  

Run the `git branch` command and confirm you are on the new branch you just created.  

### Make your first commit  
Git is great for keeping the history of all edits on files. Let's try it out by editing the file you're reading right now!  

Open this file from within your da-assignments folder using your preferred code-friendly text-editor, such as VSCode or Sublime Text.  

- Fill in your name after this colon:  

You're not done quite yet. Changes saved to the git history must be deliberate; git does not save every edit you do to the history automatically. Imagine how long the list would be if it did!  

"Stage" your edit so that it will be included in your next commit:  
- Save this file  
- In your command line window, cd into the da-assignments folder if you are not already there
- Run `git status` to see what files were modified.
- Run `git add [filename]` , after replacing `[filename]` with the name of this file    
You just told git "The next time I commit something to history, I want the changes to `[filename]` to be included."  

Commit your edit!  
- In your command line window, run `git commit -m '[my commit message]'`  , after replacing `[my commit message]` with a very short description of your changes.  
- It's good practice to prefix the description with the assignment number, like: `003 - First commit in assignment 3`  

### Compare branches  
You just switched from the develop branch to your new branch, then made an edit and committed it to your new branch. Because branches are versions of the repository, we now have multiple different versions of the same repository. What does that mean?  

It means that you can simply switch between ("checkout") your develop branch and your new branch, and all of the files in your da-assignments folder will automatically be updated to the appropriate version!  

Let's try it out. You committed your name above, let's see if it really is only on your new branch.  
- Look at your file in your text editor. Confirm the change you made (entering your name) is there
- In the command line, switch back to the develop branch. `git checkout develop`  
- Reload the file and look for the change you made, if you are on your develop branch you should not see it  

### Fork the da-assignments repository -- Allows submission of future homework assignments  
**If you have previously forked the da-assignments repository, skip this section.**  
- Log in to github.com  
- Visit:  `https://github.com/debugacademy/da-assignments`  
- Press 'Fork' in the upper right corner of the page (if you have not previously done so)  
- You have just created a copy of this repository on your github account!  
- Keep this window open for the next step!

### Communicating with remotes  
You've made updates to your local branch, now you want to share those updates with teammates. This is where 'remotes' come in.  

Adding a remote is like adding a contact to your phone book. Instead of adding a name and phone number, you add a name and git URL. The concept and governing rules are the same.  

- View the da-assignment repository on your github account (this is the page you were redirected to after 'fork'ing da-assignments in the previous task.)  
  - Did you accidentally close that window? If so, do the following to get it back: Log in to github, visit the homepage, under 'Your repositories' click the da-assignments repository which you forked.  
- Under the "Clone or Download" button, copy the `HTTPS clone URL`    
- In the command line, cd into your local da-assignments folder: cd ~/Desktop/debugacademy/da-assignments
- Run the command: `git remote add me [copied URL]`   
  - Just like a contact in your phone, you can enter any name you want. I recommend simply using `me` as the nickname for your own account.
- For example, Ali would run the following command: `git remote add me https://github.com/AliHassan7/da-assignments.git`  
  - This command will add a contact in your 'phonebook', or list of remotes, with your github account's repository.  
- Additionally, paste the URL of your remote to the #students room in slack. We will use this soon.  

Run `git remote -v` to see a list of all entries your repository has in its 'phone book'. Confirm that your github repository is listed, in addition to the Debug Academy remote, named 'origin'.  

### Push work to your github repository  
A primary benefit of using git is being able to collaborate. Push the branch we have been working on to our Github accounts.  

`git push [your remote's nickname] [branch you would like to push]` 
- For example, Ali would run the following command: `git push me git-003-ah`  

Using the remote ('contact') entry you created in the previous task, Git will send the specified branch, `[branch you would like to push]`, to the specified remote, `[your remote's nickname]`, which you entered into your 'contact book' in the previous task.  

### Add your instructor's remote contact info
Next, add your instructor's github repository as a remote git connection so that we can communicate with it.  
- Run the command: `git remote add ashraf https://github.com/ashabed/da-assignments.git`  
  - You have added a "contact" to your phone book  
  - The nickname for the contact is "ashraf"  
  - That nickname now points to the instructor's github repository  

Run `git remote -v` to confirm you have saved the remotes for debugacademy, your account, and the instructor's account.  

### Merging work  
We've edited this very file on our branch, and the instructor has edited it on their branch. What if we want to combine work from the two branches?  

- Switch to the branch you completed this assignment on  
  - `git checkout [my branch name]`  
    - If you are unsure of your branch's name, run `git branch` to see a list of available branches  
- Run `git fetch --all` to download work from all remotes  
- Run `git branch -r` to view a list of the remote branches available to us  
- Run `git merge ashraf/git-003-aa` to merge the work from your instructor's remote into your local branch.  
- The edits you've made to your git.md file and the edits the instructor made to their git.md file should automatically be combined!  

### Fix merge conflicts
You and your classmate edited the same line in the same file, so there will be a conflict. Your terminal/gitbash will inform you of the conflict.  

You can see the actual conflict by opening your git.md file in your text editor. Fix the merge conflict by cleaning up the text containing your and your instructor's names from question 1. You can do this however you like - with a comma, or rewrite it in another way. After this, commit your changes by repeating the following steps:  
- Save this file  
- In your terminal, run `git status` to see what files were modified.  
- In your terminal, run `git add [filename]`    
Next up, commit your edit!  
- In your terminal, run `git commit -m '[my commit message]'`  
- A sample commit message could be 'Git-003 - Merged Ashraf's git file'  
- Push your work to your fork of the da-assignments repository on github by repeating the steps under the heading "Push work to your github repository"  

### Create a pull request  
Now that you've merged your edits to the git.md file (the file you are reading) along with the edits of your instructor, it's time to submit your work from your github repository to the main debugacademy repository.  

Because you don't have permission to push your work to debugacademy's account, you must instead ask debugacademy to pull the work from your account. This is called creating a 'Pull Request', and it is a feature on github.com .  

Once you've pushed your branch to your github repository, visit your github repository, and click 'Create Pull Request' or 'Pull Requests'.  

The folks at debugacademy will receive a notification, review your pull request, and they can merge in the work you have submitted!   
