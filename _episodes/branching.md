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

For slide:

Branches allow you to try new ideas. Branches can be used to isolate sections of
work. Useful for collaborating with others. Branches can be used to help manage
workflows.

Only one directory of files Fast context switching

