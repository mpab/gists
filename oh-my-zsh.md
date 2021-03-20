# Setup zsh on Cygwin

Install Cygwin (using the installer)

Then install lynx, wget, tar using the Cygwin installer

Run the Cygwin shell, install apt-cyg and use that to install zsh

```shell
> lynx -source rawgit.com/transcode-open/apt-cyg/master/apt-cyg > apt-cyg
> install apt-cyg /bin
> apt-cyg install zsh
```

Set Cygwin home

```dos
HOME=%USERPROFILE%
```

Install the fonts as listed:

<https://github.com/romkatv/powerlevel10k#oh-my-zsh>

...right click on each font

...and select install

Install oh-my-zsh

```zsh
> sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Important! You have to use the cygwin git for this to work! Git bash fails

(Afterwards, if you prefer to use Git Bash, disable Cygwin git)

Create a batch file to run Cygwin - "Cygwin-zsh - MesloLGS NF.bat" in the %APPS%\Cygwin64 folder

%APPS%\cygwin64\bin\mintty.exe -o ConfirmExit=no -i /Cygwin-Terminal.ico -o Font="MesloLGS NF" /bin/zsh --login

- Create a shortcut to this batch file on the desktop
- Start in %APPS%\Cygwin64
- Select the %APPS%\Cygwin64\Cygwin.ico icon file
- Drag the shortcut to the taskbar and pin it

```zsh
export TERM=xterm-256color
setopt globdots
```

```zsh
cd /cygdrive/c/dev
```

To select a custom starting folder, at the end of ~/.zsh

Install powerlevel10k - note this may also require the Cygwin git

```zsh
> git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
... alternatively
> cd ~/.oh-my-zsh/custom/themes
> git clone https://github.com/romkatv/powerlevel10k.git
```

in .zshrc

```zsh
ZSH_THEME="powerlevel10k/powerlevel10k"
```

```zsh
> p10k configure
```

[vscode integration](./vscode-bash-zsh.md)
