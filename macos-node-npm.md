# Get npm, node playing nice

## install without npm from brew

remove any older versions, reinstall using script
(with help from: https://johnpapa.net/node-and-npm-without-sudo/)

``` console
nuke-node
install-node
```

## ignore using homebrew, doesn't work...

https://gist.github.com/DanHerbert/9520689

``` console
brew uninstall node
rm -rf /usr/local/lib/node_modules
```

or nuke all traces using the script

``` console
nuke-node
```

reinstall

``` console
brew install node --without-npm
echo prefix=~/.npm-packages >> ~/.npmrc
curl -L https://www.npmjs.com/install.sh | sh
```

fails with

``` console
sh: rimraf: command not found
```