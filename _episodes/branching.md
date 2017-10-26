---
title: Working with branches
teaching: 
exercises: 0
questions:
- ?"
objectives:
- "."
- "."
keypoints:
- "."
- "."
---
For header:

Branches allow you to try new ideas. Branches can be used to isolate sections of
work. Useful for collaborating with others. Branches can be used to help manage
workflows.

Only one directory of files Fast context switching

----

Branches are one of the most powerful features in Git and they are super easy to
use. Branches are great because they are easy to create, easy to delete, and
easy to work with. They allow you to experiment and try new ideas without
worrying about having to undo a bunch of commits in your master branch if it
doesn't work out. You can just create a new branch and test out your ideas
there.

Let's say that you want to try out a new reconciliation process for the subjects
in your project, but you have no idea what the results will be. Rather than
experimenting with the metadata in your master branch, you create a
subject_recon branch and test it out there. If you are happy with the results,
then great, you can incorporate those changes back into the master branch
through a process called merging, which we will talk about in the next section.
If not, you can delete the branch and move on with your work.

Branches are also great for isolating sections of work, for collaborating with
others, and managing workflows. For example, you have a student who will be
working with you on your project. You have asked them to ensure that none of the
titles are in all caps. You create a branch for them to work on the titles while
you continue to work on subject reconciliation. Once they are completed with
their project, you can review their changes and when you are happy with their
work, merge their changes back into the master branch.

When you create a branch, you are still going to have just one directory of
files in your project. All of the files that you are working with are still
going to be in same place. When you switch branches, Git is going to do
something called "fast content switching". This means that when you switch
branches Git is going to take all of the files in your project directory and
swap them out so that they match what is on that branch.

Let's look at an illustration. You are on your master branch, and have made
several commits to it. Then you decide you want to test out your new
reconciliation process, but you aren't sure if it will work out. You you create
and switch to your `subject_recon` branch and then make your changes, committing
them to the new branch. These new commits are not on the master branch. If you
switch back to the master branch, you will not see those changes. Each time you
switch back and forth between the branches, git will switch out the files in
your project directory. You can continue to make commits to master, but they
will not appear in your branch. Let's say you are happy with your experiment,
and want to incorporate those changes back into master. You will then merge your
`subject_recon` branch into master and Git will create a new commit that merges
the changes from the `subject_recon` branch. You can then either delete the
`subject_recon` branch, or continue to make changes, periodically merging them
back in.

You also don't have to always create branches from, or merge changes to, the
master branch. You can have many branches and merge changes between those
branches.

_______

Start by looking at current branches on local machine.

$ git branch

* master

Asterisk tells you which branch you are on, also referred to as the branch that
is checked out.

----

Now let's try creating a new branch. To do this you use git branch again, but
this time you supply the name of the new branch. You can name your branch
whatever you want, but you'll want to keep it simple: letters, numbers, and
underscores. You'll also want to give them useful meaningful names so that when you look
at your list of branches you'll know what they refer to. You can also use something like
the issue number, if you use a ticketing system to manage your work.

<< Need example>>

$ git branch funny_cats

When you hit return it will create the new branch.

---- 
Let's take a look by using git branch again.


$ git branch 
* master 
funny_cats

You can see by the asterisk that I am still on the master branch. 
----
To switch to your new branch, you use the checkout command.

$ git checkout funny_cats
Switched to branch 'funny_cats'

You should see a confirmation message of the switch, but you can also confirm using git 
branch.

$ git branch
master
* funny_cats

-----
Right now the branches are identical, because I haven't made any additional commits to 
either branch. If we switch between them, no files will change in our project directory.
Let's go ahead and make a commit on the new branch. 

<< still need something for participants to do here >>

Save your change. Then git status, git commit -am

<< need terminal example >>

-----
Switch back to master using git checkout and view the log.

$ git checkout master
Switched to branch 'master'

$ git branch
* master
funny_cats

$ git log --oneline

<< need terminal example >>

You can see that the commit you just made is not on the master branch. Open up your
project directory and view the file you changed in the 'funny_cats' branch. Your change 
is not there. Close the file, switch the branch, and reopen the same file. Your change is
now there.

------
You can also create and checkout a branch at the same time. Then use the checkout command 
followed the the dash b option and the name of your new branch.

<< need scenario >>

$ git checkout -b cat_costumes
Switched to new branch 'cat_costumes'

$ git branch
  master
  funny_cats
* cat_costumes

Let's look at the log again.

$ git log --oneline

<< need terminal example >>

You'll notice that because we were on the funny_cats branch when we made our new branch, 
and not master, our new branch was created off of funny_cats. 

<< Make and commit changes to file on new branch >>

------

<<QUESTION: should we show 
$ git log --graph --oneline --decorate --all
?>>

______

<< QUESTION: should we skip stashing changes? Or send then to further resources. What 
about using diff on branches?>>

-------
You can rename a branch using the branch move command.

<< example using ticketing system for migration>>

$ git branch -m funny_cats migrate_1

--------
Now let's learn how to delete a branch. Switch to the master branch.

$ git checkout master
Switched to branch 'master'

$ git branch delete_me

Notice that I did not create and checkout the branch at the same time.

$ git branch
  cat_costumes
  delete_me
* master
  funny_cats

This is important because you cannot delete the branch you are on. Now use the branch dash
delete command followed by the name of the branch.
  
$ git branch -d delete_me
<< need termina>>

$ git branch
  cat_costumes
* master
  funny_cats

Now the branch is gone.

----




