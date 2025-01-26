---
date: 2016-06-05
categories:
  - it
  - programming
tags:
  - Visual Studio
  - C++
  - Сложение двух чисел
  - Работа с файлами
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-file-vs-2015/add-2-num-file-vs-2015.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-file-vs-2015/
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

# Сложение двух чисел из файла в Visual Studio 2015 на C++ (консольное Win32 приложение)

![Featured image](featured-image.svg)

В статье рассказывается как считать из файла два числа, сложить их, а результат записать в другой файл.

- [Создание проекта](#создание-проекта)
- [Код основной программы](#код-основной-программы)
- [Запуск программы](#запуск-программы)

## Создание проекта

<details>
<summary>Создание проекта</summary>

![Выбор пункта меню для создания нового проекта](img/new-project_01.png)

_Рисунок 1 — Выбор пункта меню для создания нового проекта_

![Выбор типа нового проекта](img/new-project_02.png)

_Рисунок 2 — Выбор типа нового проекта_

![Первое окно мастера создания проекта](img/new-project_03.png)

_Рисунок 3 — Первое окно мастера создания проекта_

![Настройка параметров нового проекта](img/new-project_04.png)

_Рисунок 4 — Настройка параметров нового проекта_

![Созданный проект](img/new-project_05.png)

_Рисунок 5 — Созданный проект_

</details>

## Код основной программы

Пропишите данные строчки:

```cpp
#include <fstream>
using namespace std;
```

А теле главной функции добавьте этот код:

```cpp
//Создаем файловые потоки на ввод и вывод
ifstream in("input.txt");
ofstream out("output.txt");

int a, b, c;

//Считываем из файла числа
in >> a >> b;

c = a + b;

//Записываем в файл числа
out << c;
```

![Код C++ в редакторе](img/cpp.png)

_Рисунок 6 — Код C++ в редакторе_

## Запуск программы

Разместите в папку с исходным кодом программы файл `input.txt` со следующим содержимым:

```text
1 3
```

![Файл с входными данными](img/input.png)

_Рисунок 7 — Файл с входными данными_

Запустите приложение:

![Запуск приложения](img/run.png)

_Рисунок 8 — Запуск приложения_

Черный экран появится и сразу исчезнет. При этом в папке с исходным кодом программы появится файл `output.txt` с содержимым:

![Файл с выходными данными](img/output.png)

_Рисунок 9 — Файл с выходными данными_

```text
4
```
