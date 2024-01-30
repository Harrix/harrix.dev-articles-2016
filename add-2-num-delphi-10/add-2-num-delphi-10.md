---
date: 2016-05-28
categories: [it, programming]
tags: [Pascal, Delphi, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-delphi-10/add-2-num-delphi-10.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-delphi-10/
lang: ru
---

# Сложение двух чисел в Delphi 10 Seattle на Pascal

![Featured image](featured-image.svg)

В статье рассказывается как создать приложение сложения двух чисел в Delphi 10 Seattle.

## Создание нового приложения

Переходим в `File` → `New` → `VCL Form Application - Delphi`:

![Создание нового проекта](img/new-project_01.png)

_Рисунок 1 — Создание нового проекта_

Появится вот такой вид:

![Созданный проект](img/new-project_02.png)

_Рисунок 2 — Созданный проект_

Сохраняем всё в папке новой:

![Сохранение проекта](img/new-project_03.png)

_Рисунок 3 — Сохранение проекта_

![Сохранение файла исходного кода](img/new-project_04.png)

_Рисунок 4 — Сохранение файла исходного кода_

![Сохранения файла проекта](img/new-project_05.png)

_Рисунок 5 — Сохранения файла проекта_

## Заполняем форму

На форму кидаем два поля ввода:

![Добавление компонента TEdit](img/controls_01.png)

_Рисунок 6 — Добавление компонента TEdit_

Кнопку:

![Добавление компонента TButton](img/controls_02.png)

_Рисунок 7 — Добавление компонента TButton_

И поле для вывода многострочного текста:

![Добавление компонента TMemo](img/controls_03.png)

_Рисунок 8 — Добавление компонента TMemo_

В поле для вывода `Memo1` удалим первоначальное содержимое:

![Свойство Lines компонента TMemo](img/controls_04.png)

_Рисунок 9 — Свойство Lines компонента TMemo_

![Первоначальное содержимое компонента TMemo](img/controls_05.png)

_Рисунок 10 — Первоначальное содержимое компонента TMemo_

Также в поля ввода `Edit1` и `Edit2` введем первоначальное значение:

![Свойство Text компонента TEdit](img/controls_06.png)

_Рисунок 11 — Свойство Text компонента TEdit_

## Написание кода

Теперь можно переходить к написанию кода.

Двойной клик по кнопке:

![Двойной клик по кнопке](img/click_01.png)

_Рисунок 12 — Двойной клик по кнопке_

И видим это:

![Метод обработки клика кнопки](img/click_02.png)

_Рисунок 13 — Метод обработки клика кнопки_

Добавьте переменные:

```pascal
a,b,c : Integer;
S1, S2: UnicodeString;
```

И вводим такой код:

```pascal
S1 := Edit1.Text;
S2 := Edit2.Text;

a := S1.ToInteger;
b := S2.ToInteger;

c := a + b;

Memo1.Lines.Add(IntToStr(a) + ' + ' + IntToStr(b) + ' = ' + IntToStr(c));:

```

![Код метода обработки клика кнопки](img/click_03.png)

_Рисунок 14 — Код метода обработки клика кнопки_

Теперь сохраняем всё и запускаем приложение:

![Запуск приложения](img/run.png)

_Рисунок 15 — Запуск приложения_

При нажатию на кнопку вы получите результат:

![Результат выполнения кода программы](img/result.png)

_Рисунок 16 — Результат выполнения кода программы_
