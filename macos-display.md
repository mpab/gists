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