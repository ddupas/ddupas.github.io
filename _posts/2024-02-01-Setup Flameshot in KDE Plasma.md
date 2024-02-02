---
title: Setup Flameshot or Spectacle in KDE Plasma
categories:
  - KDE
  - Productivity
header:
tags:
---


![34_20200112Betancourtjumperonplastic4.jpg](https://eraser.imgix.net/workspaces/Qj05EF0NJUgnMJNG1Uym/QUxlyIfqGXYJL2M9giYm0uxIucd2/ocwnjtLueVq00WEgtLxsJ.jpg?ixlib=js-3.7.0 "34_20200112Betancourtjumperonplastic4.jpg")


# Steps Overview
1. Install Flameshot and/or Spectacle
2. Disable Default Shortcuts
3. Configure Shortcuts
4. Configure Clipboard

# Step 1: Install Flameshot
[﻿https://flameshot.org/docs/installation/installation-linux/](https://flameshot.org/docs/installation/installation-linux/)

# Step 2: Disable Default Shortcuts
Both Flameshot and Spectacle do the job. Flameshot has some nifty annotation tools, otherwise they both have the features I need from a screen capture utility. They both require some non-default configuration so that the shortcuts (Print and Shift Print) work the way I like. Print should be silent and capture the entire screen to the clipboard. Shift Print should provide a sizable rectangle to capture to the clipboard.

If we want to save an image in the clipboard as a file, we can press Control V in Dolphin File Manager. Most of the time, we will want to paste into an application like Discord, Krita or Eraser.io.

Unfortunately, the default shortcuts for both Flameshot and Spectacle in KDE Plasma interrupt you with a prompt, so we can create custom commands instead.

![image.png](https://eraser.imgix.net/workspaces/Qj05EF0NJUgnMJNG1Uym/QUxlyIfqGXYJL2M9giYm0uxIucd2/TPywLTZl943t4U24DxEjh.png?ixlib=js-3.7.0 "image.png")

Click **+ Add Command** Button - KDE Plasma Shortcut Settings

# Custom Commands
### Spectacle
```sh
spectacle -b -c   # capture screen to clipboard in the background (do not prompt)
spectacle -r -c   # rectangle selection to copy to the clipboard
```
### Flameshot
```sh
# capture screen to clipboard in the background (do not prompt)
flameshot screen -c

# rectangle selection to copy to the clipboard
flameshot gui -c --region '300x300+300+300'
```
To open Shortcut settings in Plasma Desktop

>  Alt  Space shortcut

# Step 3: System Settings, Configure Keyboard Shortcuts
![image.png](https://eraser.imgix.net/workspaces/Qj05EF0NJUgnMJNG1Uym/QUxlyIfqGXYJL2M9giYm0uxIucd2/8b0Nsxty2fzrcs7xTbV-n.png?ixlib=js-3.7.0 "image.png")

Click **+ Add custom shortcut**, then tap the Print button.

# Step 4: Configure Clipboard to hold images - Klipper settings
![settings00.png](https://eraser.imgix.net/workspaces/Qj05EF0NJUgnMJNG1Uym/QUxlyIfqGXYJL2M9giYm0uxIucd2/3naAkAHi-DVconDqKhD36.png?ixlib=js-3.7.0 "settings00.png")



![image.png](https://eraser.imgix.net/workspaces/Qj05EF0NJUgnMJNG1Uym/QUxlyIfqGXYJL2M9giYm0uxIucd2/w4sOvHFzah4_RZ3ecNA-s.png?ixlib=js-3.7.0 "image.png")

Right Click and select Configure Clipboard to find Klipper Settings.

To keep images in Clipboard History

> Non-text selection, Always save in history

More info: [﻿docs.kde.org/stable5/en/plasma-workspace/klipper/preferences.html](https://docs.kde.org/stable5/en/plasma-workspace/klipper/preferences.html)

# EXTRA: Shortcuts in both Windows and KDE Plasma that have the same functions
> Meta  v       Paste From Clipboard History

> Meta  .        Opens an Emoji Picker

> Meta           Start / Krunner Search

# EXTRA: Shortcuts KDE Plasma that are DIFFERENT
> Alt Space
     KDE - Krunner Search
     W11 - Window Menu

> Alt F3
     KDE - Window Menu

# EXTRA: Other Clipboard Settings
>  Copy Highlighted Text

Do not need to press Control C to copy, all selected text automatically gets copied. Slick, but replacing selected text will not work because the last selection will be on top of the clipboard history. The solution is to paste first then delete rather than replace.

# EXTRA: Tweek Firefox to get more laptop screen:
![image.png](https://eraser.imgix.net/workspaces/Qj05EF0NJUgnMJNG1Uym/QUxlyIfqGXYJL2M9giYm0uxIucd2/xUrE78ZK5eJBPVYk3MO9z.png?ixlib=js-3.7.0 "image.png")

Firefox Extensions: Sidebery, Facebook Container, KeepassXC Browser, Profile Switcher for Firefox.

Link to article on PCWorld : [﻿https://www.pcworld.com/article/823939/vertical-tabs-in-firefox-yes-its-really-possible.html](https://www.pcworld.com/article/823939/vertical-tabs-in-firefox-yes-its-really-possible.html)

Link to Custom CSS file called userChrome.css :
[﻿https://github.com/OneJaredNewman/firefoxcss](https://github.com/OneJaredNewman/firefoxcss)

### Summary
```
about:config in the address bar and select “Accept the Risk and Continue.”
Under “Search preference name,” paste the following text: toolkit.legacyUserProfileCustomizations.stylesheets
Tap the toggle button on the right so the preference says “true.”
```
```
about:support in the address bar.
Scroll down to the section that says “Profile Folder,” and click the “Open Folder” button.
```
Place the file userChrome.css in that folder and restart FireFox.

> You have to place userChrome.css for each profile you use



## Wrap-UP
Control C, Control V is so 2010! We no longer have to go back and forth between our source and our copy. We can collect text and images in our clipboard and then select them as we need them.

[﻿Eraser.io](https://eraser.io/) ✅

[﻿KDE.org](https://kde.org/) ✅



