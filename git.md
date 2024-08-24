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

‘git merge‘ merges changes from one branch into another, keeping distinguish branch histories. It forms merge commits that directly show where branches came together. ‘git rebase‘ reforms history by using commits from one branch onto another, causing in a linear sequence of commits. Prefer ‘merge’ to keep distinct branch timelines and use ‘rebase’ for enhancing commit history before merging branches.

`7. What is the difference between git fetch and git pull?`

‘git fetch’ fetches updates from a remote repository but does not combine them into your local repository. It fetches all the new data from the remote repository that you don’t have yet, but it stores it in a separate area, permitting you to review the changes before merging them into your working directory.

‘git pull‘ fetches the updates from the remote repository and instantly strives to merge them into your current branch. It is basically a union of ‘git fetch’ followed by ‘git merge’ .

`8. How do you check the 𝗱𝗶𝗳𝗳𝗲𝗿𝗲𝗻𝗰𝗲𝘀 between 𝘁𝘄𝗼 𝗰𝗼𝗺𝗺𝗶𝘁𝘀 in Git?`

It compares the changes between the specified commits.
Syntax:
```
git diff <commit1> <commit2>
```

`9. How do you check the 𝘀𝘁𝗮𝘁𝘂𝘀 of the 𝘄𝗼𝗿𝗸𝗶𝗻𝗴 𝗱𝗶𝗿𝗲𝗰𝘁𝗼𝗿𝘆 in Git?`

git status

`10. How to resolve a conflict in Git?`

**Identify Conflicting Files:** Use ‘git status’ to find the files where conflicts have take place because of changes from unique branches.
**Correct Files to Repair Conflicts:** Alter the files to sync conflicting changes and block future conflicts.
**Stage solved Files:** Use ‘git add’ to add the resolved files to the staging area. 
**Commit the Changes:** Complete the process by committing the changed files applying ‘git commit’.
