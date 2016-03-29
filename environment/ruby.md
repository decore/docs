Ruby
====

### [rvm + ruby](https://rvm.io/rvm/install)

```
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
\curl -sSL https://get.rvm.io | bash -s stable --ruby
```
и в новой вкладке выполнить

```
rvm install 2.1
rvm use 2.1 --default
```

### gemsets

на каждый тип проекта делаем свой gemset
```
rvm gemset create teddy
```

используем гемсет
```
rvm gemset use teddy
```
или
```
rvm use 2.1.1@teddy --default
```
