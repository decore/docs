Загрузка шрифта на сайт
=======================


1. Скачать шрифт:

.. _a link:

   http://www.webfont.ru 

   http://www.fontzone.net

2. Настроить шрифт при помощи WEBFONT GENARATOR на:

.. _a link:

   http://www.fontsquirrel.com
	Указать параметры:
	*Expert*
	*- Custom Subsetting: language Cyrillic*
3. Установка
    В папке сайта создать папку font  и положить туда файлы шрифта с расширениями .eot, .ttf, .woff.
    В папке css создать папку font и положить туда файл стиля шрифта.
    В общем файле стилей сайта добавить строку:

.. code::

		@import font/_имя файла_шрифта_без расширения