# Password Nightmares

Managing  passwords has evolved a lot for me. The way I manage files has changed
a lot for me as well. Many applications can manage a keepass database, but we
are still left to manage the keepass files.

I had tried a shared keepass file on a google drive, and that was the best
solution I had had for quite some time. Eventually that broke, but it didnt have
to. One awkward feature of this method is that I needed to authenticate to get
my passwords. 

After Linus Tech Tips Youtube account got hacked, I realized it's irresponsible
of me to not take control of this file. It turns out that I prefered having
local copies, and wasnt dilligent merging changes, resulting in lost passwords,
error prone merge attempts and making backup copies. I know from coding projects
that this is a recipie for disaster. Also, I would be lazy and keep some
passwords in a browser autofill cache, another shady idea. 

Git enables me to not be stuck to a single workstation. I can clone my
repository, make my changes, and push to the main git repository and continue.
At the end of a coding session I may as well delete the copy I've been working
on, which would prevent having to pull before making changes on a stale copy.
Or, I could not forget to pull before attempting changes, which I've gotten
better at. One thing that helps is using git helpers that show you that your
copy is stale or changed. I use bobthefish theme of oh-my-fish, it has git
indicators for the current working directory. 

So, sometimes projects have database files, images, all sorts of binary files.
I'm fairly certain the linux kernel has some binary files managed by git, and
I've been using it for database files without issue.

So all this preamble is the motivation to set up my own Git server and use that
to syncronize my keepass files.

| My text life: Powered by fish, ssh, git, micro and lazygit |
|------------------------------------------------------------|

## Step 1 Setup Git Server on life server (laptop 14-dk1018ca)

If your house is burning down it is easier to grab than your desktop.

## git-daemon configs
```txt
#  File: /usr/lib/systemd/system/git-daemon.socket
[Unit]
Description=Git Daemon Socket

[Socket]
ListenStream=9418
Accept=true

[Install]
WantedBy=sockets.target
```

```txt
#   File: /usr/lib/systemd/system/git-daemon@.service
# also set git home in /etc/passwd to /srv/git
[Unit]
Description=Git Daemon Instance

[Service]
User=git
# The '-' is to ignore non-zero exit statuses
ExecStart=-/usr/lib/git-core/git-daemon --inetd --export-all --base-path=/srv/git \
	--enable=receive-pack
StandardInput=socket
StandardOutput=inherit
StandardError=journal
ProtectSystem=full
ProtectHome=on
PrivateDevices=on
NoNewPrivileges=on
```


## Creating repository
```sh
root@14-dk1018ca /s/git# pwd
/srv/git
root@14-dk1018ca /s/git# git --bare init org.git
root@14-dk1018ca /s/git# chown -R git:git org.git
```

then from any computer on my lan:
```
git clone  git://192.168.0.151/org.git org
git add ...
git commit ...
git push 
```
Also, while we are getting organized:
1. keepass.git /keepass password db
2. org.git  /org /org/jobsearch /org/todos
3. config.git /config config files, with path at top of each

## Step 2 Consolidate

List current locations and bring together sources. This is going to be a lot of
work.
Luckily chrome passwords has export csv and keepass has import generic csv.

### Locations

- keepass files
1. Laptop
2. Desktop
3. Old Laptop
4. Phone
5. 2 google accounts gdrive
- browser autofils
1. laptop
2. phone

## Step 3 Test push / pull

for each location pull keepass repo from 

- master-life-server ->> 14-dk101ca
- git clone git://192.168.0.151/keepass.git keepass
- ~/keepass/pass.kbdx

## termux / phone setup
- location is downloads/keepass/pass.kbdx
- must use the following because android fs broken (root owns files)
```
git config --global --add safe.directory /storage/emulated/0/Download/keepass
```

## Step 5 Create autofill and sync policies

- do I want to use browser autofil - no - 
- do i want to use google password manager? - no - 
- policy only use local file, sync with git as needed
- there will be no pass.kdbx on gdrive no cloud for passwords policy
- erase all sources of passwords not pass.kdbx - delete browser caches

## Summary

What a nightmare. Hope this works, I am tired of syncronization problems leading
to missing or stale passwords.

Do you think Git is amazing? Let me know!
