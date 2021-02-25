# Install nvm

```console
wget -O install_nvm.sh https://raw.githubusercontent.com/creationix/nvm/master/install.sh
bash install_nvm.sh
```

check

```console
nvm --version
```

install node stable

```console
nvm install stable
```

upgrade npm for (node)

```console
cd ~/.nvm/versions/node/$(node -v)/lib && npm install npm
```

## Windows

<https://github.com/coreybutler/nvm-windows#node-version-manager-nvm-for-windows>

There is an install script, but there are only a few relevant settings

```console
setx NVM_HOME "D:\Apps\nvm"
setx NVM_SYMLINK "D:\Apps\nodejs"
setx PATH "%PATH%;%NVM_HOME%;%NVM_SYMLINK%"
```

**IMPORTANT** install node from an elevated command prompt (also works in bash)

```console
nvm install latest
nvm use <version>
node --version
```
