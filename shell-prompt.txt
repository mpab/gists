changing the default prompt - look in ~/.bashrc or ~/.bash_profile

add a line feed to the prompt to stop it disappearing off the edge...
PS1='${nnnn:+($nnnn)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
PS1='${nnnn:+($nnnn)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\n\$ '

see also: git-prompt

example:
export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w\[\033[m\]\n\$ "
export CLICOLOR=1
export LSCOLORS=ExFxBxDxCxegedabagacad

alias ls='ls -GFh'
alias ll='ls -la'