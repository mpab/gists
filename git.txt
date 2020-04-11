BRANCHING
=========
prime folder with all branch info
git fetch origin

List branches (all/remote)
git branch -a
git branch -r

create local branch
git branch X

view local branches
git branch

delete local branch
git branch -d X

switch branch (if exists locally)
git checkout X

Switch to remote branch (e.g. when in production)
git fetch && git checkout <<branch>>

CLEANUP/DELETION
================

remove all untracked files
$ git clean -fd

delete all unstaged changes in current folder
$ git checkout .

LFS errors...
-------------
'Encountered 1 file(s) that should have been pointers, but weren't:'
$ git rm .gitattributes
$ git add -A
$ git reset --hard

$ git rm .gitattributes && git add -A && git reset --hard

MERGING
=======

++If your branch is local only and hasn't been pushed to the server, use
git rebase master
git rebase master --preserve-merges <-- might be a better option to prevent merge conflicts...
++Otherwise, use
git merge master

probably the best option:
git rebase --onto master mpab/parking-forecastry

NOTE! you won't see the changes any more - to uncommit: git reset HEAD^

unstage those changes
git reset

stage changes but do not merge (no commit)
git merge --no-commit --squash X

merge a (remote) branch which is checked out locally
----------------------------------------------------
git pull . <<BRANCH>>
then to merge
git push

STATUS
======
git status

++what changes are ready to be pushed
git log origin/master..HEAD
git diff origin/master..HEAD


CREDENTIALS
===========
git config --global credential.helper store
git push https://XXXXX.git
<password>
then...
git config --global push.default simple

REBASING
========
git fetch origin
git rebase origin/master

"your branch is X commits ahead of.."
git pull --rebase

to get out of trouble.. (throw everything away...)
git reset --merge

IGNORING/EXCLUDING FILES
========================
e.g. add to global ignore file...
$ echo ".DS_Store" >> ~/.gitignore_global
set global exclusions...
$ git config --global core.excludesfile ~/.gitignore_global







