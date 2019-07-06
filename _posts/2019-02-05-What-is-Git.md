---
title: 'What is Git ? How to use it ? Why to use it ?'
published: true
---

In this post I’m going to explain you what is Git and how you can quickly get
started with git. Since many of you might have heard of git very often but never
understood what it exactly means and how to use it. You have stumbled upon the
right place.

![](https://cdn-images-1.medium.com/max/400/1*Wjxx83j-qyiNvFBy1yOA1w.jpeg)

Git is a **Distributed Version Control System (VCS)** which is originally
developed in 2005 by Linus Torvalds (Creator of Linux) & Open Source in nature
i.e freely available to use. It’s the most popular and most used tool right now.

Let’s understand what does Version Control means here:

**Version control systems** Are a category of software tools that help a
software team manage changes to source code over time.Version control
software keeps track of every modification to the code in a special kind
of database. If a mistake is made, developers can turn back the clock using
rollback or revert and compare earlier versions of the code to help fix the
mistake while minimizing disruption to all team members.

![](https://cdn-images-1.medium.com/max/800/1*KJ7hP_B3MZOHyqXLOWxs6g.png)
<span class="figcaption_hack">Distributed Version Control System.</span>

### Let’s quickly get started with using Git

First lets quickly grab the git from the official site which is Git SCM
[https://git-scm.com/](https://git-scm.com/)

After installing from here, Open your Terminal and type

    git --version


It will show you the version of git installed in your local machine. Now go
ahead and create a folder and Initialize a git Repository.


    mkdir git-sample-repo && cd git-sample-repo

    git init


The `git init` command adds a Local Git Repository to the project folder.

Now create a simple Hello-World.txt in your folder and add some content in it.


    touch Hello-World.txt


### Staging & Committing the Changes

Unlike the other systems, Git has something called the “staging area” or
“index”. This is an intermediate area where *commits can be formatted*** ***and
reviewed *before completing the commit.

One thing that sets Git apart from other tools is that it’s possible to quickly
**stage some of your files** and commit them without committing all of the other
modified files in your working directory or having to list them on the command
line during the commit.

![](https://cdn-images-1.medium.com/max/600/1*diRLm1S5hkVoh5qeArND0Q@2x.png)

    git add .
         
            OR

    git add Hello-World.txt

The command git add * adds all the files in the staging area.

Now let’s `commit` the changes made by us.

    git commit -m "Added the First Commit"

“Added the First Commit” is the commit message here. Enter a relevant commit
message while the -m are the options.

A shorthand version of `Staging & Committing is`

    git commit -am "Initial Commit"

### Git Status and Git Log and Diff

Now modify the `Hello-World.txt`** **file by adding few more lines.

#### Status

Use `git status` to find out information regarding what files are modified and
what files are there in the staging area.

    git status

The status shows that `Hello-World.txt` is modified and is not yet in the
staging area.

    git add 

### Log

Use `git log` to print out all the commits which have been done up until now.

    git log

The log shows the author of each commit, the date of the commit, and the commit
message.

### Diff Tool

Use `git diff` to show unstaged changes between your index and working
directory. It is a multi-use Git command that when executed runs a diff function
on Git data sources. These data sources can be commits, branches, files and
more. The `git diff` command is often used along with `git status` and `git log`
to analyze the current state of a Git repo.

    git diff

### Branches

The Git feature that really makes it stand apart from nearly every other SCM out
there is its branching model. Up until now we have not created any branch in
Git. By default, Git commits go into the **master** branch.

#### What is a branch?

**Git branches are effectively a pointer to a snapshot of your changes**. When
you want to add a new feature or fix a bug — no matter how big or how small —
you spawn a new branch to encapsulate your changes.* *So currently the master
branch is a pointer to the second commit `“Added Some Content in File”`. Diagram
shows the master branch. We always create branches for Features in our Project.

![](https://cdn-images-1.medium.com/max/600/1*MzdzZ1KxfolwMfLSFCzRYw.png)

#### Create a New Branch

Create a new branch called **sample **using the following command:


This command creates the `sample` branch.

We are still in the context of the master branch. In order to switch to the
`sample `branch. use the following command:


Now we are in the `sample` branch.

You can list out all the branches in local using the following command:


#### Let’s do some Commits in the New Branch

Modify `Hello-World.txt` by adding the following snippet:

    Hello World 
    Adding some Content 
    Adding some Content from sample Branch. Seems Nice!!

Now stage and commit using the following commands:


This commit was done in the Sample Branch, and now Sample Branch is ahead of
Master Branch by 1 commit — as the Sample branch also includes the 2 commits
from the master branch.

You can verify the commit history in Sample Branch using:

    git log

### Merging

The `git merge` command lets you take the independent lines of development
created by `git branch` and integrate them into a single branch. Currently,
Sample Branch is ahead of the Master by 1 commit. Let’s say that now we want all
the code in the Sample Branch to be brought back to the Master Branch. This is
where `git merge` is very useful. It will combine multiple sequences of commits
into one unified history.

First go back to the master branch:


Then run the `merge` command:


After running these 2 commands, the merge should be successful. In this example,
there are no conflicts.

But in real projects, there will be conflicts when a merge is being done.
Resolving the conflict is something which comes with experience, so as you work
more with Git you will be able to get the hang of resolving conflicts.

Run `git log`** **now and you will notice that the master also has 3 commits.

### The Remote Git Repository

Until now, we have been working only in the local repository. Each developer
will work in their local repository but eventually, they will push the code into
a remote repository. Once the code is in the remote repository, other developers
can see and modify that code.

![](https://cdn-images-1.medium.com/max/600/1*Mb_smSHTF7LeZrclYJBcGg.png)

Here we will be using **GitHub** it is like your Google Docs, except you can
create & save your version of the code offline, before ‘**pushing**’ it to be
saved online. Alternatives such as Bit Bucket are available.

![](https://cdn-images-1.medium.com/max/600/1*6QWMn0DApM4jmbubKuCmNA.png)

### Setting up a Remote Repository.

Go to [https://github.com/](https://github.com/) and create an account.

After registering in the GitHub homepage, click on **Start a Project** to create
a new Git repository. Give the repository a name and click “Create Repository”

Give the name as `git-sample-repo `This will create a remote repository in
GitHub.

Enter this command on the terminal and navigate to directory where local project
is stored.


The `git remote add` command takes two arguments:

* A remote name, for example, `origin`
* A remote URL, for example, `https://github.com/Jatin-8898/git-sample-repo.git`

### Set a new remote
    git remote add origin https://github.com/

### Verify new remote
    git remote -v 
    origin  https://github.com/Jatin-8898/git-sample-repo.git(fetch)
    origin  https://github.com/Jatin-8898/git-sample-repo.git(push)

### Fetch

The `git fetch` command downloads commits, files, and refs from a remote
repository into your local repo. Fetching is what you do when you want to see
what everybody else has been working on.`git pull` and `git fetch` commands are
available to accomplish the task. You can consider `git fetch` the 'safe'
version of the two commands. It will download the remote content but not update
your local repo's working state, leaving your current work intact

    Syntax: git fetch <remote> <branch>
    Example: git fetch origin sample

### Pull

The `git pull` command is used to fetch and download content from a remote
repository and immediately update the local repository to match that content.
Merging remote upstream changes into your local repository is a common task in
Git-based collaboration work flows. The `git pull` command is actually a
combination of two other commands, `git fetch`followed by `git merge`.

    Syntax : git pull <remote> <branch>
    Example: git pull origin master

### Push

The `git push` command is used to upload local repository content to a remote
repository. Pushing is how you transfer commits from your local repository to a
remote repo.

    Syntax : git push <remote> <branch>
    Example: git push origin master

**NOTE: **If you created a **Readme.md **file while creating a New Repository
then make sure you first pull then push.

### Additional Commands

### Clone

`git clone `is a Git command line utility which is used to target an existing
repository and create a clone, or copy of the target repository in your system.

    git clone <url>

### Config

The `git config` command is a convenience function that is used to set Git
configuration values on a global or local project level.

    git config --global user.email "your_email@example.com"

### Remove the Directory

To remove the director from the project folder. Use this command

    git remove -r dir

### Blame

The `git blame` command is used to examine the contents of a file line by line
and see when each line was last modified and who the author of the modifications
was.

    git blame <filename>

### Reset

To Reset staging area to match most recent commit, but leave the working
directory unchanged.

    git reset

Reset staging area and working directory to match most recent commit and
overwrites all changes in the working directory.

    git reset --hard

### **Revert**

The git revert command can be considered an 'undo' type command

    git revert

Reverting should be used when you want to apply the inverse of a commit from
your project history. This can be useful, for example, if you’re tracking down a
bug and find that it was introduced by a single commit. Instead of manually
going in, fixing it, and committing a new snapshot, you can use `git revert` to
automatically do all of this for you.

This is a forward-moving undo operation that offers a safe method of undoing
changes. Instead of deleting or orphaning commits in the commit history, a
revert will create a new commit that inverses the changes specified

### Congratulations 🎉🎉

Now you know the basics of how to use Git, so go ahead and explore more!

Feel free to connect with me on my [LinkedIn Account](https://www.linkedin.com/in/jatin-varlyani/)

You can also connect with me on [GitHub](https://github.com/Jatin-8898) ✌

### [Jatin Varlyani](https://medium.com/@Jatin_8898)

Full Stack Web Developer 🚀 | Software Developer 💻 | Tech Enthusiast 🔎 | Love
to Help Others 🔰 
