---
date: 2016-05-28
categories: [it, programming]
tags: [C++, C++ Builder, Borland, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-c-builder-6-console/add-2-num-c-builder-6-console.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-c-builder-6-console/
lang: ru
---

# Сложение двух чисел в C++ Builder 6 на C++ (консольное приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать консольное приложение сложения двух чисел в древнем и старом C++ Builder 6.

- [Создание нового приложения](#создание-нового-приложения)
- [Написание кода](#написание-кода)

## Создание нового приложения

![Выбор создание нестандартного проекта](img/new-project_01.png)

_Рисунок 1 — Выбор создание нестандартного проекта_

![Вызов Console Wizard](img/new-project_02.png)

_Рисунок 2 — Вызов Console Wizard_

![Выбор параметров проекта](img/new-project_03.png)

_Рисунок 3 — Выбор параметров проекта_

![Подтверждение сохранения изменений предыдущего проекта](img/new-project_04.png)

_Рисунок 4 — Подтверждение сохранения изменений предыдущего проекта_

В итоге, появится вот такое окно:

![Созданный проект](img/new-project_05.png)

_Рисунок 5 — Созданный проект_

Сохраните всё:

![Сохранение файла исходного кода](img/new-project_06.png)

_Рисунок 6 — Сохранение файла исходного кода_

![Сохранения файла проекта](img/new-project_07.png)

_Рисунок 7 — Сохранения файла проекта_

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
return 0;
```

Общий код будет выглядеть так:

```cpp
//---------------------------------------------------------------------------

#pragma hdrstop

#include <iostream>

using namespace std;

//---------------------------------------------------------------------------

#pragma argsused
int main(int argc, char* argv[])
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
//---------------------------------------------------------------------------
```

Сохраните всё и запустите:

![Запуск приложения](img/run.png)

_Рисунок 8 — Запуск приложения_

![Результат выполнения программы](img/result.png)

_Рисунок 9 — Результат выполнения программы_
