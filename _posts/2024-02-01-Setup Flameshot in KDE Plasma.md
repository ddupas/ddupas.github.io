---
title: Setup Flameshot or Spectacle in KDE Plasma
categories:
  - KDE
  - Productivity
header:
tags:
---
![Copy Copy Paste](/images/34_20200112Betancourtjumperonplastic4.jpg)

# Steps Overview

1. Disable Default Shortcuts
2. Install Flameshot
3. Configure Shortcuts
4. Configure Clipboard

# Step 1: Disable Default Shortcuts

Both Flameshot and Spectacle do the job. Flameshot has some nifty annotation tools, otherwise they both have the features I need from a screen capture utility. They both require some non-default configuration so that the shortcuts (Print and Shift Print) work the way I like. Print should be silent and capture the entire screen to the clipboard. Shift Print should provide a sizable rectangle to capture to the clipboard.

I do not want my screengrabber to prompt me or create files. If I want to save the capture as a file, we can press Control V to paste in Dolphin File Manager. Most of the time, we will want to paste into an application, like Discord or Krita.

Unfortunately, the default shortcuts for both Flameshot and Spectacle in KDE Plasma  interupt you with a prompt, we can create custom commands instead.

<figure>
  <img src="{{site.url}}/images/editcommand00.png"
  alt="Edit Command"/>
  <figcaption>Edit Command</figcaption>
</figure>


Spectacle
=========
spectacle -b -c   # capture screen to clipboard in the background (do not prompt)
spectacle -r -c   # provide rectangle selection to copy to the clipboard

Flameshot
=========
flameshot gui -c --region '300x300+300+300'


To open Shortcut settings in Plasma Desktop, we can use Alt + Spacebar, then type shortcut.

<figure>
  <img src="https://i.imgur.com/clqm1Ub.png"
  alt="Alt Space to open krunner"/>
  <figcaption>Alt Space to open krunner (Alt F3 is the Window Menu!!)</figcaption>
</figure>




# Step 2: Install Flameshot

https://flameshot.org/docs/installation/installation-linux/


# Step 3: System Settings, Configure Keyboard Shortcuts


# 4. Add Copy current screen to clipboard to Print button

 Commands, Add Command Button:
flameshot screen -c
Add Custom Shortcut
Print (press the print button)

5.

6. Configure KDE Clipboard

<figure>
  <img src="{{site.url}}/images/settings00.png"
  alt="Settings to keep images in Clipboard Contents History"/>
  <figcaption>MSFISH Charts </figcaption>
</figure>


- Non-text selection, Always save in history
Allows you to have images in your clipboard history that you mayvreorder when you paste.

- Meta + V for Paste Selection

7. Other Clipboard Settings

- Copy Highlighted text setting can be funky at first, you simply have to avoid 'replacing selected text'. With Copy Highlighted Text setting, you do not need to press Control C to coppy, all selected text automatically gets copied



Also:
Firefox with Vertical Tabs and no top bar article:
https://www.pcworld.com/article/823939/vertical-tabs-in-firefox-yes-its-really-possible.html
https://github.com/OneJaredNewman/firefoxcss
