Ruby
====

rvm + ruby + rails
------------------------------------------------
.. code::

    wget --no-check-certificate https://raw.github.com/joshfng/railsready/master/railsready.sh &&bash railsready.sh

// и в новой вкладке выполнить

.. code::

    rvm install 2.1
    rvm use 2.1 --default

или

.. code::

    curl -L https://get.rvm.io | bash

// и в новой вкладке выполнить

.. code::

    rvm install 2.1
    rvm use 2.1 --default

на каждый тип проекта делаем свой gemset

.. code::

    rvm gemset create teddy

используем гемсет

.. code::

    rvm gemset use teddy

либо

.. code::

    rvm use 2.1.1@teddy --default
