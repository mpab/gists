# GIT aliass/shortcuts

## Combine git add, commit, push

replace

```console
$ git add
$ git commit -m "commit message"
$ git push
```

with

```console
$ git acp "commit message"
```

run

```console
$ git config --global alias.acp '!f() { git add -A && git commit -m "$@" && git push; }; f'
```

to remove the alias

```console
$ git config --global --unset alias.acp
```

## create a new feature branch and push the changes with one command (uses acp)

First remove the requirement to call git push --set-upstream every time...

git config --global push.default current

```console
$ git config --global alias.feature '!f() { git branch -D mpab/turtles && git branch mpab/turtles && git checkout mpab/turtles && git acp "$@"; }; f'
```

to remove the alias

```console
$ git config --global --unset alias.feature
```
