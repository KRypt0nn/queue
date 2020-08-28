<h1 align="center">🚀 Queue</h1>

**Queue** - библиотека для реализации [структуры данных "очередь"](https://ru.wikipedia.org/wiki/Очередь_(программирование))

## Установка

```cmd
php qero.phar i KRypt0nn/queue
```

```php
<?php

require 'qero-packages/autoload.php';
```

[Что такое Qero?](https://github.com/KRypt0nn/Qero)

<p align="center">или</p>

Скачайте репозиторий и подключите главный файл пакета:

```php
<?php

require 'queue/queue.php';
```

## Быстрый старт

Данная библиотека представлена в единственном классе `Queue\Queue`. Для его инициализации достаточно просто создать данный объект. В качестве параметров он может принимать список элементов. Если при создании объекта не указать аргументов - создастся пустая очередь

```php
<?php

# Создаст очередь ["Hello", "World"]
$queue = new Queue\Queue ([
    'Hello',
    'World'
]);

# Создаст пустую очередь
$queue = new Queue\Queue;
```

Методы данного класса:

| Метод | Аргументы | Вывод | Описание |
| - | - | - | - |
| push | mixed $item | Queue | Добавляет элемент $item в конце очереди и возвращает экземпляр объекта очереди |
| pop | - | mixed | Возвращает элемент из начала очереди и удаляет его. Выбрасывает исключение Exception если очередь пуста |
| count | - | int | Возвращает количество элементов в очереди |
| foreach | callable $callback | Queue | Проходится по каждому элементу очереди от первого к последнему коллбэком function(mixed $item) и возвращает экземпляр объекта очереди |
| where | callable $comparator | array | Возвращает список элементов очереди от первого к последнему, отфильтрованных коллбэком function(mixed $item): bool |
| list | - | array | Возвращает список элементов очереди от первого к последнему |
| clear | - | Queue | Очищает очередь и возвращает её экземпляр объекта |

## Пример работы

```php
<?php

$queue = new Queue\Queue ([
    'Hello'
]);

$queue->push (', ');
$queue->push ('World!');

# Выведет "Hello, World!"
$queue->foreach (function ($item)
{
    echo $item;
});
```

Автор: [Подвирный Никита](https://vk.com/technomindlp). Специально для [Enfesto Studio Group](https://vk.com/hphp_convertation)