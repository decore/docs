nvm+node+yoman
---------------

##### Ставим nvm
```
curl https://raw.githubusercontent.com/creationix/nvm/v0.10.0/install.sh | bash
```
[документация](https://github.com/creationix/nvm)

##### Открыть новую вкладку и ставим nodejs
```
nvm install 0.12
nvm use 0.12
nvm alias default 0.12
```

##### Устанавливаем yeoman
```
npm install -g yo generator-webapp
```

##### Для создания в папке стандартного приложения
```
yo webapp
```
