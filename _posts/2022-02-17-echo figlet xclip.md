---
title: echo figlet xclip
comments: true

categories:
  - Computing
tags:
  - Shell

# optional alternate title to replace page.title at the top of the page
alt_title: "Ascii Art Lettering - figlet"

# optional sub-title below the page title
sub_title: "Add life to your text"

# optional intro text below titles, Markdown allowed
introduction: |
    Using linux can be unfun and confusing if you dont learn using simple tools. Here is a one line command that lets you paste ascii art representations (figures) of letters. figlet draws the font and xclip simply places it in X11 clipboard. echo 'can you hear me' |
    
# optional call to action links
actions:
  - label: "computers"
    icon: github  # references name of svg icon, see full list below
    url: "https://dirtslayer.github.io/computers/2022/02/17/echo-figlet-xclip.html"
  
image: 
  path: /images/echo figlet xclip.png
  thumbnail: /images/echo figlet xclip 400x360.png
  caption: "Jekyll is cool"

comments: false  # disable comments on this post


---

<pre style="line-height:.7 !important; overflow:hidden">

                 ██              
                ░██              
  █████   █████ ░██       ██████ 
 ██░░░██ ██░░░██░██████  ██░░░░██
░███████░██  ░░ ░██░░░██░██   ░██
░██░░░░ ░██   ██░██  ░██░██   ░██
░░██████░░█████ ░██  ░██░░██████ 
 ░░░░░░  ░░░░░  ░░   ░░  ░░░░░░  


   ████ ██          ██           ██  
  ░██░ ░░   █████  ░██          ░██  
 ██████ ██ ██░░░██ ░██  █████  ██████
░░░██░ ░██░██  ░██ ░██ ██░░░██░░░██░ 
  ░██  ░██░░██████ ░██░███████  ░██  
  ░██  ░██ ░░░░░██ ░██░██░░░░   ░██  
  ░██  ░██  █████  ███░░██████  ░░██ 
  ░░   ░░  ░░░░░  ░░░  ░░░░░░    ░░  

                  ██ ██        
                 ░██░░  ██████ 
 ██   ██  █████  ░██ ██░██░░░██
░░██ ██  ██░░░██ ░██░██░██  ░██
 ░░███  ░██  ░░  ░██░██░██████ 
  ██░██ ░██   ██ ░██░██░██░░░  
 ██ ░░██░░█████  ███░██░██     
░░   ░░  ░░░░░  ░░░ ░░ ░░      
</pre>

Ever wanted some cool ascii art in your text documents? 

The figlet utility does that and has many fonts. You can check the different fonts

[figlet examples](http://www.figlet.org/examples.html)

```sh

$ echo 'echo figlet xclip' | figlet -p -f 3d | xclip

```

## Command breakdown


| $                  | The dollar sign command prompt, you dont type that, it is in the Terminal                      |
| echo               | Command that repeats whatever it sees, outputs to standard output                              |
| 'echo figlet xlip' | A text string in quotes that is the input to the echo command                                  |
| \|                 | The pipe symbol command connector puts the output of the previous command as input to the next |
| figlet             | The program that converts character in text (strings) into a figure-letter (figlet)            |
| -p                 | An option to split lines                                                                       |
| -f 3d              | The font to use,  list fonts with showfigfonts                                                 |
| \|xclip            | Pipe into xclip (put contents into X11 clipboard may use middle mouse button to paste)         |


<pre style="line-height:.7 !important; overflow:hidden">
$ echo 'focus' | figlet -f doom
  __                     
 / _|                    
| |_ ___   ___ _   _ ___ 
|  _/ _ \ / __| | | / __|
| || (_) | (__| |_| \__ \
|_| \___/ \___|\__,_|___/
                         
 </pre>



# figlet as a discord bot called ASCII

ASCII discord bot if you like that sort of thing. 🤔
[ASCII](https://top.gg/bot/326619566719369217)

