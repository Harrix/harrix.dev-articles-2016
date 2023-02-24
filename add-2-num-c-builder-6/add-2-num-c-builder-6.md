---
date: 2016-05-28
categories: [it, programming]
tags: [C++, C++ Builder, Borland, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/add-2-num-c-builder-6/add-2-num-c-builder-6.md
---

# Сложение двух чисел в C++ Builder 6 на C++

В статье рассказывается о создании приложения сложения двух чисел в древнем и старом C++ Builder 6.

## Создание нового приложения

Переходим в `File` → `New` → `Application`:

![Создание нового приложения](img/new-project_01.png)

![Подтверждение сохранения изменений прошлого проекта](img/new-project_02.png)

Появится вот такой вид:

![Созданный проект](img/new-project_03.png)

Сохраняем всё в папке новой:

![Сохранение проекта](img/new-project_04.png)

![Выбор папки и названия CPP файла проекта](img/new-project_05.png)

![Выбор названия файла проекта](img/new-project_06.png)

## Заполняем форму

На форму кидаем два поля ввода:

![Компонент Edit](img/controls_01.png)

Кидаем на форму также кнопку:

![Компонент Button](img/controls_02.png)

Еще кидаем поле для вывода многострочного текста:

![Компонент Memo](img/controls_03.png)

В поле для вывода `Memo1` удалим первоначальное содержимое:

![Параметр Lines компонента Memo](img/controls_04.png)

![Удаление первоначального содержимого](img/controls_05.png)

Также в поля ввода `Edit1` и `Edit2` введем первоначальное значение:

![Ввод начального значения в поля ввода](img/controls_06.png)

## Написание кода

Теперь можно переходить к написанию кода.

Двойной клик по кнопке:

![Двойной клик по кнопке](img/click_01.png)

И видим это:

![Созданный метод для обработки клика кнопки](img/click_02.png)

И вводим такой код:

```cpp
AnsiString S1 = Edit1->Text;
AnsiString S2 = Edit2->Text;

int a = S1.ToInt();
int b = S2.ToInt();

int c = a + b;

Memo1->Lines->Add(AnsiString(a) + " + " + AnsiString(b) + " = " + AnsiString(c));
```

![Код, срабатываемый при клике на кнопку](img/click_03.png)

Теперь сохраняем всё и запускаем приложение:

![Запуск приложения](img/run.png)

При нажатии на кнопку вы получите результат:

![Результат выполненного приложения](img/result.png)

## Запуск приложения на компьютере без C++ Builder

Кстати, чтобы приложение EXE файл запускался без C++ Builder, сделайте это:

![Настройки проекта](img/without-c-builder_01.png)

![Настройки Linker](img/without-c-builder_02.png)

![Настройки Compiler](img/without-c-builder_03.png)

![Настройки Packages](img/without-c-builder_04.png)
