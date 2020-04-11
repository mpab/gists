copy icons to ~/.icons
copy themese to ~/.themes

use the tweak tool to set icons and themes

if the tweak tool doesn't find the themes:
$ gsettings set org.gnome.desktop.interface gtk-theme "Gnome-OSX-V-HSierra-1-3-2"
$ gsettings set org.gnome.desktop.wm.preferences theme "Gnome-OSX-V-HSierra-1-3-2"

check if the themes folder has a gtk 2 or 3 sub folder - if so, change the path, or move the files as required

