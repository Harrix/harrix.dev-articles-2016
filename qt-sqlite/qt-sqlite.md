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

![Featured image](featured-image.svg)

В статье рассказывается о том, как можно подключить SQLite в Qt.

В данной статье рассмотрен лишь самый простой пример. Более подробный материал смотрите как в [документации](https://doc.qt.io/qt-5/sql-driver.html), так и в статьях других авторов (например, <http://www.prog.org.ru/topic_26665_0.html>).

## Подготовка базы данных

В [статье](https://github.com/Harrix/harrix.dev-blog-2016/blob/main/db-browser-for-sqlite/db-browser-for-sqlite.md) <!-- https://harrix.dev/ru/blog/2016/db-browser-for-sqlite/ --> рассказывается, как создавать базы данных заранее и заполнять их в специальной программе (одной из многих).

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

_Рисунок 1 — Таблица базы данных_

Предположим, что база данных находится в папке `C:\`.

## Создание Qt приложения

Под спойлером показывается процесс создания простого приложения. Получим вот такую картинку:

![Внешниё вид приложения](img/app.png)

_Рисунок 2 — Внешниё вид приложения_

---

**Создание приложения** <!-- !details -->

![Пункт меню для создания нового проекта](img/new-project_01.png)

_Рисунок 3 — Пункт меню для создания нового проекта_

![Выбор типа проекта](img/new-project_02.png)

_Рисунок 4 — Выбор типа проекта_

![Выбор названия проекта и его расположения](img/new-project_03.png)

_Рисунок 5 — Выбор названия проекта и его расположения_

![Выбор компилятора](img/new-project_04.png)

_Рисунок 6 — Выбор компилятора_

![Выбор названия главного класса](img/new-project_05.png)

_Рисунок 7 — Выбор названия главного класса_

![Настройка системы контроля версий](img/new-project_06.png)

_Рисунок 8 — Настройка системы контроля версий_

![Окно Qt Creator с созданным проектом](img/new-project_07.png)

_Рисунок 9 — Окно Qt Creator с созданным проектом_

![Элементы на форме приложения](img/new-project_08.png)

_Рисунок 10 — Элементы на форме приложения_

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

_Рисунок 11 — Измененный PRO файл_

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

_Рисунок 12 — Результат работы программы_

P.S. В [статье](https://github.com/Harrix/harrix.dev-blog-2014/blob/main/output-data-to-qtableview/output-data-to-qtableview.md) <!-- https://harrix.dev/ru/blog/2014/output-data-to-qtableview/ --> рассказывается, как закидывать данные в таблицу в компонент `QTableView`.
