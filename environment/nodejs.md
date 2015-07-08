nvm+node+yoman
---------------

1. Ставим nvm
```
curl https://raw.githubusercontent.com/creationix/nvm/v0.10.0/install.sh | bash
```
[документация](https://github.com/creationix/nvm)

2. Открыть новую вкладку и ставим nodejs
```
nvm install 0.12
nvm use 0.12
nvm alias default 0.12
```

3. Устанавливаем yeoman
```
npm install -g yo generator-webapp
```

4. Для создания в папке стандартного приложения
```
yo webapp
```
