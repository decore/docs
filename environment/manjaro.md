### Guide

- [https://lobotuerto.com/blog/manjaro-linux-i3-setup-cheat-sheet/#.i3%2Fconfig-changes](complex guilde)

### Inotify

```
# set inotify
echo fs.inotify.max_user_watches=524288 | sudo tee \
/etc/sysctl.d/40-max-user-watches.conf && sudo sysctl --system
# check inotify
cat /proc/sys/fs/inotify/max_user_watches
```

### Python

```
sudo pacman -S python-virtualenv
```
