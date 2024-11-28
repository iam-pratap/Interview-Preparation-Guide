`1. What is Git?`

Git is a distributed version control system that helps developers
manage and track changes to their codebase. It allows multiple developers
to work on a project simultaneously and facilitates collaboration by
providing features such as branching, merging, and conflict resolution.

`2. What is a repository in Git?`

A repository, often referred to as a "repo," is a central location where
Git stores all the files and directories of a project, along with their
complete history. It contains the entire version history of the project,
including all the commits and branches.

`3. How do you create a new Git repository?`

To create a new Git repository, you can navigate to the desired
directory in your terminal and use the command ***git init***. This command
initializes a new empty Git repository in the current directory.

`4. What is the difference between Git and GitHub?`

**Git**
- Git is a version control system used to track changes in files over time.
- It runs locally on your computer.
- Git can be used offline, as it operates locally on your machine.

**GitHub**
- GitHub is a platform where Git repositories can be stored and shared.
- It is a cloud-based service
- GitHub requires an internet connection because it is hosted on the web.

`5. What are the advantages of using GIT?`

- It assists teamwork by supporting multiple developers to work on the same project together.
- Each developer has a local copy of the repository, improving performance and enabling offline work.
- Free and widely supported.
- Git supports work on various types of projects.
- Each repository has only one Git directory.

`6. What is the purpose of the "git clone" command?`

The ***git clone*** command is used to create a local copy of a remote Git
repository. It downloads the entire repository, including all its files,
commit history, and branches, to your local machine.

`7. How do you commit changes in Git?`

To commit changes in Git, you need to follow these steps:
1. Use the command ***git add <filename>*** to stage the changes you want
to include in the commit.
2. Use the command ***git commit -m "Commit message"*** to create a new
commit with the staged changes. The commit message should provide a
brief description of the changes.

`8. What is the purpose of the .gitignore file?`

The ‘.gitignore’ file tells Git which files and folders to ignore when tracking changes. It is used to avoid attaching unneeded files (like logs, temporary files, or compiled code) to your repository. This saves repository clean and targeted on important files only.

`9. What is the difference between git fetch and git pull?`

***git fetch*** only downloads the latest changes from the remote repository,
but it doesn't automatically merge them. It updates the remote-tracking
branches, allowing you to review the changes before merging.

***git pull*** is a combination of two commands: ***git fetch*** and ***git
merge***. It fetches the latest changes from the remote repository and
automatically merges them with the local branch.

`10. How do you check the 𝗱𝗶𝗳𝗳𝗲𝗿𝗲𝗻𝗰𝗲𝘀 between 𝘁𝘄𝗼 𝗰𝗼𝗺𝗺𝗶𝘁𝘀 in Git?`

It compares the changes between the specified commits.

Syntax:
```
git diff <commit1> <commit2>
```

`11. How do you check the 𝘀𝘁𝗮𝘁𝘂𝘀 of the 𝘄𝗼𝗿𝗸𝗶𝗻𝗴 𝗱𝗶𝗿𝗲𝗰𝘁𝗼𝗿𝘆 in Git?`

command:
```
git status
```
`12. What is Git conflict? How to resolve a conflict in Git?`

When same name file having different content in different branches, if you do merge, conflicts occur.

When a merge conflict occurs, it means that Git is unable to
automatically merge the changes from different branches. To resolve the
conflict, you need to manually edit the conflicting files to choose the
desired changes. After resolving the conflicts, you can use the ***git add***
command to stage the changes, followed by ***git commit*** to complete the
merge.

`13. How do you push changes to a remote Git repository?`

To push changes to a remote Git repository, you can use the ***git
push*** command followed by the name of the remote repository and the
branch you want to push. For example, ***git push origin main*** pushes the
local commits to the "main" branch of the remote repository named
"origin."

`14. What is the difference between a branch and a tag in Git?`

In Git, a branch is a lightweight movable pointer to a specific commit.
It allows for parallel development and isolates changes from each other.
Developers can create new branches to work on new features or bug fixes.
On the other hand, a tag is a reference to a specific commit that is used to
mark a significant point in the project's history, such as a release or a
stable version.

`15. What is the HEAD in Git?`

HEAD is a source to the current branch or commit you are working on. HEAD normally shows the recent commit of the current branch and moves when you switch branches or check out exact commits.

`16. Explain Git branching strategy`

Let's consider Uber as an example. Initially, they focused solely on cab services, and their code repository was hosted on GitHub. Eventually, the product manager proposed expanding Uber to include intercity travel. To accommodate this new feature, a new branch named intercity@feature was created. Developers worked on this branch, implementing the necessary changes. Once the feature was deemed ready, the changes were merged back into the main master branch.

Assuming Uber was currently on version 2, and they wanted to release a new version, they created a release branch named release-v3 from the latest master branch. This release branch underwent rigorous testing before being deployed to customers. After three days, bug was reported after the deployment, a hotfix branch would be created to address the issue. This hotfix branch would then be merged into both the master and release-v3 branches to ensure the fix was applied to all relevant versions.

`17. from which branch do you usually perform releases?`

Release branch

`18. what is feature branch?`

whenever some people want to introduce new breaking changes to your existing functionality you create feature branches.

`19. which branch that always is updated and up-to-date?`

master, main and trunk branch

`20. what is hotfix branch?`

is a temporary branch created to address critical bugs in a production environment. 

`21. How do you merge two branches in Git?`

To merge two branches in Git, you typically follow these steps:
1. Switch to the branch where you want to merge changes (e.g. ***git
checkout branch-to-merge-into***).
2. Run the command ***git merge branch-to-merge-from***. This merges the
changes from the specified branch into the current branch.
3. Resolve any merge conflicts, if they occur.
4. Commit the merge changes using ***git commit***.

`22. What is the purpose of "git rebase"?  and when would you use it?`

Git rebase is a command used to integrate changes from one branch
onto another by moving or combining commits. It is an alternative to
merging and allows for a cleaner commit history. With rebase, you can
apply a series of commits from one branch onto another, resulting in a
linear commit history.

Git rebase is a command used to modify the commit history of a
branch. It allows you to move, combine, or edit commits. You would use
***git rebase*** when you want to:
- Incorporate changes from one branch onto another with a linear commit
history.
- Squash multiple commits into a single commit for a cleaner history.
- Edit or reorder commits to improve readability or resolve conflicts.

`23. How do you undo the most recent commit in Git?`

To undo the most recent commit in Git, you have a few options:
- You can use the command ***git revert HEAD*** to create a new commit
that undoes the changes introduced by the last commit.
- Alternatively, you can use ***git reset HEAD~1*** to move the branch
pointer back one commit, effectively removing the last commit. This
operation discards the commit and any changes associated with it.

`24. What is the "git stash" command used for?`

The ***git stash*** command allows you to temporarily save changes that
are not ready to be committed yet. It's useful when you need to switch to a
different branch or apply a hotfix but don't want to commit incomplete
work. You can later retrieve the changes from the stash using ***git stash
apply*** or ***git stash pop***.

`25. What is the difference between git revert and git reset?`

**Git Revert:** 
- It can be used to undo accidental changes or correct changes made while working with others.
- Preserves the commit history by creating a new commit that undoes the change.
- It is a safer option when working with other developers because it doesn’t affect others’ work.
- ***git revert [commit-id]***

**Git Reset**
- It is more suitable for editing your local changes and cleaning up the commit history.
- Rewrites the commit history by undoing the operations.
- It can cause other developers to lose history and have conflicts in their work.
- To reset staging area ***git reset [file-name]***
  
`26. How do you revert a file to a previous commit in Git?`

To revert a file to a previous commit in Git, you can use the command
***git checkout <commit-hash> -- <file>***. This command replaces the
content of the specified file with the version from the given commit. It
effectively discards the changes made to the file since that commit.

`27. What is the purpose of the "git cherry-pick" command?`

The ***git cherry-pick*** command is used to apply a specific commit
from one branch onto another branch. It allows you to select individual
commits and apply them to a different branch, without merging the entire
branch. Cherry-picking is useful when you want to selectively apply
changes from one branch to another.

`28. How do you delete a branch in Git?`

To delete a branch in Git, you can use the command ***git branch -d
<branch-name>***. This deletes the specified branch locally. If the branch
has not been merged, you can use ***git branch -D <branch-name>*** to force
delete it. To delete a remote branch, you can use ***git push origin --delete
<branch-name>***.

`29. How do you view the commit history in Git?`

You can use the command ***git log*** to view the commit history in Git

`30. How can you recover a deleted commit in Git?`

If a commit has been deleted or lost, you can use the ***git reflog***
command to find the commit's reference and recover it. Once you identify
the commit hash, you can create a new branch or use ***git cherry-pick*** followed by the **commit-id** to
apply the changes from the recovered commit to the appropriate branch.
