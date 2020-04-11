
https://stackoverflow.com/questions/11248073/what-is-the-easiest-way-to-remove-all-packages-installed-by-pip

This will work for all Mac, Windows and Linux System. To get the list of all pip package in the requirements.txt file (Note: This will overwrite requirements.txt if exist else will create the new one.)

pip freeze > pip-installed.txt

Now to remove one by one

pip uninstall -r pip-installed.txt

If we want to remove all at once then

pip uninstall -r pip-installed.txt -y

