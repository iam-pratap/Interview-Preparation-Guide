`1. what is Git?`

Git is a distributed version control system that is used to track changes in source code during software development. It permits multiple developers to work on a project together without interrupting each other’s changes. Git is especially popular for its speed, and ability to manage both small and large projects capably.

`2. What is a repository in Git?`

A Git repository (or repo) is like a file structure that stores all the files for a project. It continues track changes made to these files over time, helping teams work together evenly. Git can control both local repositories (on your own machine) and remote repositories (usually hosted on platforms like GitHub, GitLab, or Bitbucket), allowing teamwork and backup.

`3. What is the difference between Git and GitHub?`

**Git**
- Git is a version control system used to track changes in files over time.
- It runs locally on your computer.
- Git can be used offline, as it operates locally on your machine.

**GitHub**
- GitHub is a platform where Git repositories can be stored and shared.
- It is a cloud-based service
- GitHub requires an internet connection because it is hosted on the web.

`4. What are the advantages of using GIT?`

Using Git provides multiple advantages:

- It assists teamwork by supporting multiple developers to work on the same project together.
- Each developer has a local copy of the repository, improving performance and enabling offline work.
- Free and widely supported.
- Git supports work on various types of projects.
- Each repository has only one Git directory.

`5. What is the purpose of the .gitignore file?`

The ‘.gitignore’ file tells Git which files and folders to ignore when tracking changes. It is used to avoid attaching unneeded files (like logs, temporary files, or compiled code) to your repository. This saves repository clean and targeted on important files only.

`6.Explain the difference between "git merge" and "git rebase"?`

**Git Merge**
- It is best suited for merging changes from a feature branch into the main branch.
- Creates a merge commit that has two parent commits.
- Preserves the branch history of both branches.

**Git Rebase**
- It is best suited for keeping a clean and linear commit history.
- Rewrites the commit history and creates a linear history with one branch.
- Discards the branch history of the current branch.

`7. What is the difference between git fetch and git pull?`

**Git Fetch**
- Used to fetch all changes from the remote repository to the local repository without merging into the current working directory.
- Inspect remote changes, create new branches, update tracking branches.

**Git Pull**
- Brings the copy of all the changes from a remote repository and merges them into the current working directory.
- Update local branch with remote changes.

`8. What is the difference between git revert and git reset?`

**Git Revert:** 
- It can be used to undo accidental changes or correct changes made while working with others.
- Preserves the commit history by creating a new commit that undoes the change.
- It is a safer option when working with other developers because it doesn’t affect others’ work.

**Git Reset**
- It is more suitable for editing your local changes and cleaning up the commit history.
- Rewrites the commit history by undoing the operations.
- It can cause other developers to lose history and have conflicts in their work.

`9. How do you check the 𝗱𝗶𝗳𝗳𝗲𝗿𝗲𝗻𝗰𝗲𝘀 between 𝘁𝘄𝗼 𝗰𝗼𝗺𝗺𝗶𝘁𝘀 in Git?`

It compares the changes between the specified commits.
Syntax:
```
git diff <commit1> <commit2>
```

`10. How do you check the 𝘀𝘁𝗮𝘁𝘂𝘀 of the 𝘄𝗼𝗿𝗸𝗶𝗻𝗴 𝗱𝗶𝗿𝗲𝗰𝘁𝗼𝗿𝘆 in Git?`

git status

`11. How to resolve a conflict in Git?`

**Identify Conflicting Files:** Use ‘git status’ to find the files where conflicts have take place because of changes from unique branches.
**Correct Files to Repair Conflicts:** Alter the files to sync conflicting changes and block future conflicts.
**Stage solved Files:** Use ‘git add’ to add the resolved files to the staging area. 
**Commit the Changes:** Complete the process by committing the changed files applying ‘git commit’.

`12. What is the HEAD in Git?`

HEAD is a source to the current branch or commit you are working on. HEAD normally shows the recent commit of the current branch and moves when you switch branches or check out exact commits.

`13. Explain Git branching strategy`
