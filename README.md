rfinddeleted is a quick hack to find all deleted but not wiped files. It's caused by a process owning a file descriptor on this file. Sometimes it's on purpose, sometimes not.

As you can see I rm'ed a rails log file, but the process isn't aware so the space is used and the log are not longer accessible easily (You can access it using the proc/PID/fd/FD entry).

```
    sudo ./rfinddeleted 

    find deleted but not closed files in directory : /
    Top 5 users
    simkim 42.339MB
    Top 5 files
    20541 /home/simkim/git/obi/log/development.log (deleted) 42.182MB
    3468 /home/simkim/.thunderbird/nw9l87wx.default/calendar-data/deleted.sqlite 96KB
    23312 /var/tmp/etilqs_5Dj9cjA6xG3SzNN (deleted) 32KB
    23312 /var/tmp/etilqs_JicOu5vhsmGMXYi (deleted) 32KB
    23312 /var/tmp/etilqs_Woss1sMbmJbnpa6 (deleted) 512B
```
