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
