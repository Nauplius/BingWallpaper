**Repository Moved**

This repository has moved to [tseward/BingWallpaper](https://github.com/tseward/BingWallpaper).

# Bing Wallpaper

This script and scheduled task sets the Bing Wallpaper automatically using the current Bing image of the day.

# Scheduled Task Options

You can use either the PowerShell or VBScript version of the scheduled task. The VBScript scheduled task will prevent any window from appearing when the script runs; as the scheduled task is designed to run hourly after the user logs in, this is probably the desirable version.

## VBScript Scheduled Task

The VBScript Scheduled Task uses `C:\Tools\Wallpaper.vbs` as the path. `Wallpaper.vbs` uses `C:\Tools\Wallpaper.ps1` as the path. Adjust these paths as needed.

## PowerShell Scheduled Task

The PowerShell Scheduled Task uses `C:\Tools\Wallpaper.ps1` as the path. Adjust as necessary.

## Operation

Import one of the two Scheduled Tasks into Task Scheduler. They will have the correct parameters set upon import.

The PowerShell script is set to perform file operations in `%LOCALAPPDATA%\Wallpaper`. If this folder does not exist, it will create it. Prior to downloading wallpaper, it first checks for `check.ini` in the above path. If the file does not exist, it will download the Bing wallpaper to the same directory. If `check.ini` does exist, it will query the Bing wallpaper site to see if the wallpaper has changed. If it has, it will download the wallpaper and set it; if it has not changed, the script will exit.
