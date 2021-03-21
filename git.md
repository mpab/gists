# git cheatsheet

## branching

prime folder with all branch info

```console
> git fetch origin
```

List branches (all/remote)

```console
> git branch -a
> git branch -r
```

create/view/delete/switch local branch

```console
> git branch X
> git branch
> git branch -d X
> git checkout X
```

**NOTE** switch branch only works if it exists locally

Switch to remote branch

```console
> git fetch && git checkout $branch
```

## clean/delete/unstage

remove all untracked files/delete all unstaged changes in current folder/unstage

```console
> git clean -fd
> git checkout .
> git reset
# or
> git reset --hard
```

## LFS errors

'Encountered 1 file(s) that should have been pointers, but weren't:'

```console
> git rm .gitattributes
> git add -A
> git reset --hard
```

$ git rm .gitattributes && git add -A && git reset --hard

## merging

++If your branch is local only and hasn't been pushed to the server, use
git rebase master
git rebase master --preserve-merges <-- might be a better option to prevent merge conflicts...
++Otherwise, use
git merge master

probably the best option:
git rebase --onto master mpab/parking-forecastry

NOTE! you won't see the changes any more - to uncommit: git reset HEAD^

stage changes but do not merge (no commit)
git merge --no-commit --squash X

### merge a (remote) branch which is checked out locally

git pull . $BRANCH
then to merge
git push

## status

git status

++what changes are ready to be pushed
git log origin/master..HEAD
git diff origin/master..HEAD

## credentials

```console
> git config --global credential.helper store
> git push https://$REPO.git
# enter $PASSWORD then type
> git config --global push.default simple
```

## rebasing

git fetch origin
git rebase origin/master

"your branch is X commits ahead of.."
git pull --rebase

to get out of trouble.. (throw everything away...)
git reset --merge

## ignore/exclude files from checkin

local project ignore

```console
> touch .gitignore
> echo "**/.DS_Store" >> ~/.gitignore
```

set global ignore/add to global ignore...

```console
> git config --global core.excludesfile $HOME/.gitignore_global
> touch $HOME/.gitignore_global
> echo "**/.DS_Store" >> $HOME/.gitignore_global
```
