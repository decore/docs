Image Magick
============

Установка

```
   sudo apt-get install -y imagemagick
```

### Изменение размера и качества картинок

1) Изменить размер фото до 400px на 300px с качестом 30% и перезаписать их:

```
   find . -iregex '.*.jpg' -exec convert '{}' -resize 400*300 -quality 30 jpg:'{}' \;
или тоже самое, но проще
```
чаще не нужно уменьшать размер, а только качество:
```
find . -iregex '.*.jpg' -exec convert '{}' -quality 30 jpg:'{}' \;
```

```
   mogrify -resize 400*300 -quality 30  *.jpg
   Можно указать только ширину или только высоту:
```

```
   mogrify -resize 400*  *.jpg (ширина 400px)
   mogrify -resize *300   *.jpg (высота 300px)
```

2) Cоздает папку “new”, куда и закидывает измененные фото

```
   mkdir new; for f in *.jpg ; do convert -quality 30 -resize 400x300 "$f" "new/${f%.jpg}.jpg" ;
```
