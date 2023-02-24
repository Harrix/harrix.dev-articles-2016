---
date: 2016-05-28
categories: [it, programming]
tags: [C++, C++ Builder, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/add-2-num-c-builder-10-console/add-2-num-c-builder-10-console.md
url: https://harrix.dev/ru/blog/2016/add-2-num-c-builder-10-console/
---

# Сложение двух чисел в C++ Builder 10 Seattle на C++ (консольное приложение)

В статье рассказывается как создать консольное приложение сложения двух чисел в C++ Builder 10 Seattle.

## Создание нового приложения

![Создание нового проекта](img/new-project_01.png)

![Выбор типа консольного приложения](img/new-project_02.png)

![Параметры консольного приложения](img/new-project_03.png)

В итоге, появится вот такое окно:

![Созданный проект](img/new-project_04.png)

Сохраните всё:

![Сохраненный проект](img/new-project_05.png)

![Сохранение файла исходного кода проекта](img/new-project_06.png)

![Сохранение заголовочного файла проекта](img/new-project_07.png)

![Сохранение файла проекта](img/new-project_08.png)

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

![Результат выполненной программы](img/result.png)
