---
date: 2016-05-29
categories: [it, programming]
tags: [Basic, Visual Studio, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/add-2-num-vs-2015-basic-console/add-2-num-vs-2015-basic-console.md
---

# Сложение двух чисел в Visual Studio 2015 на Basic (консольное приложение)

В статье рассказывается как создать консольное приложения сложения двух чисел на Basic в Visual Studio 2015.

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

![Выбор типа нового проекта](img/new-project_02.png)

![Созданный проект](img/new-project_03.png)

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

## Запуск программы

![Запуск приложения](img/run.png)

Получаем наше приложение:

![Запущенное приложения](img/result_01.png)

![Результат выполнения программы](img/result_02.png)
