---
date: 2016-05-29
categories:
  - it
  - programming
tags:
  - Pascal
  - Сложение двух чисел
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-free-pascal/add-2-num-free-pascal.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-free-pascal/
lang: ru
---

# Сложение двух чисел в Free Pascal IDE на Pascal (консольное приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать консольное приложения сложения двух чисел в Free Pascal IDE.

<details>
<summary>📖 Содержание ⬇️</summary>

## Содержание

- [Установка программы](#установка-программы)
- [Создаем проект](#создаем-проект)
- [Написание кода](#написание-кода)
- [Запуск программы](#запуск-программы)

</details>

## Установка программы

Под спойлером находится краткое описание установки программы.

<details>
<summary>Установка Free Pascal IDE</summary>

Скачиваем программу тут: <https://sourceforge.net/projects/freepascal/files/?source=navbar>:

![Выбор сборки под семейство операционной системы](img/install_01.png)

_Рисунок 1 — Выбор сборки под семейство операционной системы_

![Выбор версии программы](img/install_02.png)

_Рисунок 2 — Выбор версии программы_

![Скачивание установщика](img/install_03.png)

_Рисунок 3 — Скачивание установщика_

И устанавливаем:

![Первое окно установщика](img/install_04.png)

_Рисунок 4 — Первое окно установщика_

![Выбор папки установки приложения](img/install_05.png)

_Рисунок 5 — Выбор папки установки приложения_

![Выбор типа установки](img/install_06.png)

_Рисунок 6 — Выбор типа установки_

![Выбор названия папки в главном меню](img/install_07.png)

_Рисунок 7 — Выбор названия папки в главном меню_

![Дополнительные настройки](img/install_08.png)

_Рисунок 8 — Дополнительные настройки_

![Окно перед установкой программы](img/install_09.png)

_Рисунок 9 — Окно перед установкой программы_

![Установка программы](img/install_10.png)

_Рисунок 10 — Установка программы_

![Завершение установки](img/install_11.png)

_Рисунок 11 — Завершение установки_

</details>

## Создаем проект

Создаем новый проект:

![Создание нового проекта](img/new_project_01.png)

_Рисунок 12 — Создание нового проекта_

![Созданный пустой файл исходного кода](img/new_project_02.png)

_Рисунок 13 — Созданный пустой файл исходного кода_

## Написание кода

Пропишите такой код:

```pascal
uses crt;
var
   a,b,c:integer;
begin
    clrscr;
    writeln('Input first number');
    readln(a);

    writeln('Input second number');
    readln(b);

    c := a + b;

    writeln('Sum ', c);

    readln();
end.
```

## Запуск программы

Вначале скомпилируем приложение:

![Выбор команды компилирования проекта](img/compile.png)

_Рисунок 14 — Выбор команды компилирования проекта_

Перед компиляцией попросит сохранить файл:

![Сохранения файла исходного кода](img/save.png)

_Рисунок 15 — Сохранения файла исходного кода_

При успешном компилировании увидите вот такое окно:

![Окно успешного компилирования проекта](img/compile_02.png)

_Рисунок 16 — Окно успешного компилирования проекта_

И запустим приложение:

![Запуск приложения](img/run.png)

_Рисунок 17 — Запуск приложения_

![Запущенное приложение](img/result_01.png)

_Рисунок 18 — Запущенное приложение_

![Результат выполнения программы](img/result_02.png)

_Рисунок 19 — Результат выполнения программы_
