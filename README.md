# Windows10SetupMemo
Windows10SetupMemo

# Windows10 settings
- privacy policy
- folder settings
- icon size, start menu, no sound

# Applications to be installed
- firefox
- chrome
- lhaplus
- explzh
- irfanview
- vlc
- media player classic
- sublime
    - package manager
- sakura editor
    - ctag
- winmerge
- Stirling
    - add to sendto
- keyhac
- sharpkeys
- JpegAnalyzer
- git
    - user, ssh, winmerge
- mingw
    - alias for text editors


# msys
### .inputrc
```
set bell-style none
```

### .profile
```
alias subl='"/c/Program Files/Sublime Text 3/sublime_text.exe"'
alias sakura='"/c/Program Files (x86)/sakura/sakua.exe"'
```

# .gitconfig
```
[user]
    name = jieajoa
    email = jieajoa@gmail.com
[diff]
    tool = WinMerge
[difftool "WinMerge"]
    path = C:/Program Files (x86)/WinMerge/WinMergeU.exe
    cmd = \"C:/Program Files (x86)/WinMerge/WinMergeU.exe\" -f \"*.*\" -e -u -r \"$LOCAL\" \"$REMOTE\"
[merge]
    tool = WinMerge
[mergetool "WinMerge"]
    path = C:/Program Files (x86)/WinMerge/WinMergeU.exe
    cmd = \"C:/Program Files (x86)/WinMerge/WinMergeU.exe\" -e -u \"$LOCAL\" \"$REMOTE\" \"$MERGED\"
[alias]
    windiff = difftool -y -d -t WinMerge
    winmerge = mergetool -y -t WinMerge
```

# sharpkeys
- Left Alt (00_38) -> Left Ctrl (00_1D)
- Left Ctrl (00_1D) -> Left Alt (00_38)
- Caps Lock (00_3A) -> Right Ctrl (E0_1D)  @only for JP keyboard
- (add into startup)

# keyhac
```
import sys
import os
import datetime

import pyauto
from keyhac import *

def configure(keymap):
    keymap.replaceKey( "RCtrl", 235 )
    keymap.defineModifier( 235, "User0" )
    keymap_global = keymap.defineWindowKeymap()
    keymap_global[ "U0-P" ] = "Up"
    keymap_global[ "U0-N" ] = "Down"
    keymap_global[ "U0-B" ] = "Left"
    keymap_global[ "U0-F" ] = "Right"
    keymap_global[ "U0-A" ] = "Home"
    keymap_global[ "U0-E" ] = "End" 
    keymap_global[ "Shift-U0-P" ] = "S-Up"
    keymap_global[ "Shift-U0-N" ] = "S-Down"
    keymap_global[ "Shift-U0-B" ] = "S-Left"
    keymap_global[ "Shift-U0-F" ] = "S-Right"
    keymap_global[ "Shift-U0-A" ] = "S-Home"
    keymap_global[ "Shift-U0-E" ] = "S-End" 
    keymap_global[ "U0-D" ] = "Delete"
    keymap_global[ "U0-K" ] = "S-End","Delete"
    keymap_global[ "U0-H" ] = "Back"
    keymap_global[ "U0-M" ] = "PageDown"
    keymap_global[ "U0-O" ] = "PageUp"
    keymap_global[ "U0-RShift" ] = ""
    keymap_global[ "U0-RShift-LShift" ] = "CapsLock"
    keymap_global[ "LCtrl-Q" ] = "Alt-F4" 
    keymap_global[ "LCtrl-W" ] = "Ctrl-F4" 
    keymap_global[ "RWin-Enter" ] = "Alt-Enter"  
    keymap_global[ "U0-Tab" ] = "CapsLock"
    keymap_global[ "U0-BackSlash" ] = "Insert"
    keymap_global[ "U0-Space" ] = "Ctrl-Space"
```
