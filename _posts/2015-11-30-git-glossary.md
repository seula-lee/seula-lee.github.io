---
layout: post
category : Git
title:  Git 용어 정리
date: 2015-11-30
---

### Git 용어 정리

`git add`

Moves changes from the working directory to the staging area. This gives you the opportunity to prepare a snapshot before committing it to the official history.

>Related Tutorials
Saving changes: git add
Using Branches: git merge
Inspecting a repository: git status
Comparing Workflows: Centralized Workflow

`git branch`
This command is your general-purpose branch administration tool. It lets you create isolated development environments within a single repository.

>Related Tutorials
Using Branches: git branch
Using Branches: git checkout
Using Branches: git merge
Comparing Workflows: Gitflow Workflow

`git checkout`
In addition to checking out old commits and old file revisions, git checkout is also the means to navigate existing branches. Combined with the basic Git commands, it’s a way to work on a particular line of development.

>Related Tutorials
Using Branches: git checkout
Viewing old commits: viewing-old-commits-intro
Undoing Changes: git checkout
Comparing Workflows: Gitflow Workflow

`git clean`
Removes untracked files from the working directory. This is the logical counterpart to git reset, which (typically) only operates on tracked files.

>Related Tutorials
Undoing Changes: git clean

`git clone`
Creates a copy of an existing Git repository. Cloning is the most common way for developers to obtain a working copy of a central repository.

>Related Tutorials
Comparing Workflows: Forking Workflow
Setting up a repository: git clone

`git commit`
Takes the staged snapshot and commits it to the project history. Combined with git add, this defines the basic workflow for all Git users.

>Related Tutorials
Using Branches: git merge
Rewriting history: git commit --amend
Saving changes: git add
Saving changes: git commit

`git commit --amend`
Passing the --amend flag to git commit lets you amend the most recent commit. This is very useful when you forget to stage a file or omit important information from the commit message.

>Related Tutorials
Rewriting history: git commit --amend

`git config`
A convenient way to set configuration options for your Git installation. You’ll typically only need to use this immediately after installing Git on a new development machine.

>Related Tutorials
Setting up a repository: git config

`git fetch`
Fetching downloads a branch from another repository, along with all of its associated commits and files. But, it doesn't try to integrate anything into your local repository. This gives you a chance to inspect changes before merging them with your project.

>Related Tutorials
Syncing: git fetch
Refs and the Reflog: Refspecs
Syncing: git pull

`git init`
Initializes a new Git repository. If you want to place a project under revision control, this is the first command you need to learn.

>Related Tutorials
Setting up a repository: git init

`git log`
Lets you explore the previous revisions of a project. It provides several formatting options for displaying committed snapshots.

>Related Tutorials
Inspecting a repository: git log
Advanced Git log: Filtering the Commit History
Advanced Git log: Formatting Log Output
Advanced Git log: git-log-intro

`git merge`
A powerful way to integrate changes from divergent branches. After forking the project history with git branch, git merge lets you put it back together again.

>Related Tutorials
Merging vs. Rebasing: Workflow Walkthrough
Using Branches: git merge
Comparing Workflows: Gitflow Workflow
Merging vs. Rebasing: Conceptual Overview

`git pull`
Pulling is the automated version of git fetch. It downloads a branch from a remote repository, then immediately merges it into the current branch. This is the Git equivalent of svn update.

>Related Tutorials
Syncing: git pull
Comparing Workflows: Centralized Workflow
Comparing Workflows: Feature Branch Workflow
Comparing Workflows: Forking Workflow

`git push`
Pushing is the opposite of fetching (with a few caveats). It lets you move a local branch to another repository, which serves as a convenient way to publish contributions. This is like svn commit, but it sends a series of commits instead of a single changeset.

>Related Tutorials
Syncing: git push
Refs and the Reflog: Refspecs
Comparing Workflows: Gitflow Workflow
Comparing Workflows: Centralized Workflow

`git rebase`
Rebasing lets you move branches around, which helps you avoid unnecessary merge commits. The resulting linear history is often much easier to understand and explore.

>Related Tutorials
Merging vs. Rebasing: Workflow Walkthrough
Rewriting history: git rebase -i
Merging vs. Rebasing: Conceptual Overview
Rewriting history: git rebase

`git rebase -i`
The -i flag is used to begin an interactive rebasing session. This provides all the benefits of a normal rebase, but gives you the opportunity to add, edit, or delete commits along the way.

>Related Tutorials
Rewriting history: git rebase -i

`git reflog`
Git keeps track of updates to the tip of branches using a mechanism called reflog. This allows you to go back to changesets even though they are not referenced by any branch or tag.

>Related Tutorials
Rewriting history: git reflog

`git remote`
A convenient tool for administering remote connections. Instead of passing the full URL to the fetch, pull, and push commands, it lets you use a more meaningful shortcut.

>Related Tutorials
Syncing: git remote

`git reset`
Undoes changes to files in the working directory. Resetting lets you clean up or completely remove changes that have not been pushed to a public repository.

>Related Tutorials
Undoing Changes: git reset
Reset, Checkout, and Revert: Commit-level Operation
Reset, Checkout, and Revert: File-level Operations
Undoing Changes: git clean

`git revert`
Undoes a committed snapshot. When you discover a faulty commit, reverting is a safe and easy way to completely remove it from the code base.

>Related Tutorials
Undoing Changes: git revert
Reset, Checkout, and Revert: Commit-level Operation
Reset, Checkout, and Revert: Summary

`git status`
Displays the state of the working directory and the staged snapshot. You’ll want to run this in conjunction with git add and git commit to see exactly what’s being included in the next snapshot.

>Related Tutorials
Inspecting a repository: git status
Comparing Workflows: Centralized Workflow
