# GIT alias/shortcut

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
