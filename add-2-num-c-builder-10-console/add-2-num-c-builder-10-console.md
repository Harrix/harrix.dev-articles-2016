---
date: 2016-05-28
categories:
  - it
  - programming
tags:
  - C++
  - C++ Builder
  - Сложение двух чисел
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-c-builder-10-console/add-2-num-c-builder-10-console.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-c-builder-10-console/
lang: ru
---

# Сложение двух чисел в C++ Builder 10 Seattle на C++ (консольное приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать консольное приложение сложения двух чисел в C++ Builder 10 Seattle.

## Содержание

- [Создание нового приложения](#создание-нового-приложения)
- [Написание кода](#написание-кода)

## Создание нового приложения

![Создание нового проекта](img/new-project_01.png)

_Рисунок 1 — Создание нового проекта_

![Выбор типа консольного приложения](img/new-project_02.png)

_Рисунок 2 — Выбор типа консольного приложения_

![Параметры консольного приложения](img/new-project_03.png)

_Рисунок 3 — Параметры консольного приложения_

В итоге, появится вот такое окно:

![Созданный проект](img/new-project_04.png)

_Рисунок 4 — Созданный проект_

Сохраните всё:

![Сохраненный проект](img/new-project_05.png)

_Рисунок 5 — Сохраненный проект_

![Сохранение файла исходного кода проекта](img/new-project_06.png)

_Рисунок 6 — Сохранение файла исходного кода проекта_

![Сохранение заголовочного файла проекта](img/new-project_07.png)

_Рисунок 7 — Сохранение заголовочного файла проекта_

![Сохранение файла проекта](img/new-project_08.png)

_Рисунок 8 — Сохранение файла проекта_

## Написание кода

Пропишите выше функции `main`:

```cpp
#include <iostream>

using namespace std;
```

А в самой функции `main` пропишите стандартный код:

```cpp
int a,b,c;

cout << "Input first number:"<<endl;
cin >> a;
cout << "Input second number:"<<endl;
cin >> b;

c = a + b;

cout << a << " + " << b << " = " << c << endl;

system("pause");
```

Общий код будет выглядеть так:

```cpp
#pragma hdrstop
#pragma argsused

#ifdef _WIN32
#include <tchar.h>
#else
  typedef char _TCHAR;
  #define _tmain main
#endif

#include <stdio.h>

#include <iostream>

using namespace std;

int _tmain(int argc, _TCHAR* argv[])
{
int a,b,c;

cout << "Input first number:"<<endl;
cin >> a;
cout << "Input second number:"<<endl;
cin >> b;

c = a + b;

cout << a << " + " << b << " = " << c << endl;

system("pause");
return 0;
}
```

Сохраните всё и запустите:

![Запуск приложения](img/run.png)

_Рисунок 9 — Запуск приложения_

![Результат выполненной программы](img/result.png)

_Рисунок 10 — Результат выполненной программы_
