Git + Heroku
============


Heroku
------------------------------

Проект не создан на heroku.com, инициализируем и создаем из консоли

.. code::

    git init
    heroku create название проекта
    git add .
    git commit -m “название коммита”
    git push -u heroku master

Стандартный config, если проект уже создан на heroku.com

.. code::

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

Чтобы добавить collabarators в проект

.. code::

    heroku sharing:add email@gmail.com

Чтобы передать проект

.. code::

    heroku sharing:transfer suenot@gmail.com


Как откатить коммиты на github.com
----------------------------------

Ситуация когда у вас уже есть клон репозитория с которым вы работаете, делаете pull и смотрите что там какая то фигня накоммитчена от разработчиков.

Выбираем нужную ветку, у меня она master

.. code::

    git checkout master

делаем откат изменений в репозитории для примера на два коммита назад

.. code::

     git reset --hard HEAD~2

Можно сделать до какого то определенного коммита по хешу

.. code::

    git reset --hard HEAD hash
    ( git reset --hard hash )

Хеш можно взять в вебинтерфейсе гитхаба.

Далее делаем принудительный коммит в основной репо на гитхабе

.. code::

    git push -f origin master

без -f будет ругаться что у вас версия младше чем в гитхабе и вам надо сделать pull
