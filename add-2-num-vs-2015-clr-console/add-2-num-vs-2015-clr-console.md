---
date: 2016-05-29
categories: [it, programming]
tags: [C++, Visual Studio, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/add-2-num-vs-2015-clr-console/add-2-num-vs-2015-clr-console.md
permalink: https://harrix.dev/ru/blog/2016/add-2-num-vs-2015-clr-console/
lang: ru
---

# Сложение двух чисел в Visual Studio 2015 на C++ (консольное CLR приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать консольное приложения сложения двух чисел CLR в Visual Studio 2015.

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

_Рисунок 1 — Создание нового проекта_

![Выбор типа нового проекта](img/new-project_02.png)

_Рисунок 2 — Выбор типа нового проекта_

![Созданный проект](img/new-project_03.png)

_Рисунок 3 — Созданный проект_

## Написание кода основной программы

Пропишем в функции `main` такой код:

```cpp
Console::WriteLine(L"Введите первое число");
String^ S1 = Console::ReadLine();
int a = int::Parse(S1);

Console::WriteLine(L"Введите второе число");
String^ S2 = Console::ReadLine();
int b = int::Parse(S2);

int c = a + b;

Console::WriteLine(a.ToString() + " + " + b.ToString() + " = " + c.ToString());

Console::ReadLine();
```

Полная программа будет выглядеть так:

```cpp
// ConsoleApplication7.cpp: главный файл проекта.

#include "stdafx.h"

using namespace System;

int main(array<System::String ^> ^args)
{
  Console::WriteLine(L"Введите первое число");
  String^ S1 = Console::ReadLine();
  int a = int::Parse(S1);

  Console::WriteLine(L"Введите второе число");
  String^ S2 = Console::ReadLine();
  int b = int::Parse(S2);

  int c = a + b;

    Console::WriteLine(a.ToString() + " + " + b.ToString() + " = " + c.ToString());

  Console::ReadLine();

    return 0;
}
```

## Запуск программы

![Запуск программы](img/run.png)

_Рисунок 4 — Запуск программы_

Получаем наше приложение:

![Запущенное приложение](img/result_01.png)

_Рисунок 5 — Запущенное приложение_

![Результат выполнения программы](img/result_02.png)

_Рисунок 6 — Результат выполнения программы_
