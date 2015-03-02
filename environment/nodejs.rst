Инструкции по установкам
========================

nvm+node+youman
---------------

https://github.com/creationix/nvm

.. code::

    curl https://raw.githubusercontent.com/creationix/nvm/v0.10.0/install.sh | bash

Открыть новую вкладку (возможно нужен sudo)

.. code::

    nvm install 0.12
    nvm use 0.12
    nvm alias default 0.12

.. code::

    npm install -g yo generator-webapp

Для создания в папке стандартного приложения

.. code::

    yo webapp
