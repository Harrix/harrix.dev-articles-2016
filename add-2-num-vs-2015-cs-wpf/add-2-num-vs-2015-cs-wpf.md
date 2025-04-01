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
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-vs-2015-cs-wpf/add-2-num-vs-2015-cs-wpf.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-vs-2015-cs-wpf/
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

# Сложение двух чисел в Visual Studio 2015 на C# (WPF приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать приложение сложения двух чисел в Visual Studio 2015 на C# в виде WPF приложения.

<details>
<summary>📖 Содержание</summary>

## Содержание

- [Создание проекта](#создание-проекта)
- [Интерфейс приложения](#интерфейс-приложения)
- [Написание кода основной программы](#написание-кода-основной-программы)
- [Запуск программы](#запуск-программы)

</details>

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

_Рисунок 1 — Создание нового проекта_

![Выбор типа нового проекта](img/new-project_02.png)

_Рисунок 2 — Выбор типа нового проекта_

![Созданный проект](img/new-project_03.png)

_Рисунок 3 — Созданный проект_

Откройте панель инструментов:

![Панель инструментов](img/panel.png)

_Рисунок 4 — Панель инструментов_

## Интерфейс приложения

Перетащите два `textBox` на форму, в которые будем записывать наши числа:

![Поля ввода](img/controls_01.png)

_Рисунок 5 — Поля ввода_

И поменяйте значения в этих полях ввода:

![Изменения начального текста в полях ввода](img/controls_02.png)

_Рисунок 6 — Изменения начального текста в полях ввода_

![Форма с полями ввода](img/controls_03.png)

_Рисунок 7 — Форма с полями ввода_

Перетащите кнопку на форму:

![Кнопка на форме](img/controls_04.png)

_Рисунок 8 — Кнопка на форме_

Перетащите третий `textBox` на форму, в которую мы будем выводить информацию, и растяните его:

![Поле для вывода информации](img/controls_05.png)

_Рисунок 9 — Поле для вывода информации_

## Написание кода основной программы

Щелкнете по кнопке двойным кликом:

![Двойной клик по кнопке](img/button_01.png)

_Рисунок 10 — Двойной клик по кнопке_

Мы получили метод, в котором прописываем реакцию на клик нашей мыши:

![Метод обработки клика кнопки](img/button_02.png)

_Рисунок 11 — Метод обработки клика кнопки_

В фигурных скобках пропишем код нашей программы по считыванию двух чисел, их сложении и выводе результата:

```cs
int x, y, z;

// Считаем значение из первого lineEdit
string S1 = textBox.Text;
//Переведем значение в число
x = Convert.ToInt32(S1);

// Считаем значение из второго lineEdit
string S2 = textBox1.Text;
// Переведем значение в число
y = Convert.ToInt32(S2);

// Посчитаем сумму
z = x + y;

// Выведем результат
textBox2.Text = z.ToString();
```

![Код метода обработки клика кнопки](img/code.png)

_Рисунок 12 — Код метода обработки клика кнопки_

## Запуск программы

![Запуск приложения](img/run.png)

_Рисунок 13 — Запуск приложения_

Получаем наше приложение:

![Запущенное приложение](img/result_01.png)

_Рисунок 14 — Запущенное приложение_

При вводе наших чисел получим вот это:

![Результат работы программы](img/result_02.png)

_Рисунок 15 — Результат работы программы_
