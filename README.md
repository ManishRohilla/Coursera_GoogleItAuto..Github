# Coursera_GoogleItAuto..Github

Git or VCS Version Control System

Historical Copies

most primitive form of version control, keeping historical copies.
These copies let you see what the project was like before, and go back to that version if you end up deciding that the latest changes were wrong. 
They also let you see the progress of the changes over time, and maybe even help you understand why a change was made. We say that this is primitive because it's very
manual and not very detailed. First, you need to remember to make the copy. Second, you usually make a copy of the whole thing, even if you're only changing one small part.

Differences in files

--> diff filename filename
TO get the difference between two files line by line.

--> diff -u filename filename
To get the differences between 2 files line by line with "+" "-" symbols to highlight changes.

--> diff -u old_file new_file > change.diff
To get the differences between old_file and new_file and save those changes to change.diff 

**The wdiff command highlights the words that changed in a file by color, in addition to working line by line.

#############################################################################################

Applying changes to files.

--> patch afterchange_file < applychangesfrom_file
To apply changes from applychangesfrom_file to afterchange_file


A VCS even provides a mechanism to allow the author of a commit to record why the change was made, including what bugs, tickets or issues were fixed by the change. 

###############################################################
First Step with github 

Git keeps record about who made changes to the file and for that git needs to know, "WHO YOU ARE?" and to set ur identity in git these commands are followed.

--> git config --global user.email "abc@gmail.com"

--> git config --global user.name "Name"

Make Directory -- mkdir DirName
Change to directory -- cd DirName

----- To initialize git to a directory-----
Change current directory to directory you want to initialize for git by using "cd" command
--> git init    [Enter this command to initialize to that directory]

-- To see the files in directory initilaized for git --

--> ls -la  command which lists files that start with a dot

--> ls -l .git  

*****
>The git directory contains all the changes and their history and the working tree contains the current versions of the files.
>The staging area which is also known as the index is a file maintained by Git that contains all of the information 
about what files and changes are going to go into your next command.
*****

To Copy a file
--> cp locationWITHfilename (make sure your current directory is the one where you want to copy it.)

To make Git track our file, we'll add it to the project using the git add command passing the file that we want as a parameter.
--> git add filename

To check status 
--> git status

To commit or add changes in file
--> git commit

and then u will be asked to enter the statement "briefing about the changes u made".
--> git commit -m "statement"



Git project will consist of three sections.
The Git directory, The Git directory contains the history of all the files and changes. 
The working tree, The working tree contains the current state of the project, including any changes that we've made. 
The staging area, And the staging area contains the changes that have been marked to be included in the next commit.
***************************************************************************************************************************************************
Question
When committing new files or changes with git commit, the user is asked to provide a commit message. What will happen if an empty commit message is entered?
Ans--The commit will be aborted.

To get all the commit messages with detailed information about when the changes are made.
-->git log


MCQ WEEK 1
TOTAL POINTS 5

Question 1
Before changes in new files can be added to the Git directory, what command will tell Git to track our file in the list of changes to be committed?
-git status
-git add
-git commit 
-git init

Correct
Right on! git add will add a file to the staging area and mark it for tracking.


Question 2
Which command would we use to review the commit history for our project?
-git clone
-git status
-git config -l
-git log

Correct
Awesome! git log will give us information about the author of each commit, its timestamp, and each commit message.

Question 3
What command would we use to make Git track our file?
-git clone
-git status
-git add
-git log

Correct
Great work! git add is used to make git mark our file as tracked.

Question 4
Which command would we use to look at our config?
-git clone
-git status
-git config -l
-git log

Correct
Great work! git config -l is used to check the current user configuration.

Question 5
Which command would we use to view pending changes?
-git clone
-git status
-git config -l
-git log

Correct
Woohoo! git status is used to retrieve information about changes waiting to be committed.

**********************************************************************************************************************************

--> git commit -a == is a shortcut to stage any changes to tracked files only and commit them in one step. git add is not required.

--> git commit -a -m "statement".

--> git log -p == The p comes from patch, because using this flag gives us the patch that was created.

--> git show commitId == This command takes a commit ID (from git log) as a parameter, and will display the information about the commit and the associated patch.

--> git log --stat == This will cause git log to show some stats about the changes in the commit, like which files were changed and how many lines were added or removed.

--> git diff ==  is equivalent to the diff -u output . git diff shows only unstaged changes by default [[git diff -- staged]].

--> git add -p == will show us the change being added and ask us if we want to stage it or not.

--> git rm filename  git status  git commit -m "" == to remove file from git repository.

--> git mv oldfilename newfilename  git status  git commit -m "" == to change name of a file.

--> echo fileIgnore > .gitignore == then add and commit. 


                                              Undoing Changes Before Committing
--> git checkout filename == to revert changes to modify files before they get staged. This command will restore the file to the latest storage snapshot, which can be either committed or staged.

--> git reset filename == to unstage and staged file. [[ git reset HEAD filename ]] .

--> git add * == adds all the files to the staging area.

--> git revert HEADorCommitId== will create a new commit, that is the opposite of everything in the given commit or rollback.

--> git commit --amend == allows us to modify and add changes to the most recent commit. 

--> git commit -a --amend == allows us to modify and add changes to the most recent commit. 

The commit ID is the 40 character long string after the word commit.
This long jumble of letters and numbers is actually something called a hash, which is calculated using an algorithm called SHA1.
Essentially, what this algorithm does is take a bunch of data as input and produce a 40 character string from the data as the output. 
In the case of Git, the input is all information related to the commit, and the 40 character string is the commit ID.
Cryptographic algorithms like SHA1 can be really complex


                                       Branching
--> git branch == list all the branches of our repository.

--> git branch BranchName == To create a new branch.

--> git checkout BranchName == To switch to other branch.

--> git checkout -b BranchName == To create and switch to other branch in one go.

--> git branch -d BranchName == To delete a branch.

--> git merge BranchName == To merge the branch to the current pointing or working head branch.

****Merging is the term that Git uses for combining branch data and history together. After merging both points at the same commit.****
****Git uses two different algorithms to perform a merge, fast-forward and three-way merge.****
**** If two different branches have same files and both have gone thru some changes recently and commit, during the time of merging it will cause conflict.****

QUES- How does git checkout switch branches?
ANS - By updating the working tree to match the selected branch.

--> git log --graph --oneline == for seeing the commits as a graph, and --oneline to only see one line per commit

--> git log --graph --oneline --all

****Git is a distributed version control system. Distributed means that each developer has a copy of the whole repository on their local machine.****
#GitHub Cloning using url.
--> git clone HTTPlink == To make a clone.

--> git push == To pass every change u made on ur local repo to main GitHub.

--> git push - u origin branchName == to create the corresponding remote branch. 

--> git config --global credential.helper cache == To store credentials in cache, will be valid for interval of 15 minutes. Dont have to enter username and password for valid intervals again and again.

# Ques--What will happen if the master repository receives a major update since the last local copy was synced?
# ANS----Git will let you know it's time for an update.

--> git remote -v == Run this command in directory of the repo,the two URLs associated with the origin remote,to fetch data and to push data.

--> git remote show origin == Similar to remote -v just more detailed.

--> git branch -r == To get the list of branches that is being tracked by Git Repository.

--> git pull == To get every change from remote repo to local repo and merge it automatically implicitly.


# Ques- If we want to make a change to a remote branch, what must we do?
# Ans- Pull the remote branch, merge it with the local branch, then push it back to its origin.

# Ques- What???s the main difference between git fetch and git pull?
# Ans- git fetch fetches remote updates but doesn't merge; git pull fetches remote updates and merges.

# Ques- What should you do with the <<<<<<<, =======, and >>>>>>> conflict markers when resolving a merge conflict?
# Ans- Remove all of the conflict markers and only leave the code as it should be after the merge.

--> git fetch == To sync the data, This command copies the commits done in the remote repository to the remote branches, so we can see what other people have committed.

--> git merge origin/master == To merges the origin/master branch into our local master branch. We'll call git merge origin/master(online repo) with local repo.

--> git remote update == If we want to get the contents of remote branches without automatically merging any contents into the local branches, we can call git remote update.

**git pull will merge branches with fast-forward algo. automatically**

Once our branch has been properly reviewed and tested, it can get merged back into the master branch. One option is to use the git merge command. Another option is to use the git rebase command. 

**Rebasing means changing the base commit that's used for our branch. Uses fast-forward merge**

# Ques- What does ???git rebase refactor??? do?
# Ans - Move the current branch on top of the refactor branch

--> git rebase BranchName == Move the current branch on the top of BranchName.

--> git rebase --continue == To continue the rebasing that was failed due to any conflict.
**A pull request is a commit or series of commits that you send to the owner of the repository so that they incorporate it into their tree. **
**Forking is a way of creating a copy of the given repository so that it belongs to our user. In other words, our user will be able to push changes to the forked copy, even when we can't push changes to the other repo.**

--> git rebase-i master == a text editor opens with a list of all the selected commits from the oldest to the most recent. By changing the first word of each line, we can select what we want to do with the commits. The **default action here is pick which takes the commits and rebases them against the branch we selected.**

--> git show == To see the latest commit and the changes in it.

--> git push -f == to force git to push the current snapshot into the repo as is.

**lots of Python projects, use the PEP8 style guide.**
**Continuous Delivery means new code is often deployed with the goal of avoiding rollouts with lots of changes between two versions**
**A continuous integration system will build and test our code every time there's a change. **
** you're "downstream" when you copy (clone, checkout, etc) from a repository. Information is flowed "downstream" to you.
When you make changes, you usually want to send them back "upstream" so they make it into that repository so that everyone pulling from the same source is working with all the same changes.**

--> git remote add upstream https://github.com/[git-username]/it-cert-automation-practice.git == Setting the upstream for a fork you have created using the following command:





