---
categories: [it, programming]
tags: [C++, Visual Studio, Сложение двух чисел]
---

# Сложение двух чисел в Visual Studio 2015 на C++ (консольное CLR приложение)

В статье рассказывается как создать консольное приложения сложения двух чисел CLR в Visual Studio 2015.

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

![Выбор типа нового проекта](img/new-project_02.png)

![Созданный проект](img/new-project_03.png)

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

Получаем наше приложение:

![Запущенное приложение](img/result_01.png)

![Результат выполнения программы](img/result_02.png)
