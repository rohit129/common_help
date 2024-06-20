## **Add Terminal to Sublime Notebook**

**Step 1:** Open Sublime Text
**Step 2:** Open Command Palette using the command Ctrl+shift+p
Type the below until the option appears and select it.

```
Package Control: Install Package
```

[ Note: You’ll need to install package control if you are using it for the first time. ]

Type ‘Terminus’ and select it. Wait for it to Complete installation and Restart Sublime Text.

**Step 3:** Now go to Preferences >Package Settings > Terminus > Command Palette
Now paste this code in the Default Sublime Commands Section

```
[
   {
        "caption": "Terminal (panel)",
        "command": "terminus_open",
        "args"   : {
           "cmd": "bash",
           "cwd": "${file_path:${folder}}",
           "title": "Command Prompt",
           "panel_name": "Terminus"
        }
   },
]  
```

And save it.

```
Note: The above code is for Linux users for Windows users you have to enter “cmd.exe” in place of “bash”
```

**Step 4:** Now go to Preferences > Package Settings > Terminus > Key Bindings

steps-to-open-sublime-text-from-terminal-windows

Now paste this code in the Default Sublime Keymap Section and save it:

```
[
   {
       "keys": ["alt+1"],
       "command": "terminus_open",
       "args" : {
           "cmd": "bash",
           "cwd": "${file_path:${folder}}",
           "panel_name": "Terminus"
       }
   }
] 
```

[ Note: The above code is for Linux users for Windows users you have to enter “cmd.exe” in place of “bash”, also here we kept the shortcut key as “alt+1” you can use your own key.]

Step 5: So whenever you want to use Terminal press alt+1 and to close Terminal type exit in the terminal and hit ENTER.

**References**

Link followed for details : https://www.geeksforgeeks.org/how-to-use-terminal-in-sublime-text-editor/
