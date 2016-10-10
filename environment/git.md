# Git

### Как откатить коммиты на github.com

1. Выбираем нужную ветку, у меня она master
```
git checkout master
```

2. Делаем откат изменений в репозитории, например,
на два коммита назад:
```git reset --hard HEAD~2```
или на конкретный коммит по хешу (можно посмотреть через ```git log```):
```git reset --hard HEAD hash```
или откатить все до последнего коммита (удобно после пула не в ту ветку):
```git reset --hard HEAD```

3. Далее делаем принудительный коммит в основной репо на гитхабе: без -f будет ругаться что у вас версия младше чем в гитхабе и вам надо сделать pull
```
git push -f origin master
```

# Heroku
Проект не создан на heroku.com, инициализируем и создаем из консоли
```
git init
heroku create название проекта
git add .
git commit -m “название коммита”
git push -u heroku master
```
Стандартный config, если проект уже создан на heroku.com
```
[core]
  repositoryformatversion = 0
  filemode = false
  bare = false
  logallrefupdates = true
  symlinks = false
  ignorecase = true
  hideDotFiles = dotGitOnly
[remote "heroku"]
  url = git@heroku.com:название проекта.git
  fetch = +refs/heads/*:refs/remotes/heroku/*
[branch "master"]
  remote = origin
  merge = refs/heads/master
```

Чтобы добавить collabarators в проект
```
heroku sharing:add suenot@gmail.com
```

Чтобы передать проект
```
heroku sharing:transfer suenot@gmail.com
```
