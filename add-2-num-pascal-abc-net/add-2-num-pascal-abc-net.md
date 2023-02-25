---
date: 2016-04-02
categories: [it, programming]
tags: [Pascal, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/add-2-num-pascal-abc-net/add-2-num-pascal-abc-net.md
url: https://harrix.dev/ru/blog/2016/add-2-num-pascal-abc-net/
lang: ru
---

# Сложение двух чисел в PascalABC.NET на Pascal (консольное приложение)

В статье рассказывается как создать консольное приложения сложения двух чисел в PascalABC.NET.

## Установка программы

Под спойлером находится краткое описание установки программы.

---

**Установка PascalABC.NET** <!-- !details -->

Скачиваем программу на сайте <http://pascalabc.net/>:

![Скачивание установщика](img/install_01.png)

![Выбор установщика](img/install_02.png)

И устанавливаем:

![Выбор устанавливаемых компонентов](img/install_03.png)

![Выбор папки для программы](img/install_04.png)

![Выбор рабочей папки](img/install_05.png)

![Процесс установки](img/install_06.png)

![Завершение установки](img/install_07.png)

---

## Создаем проект

Открываем программу PascalABC.NET (программа открывается не очень быстро):

![Первоначальное окно программы](img/app.png)

Создаем новый проект:

![Создание нового проекта](img/new-project_01.png)

Выбираем консольное приложение и название проекта:

![Выбор типа нового проекта](img/new-project_02.png)

Появится вот такая болванка:

![Созданный новый проект](img/new-project_03.png)

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

![Поле для ввода данных](img/run_02.png)

![Результат выполнения программы](img/run_03.png)
