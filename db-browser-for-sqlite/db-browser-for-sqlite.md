---
date: 2016-03-22
categories: [it, programming]
tags: [SQLite, Базы данных]
update: 2019-08-05
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/db-browser-for-sqlite/db-browser-for-sqlite.md
url: https://harrix.dev/ru/blog/2016/db-browser-for-sqlite/
lang: ru
---

# Создание SQLite базы данных в DB Browser for SQLite

![Featured image](featured-image.svg)

Базы данных [SQLite](https://ru.wikipedia.org/wiki/SQLite) очень удобны для работы с небольшими объемами данных как в Windows приложениях, так и в Android приложениях. В статье говорится, как создавать и подготавливать базы данных заранее.

Особенно SQLite удобен тем, что не нужно поднимать сервер СУБД перед использованием в приложениях.

## Установка DB Browser for SQLite

Итак, скачиваем версию без установщика `DB Browser for SQLite` (`SQLiteBrowser`): <http://sqlitebrowser.org>:

![Скачивание установщика](img/download.png)

Просто распаковываем архив. В нем будет два EXE файла:

![Файлы в распакованной папке](img/app_01.png)

Файл `DB Browser for SQLite.exe` представляет обычную версию программы, а файл `DB Browser for SQLCipher.exe` позволяет работать с зашифрованными базами данных. И во второй программе есть вот такой пункт:

![Возможность шифрования базы данных](img/sqlcipher.png)

Окно программы:

![Окно программы](img/app_02.png)

## Создание базы данных

Создадим простую базу данных `database` с одной таблицей и тремя столбцами:

![Создание новой базы данных](img/database_01.png)

![Выбор имени файла новой базы данных](img/database_02.png)

Появится окно создания таблицы в программе:

![Открытая база данных](img/database_03.png)

Создадим таблицу `People`:

![Создание таблицы People](img/database_04.png)

Ввиду того, что вдруг база данных будет использоваться в Android, то первым полем задавайте идентификатор по имени `_id`:

![Создание поля _id](img/database_05.png)

Добавим, например, поля `Name` и `Age`:

![Создание полей базы данных](img/database_06.png)

![Структура базы данных](img/database_07.png)

Во вкладке `Данные` можем вносить данные:

![Вкладка Данные](img/database_08.png)

![Ввод первой строчки данных](img/database_09.png)

Сохраним изменения:

![Сохранение базы данных](img/database_10.png)

У вас есть готовая база данных SQLite, которую можете использовать, где вам нужно:

![Сохраненный файл базы данных](img/database_11.png)
