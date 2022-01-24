#### Ставим Command line tools
```sh
https://developer.apple.com/downloads/index.action
```

#### Ставим Homebrew
```sh
http://brew.sh/
```


#### Ставим pip
```sh
sudo easy_install pip
```


#### Установка python3 и pip3
```sh
curl -O http://python-distribute.org/distribute_setup.py
sudo python3 distribute_setup.py
```

```sh
curl -O https://raw.github.com/pypa/pip/master/contrib/get-pip.py
sudo python3 get-pip.py
```

```sh
export PATH=/Library/Frameworks/Python.framework/Versions/3.3/bin:$PATH
```

### Отключаем запуск Music
```
brew install --cask notunes
```

#### Watchers
```sh
echo fs.inotify.max_user_watches=65536 | sudo tee -a /etc/sysctl.conf
cat /etc/sysctl.conf # проверить, что переопределили max_user_watchers
```
