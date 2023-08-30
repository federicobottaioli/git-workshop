# Git Workshop

## Intro to Git and GitHub

### Step 0: Install git and create a GitHub account

The best way to install git is to follow the git guide at https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

While there are some great git GUIs (graphical user interfaces, like GitKraken), I think it's easier to learn git using git-specific commands first and then to try out a git GUI once you're more comfortable with the command.

After the installation of git run the following commands:

```sh
git config --global user.name "Your Name"
git config --global user.email "
```

### Step 1: Create a new repository on your GitHub

Clone the repository to your local machine

```sh
git clone <repo url>
```

### Step 2: Add a new file to the repo

Add a new file to the project, using any text editor you like or running a touch command if you are on mac/linux

```sh
touch newFile.txt
```

After creating the new file, you can use the git status command to see which files git knows exist.

```sh
git status
```

It should show something like

```sh
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	git-workshop.md

nothing added to commit but untracked files present (use "git add" to track)
```

### Step 3: Add a file to the staging environment

```sh
git add . # adds all created or modified files
git add newFile.txt # adds only newFile.txt
```

You can use git status again to see which files are staged for the next commit.

```sh
git status
```

It should show something like

```sh
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   newFile.txt
```

### Step 4: Create a commit

```sh
git commit -m "My first commit"
```

You should see an output similar to this:

```sh
[master (root-commit) 0b0d0a1] My first commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 newFile.txt
```

You can see the commit you just created by running git log

```sh
git log
```

It should show something like

```sh
commit 0b0d0a1b2c3d4e5f6a7b8c9d0e1f2a3b4c5d6e7f (HEAD -> master)
Author: Your Name <
Date:   Mon Aug 23 19:28:35 2021 -0400

    My first commit
```

Now, we can push the local changes to the remote repo

```sh
git push
```

### Step 5: Create a new branch

Now that you've made a new commit, let's try something a little more advanced.

```sh
git checkout -b <my branch name>
```

This will create a new branch and switch to it. It uses as base branch, the branch you were on when you ran the command.

You can use git branch to see which branch you're currently on and all your local branches.

```sh
git branch
```

It should show something like

```sh
* <my branch name>
  main
```

### Step 6: Make a change to the new branch

Create a new file in the project

```sh
touch newFile2.txt # use this command on mac/linux
ECHO >> filename.txt # use this command on windows

git add .
git commit -m "My second commit"
```

### Step 7: Push a branch to GitHub

```sh
git push -u origin <my branch name>
```

### Step 8: Create a pull request

Go to your GitHub repository and click on the "Compare & pull request" button

![pull-request](https://cloud.githubusercontent.com/assets/5241432/9189500/4688c07e-3fb7-11e5-99ed-d75b50ed9e48.png)

And this is what it looks like once you've submitted the PR request:

![pull-request-sent](https://cloud.githubusercontent.com/assets/5241432/9189528/b39a7176-3fb7-11e5-87b1-7fed3e63b6bb.png)

### Step 9: Merge a pull request

Click on the "Merge pull request" button to merge the pull request

![merge-pull-request](https://cloud.githubusercontent.com/assets/5241432/9189587/76631d98-3fb8-11e5-9fdb-17e7dec1c2a4.png)

### Step 10: Pull the changes locally

```sh
git checkout main
git pull
```

It will show something like this

```sh
From
* branch            main       -> FETCH_HEAD
Updating 0b0d0a1..f1f2f3f
Fast-forward
  newFile2.txt | 0
  1 file changed, 0 insertions(+), 0 deletions(-)
  create mode 100644 newFile2.txt
```

Now we can use the git log command again to see all new commits.

```sh
git log
```

It should show something like

```sh
commit f1f2f3f4g5h6i7j8k9l0m1n2o3p4q5r6s7t8u9v (HEAD -> main, origin/main, origin/<my branch name>, <my branch name>)
Author: Your Name <
Date:   Mon Aug 23 19:28:35 2021 -0400

    My second commit

commit 0b0d0a1b2c3d4e5f6a7b8c9d0e1f2a3b4c5d6e7f
Author: Your Name <
Date:   Mon Aug 23 19:28:35 2021 -0400

    My first commit
```
### Some common errors...

#### Error: failed to push some refs to '

```sh
git pull origin main
```

```sh
git push origin main
```

#### Error: Updates were rejected because the remote contains work that you do not have locally.

```sh
git pull origin main
```

#### Error: The current branch <branch name> has no upstream branch.

```sh
git push -u origin <branch name>
```

###
