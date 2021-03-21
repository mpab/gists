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

## install & upgrade yarn

**PREREQUISITE:** Install nvm

## uninstall/install/select npm using nvm

```console
nvm uninstall 14.16.0
nvm install 14.16.0
nvm use 14.16.0
```

```console
npm install -g yarn
yarn set version latest
```

## create applications from templates

### react with typesscript

```console
npx create-react-app my-app --template typescript
# OR
yarn create react-app my-app --template typescript
```

### react native with typescript

```console
npx react-native init my-app --template react-native-template-typescript
npx create-react-native-app my-app --template-with-typescript <-->
```

add windows target & run

```console
npx react-native-windows-init --overwrite
npx react-native run-windows
```

### list of templates

<https://www.npmjs.com/search?q=cra-template-*>
