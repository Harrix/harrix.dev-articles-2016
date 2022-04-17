---
date: 2016-05-29
categories: [it, programming]
tags: [Pascal, Delphi, Сложение двух чисел]
---

# Сложение двух чисел в Delphi 10 Seattle на C++ (консольное приложение)

В статье рассказывается как создать консольное приложение сложения двух чисел в Delphi 10 Seattle.

## Создание нового приложения

![Создание нового проекта](img/new-project_01.png)

![Выбор консольного типа проекта](img/new-project_02.png)

В итоге, появится вот такое окно:

![Созданный проект](img/new-project_03.png)

Сохраните всё:

![Сохранение проекта](img/new-project_04.png)

![Сохранение файла проекта](img/new-project_05.png)

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

![Результат выполненной программы](img/result.png)
