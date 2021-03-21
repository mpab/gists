# Display

## Enable HDPI resolutions

``` console
$ sudo defaults write /Library/Preferences/com.apple.windowserver.plist DisplayResolutionEnabled -bool true
```

then reboot

## Show screen resolution

``` console
$ system_profiler SPDisplaysDataType | grep Resolution
```

## fix fuzzy HDMI output on TV displays

https://gist.github.com/ejdyksen/8302862

```console
sudo mkdir -p /Library/Displays/Contents/Resources/Overrides
cd /Library/Displays/Contents/Resources/Overrides
sudo curl -O https://gist.githubusercontent.com/adaugherity/7435890/raw/3403436446665aec2b5cf423ea4a5af63125e5af/patch-edid.rb
sudo rb patch-edid.rb
```

then reboot

