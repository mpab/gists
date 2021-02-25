# PYTHON

## git bash issues

Not seeing any console output? may need to use winpty

.bashrc

```bash
#
export HOME_GLOBAL_PYTHON=$HOME_PYENV/versions/$(pyenv global)
export PATH=$PATH:$APPS/scripts:$SCALA_HOME/bin:$HOME_GLOBAL_PYTHON

alias py='winpty python.bat'
alias pr='pipenv run $*'
alias prpy='pipenv run python $*'
alias python='winpty python $*'
```

**NOTE** if using pyenv

1. Set HOME_PYENV
2. Use the above export to ensure the correct version is selected
