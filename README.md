# Windows10SetupMemo
Windows10SetupMemo

# Windows10 settings
- privacy policy
- folder settings
- icon size, start menu, no sound

### IME (for US keyboard)
- IMEバーで右クリック->プロパティ->詳細設定->全般タブ、編集操作、キー設定->変更
- キー追加. Ctrl+Shift+SpaceをIME オン/オフへ割り当て

# Applications to be installed
- firefox
- chrome
- lhaplus
- explzh
- irfanview
- vlc
- media player classic
- sublime
- sakura editor
    - ctag
- winmerge
- Stirling
    - add to sendto
- keyhac
- sharpkeys
- JpegAnalyzer
- git
    - user, ssh-keygen, winmerge
- mingw
    - alias for text editors
- Visual Studio Code

# sublime text
install package manager
### packages to be installed
- IMESupport
- SimpleClone
- OmniMarkupPreviewer
- BracketHighlighter
- ConvertToUTF8
- CTags
- Package Control
- SublimeCodeIntel
- Terminal
- Theme - Flatland
- TrailingSpaces

### Key Bindings
```
[

	{ "keys": ["alt+shift+up"], "command": "select_lines", "args": {"forward": false} },
	{ "keys": ["alt+shift+down"], "command": "select_lines", "args": {"forward": true} }, 

	{ "keys": ["ctrl+shift+m"], "command": "toggle_record_macro" },
	{ "keys": ["ctrl+m"], "command": "run_macro" },

	{ "keys": ["ctrl+["], "command": "jump_back" },
	{ "keys": ["ctrl+]"], "command": "jump_forward" },

	{ "keys": ["ctrl+shift+up"],
		"command": "set_layout",
		"args":
		{
			"cols": [0.0, 1.0],
			"rows": [0.0, 1.0],
			"cells": [[0, 0, 1, 1]]
		}
	}
]
```
- ctrl+shift+down -> split
- ctrl+shift+up -> single

### Settings
```
{
	"always_show_minimap_viewport": false,
	"color_scheme": "Packages/Color Scheme - Default/Monokai.tmTheme",
	"default_encoding": "UTF-8",
	"draw_minimap_border": true,
	"draw_white_space": "all",
	"fallback_encoding": "UTF-8",
	"font_size": 10,
	"highlight_line": true,
	"hot_exit": false,
	"ignored_packages":
	[
		"Vintage"
	],
	"match_brackets": true,
	"open_files_in_new_window": true,
	"remember_open_files": false,
	"ruler":
	[
		0,
		200
	],
	"show_encoding": true,
	"show_line_endings": true,
	"spacegray_sidebar_font_large": true,
	"spacegray_sidebar_tree_large": true,
	"spacegray_tabs_font_large": true,
	"spacegray_tabs_large": true,
	"tab_size": 2,
	"translate_tabs_to_spaces": false,
	"update_check": false,
	"word_wrap": true
}
```

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

git difftool --dir-diff 


# sharpkeys
- Left Alt (00_38) -> Left Ctrl (00_1D)
- Left Ctrl (00_1D) -> Left Alt (00_38)
- Caps Lock (00_3A) -> Scroll Lock (00_46)  @only for JP keyboard

# keyhac
```
import sys
import os
import datetime

import pyauto
from keyhac import *

def configure(keymap):
    keymap.replaceKey( "ScrollLock", 235 ) # for JP keyboard
    #keymap.replaceKey( "RCtrl", 235 ) # for JP keyboard
    #keymap.replaceKey( "CapsLock", 235 ) # for US keyboard
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
    #keymap_global[ "U0-RShift" ] = ""
    #keymap_global[ "U0-RShift-LShift" ] = "CapsLock"
    keymap_global[ "LCtrl-Q" ] = "Alt-F4" 
    keymap_global[ "LCtrl-W" ] = "Ctrl-F4" 
    #keymap_global[ "RWin-Enter" ] = "Alt-Enter"
    #keymap_global[ "U0-Tab" ] = "CapsLock"
    #keymap_global[ "U0-BackSlash" ] = "Insert"
    keymap_global[ "U0-Space" ] = "Ctrl-Space"
```
- (add into startup)
