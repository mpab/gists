#Icon cleanup

##Remove a named file/icon

```console
$ sudo sqlite3 $(sudo find /private/var/folders/mv -name com.apple.dock.launchpad)/db/db "DELETE FROM apps WHERE title='Python Launcher 3';" && killall Dock
```

##For empty folders

```console
$ defaults write com.apple.dock ResetLaunchPad -bool true; killall Dock
```

##Remove db and reset icons

```console
$ rm ~/Library/Application\ Support/Dock/*.db; killall Dock
```
