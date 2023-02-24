---
date: 2016-05-29
categories: [it, programming]
tags: [Pascal, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
---

# Сложение двух чисел в Free Pascal IDE на Pascal (консольное приложение)

В статье рассказывается как создать консольное приложения сложения двух чисел в Free Pascal IDE.

## Установка программы

Под спойлером находится краткое описание установки программы.

---

**Установка Free Pascal IDE** <!-- !details -->

Скачиваем программу тут: <https://sourceforge.net/projects/freepascal/files/?source=navbar>:

![Выбор сборки под семейство операционной системы](img/install_01.png)

![Выбор версии программы](img/install_02.png)

![Скачивание установщика](img/install_03.png)

И устанавливаем:

![Первое окно установщика](img/install_04.png)

![Выбор папки установки приложения](img/install_05.png)

![Выбор типа установки](img/install_06.png)

![Выбор названия папки в главном меню](img/install_07.png)

![Дополнительные настройки](img/install_08.png)

![Окно перед установкой программы](img/install_09.png)

![Установка программы](img/install_10.png)

![Завершение установки](img/install_11.png)

---

## Создаем проект

Создаем новый проект:

![Создание нового проекта](img/new_project_01.png)

![Созданный пустой файл исходного кода](img/new_project_02.png)

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

Перед компиляцией попросит сохранить файл:

![Сохранения файла исходного кода](img/save.png)

При успешном компилировании увидите вот такое окно:

![Окно успешного компилирования проекта](img/compile_02.png)

И запустим приложение:

![Запуск приложения](img/run.png)

![Запущенное приложение](img/result_01.png)

![Результат выполнения программы](img/result_02.png)