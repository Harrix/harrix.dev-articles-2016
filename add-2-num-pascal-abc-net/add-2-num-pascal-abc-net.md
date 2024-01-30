---
date: 2016-04-02
categories: [it, programming]
tags: [Pascal, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-pascal-abc-net/add-2-num-pascal-abc-net.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-pascal-abc-net/
lang: ru
---

# Сложение двух чисел в PascalABC.NET на Pascal (консольное приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать консольное приложения сложения двух чисел в PascalABC.NET.

## Установка программы

Под спойлером находится краткое описание установки программы.

---

**Установка PascalABC.NET** <!-- !details -->

Скачиваем программу на сайте <http://pascalabc.net/>:

![Скачивание установщика](img/install_01.png)

_Рисунок 1 — Скачивание установщика_

![Выбор установщика](img/install_02.png)

_Рисунок 2 — Выбор установщика_

И устанавливаем:

![Выбор устанавливаемых компонентов](img/install_03.png)

_Рисунок 3 — Выбор устанавливаемых компонентов_

![Выбор папки для программы](img/install_04.png)

_Рисунок 4 — Выбор папки для программы_

![Выбор рабочей папки](img/install_05.png)

_Рисунок 5 — Выбор рабочей папки_

![Процесс установки](img/install_06.png)

_Рисунок 6 — Процесс установки_

![Завершение установки](img/install_07.png)

_Рисунок 7 — Завершение установки_

---

## Создаем проект

Открываем программу PascalABC.NET (программа открывается не очень быстро):

![Первоначальное окно программы](img/app.png)

_Рисунок 8 — Первоначальное окно программы_

Создаем новый проект:

![Создание нового проекта](img/new-project_01.png)

_Рисунок 9 — Создание нового проекта_

Выбираем консольное приложение и название проекта:

![Выбор типа нового проекта](img/new-project_02.png)

_Рисунок 10 — Выбор типа нового проекта_

Появится вот такая болванка:

![Созданный новый проект](img/new-project_03.png)

_Рисунок 11 — Созданный новый проект_

## Написание кода

Пропишите такой код:

```pascal
var
   a,b,c:integer;
begin
    writeln('Input first number');
    readln(a);

    writeln('Input second number');
    readln(b);

    c := a + b;

    writeln('Sum ', c);
end.
```

## Запуск программы

![Кнопка запуска программы](img/run_01.png)

_Рисунок 12 — Кнопка запуска программы_

![Поле для ввода данных](img/run_02.png)

_Рисунок 13 — Поле для ввода данных_

![Результат выполнения программы](img/run_03.png)

_Рисунок 14 — Результат выполнения программы_
