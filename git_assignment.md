# Intro to Git  
In this assignment, we will learn git by using it.  

## Answering questions  
In this assignment, simply edit the homework file itself to answer the questions on it. Your answers will be submitted as a pull request on github.  

**You CAN use lessons provided by the class as well as google to answer the questions, but all answers must be in your own words**  

## Committing  
Your commits should always be clear, concise explanations of what is being committed. They should be granular and easy to review.  

## Tasks  
Tasks are listed below.  

### Github set up  
- Log in to github.com  
- Visit:  ```https://github.com/debugacademy/debugacademy-git```  
- Press 'Fork' in the upper right corner of the page  
- You have just created a copy of this repository on your github account!  

### Local set up  
- Open the command line (where git is installed)  
- Run: ```git --version``` to confirm git is working  
  - If you receive an error, git was not installed correctly  
- ```cd``` to where you would like this repository to reside on your computer  
    - e.g. I would like to work in ```~/Sites```, so I will open the terminal and run ```cd ~/Sites```  
    - There is more information on the ```cd``` command in this repository's README.md file.  
- Clone the git repository you are reading by running the following command in your command line:  
    - ```git clone https://github.com/debugacademy/debugacademy-git.git```  

This will create a copy of this repository on your computer, in a folder named debugacademy-git, which will be placed where you ran the ```git clone``` command.  

Wonderful! You now have cloned this repository twice. Once in your github.com account, and once to your local computer. Let's proceed.  

### Create and switch to a new branch  
A branch is a version of your repository. We don't want to edit the 'master' branch - that version of your repository should continue to match that of Debug Academy's repository.  

- Create a new branch based off of the master branch  
  - ```git checkout -b [new-branch] [base-branch]```  
- Name the branch using the following common convention  
  - [Topic]-[Task Number]-[Your initials]  

For example, Ashraf Abed would run the following command:  
```git checkout -b git-01-aa master```  

### Confirm you are on your new branch  
The ```git branch``` command lists all branches, and tells you what branch you are on by denoting it with ```*```  

Simply run the ```git branch``` command and confirm you are where you expect to be.  

### Make your first commit  
Git is great for keeping the history of all edits on files. Let's try it out by editing the file you're reading right now!  

Fill in your name after this colon: Ahmed Malik 

You're not done quite yet. Changes saved to the git history must be deliberate; git does not save every edit you do to the history automatically. Imagine how long the list would be if it did!  

Stage your edit so that it will be included in the next commit:  
- ```git add [filename]```    
Commit your edit!  
- ```git commit -m '[my commit message]'```  

### Compare branches  
You just switched from the master branch to your new branch, then made an edit and committed it to your new branch. Because branches are versions of the repository, we now have two different versions of the same repository! What does that mean?  

It means that you can simply jump between ( ```git checkout [branch]``` ) your master branch and your new branch, and all of the files in your repository will automatically be updated to the appropriate version!  

Let's try it out. You committed your name above, let's see if it really is only on your new branch.  
- Review the change to confirm it was made  
- Switch to the master branch. ```git checkout master```  
- Reload the file and look for the change you made  

What happened to it?  

### Create another branch based off of master  
Name this branch git-02-[your initials]  
You've done this before! Look at the earlier notes to see how it's done.  

### Commit to the latest branch  
On your newest branch, write the company you are representing, if any: [right here]  

Also, (optionally) check the appropriate boxes as they apply to you or the company you represent:  
[ ] Interested in hearing about upcoming Debug Academy classes  
[ ] Interested in hiring Drupal developers  
[ ] Interested in discussing something else with Debug Academy  

Wonderful - more edits have been made, but this time on a different branch (version of the repository.) Stage and commit your changes, as you have done before.  

Now, switch between your branches and refresh this file to confirm that the edits you've made are saved to only their branches.  

### Merging work  
We've edited this very file on one branch, and then we've edited it once again on a different branch. What if we want to combine our work from the two branches?  

- Switch to one of the branches you would like to be combined  
- Run ```git merge [other branch]```  
- The edits you've made to your two branches should automatically be combined!  

### Communicating with remotes  
You've made updates to your local, now you want to share them with teammates. This is where 'remotes' come in.  

Adding a remote is like adding an entry to your phone book. Instead of adding a name and phone number, you add a name and git URL. The concept and governing rules are essentially the same.  

Go to your github account, and click on the debugacademy-git repository which you forked.  
- Copy the ```HTTPS clone URL``` on the right of the page  
- Run the command: ```git remote add [nickname] [copied URL]```  
  - This command will add an entry in your 'phonebook', or list of remotes, with your github account's repository.  

Run ```git remote -v``` to see a list of all entries your repository has in its 'phone book'. Confirm that your github repository is listed.  

### Push work to your repository  
Let us now push one of the branches we have been working on to our Github accounts. After all, a primary point of git is to be able to collaborate.  

```git push [remote's nickname] [branch you would like to push]```  

Using the remote ('contact') entry from the previous task, git will send the specified branch to the remote which has the specified nickname in your contacts list.  

### Create a pull request  
Now that you've pushed your work to your github repository, it's time to submit your work from your github repository to the main debugacademy repository.  

Because you don't have permission to push your work to debugacademy's account, you must instead ask debugacademy to pull the work from your account. This is called creating a 'Pull Request', and it is a feature on github.com .  

Once you've pushed your branch to your github repository, visit your github repository, and click 'Create Pull Request' or 'Pull Requests'.  

Review the pull request you are about to create, and confirm its creation. The folks at debugacademy will receive a notification, review your pull request, and merge in the work you have submitted!  
