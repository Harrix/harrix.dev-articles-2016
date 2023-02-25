---
date: 2016-06-05
categories: [it, programming]
tags: [Visual Studio, C++, Сложение двух чисел, Работа с файлами]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/add-2-num-file-vs-2015/add-2-num-file-vs-2015.md
url: https://harrix.dev/ru/blog/2016/add-2-num-file-vs-2015/
lang: ru
---

# Сложение двух чисел из файла в Visual Studio 2015 на C++ (консольное Win32 приложение)

В статье рассказывается как считать из файла два числа, сложить их, а результат записать в другой файл.

## Создание проекта

---

**Создание проекта** <!-- !details -->

![Выбор пункта меню для создания нового проекта](img/new-project_01.png)

![Выбор типа нового проекта](img/new-project_02.png)

![Первое окно мастера создания проекта](img/new-project_03.png)

![Настройка параметров нового проекта](img/new-project_04.png)

![Созданный проект](img/new-project_05.png)

---

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

## Запуск программы

Разместите в папку с исходным кодом программы файл `input.txt` со следующим содержимым:

```text
1 3
```

![Файл с входными данными](img/input.png)

Запустите приложение:

![Запуск приложения](img/run.png)

Черный экран появится и сразу исчезнет. При этом в папке с исходным кодом программы появится файл `output.txt` с содержимым:

![Файл с выходными данными](img/output.png)

```text
4
```
