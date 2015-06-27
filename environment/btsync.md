### Взять от сюда:
```sh
http://forum.bittorrent.com/topic/18974-debian-and-ubuntu-server-unofficial-packages-for-bittorrent-sync/
```

### Установка:
```sh
sh -c "$(curl -fsSL http://debian.yeasoft.net/add-btsync-repository.sh)"
`which sudo` apt-get update
`which sudo` apt-get install btsync
```

### Если надо перенастроить:
```sh
`which sudo` dpkg-reconfigure btsync
```