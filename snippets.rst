#### узнать, что работает на порту
```sh
netstat -tulpn | grep :80
```

#### настройка ssh на сервере
со своего компа
```sh
ssh-copy-id user@de-core.net
serverssh-copy-id root@de-core.net // можно сделать и для рут, если нужен к нему доступ
```
ИЛИ заходим на сервер // вот в маке только такой способ и работает
```sh
ssh user@de-core.net
mkdir .ssh
```
а потом со своего компа
```sh
scp ~/.ssh/id_rsa.pub user@server.ru:~/.ssh/authorized_keys
```

#### файл, куда можно написать команды для выполнения при запуске сервера
```sh
nano /etc/rc.local
```
проверяем работу
```sh
/etc/init.d/rc.local start
```

#### файл, куда можно написать команды для выполнения при входе пользователя
```sh
nano ~/.profile
```
