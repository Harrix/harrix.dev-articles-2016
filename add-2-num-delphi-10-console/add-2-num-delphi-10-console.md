---
date: 2016-05-29
categories: [it, programming]
tags: [Pascal, Delphi, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
permalink-source: https://github.com/Harrix/harrix.dev-articles-2016/blob/main/add-2-num-delphi-10-console/add-2-num-delphi-10-console.md
permalink: https://harrix.dev/ru/articles/2016/add-2-num-delphi-10-console/
lang: ru
---

# Сложение двух чисел в Delphi 10 Seattle на C++ (консольное приложение)

![Featured image](featured-image.svg)

В статье рассказывается как создать консольное приложение сложения двух чисел в Delphi 10 Seattle.

## Создание нового приложения

![Создание нового проекта](img/new-project_01.png)

_Рисунок 1 — Создание нового проекта_

![Выбор консольного типа проекта](img/new-project_02.png)

_Рисунок 2 — Выбор консольного типа проекта_

В итоге, появится вот такое окно:

![Созданный проект](img/new-project_03.png)

_Рисунок 3 — Созданный проект_

Сохраните всё:

![Сохранение проекта](img/new-project_04.png)

_Рисунок 4 — Сохранение проекта_

![Сохранение файла проекта](img/new-project_05.png)

_Рисунок 5 — Сохранение файла проекта_

## Написание кода

Добавьте такие переменные:

```pascal
var
a,b,c:integer;
```

А тело программы замените на это:

```pascal
writeln('Input first number');
readln(a);

writeln('Input second number');
readln(b);

c := a + b;

writeln('Sum ', c);

readln(a);
```

Общий код будет выглядеть так:

```pascal
program Project1;

{$APPTYPE CONSOLE}

{$R *.res}

uses
  System.SysUtils;

  var
   a,b,c:integer;

begin
    writeln('Input first number');
    readln(a);

    writeln('Input second number');
    readln(b);

    c := a + b;

    writeln('Sum ', c);

    readln(a);
end.
```

Сохраните всё и запустите:

![Запуск приложения](img/run.png)

_Рисунок 6 — Запуск приложения_

![Результат выполненной программы](img/result.png)

_Рисунок 7 — Результат выполненной программы_
