# slim-theme
My SLiM lock screen theme

![screenshot](slim-theme-screenshot.png)



# Gnome
In order to be to lock the screen with Gnome and using SLiM at the same time, one needs to create a new hook `etc/systemd/system/lockit@$USER.service`
```
[Unit]
Description=allow slim as lock screen for gnome
After=sleep.target

[Service]
User=%I
Type=forking
Environment=DISPLAY=:0
ExecStart=/usr/bin/slimlock

[Install]
WantedBy=sleep.target
```
