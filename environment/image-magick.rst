Image Magick
============

Изменение размера и качества картинок
-------------------------------------

1) Изменить размер фото до 400px на 300px с качестом 30% и перезаписать их:

.. code::

   find . -iregex '.*.jpg' -exec convert '{}' -resize 400*300 -quality 30 jpg:'{}' \;
или тоже самое, но проще

.. code::

   mogrify -resize 400*300 -quality 30  *.jpg
Можно указать только ширину или только высоту:

.. code::

   mogrify -resize 400*  *.jpg (ширина 400px)
   mogrify -resize *300   *.jpg (высота 300px)

2) Cоздает папку “new”, куда и закидывает измененные фото

.. code::

   mkdir new; for f in *.jpg ; do convert -quality 30 -resize 400x300 "$f" "new/${f%.jpg}.jpg" ;

