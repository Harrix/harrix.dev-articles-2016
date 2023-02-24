---
date: 2016-05-29
categories: [it, programming]
tags: [Basic, Visual Studio, Сложение двух чисел]
author: Anton Sergienko
author-email: anton.b.sergienko@gmail.com
license: CC BY 4.0
license-url: https://github.com/Harrix/harrix.dev/blob/main/LICENSE.md
url-src: https://github.com/Harrix/harrix.dev-blog-2016/blob/main/add-2-num-vs-2015-basic/add-2-num-vs-2015-basic.md
url: https://harrix.dev/ru/blog/2016/add-2-num-vs-2015-basic/
---

# Сложение двух чисел в Visual Studio 2015 на Basic

В статье рассказывается как создать приложение сложения двух чисел в Visual Studio 2015 на Basic.

## Создание проекта

![Создание нового проекта](img/new-project_01.png)

![Выбор типа проекта под Basic](img/new-project_02.png)

![Созданный проект](img/new-project_03.png)

## Интерфейс приложения

Перетащите два `textBox` на форму, в которые будем записывать наши числа:

![Поля ввода на форме приложения](img/controls_01.png)

Перетащите кнопку на форму:

![Кнопка на форме приложения](img/controls_02.png)

Перетащите третий `textBox` на форму, в которую мы будем выводить информацию. Также поменяем значение `Multiline` на `true`, чтобы можно было писать многострочные тексты:

![Изменение параметра Multiline](img/controls_03.png)

Теперь мы можем его растянуть вниз:

![Растянутый контрол для вывода текста](img/controls_04.png)

А в первых двух `textBox` поменяем начальное значение:

![Изменение начального текста в контроле](img/controls_05.png)

![Внешний вид формы приложения](img/controls_06.png)

## Написание кода основной программы

Щелкнете по кнопке двойным кликом:

![Двойной клик по кнопке](img/button_01.png)

Мы получили метод, в котором прописываем реакцию на клик нашей мыши:

![Метод обработки клика кнопки](img/button_02.png)

В фигурных скобках пропишем код нашей программы по считыванию двух чисел, их сложении и выводе результата:

```bas
Dim a, b, c As Integer
Dim S1, S2 As String

' Считаем значение из TextBox1
S1 = TextBox1.Text
' Считаем значение из TextBox2
S2 = TextBox2.Text

' Переведем строки в числа
a = CInt(S1)
b = CInt(S2)

' Посчитаем сумму
c = a + b

' Выведем результат
TextBox3.Text = CStr(c)
```

![Код метода обработки клика кнопки](img/code.png)

## Запуск программы

![Запуск приложения](img/run.png)

Получаем наше приложение:

![Запущенное приложение](img/result_01.png)

При вводе наших чисел получим вот это:

![Результат выполнения приложения](img/result_02.png)
