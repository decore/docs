nvm+node
---------------

### Обходим ограничение на количество отслеживаемых файлов
```
echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
```

### Ставим nvm
```
curl https://raw.githubusercontent.com/creationix/nvm/v0.10.0/install.sh | bash
```
[документация](https://github.com/creationix/nvm)

### Открыть новую вкладку и ставим nodejs
```
nvm install 6
nvm use 6
nvm alias default 6
```

### Для использования локальных пакетов добавляем PATH
```
PATH=$PATH:node_modules/.bin
```

### ws простой локальный сервер
```
npm install -g local-web-server
```
#### запуск
```
ws
```
#### запуск с gzip + ngrok (для прохождения тестов google page speed)
```
ws -c
ngrok http 8000
```
