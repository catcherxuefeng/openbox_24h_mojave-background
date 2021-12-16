## Download and unzip Mojave dynamic background 
> here: https://files.rb.gd/mojave_dynamic.zip 
and rename them to 1-16.jpeg 
## Create a Mojave-background.sh 
```bash
cat Shells/mojave-background.sh 
#!/bin/bash
H_DATE=`date "+%H"`
PIC=/home/catcher/Pictures/mojave-background

ARY15=(00 01 02)
ARY16=(03 04)
ARY1=(05)
ARY2=(06)
ARY3=(07)
ARY4=(08)
ARY5=(09)
ARY6=(10)
ARY7=(11 12)
ARY8=(13)
ARY9=(14)
ARY10=(15)
ARY11=(16)
ARY12=(17)
ARY13=(18 19)
ARY14=(20 21 22 23)


if [[ "${ARY1[@]}" =~ "$H_DATE" ]]; then 
    feh --bg-scale $PIC/1.jpeg
    exit 0
fi
if [[ ${ARY2[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/2.jpeg
    exit 0
fi
if [[ ${ARY3[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/3.jpeg
    exit 0
fi
if [[ ${ARY4[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/4.jpeg    
    exit 0

fi
if [[ ${ARY5[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/5.jpeg    
    exit 0
fi
if [[ ${ARY6[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/6.jpeg
    exit 0
fi
if [[ ${ARY7[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/7.jpeg
    exit 0
fi
if [[ ${ARY8[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/8.jpeg
    exit 0
fi
if [[ ${ARY9[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/9.jpeg
    exit 0
fi
if [[ ${ARY10[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/10.jpeg
    exit 0
fi
if [[ ${ARY11[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/11.jpeg
    exit 0
fi
if [[ ${ARY12[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/12.jpeg
    exit 0
fi
if [[ ${ARY13[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/13.jpeg
    exit 0
fi
if [[ ${ARY14[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/14.jpeg
    exit 0
fi
if [[ ${ARY15[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/15.jpeg
    exit 0
fi
if [[ ${ARY16[@]} =~ $H_DATE ]]; then 
    feh --bg-scale $PIC/16.jpeg
    exit 0
fi
exit 0
```

## openbox autostart
cat .config/openbox/autostart
```bash
## Restore Wallpaper
sh $HOME/.fehbg
```
## Create a systemd-timer & systemd-service
```bash
systemctl --user cat mojave-background.timer 
[Unit]
Description=每小时更换一次壁纸

[Timer]
OnCalendar=*-*-* *:00:00
Unit=mojave-background.service

[Install]
WantedBy=timers.target

systemctl --user cat mojave-background.service
[Unit]
Description=每小时更换一次壁纸

[Service]
ExecStart=/bin/bash /home/catcher/Shells/mojave-background.sh

```
