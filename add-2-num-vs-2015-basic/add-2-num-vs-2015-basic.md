---
date: 2016-05-29
categories:
  - it
  - programming
tags:
  - Basic
  - Visual Studio
  - Сложение двух чисел
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-vs-2015-basic/add-2-num-vs-2015-basic.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-vs-2015-basic/
lang: ru
attribution:
  - author: Microsoft Corporation
    author-site: https://www.microsoft.com/
    license: Public domain
    license-url: https://en.wikipedia.org/wiki/Public_domain
    permalink: https://commons.wikimedia.org/wiki/File:Visual_Studio_2017_Logo.svg
    permalink-date: 2019-06-08
    name: Visual Studio 2017 Logo.svg
---

# Сложение двух чисел в Visual Studio 2015 на Basic

![Featured image](featured-image.svg)

В статье рассказывается как создать приложение сложения двух чисел в Visual Studio 2015 на Basic.

- [Создание проекта](#создание-проекта)
- [Интерфейс приложения](#интерфейс-приложения)
- [Написание кода основной программы](#написание-кода-основной-программы)
- [Запуск программы](#запуск-программы)

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

_Рисунок 1 — Создание нового проекта_

![Выбор типа проекта под Basic](img/new-project_02.png)

_Рисунок 2 — Выбор типа проекта под Basic_

![Созданный проект](img/new-project_03.png)

_Рисунок 3 — Созданный проект_

## Интерфейс приложения

Перетащите два `textBox` на форму, в которые будем записывать наши числа:

![Поля ввода на форме приложения](img/controls_01.png)

_Рисунок 4 — Поля ввода на форме приложения_

Перетащите кнопку на форму:

![Кнопка на форме приложения](img/controls_02.png)

_Рисунок 5 — Кнопка на форме приложения_

Перетащите третий `textBox` на форму, в которую мы будем выводить информацию. Также поменяем значение `Multiline` на `true`, чтобы можно было писать многострочные тексты:

![Изменение параметра Multiline](img/controls_03.png)

_Рисунок 6 — Изменение параметра Multiline_

Теперь мы можем его растянуть вниз:

![Растянутый контрол для вывода текста](img/controls_04.png)

_Рисунок 7 — Растянутый контрол для вывода текста_

А в первых двух `textBox` поменяем начальное значение:

![Изменение начального текста в контроле](img/controls_05.png)

_Рисунок 8 — Изменение начального текста в контроле_

![Внешний вид формы приложения](img/controls_06.png)

_Рисунок 9 — Внешний вид формы приложения_

## Написание кода основной программы

Щелкнете по кнопке двойным кликом:

![Двойной клик по кнопке](img/button_01.png)

_Рисунок 10 — Двойной клик по кнопке_

Мы получили метод, в котором прописываем реакцию на клик нашей мыши:

![Метод обработки клика кнопки](img/button_02.png)

_Рисунок 11 — Метод обработки клика кнопки_

В фигурных скобках пропишем код нашей программы по считыванию двух чисел, их сложении и выводе результата:

```bas
Dim a, b, c As Integer
Dim S1, S2 As String

' Считаем значение из TextBox1
S1 = TextBox1.Text
' Считаем значение из TextBox2
S2 = TextBox2.Text

' Переведем строки в числа
a = CInt(S1)
b = CInt(S2)

' Посчитаем сумму
c = a + b

' Выведем результат
TextBox3.Text = CStr(c)
```

![Код метода обработки клика кнопки](img/code.png)

_Рисунок 12 — Код метода обработки клика кнопки_

## Запуск программы

![Запуск приложения](img/run.png)

_Рисунок 13 — Запуск приложения_

Получаем наше приложение:

![Запущенное приложение](img/result_01.png)

_Рисунок 14 — Запущенное приложение_

При вводе наших чисел получим вот это:

![Результат выполнения приложения](img/result_02.png)

_Рисунок 15 — Результат выполнения приложения_
