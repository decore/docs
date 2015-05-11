#### узнать, что работает на порту
```sh
netstat -tulpn | grep :80
```

#### узнать версию и разрядность системы, а также версию ядра
```sh
cat /etc/*release* 
DISTRIB_ID=Ubuntu 
DISTRIB_RELEASE=8.04 
DISTRIB_CODENAME=hardy 
DISTRIB_DESCRIPTION="Ubuntu 8.04.1"
```
или
```sh
lsb_release -a
No LSB modules are available.
Distributor ID:	Ubuntu
Description:	Ubuntu 8.04.1
Release:	8.04
Codename:	hardy
```
```sh
uname -a
Linux parazit 2.6.35-24-generic #42-Ubuntu SMP Thu Dec 2 01:41:57 UTC 2010 i686 GNU/Linux
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
