# HTMX
HTMX

https://unpkg.com/

=======================

## Подключение библиотеки:
1. Лучший в head
2. Атрибуты type, async и defer не нужны

```HTML
<head>
    <!-- Подключение библиотеки HTMX -->
    <script src="https://unpkg.com/htmx.org"></script>
</head>
```


## Версия
Можно подключить другую версию
```HTML
<script src="https://unpkg.com/htmx.org@2.0.4"></script>
https://unpkg.com/browse/htmx.org@2.0.4/
```



=============================


HTMX всегда требует сервер!
HTMX всегда требует сервер, потому что его главная задача - отправлять запросы на сервер и получать HTML в ответ
HTMX всегда работает по схеме: "отправить запрос на сервер → получить HTML → вставить его на страницу"
Поэтому нам всегда нужен какой-то сервер
HTMX может работать с любым бэкендом, но самые популярные связки:
HTML + HTMX + PHP (самый простой старт)
HTML + HTMX + Node.js (современный подход)
HTML + HTMX + Python (Flask/Django)


=================

## Атрибуты
```HTML
<!-- Кнопка с атрибутом hx-get -->
<button hx-get="hx-get.php">
    Нажми на меня
</button>


<!-- hx-target -->
<button hx-get="hx-target.php" hx-target="#результат">
    Нажми на меня
</button>

<!-- Место для результата -->
<div id="результат">
    Здесь появится привет
</div>
```

Если бы не указали hx-target, то контент, полученный от сервера, заменил бы сам элемент, который вызвал запрос (например, кнопку), но мы хотим обновить только определённую часть страницы, а не всю.



## Ошибки в консоли
Следующие ошибки связанные с тем что нет файла hx-get="hx-get.php"
```
hx-get.php:1 Failed to load resource: the server responded with a status of 404 ()
```
При клике переходим во вкладку Sources и видим "No resource with given identifier found"
```
htmx.org:1 Response Status Error Code 404 from hx-get.php
b @ htmx.org:1
ce @ htmx.org:1
fe @ htmx.org:1
Mr @ htmx.org:1
b.onload @ htmx.org:1
load
he @ htmx.org:1
(anonymous) @ htmx.org:1
i @ htmx.org:1
```
А если тут кликнуть а после открыть в новом окне то переходим
в https://unpkg.com/htmx.org@1.9.12/dist/htmx.min.js
