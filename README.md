# slim-theme
My SLiM lock screen theme

![screenshot](slim-theme-screenshot.png)


Usage
-------
Copy or link the theme into `/etc/usr/share/slim/themes/<my-slim-theme>`. 
To apply the new theme, enter the theme name in the current_theme line in `/etc/slim.conf`

```
#current_theme       default
current_theme        <my-slim-theme>
```


Gnome
-------
In order to lock the screen with Gnome and using SLiM at the same time, one needs to create a new hook `etc/systemd/system/lockit@$USER.service`
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

License
-------
This project is licensed under the MIT License.
