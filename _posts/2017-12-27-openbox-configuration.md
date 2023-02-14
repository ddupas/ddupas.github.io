---
title: Openbox Configuration
categories: Linux
header:
    image: /images/Screenshot from 2023-01-11 21-43-37.png
---
If you use a login manager Openbox will
read its startup program list from the file ~/.config/openbox/autostart. 
If that file does not exist it might use the system wide autostart located 
at /etc/xdg/openbox/autostart. But, if you use startx you will need to 
add your startup programs to ~/.xinitrc.

Here is the ever changing Openbox autostart file.

~~~
dbus-launch &
dunst &
pasystray &
nitrogen --restore &
tint2 &
notify-send "Welcome to Zenbook" &
~~~

* dbus-launch - dbus an inter-process communication daemon
* dunst - a dbus messaging daemon
* pasystray - pulse audio tray for configuring sound and mic settings
* nitrogen - sets desktop wallpaper
* tint2 - a very configurable toolbar
* notify-send - uses dunst to display welcom message

You will want to do 2 important things now:

1. set up openbox menu
2. configure tint2

# obmenu-generator

A static menu is slightly more responsive, but you need to 
re-generate your menu if new software is added.

~~~
$ cd ~/.config/openbox
$ obmenu-generator -s > menu.xml
~~~

# use your own menu.xml

The system wide menu is /etc/xdg/openbox/menu.xml, it might look something like this:

<script src="https://gist.github.com/ddupas/0af59ab65c3ffda354e44065ee1a17c8.js"></script>

# tint2rc

You might want to add launchers for your most frequently used programs.
.desktop files are act as shortcuts to programs and provides icons etc.

~~~
launcher_item_app = /usr/share/applications/google-chrome.desktop
launcher_item_app = /usr/share/applications/xfce4-terminal.desktop
launcher_item_app = /usr/share/applications/thunar.desktop
~~~

I also prefer the bar on the top of the screen, the reason being is the mouse
pointer is more likely to be near the top of the screen and I like to minimize
the distance the mouse has to move in general. I also like to use autohide.

~~~
panel_position = top center horizontal
autohide = 1
~~~

The laptop battery indicator built into tint2 shows up when you have a charge
percentage lower than the value for battery_hide.

~~~
battery_hide = 95
~~~


## Font dpi force ~/.Xresources 

Xft.dpi:    144


# xfce4-mime-settings 

One thing that can be frustrating in Linux at this point can be setting your
default applications. Especially since there doesn't seem to be a default 
file browser set on a fresh install.

I use xfce4-mime-settings to set my default applications in openbox. 
Set inode/directory to thunar.

# kate

Check out this editor. It has been around a long time now and is very good. You will 
need to add hunspell to your install to get spell checking. Kate has decent support
for projects that use git. It is lightning fast compared to atom or sublime. 

# mypaint

If you have a tablet or touchscreen you will want this program. It is the closest
thing to pen and paper I can find. Mypaint uses the keyboard a lot, it is worth
while to learn the keys:

* shift - draw a line
* z - undo
* d - smaller pen
* f - bigger pen
* '-' - zoom out
* '+' - zoom in
* r - pick color
* x - recent colors
* e - eraser

![mypaint](/images/Screenshot_20170127_105831.png)

# spectacle

A less geeky simple screenshot utility.
