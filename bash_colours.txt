use dircolors

dircolors -p > .my_dircolors

edit the file

add to .bashrc

eval "$(dircolors ~/.my_dircolors)"
