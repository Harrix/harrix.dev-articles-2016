---
date: 2016-03-22
categories: [it, programming]
tags: [SQLite, Qt]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/qt-sqlite/qt-sqlite.md
url: https://harrix.dev/ru/blog/2016/qt-sqlite/
lang: ru
---

# Подключение базы данных SQLite в Qt

В статье рассказывается о том, как можно подключить SQLite в Qt.

В данной статье рассмотрен лишь самый простой пример. Более подробный материал смотрите как в [документации](https://doc.qt.io/qt-5/sql-driver.html), так и в статьях других авторов (например, <http://www.prog.org.ru/topic_26665_0.html>).

## Подготовка базы данных

В [статье](https://github.com/Harrix/harrix.dev-blog-2016/blob/main/db-browser-for-sqlite/db-browser-for-sqlite.md) рассказывается, как создавать базы данных заранее и заполнять их в специальной программе (одной из многих).

В данной статье будем придерживаться именно этой идеологии: проектирование базы данных и её создание мы осуществляем не в Qt.

Итак, допустим у нас есть небольшая [база данных](files/database.zip), в которой есть одна таблица и три столбца:

```sql
CREATE TABLE `People` (
`_id`  INTEGER PRIMARY KEY AUTOINCREMENT,
`Name`  TEXT NOT NULL,
`Age`  INTEGER NOT NULL
)
```

![Таблица базы данных](img/table.png)

Предположим, что база данных находится в папке `C:\`.

## Создание Qt приложения

Под спойлером показывается процесс создания простого приложения. Получим вот такую картинку:

![Внешниё вид приложения](img/app.png)

---

**Создание приложения** <!-- !details -->

![Пункт меню для создания нового проекта](img/new-project_01.png)

![Выбор типа проекта](img/new-project_02.png)

![Выбор названия проекта и его расположения](img/new-project_03.png)

![Выбор компилятора](img/new-project_04.png)

![Выбор названия главного класса](img/new-project_05.png)

![Настройка системы контроля версий](img/new-project_06.png)

![Окно Qt Creator с созданным проектом](img/new-project_07.png)

![Элементы на форме приложения](img/new-project_08.png)

---

## Подключение базы данных

В файле `.pro` пропишите подключение блока `sql`.

Было:

```text
QT += core gui
```

Стало:

```text
QT += core gui sql
```

![Измененный PRO файл](img/pro.png)

Подключите инклуды:

```h
#include "QtSql/QSqlDatabase"
#include "QSqlQuery"
```

И в клике кнопки (или где вы хотите) пропишем код:

```cpp
// Подключаем базу данных
QSqlDatabase db;
db = QSqlDatabase::addDatabase("QSQLITE");
db.setDatabaseName("C:\\database.db3");
db.open();

// Осуществляем запрос
QSqlQuery query;
query.exec("SELECT _id, name, age FROM People");

// Выводим значения из запроса
while (query.next()) {
  QString _id = query.value(0).toString();
  QString name = query.value(1).toString();
  QString age = query.value(2).toString();
  ui->textEdit->insertPlainText(_id+" "+name+" "+age+"\n");
  }
```

![Результат работы программы](img/result.png)

P.S. В [статье](https://github.com/Harrix/harrix.dev-blog-2014/blob/main/output-data-to-qtableview/output-data-to-qtableview.md) рассказывается, как закидывать данные в таблицу в компонент `QTableView`.
