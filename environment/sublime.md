### Устанавливаем менеджер пакетов
Копируем код для нужной версии sublime. В sublime открываем консоль ctrl+`, вставляем код, энтер
перезагружаем sublime.
Для ST2:

```sh
import urllib2,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); os.makedirs( ipp ) if not os.path.exists(ipp) else None; urllib2.install_opener( urllib2.build_opener( urllib2.ProxyHandler()) ); by = urllib2.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); open( os.path.join( ipp, pf), 'wb' ).write(by) if dh == h else None; print('Error validating download (got %s instead of %s), please try manual install' % (dh, h) if dh != h else 'Please restart Sublime Text to finish installation')
```

Для ST3: 

```sh
import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```

ctrl+shift+P
package control: install
ставим нужный пакет

### Устаналиваем пакеты

```
sass
ColorPicker
emmet
coffee
stylus
```

По желаению ставим:

```
less
jade
haml
slim
coffeelint
lint
```

### Добавляем нужные параметры в пользовательские настройки

```
"draw_white_space": "all",
"update_check": false,
"folder_exclude_patterns": [".svn", ".hg", "CVS"]
```

### Документация по [Emmet sublime]


[Emmet sublime]:https://github.com/sergeche/emmet-sublime
