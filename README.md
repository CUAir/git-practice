
Like most companies, CUAir has its own developer workflow that we enforce in order to ensure that our software is bug-free and stable while also allowing people to push code as efficiently as possible. While these processes may vary from subteam to subteam, there are a few things that are common to all software subteams:

# Git

CUAir uses Github for version control, which is built on [git](https://en.wikipedia.org/wiki/Git). Version control is best explained as a way for multiple developers to work on the same codebase concurrently. If you have ever had to work on code with someone else before and were unaware of version control systems, you might have tried to email different versions of the code to each other with no easy way to merge code or undo a set of changes, while also having to coordinate timing. Git makes that all simple.

Git is used widely by many top tech companies, and all tech companies (hopefully) use some form of version control, so this is a very valuable skill to pick up in the near future. Git might be confusing and intimidating, but it doesn't have to be, as we can break it down below:

## Git Basics

### Installing Git
If you're a Mac user, it should already be installed on your computer or if it's not, attempt to enter `git --version` into the terminal and it should prompt you to install it if you don't have it on your computer already. Follow the directions and it should be good to go!


If you're on Windows, you can install Git Bash [here](https://git-scm.com/downloads). You can then launch Git Bash and start using Git!

### How to Use Git
We'll guide you all the way to pushing a change onto the repository! The first step is to clone a repository, which is a collection of files (can be thought of the codebase, e.g. ground-server is the repo for the Platform ground server codebase), alongside its history of changes. For this we'll be using the CUAir tutorial repo, `git-practice`. Open up Terminal (Mac) or Git Bash (Windows), navigate to your desired directory and type in

`git clone https://github.com/CUAir/git-practice`.

What this does is essentially clone, or copy the current repository from the `master` branch (we'll cover branches later) to your current working directory. You'll also notice that there is a hidden folder `.git` in the directory, which indicates that this is a git-controlled directory.

Once you clone, you will have a *local repository*. You have just cloned from the *remote repository*. Changes that are pushed to the remote repo will not be reflected on your local repository unless you update your local. We'll go over that later! For now, you can now do:

`git status`
This returns the status of your directory, although I like to consider this "what has changed since the last commit" (commit will be covered later). If you have not changed anything, this is will return nothing.

`git log`
This will print the entire history of the local repository. For Terminal and git bash users this should enter a vim-like interface and so you can hit the space key to continue scrolling, or type 'q' to exit it.

Onto more exciting things! First of all create a new branch (for more info on branches, go to the 'Branching' section) You can do this by: `git checkout -b <your username/useful-name>`, (ex. `git checkout -b ef23/git-tutorial`) The `-b` flag indicates you are switching to a new branch. You can use `git checkout <branch name>` to switch branches, so you can do `git checkout master` to return to the master branch.

On your new branch (you can check which branch you're on by doing `git branch`), create a new file in the local repo and name it after your netid. Enter whatever you'd like into the file and save it. Now, if you enter `git status`, this file should show up as an 'unstaged change'. You can then type `git add <filename>` and assuming you didn't type in your filename wrong, if you `git status` again, that file should now show up as a 'change to be committed'. Now, you can type `git commit -m '<helpful message>'` in and hit enter. Congratulations! You have made your first commit. You can then do `git push -u origin <branch name>` to push this to the remote repo. Navigate to the repo on Github and you should be able to see it there!

There should be a box telling you your recently pushed branches. Click on the "Compare & Pull Request" box to open a new PR. If you don't you can simply click on the "branches" link (next to the # of commits), find your branch, and click "New pull request". Give it an appropriate title, A quick summary in the text box, and click "Open Pull Request". Optionally, if you are in a group, you can request a reviewer to review your changes before you merge it into master. Once you get the approval (or if no one is really available to do it), click "Merge Pull Request".

You have now merged in your change into `master`! However, if you switch back to `master` (remember how to do this?), you'll notice that your change still isn't there! That's because you updated the remote repo, but not your local. You can do this with a `git pull` command. It will "pull" all the changes from the remote `master` into your local `master`.

Congratulations! You have just began from cloning the repository all the way to merging in a change into `master`. The following sections will go into much more depth about exactly what happens. A summary of git operations is shown below:

![git-operations](./git-operations.png)
(source: http://blog.podrezo.com/wp-content/uploads/2014/09/git-operations.png)

## Branching


## Git Practices


## Git Tips & Tricks


# The CUAir Git Flow
your branch --> ground-test --> flight-test --> master!


# Continuous Integration
We use Travis CI


## Pull Requests

## How to open a PR

## How to review a PR
