cd ~/Downloads
wget http://ftp.us.debian.org/debian/pool/contrib/m/msttcorefonts/ttf-mscorefonts-installer_3.6_all.deb
sudo gdebi ~/Downloads/ttf-mscorefonts-installer_3.6_all.deb
sudo fc-cache -f -v

https://github.com/hbin/top-programming-fonts
curl -L https://github.com/hbin/top-programming-fonts/raw/master/install.sh | bash
sudo apt-get install font-manager

manual e.g.:
sudo cp -R SanFranciscoFont/ /usr/share/fonts/opentype/.
sudo fc-cache -f -v
