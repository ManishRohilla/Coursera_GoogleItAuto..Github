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
--> git commit -a -m "statement"
--> git log -p == The p comes from patch, because using this flag gives us the patch that was created.
--> git show commitId == This command takes a commit ID (from git log) as a parameter, and will display the information about the commit and the associated patch.
--> git log --stat == This will cause git log to show some stats about the changes in the commit, like which files were changed and how many lines were added or removed.
--> git diff ==  is equivalent to the diff -u output . git diff shows only unstaged changes by default [[git diff -- staged]]
--> git add -p == will show us the change being added and ask us if we want to stage it or not.
--> git rm filename  git status  git commit -m "" == to remove file from git repository
--> git mv oldfilename newfilename  git status  git commit -m "" == to change name of a file.
--> echo fileIgnore > .gitignore == then add and commit .. 


                                              Undoing Changes Before Committing
--> git checkout filename == to revert changes to modify files before they get staged. This command will restore the file to the latest storage snapshot, which can be either committed or staged
--> git reset filename == to unstage and staged file. [[ git reset HEAD filename ]] 
--> git add * == adds all the files to the staging area.
--> git revert HEADorCommitId== will create a new commit, that is the opposite of everything in the given commit or rollback.

The commit ID is the 40 character long string after the word commit.
This long jumble of letters and numbers is actually something called a hash, which is calculated using an algorithm called SHA1.
Essentially, what this algorithm does is take a bunch of data as input and produce a 40 character string from the data as the output. 
In the case of Git, the input is all information related to the commit, and the 40 character string is the commit ID.
Cryptographic algorithms like SHA1 can be really complex
--> git commit --amend == allows us to modify and add changes to the most recent commit. 

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
****Git is a distributed version control system. Distributed means that each developer has a copy of the whole repository on their local machine.****
