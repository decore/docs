### Установка php >=5.4 (по-умолчанию пока ставится 5.3)
```sh
sudo apt-get install python-software-properties
sudo add-apt-repository ppa:ondrej/php5
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install php5-cgi
```
Проверка
```sh
php -v
```
Запуск php >=5.4 без apache/nginx прямо из директории
```sh
php -S 0.0.0.0:4000
```