---
date: 2016-02-15
categories:
  - it
  - programming
tags:
  - Dev C++
  - C++
  - Сложение двух чисел
  - Установка
update: 2021-09-14
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-devcpp/add-2-num-devcpp.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-devcpp/
lang: ru
attribution:
  - author: Remember the dot
    author-site: https://en.wikipedia.org/wiki/User:Remember_the_dot
    license: GNU General Public License
    license-url: https://en.wikipedia.org/wiki/GNU_General_Public_License
    permalink: https://commons.wikimedia.org/wiki/File:Dev-C%2B%2B_4.9.9.2_icon.png
    permalink-date: 2019-06-22
    name: Dev-C++ 4.9.9.2 icon.png
---

# Сложение двух чисел в Dev-C++

![Featured image](featured-image.svg)

В статье рассказывается как создать консольное приложения сложения двух чисел Win32 в Dev-C++.

<details>
<summary>📖 Содержание ⬇️</summary>

## Содержание

- [Установка программы](#установка-программы)
- [Создание проекта](#создание-проекта)
- [Создание проекта (II способ)](#создание-проекта-ii-способ)
- [Написание кода](#написание-кода)
- [Запуск программы](#запуск-программы)
- [Отличия от консольной программы Visual Studio](#отличия-от-консольной-программы-visual-studio)
- [Русская кодировка в Embarcadero Dev C++](#русская-кодировка-в-embarcadero-dev-c)

</details>

## Установка программы

Раньше программа скачивалась на сайте <https://sourceforge.net/projects/orwelldevcpp/>. Это можно сделать и сейчас, но программа не обновлялась там с 2015 года, поэтому возможности современного C++ не поддерживаются. Например, `to_string()` работать не будет.

К счастью Embarcadero (которая занимается Delphi и C++ Builder) подхватила проект и его поддерживает. Поэтому идем на сайт <https://www.embarcadero.com/ru/free-tools/dev-cpp/free-download>, где заполняем форму какими-нибудь данными:

![Скачивание установщика](img/download_01.png)

_Рисунок 1 — Скачивание установщика_

Скачается архив, в котором после распаковки окажется установщик:

![Архив и его содержимое](img/download_02.png)

_Рисунок 2 — Архив и его содержимое_

Под спойлером находится краткое описание установки программы.

<details>
<summary>Установка Dev-C++</summary>

![Выбор языка](img/install_01.png)

_Рисунок 3 — Выбор языка_

![Соглашение с условиями](img/install_02.png)

_Рисунок 4 — Соглашение с условиями_

![Выбор компонентов для установки](img/install_03.png)

_Рисунок 5 — Выбор компонентов для установки_

![Выбор пути установки программы](img/install_04.png)

_Рисунок 6 — Выбор пути установки программы_

![Процесс установки](img/install_05.png)

_Рисунок 7 — Процесс установки_

![Окончание установки](img/install_06.png)

_Рисунок 8 — Окончание установки_

Запускаем программу и настройки делаем по своему вкусу:

![Выбор языка программы](img/config_01.png)

_Рисунок 9 — Выбор языка программы_

![Настройка внешнего вида](img/config_02.png)

_Рисунок 10 — Настройка внешнего вида_

Лично я ставлю в качестве шрифта [JetBrains Mono](https://www.jetbrains.com/ru-ru/lp/mono/)

![Настройка внешнего вида](img/config_03.png)

_Рисунок 11 — Настройка внешнего вида_

![Окончание настройки программы](img/config_04.png)

_Рисунок 12 — Окончание настройки программы_

</details>

## Создание проекта

Если вы пользуетесь Dev C++ для обучения, то вам будет достаточно работать с одним файлом исходного кода.

Создайте файл исходного кода:

![Создание файла исходного кода](img/new-source_01.png)

_Рисунок 13 — Создание файла исходного кода_

![Создание файла исходного кода](img/new-source_02.png)

_Рисунок 14 — Создание файла исходного кода_

Напишите болванку приложения:

```cpp
#include <iostream>

using namespace std;

int main () {

  return 0;
}
```

![Болванка кода на C++](img/new-source_03.png)

_Рисунок 15 — Болванка кода на C++_

Сохраните где-нибудь файл:

![Сохранение файла исходного кода](img/new-source_04.png)

_Рисунок 16 — Сохранение файла исходного кода_

## Создание проекта (II способ)

Если вы хотите создавать проект полноценный с множеством файлов и так далее, то проект нужно создавать нормально. Об этом под спойлером.

<details>
<summary>Установка Dev-C++</summary>

Открываем программу `Dev-C++`:

![Внешний вид программы](img/new-project_01.png)

_Рисунок 17 — Внешний вид программы_

Создаем новый проект:

![Создание нового проекта](img/new-project_02.png)

_Рисунок 18 — Создание нового проекта_

Выбираем консольное приложение и название проекта:

![Настройка проекта](img/new-project_03.png)

_Рисунок 19 — Настройка проекта_

Выбираем место, где сохраним проект:

![Сохранение проекта](img/new-project_04.png)

_Рисунок 20 — Сохранение проекта_

Появится вот такая болванка:

![Созданный проект](img/new-project_05.png)

_Рисунок 21 — Созданный проект_

Если вам нужно закрыть проект, но не сам Dev C++, то закройте его так:

![Созданный проект](img/new-project_06.png)

_Рисунок 22 — Созданный проект_

</details>

## Написание кода

Перейдем теперь к написанию программы сложения двух чисел.

В функции `main` добавьте код:

```cpp
int a, b, c;

cout << "Input first number" << endl;
cin >> a;

cout << "Input second number" << endl;
cin >> b;

c = a + b;

cout << "Sum " << c << endl;
```

![Код программы сложения двух чисел](img/cpp.png)

_Рисунок 23 — Код программы сложения двух чисел_

Полный вид программы будет такой:

```cpp
#include <iostream>

using namespace std;

int main () {

  int a, b, c;

  cout << "Input first number" << endl;
  cin >> a;

  cout << "Input second number" << endl;
  cin >> b;

  c = a + b;

  cout << "Sum " << c << endl;

  return 0;
}
```

На всякий случай упрощенный вариант программы:

```cpp
#include <iostream>

using namespace std;

int main () {

  int a, b, c;

  cin >> a >> b;
  c = a + b;

  cout << c;

  return 0;
}
```

Сохраните файл:

![Сохранение файла исходного кода](img/new-source_04.png)

_Рисунок 24 — Сохранение файла исходного кода_

## Запуск программы

Вначале скомпилируем программу:

![Компилирование программы](img/run_01.png)

_Рисунок 25 — Компилирование программы_

Компиляция должна пройти успешно:

![Процесс компиляции прошел успешно](img/run_02.png)

_Рисунок 26 — Процесс компиляции прошел успешно_

А теперь запустим программу:

![Запуск программы](img/run_03.png)

_Рисунок 27 — Запуск программы_

![Запущенное приложение](img/run_04.png)

_Рисунок 28 — Запущенное приложение_

## Отличия от консольной программы Visual Studio

Вам в программе не надо будет писать строчки:

```cpp
#include "stdafx.h"
```

```cpp
#include <windows.h>
```

Не обязательно в конце программы писать эту строчку (если запускать программу через Dev C++):

```cpp
system("pause");
```

Название главной функции в Visual Studio выглядит так:

```cpp
int _tmain(int argc, _TCHAR* argv[])
```

Название главной функции в Dev C++ выглядит так (если создавать через проект):

```cpp
int main(int argc, char** argv)
```

Или название главной функции в Dev C++ может выглядеть так:

```cpp
int main()
```

## Русская кодировка в Embarcadero Dev C++

Embarcadero перешел на кодировку UTF-8 для работы с текстом. Что вызывает проблемы с работой русского текста в консоли.

Самый простой способ сохранять текст в ANSI кодировке, и при компиляции проекта не позволяйте перевести код в UTF-8:

![Сохранение файла](img/encode_01.png)

_Рисунок 29 — Сохранение файла_

![Отказ от перевода кодировки](img/encode_02.png)

_Рисунок 30 — Отказ от перевода кодировки_

И используйте функции `SetConsoleCP` и `SetConsoleOutputCP`:

```cpp
#include <iostream>
#include <string>
#include <Windows.h>

using namespace std;

int main() {
    setlocale(LC_ALL, "RUSSIAN");
    SetConsoleCP(1251);
    SetConsoleOutputCP(1251);

    cout << "Пример текста"<< endl;

    string input;
    cin >> input;
    cout << "Вывод: "<< input << endl;

    return 0;
}
```

Если же вы хотите использовать кодировку UTF-8 или согласились на преобразование файла в UTF-8, то тогда вам будет нужен подобный код:

```cpp
#include <iostream>
#include <string>
#include <Windows.h>

using namespace std;

int main() {
    SetConsoleOutputCP(CP_UTF8);
    SetConsoleCP(CP_UTF8); // не работает

    cout << "Пример текста"<< endl;

    return 0;
}
```

Считывание русского языка из консоли в Windows 10 я победить не смог. Английский текст считывается прекрасно, а русский отказывается.
