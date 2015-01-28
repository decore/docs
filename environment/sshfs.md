### Устанавливаем
```sh
sudo apt-get install sshfs
```
Установка своих публичных ключей на хост
со своего компа
```sh
ssh-copy-id user@server // работает в ubuntu
```
или
```sh
заходим на сервер // вот в маке только такой способ и работает
ssh user@server
mkdir .ssh
а потом со своего компа
scp ~/.ssh/id_rsa.pub user@server:~/.ssh/authorized_keys
```
### Прикручиваем папку
```sh
mkdir ~название папки
sshfs user@server:/путь ~/название папки
```
особенность: пусть на сервере нужно указывать от корня системы (pwd в помощь)
### Откручивание папки
```sh
fusermount -u ~/название папки
Часто используемые
sshfs webs@dev.zavode.ru:/webs/p33m2.dev.zavode.ru/p33m2 ~/p33m2
sshfs webs@dev.zavode.ru:/webs ~/webs
sshfs suenot@djng.ru:/hosts ~/hosts
sshfs pereira@46.4.66.71:/var/www/pereira/data/alohaaloha.net ~/aloha
sshfs frontend@178.79.186.93:/home/frontend/projects/tvoidveri_spb ~/tvoidveri_spb
```
Также, можно войти в конкретную папку через ssh
```sh
ssh webs@dev.zavode.ru -t "cd /webs/p33m2.dev.zavode.ru/p33m2; bash --login"
ssh webs@dev.zavode.ru -t "cd /webs/game.dev.zavode.ru/game/templates/shop/; bash --login"
ssh frontend@178.79.186.93 -t "cd ~/projects/tvoidveri_spb; bash --login"
```
