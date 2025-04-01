---
date: 2016-05-29
categories:
  - it
  - programming
tags:
  - C#
  - Visual Studio
  - Сложение двух чисел
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-vs-2015-cs-console/add-2-num-vs-2015-cs-console.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-vs-2015-cs-console/
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

# Сложение двух чисел в Visual Studio 2015 на C# (консольное приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать консольное приложения сложения двух чисел на C# в Visual Studio 2015.

<details>
<summary>📖 Содержание</summary>

## Содержание

- [Создание проекта](#создание-проекта)
- [Написание кода основной программы](#написание-кода-основной-программы)
- [Запуск программы](#запуск-программы)

</details>

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

_Рисунок 1 — Создание нового проекта_

![Выбор типа проекта](img/new-project_02.png)

_Рисунок 2 — Выбор типа проекта_

![Созданный проект](img/new-project_03.png)

_Рисунок 3 — Созданный проект_

## Написание кода основной программы

Пропишем в методе `Main` основного класса такой код:

```cs
Console.WriteLine("Введите первое число");

string S1 = Console.ReadLine();
int a = int.Parse(S1);

Console.WriteLine("Введите второе число");
string S2 = Console.ReadLine();
int b = int.Parse(S2);

int c = a + b;

Console.WriteLine(a.ToString() + " + " + b.ToString() + " = " + c.ToString());

Console.ReadLine();
```

Полная программа будет выглядеть так:

```cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApplication8
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Введите первое число");

            string S1 = Console.ReadLine();
            int a = int.Parse(S1);

            Console.WriteLine("Введите второе число");
            string S2 = Console.ReadLine();
            int b = int.Parse(S2);

            int c = a + b;

            Console.WriteLine(a.ToString() + " + " + b.ToString() + " = " + c.ToString());

            Console.ReadLine();
        }
    }
}
```

![Код программы в редакторе](img/code.png)

_Рисунок 4 — Код программы в редакторе_

## Запуск программы

![Запуск программы](img/run.png)

_Рисунок 5 — Запуск программы_

Получаем наше приложение:

![Запущенное приложение](img/result_01.png)

_Рисунок 6 — Запущенное приложение_

![Результат выполнения программы](img/result_02.png)

_Рисунок 7 — Результат выполнения программы_
