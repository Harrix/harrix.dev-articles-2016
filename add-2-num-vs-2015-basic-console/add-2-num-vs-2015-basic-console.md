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
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-vs-2015-basic-console/add-2-num-vs-2015-basic-console.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-vs-2015-basic-console/
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

# Сложение двух чисел в Visual Studio 2015 на Basic (консольное приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать консольное приложения сложения двух чисел на Basic в Visual Studio 2015.

<details>
<summary>📖 Содержание</summary>

- [Создание проекта](#создание-проекта)
- [Написание кода основной программы](#написание-кода-основной-программы)
- [Запуск программы](#запуск-программы)

</details>

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

_Рисунок 1 — Создание нового проекта_

![Выбор типа нового проекта](img/new-project_02.png)

_Рисунок 2 — Выбор типа нового проекта_

![Созданный проект](img/new-project_03.png)

_Рисунок 3 — Созданный проект_

## Написание кода основной программы

Пропишем в функции `Main` такой код:

```bas
Dim a, b, c As Integer
Dim S1, S2 As String

Console.WriteLine("Введите первое число")
S1 = Console.ReadLine()

Console.WriteLine("Введите второе число")
S2 = Console.ReadLine()

' Переведем строки в числа
a = CInt(S1)
b = CInt(S2)

' Посчитаем сумму
c = a + b

Console.WriteLine("Сумма = " + CStr(c))

Console.ReadLine()
```

Полная программа будет выглядеть так:

```bas
Module Module1

    Sub Main()
        Dim a, b, c As Integer
        Dim S1, S2 As String

        Console.WriteLine("Введите первое число")
        S1 = Console.ReadLine()

        Console.WriteLine("Введите второе число")
        S2 = Console.ReadLine()

        ' Переведем строки в числа
        a = CInt(S1)
        b = CInt(S2)

        ' Посчитаем сумму
        c = a + b

        Console.WriteLine("Сумма = " + CStr(c))

        Console.ReadLine()
    End Sub

End Module
```

![Код программы](img/code.png)

_Рисунок 4 — Код программы_

## Запуск программы

![Запуск приложения](img/run.png)

_Рисунок 5 — Запуск приложения_

Получаем наше приложение:

![Запущенное приложения](img/result_01.png)

_Рисунок 6 — Запущенное приложения_

![Результат выполнения программы](img/result_02.png)

_Рисунок 7 — Результат выполнения программы_
