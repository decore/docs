# Jade - HTML препроцессор

**Статус:** в разработке.

На проекте используется шаблонизатор [Jade](http://jade-lang.com/) для компиляции в HTML.

Полезные ссылки для ознакомления:
* [jade-lang.com](http://jade-lang.com/) - документация Jade.
* [naltatis.github.io/jade-syntax-docs](http://naltatis.github.io/jade-syntax-docs/) - ещё одна документация Jade.
* [jsman.ru/jade/](http://jsman.ru/jade/) - ещё одна документация Jade.
* [html2jade.org](http://html2jade.org/) - конвертация HTML в Jade и Jade в HTML.
* [html2jade.aaron-powell.com](http://html2jade.aaron-powell.com/) - и еще один инструмент для конвертации HTML → Jade.


## 1. Назначение папок

```
templates/                     # Папка с шаблонами Jade
├── blocks/                    # Папка с подключаемыми блоками
├── helpers/                   # Папка с помощниками
│   ├── mixins.jade            # Примеси
│   └── variables.jade         # Переменные
├── layouts/                   # Папка с шаблонами раскладки
│   └── default.jade           # Шаблон раскладки по умолчанию
├── pages/                     # Папка с генерируемыми страницами
│   └── index.jade             # Шаблон одной из страниц
└── partials/                  # Папка с подлючаемыми шаблонами
    ├── head.jade              # Шаблон с ресурсами, SEO и мета-тегами
    └── foot.jade              # Шаблон со скриптами
```


## 2. Подключение частиц в страницы

* `include block/header` -  вставляем код из файла.
* `extends partials/default` -  наследуемся от шаблона.
* `block content` - используется для добавления строк кода в определённое место.

Во всех случаях через пробел указывается путь от текущего расположения до шаблона без расширения `.jade`.


## 3. Теги, классы и идентификаторы

- Классы и идентификаторы пишутся в начале, а не в атрибутах. Указывать тег `div` не нужно, т.к. он используется по умолчанию.
```jade
//- Плохо
div(class='carousel' id="carousel")
nav(class='nav nav_pos_left')
div(id="carousel")

//- Хорошо
.carousel
nav.nav.nav_pos_left
#carousel
```

- Идентификатор ставится после классов.
```jade
//- Плохо
.carousel#carousel.carousel_theme_dark
#carousel.carousel

//- Хорошо
.carousel.carousel_theme_dark#carousel
.carousel#carousel
```


## 4. Атрибуты элемента и их значения

- Для нескольких атрибутов запятая не нужна.
```jade
//- Плохо
input.input-text(type='text', name='auto', value='bmw', required)

//- Хорошо
input.input-text(type='text' name='auto' value='bmw' required)
```

- Используйте двойные кавычки для текстовых значений.
```jade
//- Плохо
input.input-text(type='text' name='auto' value='bmw' required)

//- Хорошо
input.input-text(type="text" name="auto" value="bmw" required)
```

- Не давайте необязательные значения атрибутам.
```jade
//- Плохо
input.input-checkbox(type='checkbox' name='browser[]' value='chrome' checked='checked')

//- Хорошо
input.input-checkbox(type='checkbox' name='browser[]' value='chrome' checked)
```

- Распологайте одиночные атрибуты в последнюю очередь.
```jade
//- Плохо
input.input-checkbox(type='checkbox' checked name='browser[]' value='chrome')

//- Хорошо
input.input-checkbox(type='checkbox' name='browser[]' value='chrome' checked)
```

- Для числовых значений кавычки не нужны.
```jade
//- Плохо
input.input-text(type="text" name="price" value="24999")

//- Хорошо
input.input-text(type='text' name='price' value=24999)
```

- Переносите атрибуты новую строку, если их много и/или значения длинные.
```jade
//- Плохо
input.input-text(type='text' name='project' value='csssr' data-required='Это поле обязательно для заполнения!'  data-hint='Допустимы только символы латинского алфавита `[a-z-A-Z]` и числа `[0-9]`.' required)

//- Хорошо
input.input-text(
    type='text'
    name='project'
    value='csssr'
    data-required='Это поле обязательно для заполнения!'
    data-hint='Допустимы только символы латинского алфавита `[a-z-A-Z]` и числа `[0-9]`.'
    required
)
```

## 5. Переносы строк

- Стараемся поменьше использовать `|`.
```jade
//- Плохо
.project
   .project__desc
      | Lorem ipsum dolor sit amet, consectetur adipisicing elit.
      | Unde doloremque neque facilis sed repudiandae tempore ipsum provident officia eaque quas.

//- Хорошо
.project
   .project__desc.
      Lorem ipsum dolor sit amet, consectetur adipisicing elit.
      Unde doloremque neque facilis sed repudiandae tempore ipsum provident officia eaque quas.
```

- Строчные элементы можно записывать на одной строке через двоеточие `:`.<br>Не злоупотреблять с длинными классами.
```jade
//- Хорошо
ul.nav
   li.nav__item
      a.nav__link(href='/') Главная
   li.nav__item
      a.nav__link(href='/projects') Проекты
   li.nav__item
      a.nav__link(href='/contacts') Контакты

//- Лучше
ul.nav
    li.nav__item: a.nav__link(href='/') Главная
    li.nav__item: a.nav__link(href='/projects') Проекты
    li.nav__item: a.nav__link(href='/contacts') Контакты
```

## 6. Комментарии

- Комментарии в Jade, которые не должны попасть в HTML записываются через `//-`.
```jade
// Этот комментарий попадёт в HTML.

//- Этот комментарий не попадёт в HTML.
```

- Простые или условные комментарии можно записывать прямо в HTML-формате.
```html
<!--[if IE]>
meta(name='imagetoolbar' content='no')
meta(name='msthemecompatible' content='no')
<![endif]-->

<!--noindex-->
Это содержимое не будет индексироваться поисковиком.
<!--/noindex-->
```


## 7. Пиши меньше, делай больше или используйте примеси!

Для однотипных и повторяющихся строк кода имеет смысл использовать [примеси (mixins)](http://jade-lang.com/reference/#mixins) и указать только данные.
```html
mixin tools(list)
    ul.list
        each item in list
            li.list__item
                span.mark= item[0]
                = ' - ' + item[1]

+tools([
    ['spritesmith', 'генератор спрайтов и CSS переменных'],
    ['imagemin', 'сжатие картинок']
])
```

Скомпилирует

```html
<ul class="list">
    <li class="list__item">
        <span class="mark">spritesmith</span> - генератор спрайтов и CSS переменных
    </li>
    <li class="list__item">
        <span class="mark">imagemin</span> - сжатие картинок
    </li>
</ul>
```
